---
title: 복원력 있는 Entity Framework Core SQL 연결 구현
description: 복원력 있는 Entity Framework Core SQL 연결을 구현하는 방법을 알아봅니다. 이 기술은 클라우드에서 Azure SQL Database를 사용하는 경우에 특히 중요합니다.
ms.date: 10/16/2018
ms.openlocfilehash: 7a047edca21d63a451e90f407b23f3358d461330
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78241067"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="015de-104">복원력 있는 Entity Framework Core SQL 연결 구현</span><span class="sxs-lookup"><span data-stu-id="015de-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="015de-105">Azure SQL DB의 경우, EF(Entity Framework) Core에서 이미 내부 데이터베이스 연결 복원력과 다시 시도 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="015de-106">그러나 [복원력 있는 EF Core 연결](/ef/core/miscellaneous/connection-resiliency)을 원할 경우 각 <xref:Microsoft.EntityFrameworkCore.DbContext> 연결에 대한 Entity Framework 실행 전략을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="015de-107">예를 들어, EF 코어 연결 수준의 다음 코드는 연결이 실패할 경우 다시 시도되는 복원력 있는 SQL 연결을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="015de-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="015de-108">BeginTransaction 및 여러 DbContexts를 사용한 실행 전략 및 명시적 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="015de-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="015de-109">EF Core 연결에서 다시 시도를 사용하도록 설정되면 EF Core를 사용하여 수행하는 각 작업이 자체적으로 다시 시도할 수 있는 작업이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="015de-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="015de-110">일시적인 오류가 발생할 경우 `SaveChanges`에 대한 각 쿼리와 각 호출이 하나의 단위로 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="015de-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="015de-111">그러나 코드에서 `BeginTransaction`을 사용하여 트랜잭션을 시작하는 경우 하나의 단위로 처리해야 하는 고유한 작업 그룹이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="015de-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="015de-112">오류가 발생할 경우 트랜잭션 내부의 모든 항목을 롤백해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="015de-113">EF 실행 전략(재시도 정책)을 사용할 때 해당 트랜잭션을 실행하려고 시도하고 다중 DbContext에서 `SaveChanges`를 호출하는 경우 다음과 같은 예외가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="015de-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="015de-114">System.InvalidOperationException: 구성된 실행 전략 ‘SqlServerRetryingExecutionStrategy’는 사용자가 시작한 트랜잭션을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="015de-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="015de-115">'DbContext.Database.CreateExecutionStrategy()'에서 반환된 실행 전략을 사용하여 트랜잭션을 다시 시도가 가능한 단위로 트랜잭션의 모든 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="015de-116">해결책은 실행해야 하는 모든 것을 나타내는 대리자를 사용하여 EF 실행 전략을 수동으로 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="015de-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="015de-117">일시적인 오류가 발생하면, 실행 전략에서 대리자를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="015de-118">예를 들어 다음 코드는 제품을 업데이트한 이후 다른 DbContext를 사용해야 하는 ProductPriceChangedIntegrationEvent 개체를 저장할 때, 두 개의 다중 DbContext(\_catalogContext 및 IntegrationEventLogContext)를 사용하여 eShopOnContainers에서 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="015de-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

<span data-ttu-id="015de-119">첫 번째 <xref:Microsoft.EntityFrameworkCore.DbContext>는 `_catalogContext`이고, 두 번째 `DbContext`는 `_catalogIntegrationEventService` 개체 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="015de-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_catalogIntegrationEventService` object.</span></span> <span data-ttu-id="015de-120">커밋 작업은 EF 실행 전략을 사용하여 모든 `DbContext` 개체에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="015de-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="015de-121">이 다중 `DbContext` 커밋을 달성하기 위해 `SaveEventAndCatalogContextChangesAsync`는 다음 코드와 같이 `ResilientTransaction` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

<span data-ttu-id="015de-122">`ResilientTransaction.ExecuteAsync` 메서드는 기본적으로 전달된 `DbContext`(`_catalogContext`)에서 트랜잭션을 시작하고 `EventLogService`에서 해당 트랜잭션을 사용하여 `IntegrationEventLogContext`의 변경 내용을 저장하도록 한 다음, 전체 트랜잭션을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="015de-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="015de-123">추가 자료</span><span class="sxs-lookup"><span data-stu-id="015de-123">Additional resources</span></span>

- <span data-ttu-id="015de-124">**ASP.NET MVC 애플리케이션에서 EF를 사용한 연결 복원력 및 명령 인터셉션** </span><span class="sxs-lookup"><span data-stu-id="015de-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** </span></span>\
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="015de-125">**Cesar de la Torre. 복원력 있는 Entity Framework Core SQL 연결 및 트랜잭션 사용** </span><span class="sxs-lookup"><span data-stu-id="015de-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="015de-126">[이전](implement-retries-exponential-backoff.md)
>[다음](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="015de-126">[Previous](implement-retries-exponential-backoff.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>
