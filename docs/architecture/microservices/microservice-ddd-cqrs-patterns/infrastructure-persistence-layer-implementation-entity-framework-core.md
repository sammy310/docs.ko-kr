---
title: Entity Framework Core를 사용하여 인프라 지속성 레이어 구현
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | Entity Framework Core를 사용하여 인프라 지속성 계층에 대한 구현 세부 정보를 탐색합니다.
ms.date: 01/30/2020
ms.openlocfilehash: 878d4d64e92ca92fd2393d60d496f1c5671e7029
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172354"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="35909-103">Entity Framework Core를 사용하여 인프라 지속성 레이어 구현</span><span class="sxs-lookup"><span data-stu-id="35909-103">Implement the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="35909-104">SQL Server, Oracle 또는 PostgreSQL 같은 관계형 데이터베이스를 사용하는 경우 EF(Entity Framework) 기반의 지속성 레이어를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-104">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="35909-105">EF는 LINQ 지원하며 데이터베이스에 간소화된 지속성을 제공할 뿐 아니라 모델에 대한 강력한 형식의 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-105">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="35909-106">Entity Framework는 .NET Framework의 일부로 오랜 역사를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-106">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="35909-107">.NET Core를 사용하는 경우 .NET Core와 마찬가지로 Windows 또는 Linux에서 실행되는 Entity Framework Core도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-107">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="35909-108">EF Core는 Entity Framework를 완전히 새로 작성한 것으로, 훨씬 적은 공간을 차지하며 성능이 대폭 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-108">EF Core is a complete rewrite of Entity Framework that's implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="35909-109">Entity Framework Core 소개</span><span class="sxs-lookup"><span data-stu-id="35909-109">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="35909-110">EF(Entity Framework) Core는 널리 사용되는 Entity Framework 데이터 액세스 기술의 가볍고 확장 가능하며 플랫폼 교차적인 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-110">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="35909-111">2016년 중순에 .NET Core에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-111">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="35909-112">EF Core를 소개하는 내용은 이미 Microsoft 설명서에 있으므로 여기서는 간단하게 해당 정보에 대한 링크만 제공하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-112">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="35909-113">추가 자료</span><span class="sxs-lookup"><span data-stu-id="35909-113">Additional resources</span></span>

- <span data-ttu-id="35909-114">**Entity Framework Core** </span><span class="sxs-lookup"><span data-stu-id="35909-114">**Entity Framework Core** </span></span>\
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- <span data-ttu-id="35909-115">**Visual Studio를 사용하여 ASP.NET Core 및 Entity Framework Core 시작** </span><span class="sxs-lookup"><span data-stu-id="35909-115">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio** </span></span>\
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- <span data-ttu-id="35909-116">**DbContext 클래스** </span><span class="sxs-lookup"><span data-stu-id="35909-116">**DbContext Class** </span></span>\
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- <span data-ttu-id="35909-117">**EF Core & EF6.x 비교** </span><span class="sxs-lookup"><span data-stu-id="35909-117">**Compare EF Core & EF6.x** </span></span>\
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="35909-118">DDD 관점에서 본 Entity Framework Core의 인프라</span><span class="sxs-lookup"><span data-stu-id="35909-118">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="35909-119">DDD 관점에서 본 EF의 중요한 기능은 POCO 도메인 엔터티를 사용하는 기능으로, EF 용어로는 POCO *코드 중심 엔터티*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-119">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="35909-120">POCO 도메인 엔터티를 사용하는 경우 도메인 모델 클래스는 [지속성 무시](https://deviq.com/persistence-ignorance/) 및 [인프라 무시](https://ayende.com/blog/3137/infrastructure-ignorance) 원칙에 따라 지속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-120">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](https://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="35909-121">DDD 패턴마다 엔터티 클래스 자체 내의 도메인 동작과 규칙을 캡슐화해야만 컬렉션에 액세스할 때 고정, 유효성 검사 및 규칙을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-121">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="35909-122">따라서 DDD에서 자식 엔터티 또는 값 개체 컬렉션에 대한 공용 액세스를 허용하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-122">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="35909-123">그 대신, 속성 컬렉션을 업데이트할 수 있는 방법 및 시기 그리고 속성 컬렉션 업데이트가 발생할 때 수행할 동작 및 작업을 제어하는 메서드를 노출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-123">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="35909-124">EF Core 1.1부터는 DDD 요구 사항을 충족하기 위해 엔터티에 공용 속성 대신 일반 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-124">Since EF Core 1.1, to satisfy those DDD requirements, you can have plain fields in your entities instead of public properties.</span></span> <span data-ttu-id="35909-125">외부에서 엔터티 필드에 액세스하지 못하게 하려면 속성 대신 특성 또는 필드를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-125">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="35909-126">개인 속성 setter를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-126">You can also use private property setters.</span></span>

<span data-ttu-id="35909-127">이와 비슷한 방법으로, 이제 `IReadOnlyCollection<T>`으로 형식화된 공용 속성을 사용하여 컬렉션에 읽기 전용으로 액세스할 수 있으며, 이 형식은 지속성 때문에 EF를 사용하는 엔터티의 컬렉션에 대한 전용 필드 멤버(예: `List<T>`)를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-127">In a similar way, you can now have read-only access to collections by using a public property typed as  `IReadOnlyCollection<T>`, which is backed by a private field member for the collection (like a `List<T>`) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="35909-128">이전 버전의 Entity Framework는 `ICollection<T>`을 지원하려면 컬렉션 속성이 필요했으며, 부모 엔터티 클래스를 사용하는 개발자가 속성 컬렉션을 통해 항목을 추가 또는 제거할 수 있었다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-128">Previous versions of Entity Framework required collection properties to support `ICollection<T>`, which meant that any developer using the parent entity class could add or remove items through its property collections.</span></span> <span data-ttu-id="35909-129">이 가능성은 DDD의 권장 패턴과 상반됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-129">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="35909-130">다음 코드 예제와 같이, 읽기 전용 `IReadOnlyCollection<T>` 개체를 노출할 때 전용 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-130">You can use a private collection while exposing a read-only `IReadOnlyCollection<T>` object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
                             decimal unitPrice, decimal discount,
                             string pictureUrl, int units = 1)
    {
        // Validation logic...

        var orderItem = new OrderItem(productId, productName,
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="35909-131">`OrderItems` 속성은 `IReadOnlyCollection<OrderItem>`을 사용하여 읽기 전용으로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-131">The `OrderItems` property can only be accessed as read-only using `IReadOnlyCollection<OrderItem>`.</span></span> <span data-ttu-id="35909-132">이 형식은 읽기 전용이므로 정기적인 업데이트로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-132">This type is read-only so it is protected against regular external updates.</span></span>

<span data-ttu-id="35909-133">EF Core는 도메인 모델을 "오염"시키지 않고 도메인 모델을 물리적 데이터베이스에 매핑할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-133">EF Core provides a way to map the domain model to the physical database without "contaminating" the domain model.</span></span> <span data-ttu-id="35909-134">매핑 작업이 지속성 레이어에서 구현되는 순수 .NET POCO 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-134">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="35909-135">이 매핑 작업에서 필드-데이터베이스 매핑을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-135">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="35909-136">`OrderingContext` 및 `OrderEntityTypeConfiguration` 클래스의 `OnModelCreating` 메서드에 대한 다음 예제에서 `SetPropertyAccessMode`에 대한 호출은 EF Core가 해당 필드를 통해 `OrderItems` 속성에 액세스하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-136">In the following example of the `OnModelCreating` method from `OrderingContext` and the `OrderEntityTypeConfiguration` class, the call to `SetPropertyAccessMode` tells EF Core to access the `OrderItems` property through its field.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation =
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

<span data-ttu-id="35909-137">속성 대신 필드를 사용하면 `OrderItem` 엔터티는 마치 `List<OrderItem>` 속성이 있는 것처럼 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-137">When you use fields instead of properties, the `OrderItem` entity is persisted as if it had a `List<OrderItem>` property.</span></span> <span data-ttu-id="35909-138">그러나 주문에 새 항목을 추가하기 위한 단일 접근자인 `AddOrderItem` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-138">However, it exposes a single accessor, the `AddOrderItem` method, for adding new items to the order.</span></span> <span data-ttu-id="35909-139">결과적으로 동작 및 데이터는 서로 연결되고 도메인 모델을 사용하는 애플리케이션 코드 전체에서 일관적으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-139">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implement-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="35909-140">Entity Framework Core를 사용하여 사용자 지정 리포지토리 구현</span><span class="sxs-lookup"><span data-stu-id="35909-140">Implement custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="35909-141">구현 수준에서 보자면, 리포지토리는 다음 클래스에서 볼 수 있듯이 업데이트를 수행할 때 작업 단위(EF Core의 DBContext)에 의해 조정되는 데이터 지속성 코드가 있는 클래스일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-141">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using directives...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;
        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity;
        }

        public async Task<Buyer> FindAsync(string buyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == buyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

<span data-ttu-id="35909-142">`IBuyerRepository` 인터페이스는 도메인 모델 레이어에서 계약으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35909-142">The `IBuyerRepository` interface comes from the domain model layer as a contract.</span></span> <span data-ttu-id="35909-143">그러나 리포지토리 구현은 지속성 및 인프라 레이어에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-143">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="35909-144">EF DbContext는 종속성 주입을 통해 생성자를 거쳐 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35909-144">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="35909-145">IoC 컨테이너(`services.AddDbContext<>`를 사용하여 명시적으로 설정할 수도 있음)의 기본 수명 주기(`ServiceLifetime.Scoped`) 덕분에 동일한 HTTP 요청 범위 내의 여러 리포지토리 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-145">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (`ServiceLifetime.Scoped`) in the IoC container (which can also be explicitly set with `services.AddDbContext<>`).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="35909-146">리포지토리에서 구현하는 메서드(업데이트 또는 트랜잭션과 쿼리 비교)</span><span class="sxs-lookup"><span data-stu-id="35909-146">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="35909-147">각 리포지토리 클래스 내에서, 관련 집계에 의해 포함되는 엔터티 상태를 업데이트하는 지속성 메서드를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-147">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="35909-148">집계와 집계 관련 리포지토리 사이에는 일대일 관계가 성립합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-148">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="35909-149">집계 루트 엔터티 개체가 EF 그래프 내에 자식 엔터티를 포함할 수 있다는 점을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-149">Consider that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="35909-150">예를 들어 구매자가 관련 자식 엔터티로 여러 지불 방법을 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-150">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="35909-151">eShopOnContainers에서 마이크로 서비스를 주문하는 방식도 CQS/CQRS 기반이므로 대부분의 쿼리가 사용자 지정 리포지토리에서 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-151">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="35909-152">개발자는 집계, 집계별 사용자 지정 리포지토리 그리고 일반적으로 DDD에서 부과하는 제한 없이 프레젠테이션 레이어에 필요한 쿼리 및 조인을 자유롭게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-152">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="35909-153">이 가이드에서 권장하는 대부분의 사용자 지정 리포지토리는 여러 업데이트 또는 트랜잭션 메서드를 갖고 있지만 데이터를 가져오는 데 필요한 쿼리 메서드만 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-153">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="35909-154">예를 들어 BuyerRepository 리포지토리는 FindAsync 메서드를 구현합니다. 애플리케이션에서 특정 구매자의 존재 여부를 알아야만 주문과 관련된 새 구매자를 만들 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-154">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="35909-155">그러나 프레젠테이션 레이어 또는 클라이언트 앱으로 보낼 데이터를 가져오는 실제 쿼리 메서드는 앞서 언급했듯이 Dapper를 사용하여 유연한 쿼리를 기반으로 CQRS 쿼리로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-155">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="35909-156">사용자 지정 리포지토리를 사용하는 방법과 EF DbContext를 직접 사용하는 방법 비교</span><span class="sxs-lookup"><span data-stu-id="35909-156">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="35909-157">Entity Framework DbContext 클래스는 작업 단위 및 리포지토리 패턴을 기반으로 하며, ASP.NET Core MVC 컨트롤러처럼 코드에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-157">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="35909-158">eShopOnContainers의 CRUD 카탈로그 마이크로 서비스에서 하듯이, 작업 단위 및 리포지토리 패턴은 가장 간단한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-158">The Unit of Work and Repository patterns result in the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="35909-159">최대한 간단한 코드를 원하는 경우 여러 개발자들이 하는 것처럼 DbContext 클래스를 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-159">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="35909-160">그러나 사용자 지정 리포지토리를 구현하면 보다 복잡한 마이크로 서비스 또는 애플리케이션을 구현할 때 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-160">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="35909-161">작업 단위 및 리포지토리 패턴은 애플리케이션 및 도메인 모델 레이어에서 분리되는 인프라 지속성 레이어를 캡슐화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-161">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain-model layers.</span></span> <span data-ttu-id="35909-162">이러한 패턴을 구현하면 모의 리포지토리를 사용하여 데이터베이스에 대한 액세스를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-162">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="35909-163">그림 7-18에서는 리포지토리를 사용하지 않을 때와(EF DbContext를 직접 사용) 리포지토리를 사용하여 좀 더 쉽게 리포지토리 모형을 만들 때의 차이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-163">In Figure 7-18, you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories, which makes it easier to mock those repositories.</span></span>

![두 리포지토리의 구성 요소 및 데이터 흐름을 보여 주는 다이어그램](./media/infrastructure-persistence-layer-implementation-entity-framework-core/custom-repo-versus-db-context.png)

<span data-ttu-id="35909-165">**그림 7-18**.</span><span class="sxs-lookup"><span data-stu-id="35909-165">**Figure 7-18**.</span></span> <span data-ttu-id="35909-166">사용자 지정 리포지토리와 일반 DbContext 비교</span><span class="sxs-lookup"><span data-stu-id="35909-166">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="35909-167">그림 7-18에서는 사용자 지정 리포지토리를 사용하여 추상화 레이어를 추가하고 리포지토리를 모의하여 손쉽게 테스트하는 데 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="35909-167">Figure 7-18 shows that using a custom repository adds an abstraction layer that can be used to ease testing by mocking the repository.</span></span> <span data-ttu-id="35909-168">모형을 만들 때 여러 가지 대안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="35909-169">리포지토리 모형만 만들 수도 있고 작업 단위 전체의 모형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="35909-170">일반적으로 리포지토리 모형만 만들면 충분하며, 복잡하게 작업 단위 전체를 추상화하고 모형을 만들 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="35909-171">뒤에서 애플리케이션 계층을 살펴볼 때, ASP.NET Core에서 종속성 주입의 작동 원리와 리포지토리를 사용할 때 구현 방식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="35909-172">요약하자면, 사용자 지정 리포지토리를 사용하면 데이터 계층 상태의 영향을 받지 않는 단위 테스트로 코드를 보다 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="35909-173">Entity Framework를 통해 실제 데이터베이스에 액세스하는 테스트를 실행하는 경우 통합 테스트가 아닌 단위 테스트이며, 속도가 훨씬 느립니다.</span><span class="sxs-lookup"><span data-stu-id="35909-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="35909-174">DbContext를 직접 사용하는 경우 단위 테스트를 위해 예측 가능한 데이터와 함께 메모리 내 SQL Server를 사용하여 모의하거나 단위 테스트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-174">If you were using DbContext directly, you would have to mock it or to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="35909-175">하지만 DbContext를 모의하거나 모조 데이터를 제어하는 것은 리포지토리 수준에서 모의하는 것보다 더 많은 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-175">But mocking the DbContext or controlling fake data requires more work than mocking at the repository level.</span></span> <span data-ttu-id="35909-176">물론, 항상 MVC 컨트롤러를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="35909-177">IoC 컨테이너의 EF DbContext 및 IUnitOfWork 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="35909-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="35909-178">`DbContext` 개체(`IUnitOfWork` 개체로 노출)는 동일한 HTTP 요청 범위 내에 있는 여러 리포지토리 간에 공유되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-178">The `DbContext` object (exposed as an `IUnitOfWork` object) should be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="35909-179">실행 중인 작업에서 여러 집계를 처리해야 하거나 여러 리포지토리 인스턴스를 사용하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="35909-180">`IUnitOfWork` 인터페이스는 EF Core 형식이 아닌 도메인 레이어의 일부라는 점도 언급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-180">It is also important to mention that the `IUnitOfWork` interface is part of your domain layer, not an EF Core type.</span></span>

<span data-ttu-id="35909-181">그러려면 `DbContext` 개체 인스턴스의 서비스 수명이 ServiceLifetime.Scoped로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-181">In order to do that, the instance of the `DbContext` object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="35909-182">이는 ASP.NET Core Web API 프로젝트의 `Startup.cs` 파일에 대한 ConfigureServices 메서드에서 IoC 컨테이너의 `services.AddDbContext`가 있는 `DbContext`를 등록할 때의 기본 수명입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-182">This is the default lifetime when registering a `DbContext` with `services.AddDbContext` in your IoC container from the ConfigureServices method of the `Startup.cs` file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="35909-183">다음 코드에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35909-183">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
      .AddDbContext<OrderingContext>(options =>
      {
          options.UseSqlServer(Configuration["ConnectionString"],
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

<span data-ttu-id="35909-184">DbContext 인스턴스화 모드를 ServiceLifetime.Transient 또는 ServiceLifetime.Singleton로 구성하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="35909-185">IoC 컨테이너의 리포지토리 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="35909-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="35909-186">마찬가지로 리포지토리 수명은 일반적으로 그 범위를 지정해야 합니다(Autofac의 InstancePerLifetimeScope).</span><span class="sxs-lookup"><span data-stu-id="35909-186">In a similar way, repository's lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="35909-187">임시로 지정할 수도 있지만(Autofac의 InstancePerDependency) 수명 범위를 지정하면 메모리와 관련한 서비스 효율이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="35909-188">리포지토리에 singleton 수명을 사용하면 DbContext를 범위가 지정된(InstancePerLifetimeScope) 수명으로 설정(DBContext의 기본 수명)할 경우 심각한 동시성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-188">Using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="35909-189">추가 자료</span><span class="sxs-lookup"><span data-stu-id="35909-189">Additional resources</span></span>

- <span data-ttu-id="35909-190">**ASP.NET MVC 애플리케이션에서 작업 패턴의 리포지토리 및 단위 구현** </span><span class="sxs-lookup"><span data-stu-id="35909-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application** </span></span>\
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- <span data-ttu-id="35909-191">**Jonathan Allen. Entity Framework, Dapper 및 Chain을 사용하여 리포지토리 패턴에 대한 전략 구현** </span><span class="sxs-lookup"><span data-stu-id="35909-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain** </span></span>\
  <https://www.infoq.com/articles/repository-implementation-strategies>

- <span data-ttu-id="35909-192">**Cesar de la Torre. ASP.NET Core IoC 컨테이너 서비스 수명과 Autofac IoC 컨테이너 인스턴스 범위 비교** </span><span class="sxs-lookup"><span data-stu-id="35909-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a><span data-ttu-id="35909-193">테이블 매핑</span><span class="sxs-lookup"><span data-stu-id="35909-193">Table mapping</span></span>

<span data-ttu-id="35909-194">테이블 매핑은 데이터베이스에서 쿼리하고 저장할 테이블 데이터를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="35909-195">앞에서 도메인 엔터티(예: 제품 또는 주문 도메인)를 사용하여 관련 데이터베이스 스키마를 생성하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="35909-196">EF는 *규칙* 개념을 중심으로 강력하게 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="35909-197">규칙은 “테이블의 이름은 무엇인가요?”</span><span class="sxs-lookup"><span data-stu-id="35909-197">Conventions address questions like "What will the name of a table be?"</span></span> <span data-ttu-id="35909-198">또는 “기본 키는 무슨 속성인가요?”와 같은 질문을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-198">or "What property is the primary key?"</span></span> <span data-ttu-id="35909-199">규칙은 일반적으로 관습적 이름을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-199">Conventions are typically based on conventional names.</span></span> <span data-ttu-id="35909-200">예를 들어 일반적으로 기본 키는 `Id`로 끝나는 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-200">For example, it is typical for the primary key to be a property that ends with `Id`.</span></span>

<span data-ttu-id="35909-201">규칙에 따라 각 엔터티는 파생 컨텍스트에 엔터티를 노출하는 `DbSet<TEntity>` 속성과 이름이 같은 테이블에 매핑되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-201">By convention, each entity will be set up to map to a table with the same name as the `DbSet<TEntity>` property that exposes the entity on the derived context.</span></span> <span data-ttu-id="35909-202">지정된 엔터티에 `DbSet<TEntity>` 값이 제공되지 않으면 클래스 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-202">If no `DbSet<TEntity>` value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="35909-203">데이터 주석과 흐름 API 비교</span><span class="sxs-lookup"><span data-stu-id="35909-203">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="35909-204">여러 가지 추가 EF Core 규칙이 있으며, 그 중 대부분은 데이터 주석 또는 흐름 API를 사용하여 변경하고, OnModelCreating 메서드 내에서 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-204">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="35909-205">데이터 주석은 엔터티 모델 클래스 자체에 사용해야 하며, DDD 관점에서 개입 수준이 높은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-205">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="35909-206">인프라 데이터베이스와 관련된 데이터 주석으로 모델을 오염시키기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-206">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="35909-207">반면 흐름 API는 데이터 지속성 인프라 계층 내부의 규칙과 매핑을 대부분 변경할 수 있는 편리한 방법으로, 엔터티 모델이 깔끔하고 지속성 인프라와 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-207">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="35909-208">흐름 API 및 OnModelCreating 메서드</span><span class="sxs-lookup"><span data-stu-id="35909-208">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="35909-209">앞서 언급했듯이, 규칙 및 매핑을 변경하려면 DbContext 클래스의 OnModelCreating 메서드를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-209">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span>

<span data-ttu-id="35909-210">eShopOnContainers의 주문 마이크로 서비스는 다음 코드에 보이는 것처럼 필요에 따라 명시적 매핑 및 구성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-210">The ordering microservice in eShopOnContainers implements explicit mapping and configuration, when needed, as shown in the following code.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

        orderConfiguration.HasKey(o => o.Id);

        orderConfiguration.Ignore(b => b.DomainEvents);

        orderConfiguration.Property(o => o.Id)
            .UseHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

        //Address value object persisted as owned entity type supported since EF Core 2.0
        orderConfiguration
            .OwnsOne(o => o.Address, a =>
            {
                a.WithOwner();
            });

        orderConfiguration
            .Property<int?>("_buyerId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("BuyerId")
            .IsRequired(false);

        orderConfiguration
            .Property<DateTime>("_orderDate")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderDate")
            .IsRequired();

        orderConfiguration
            .Property<int>("_orderStatusId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderStatusId")
            .IsRequired();

        orderConfiguration
            .Property<int?>("_paymentMethodId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("PaymentMethodId")
            .IsRequired(false);

        orderConfiguration.Property<string>("Description").IsRequired(false);

        var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        // DDD Patterns comment:
        //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        orderConfiguration.HasOne<PaymentMethod>()
            .WithMany()
            .HasForeignKey("_paymentMethodId")
            .IsRequired(false)
            .OnDelete(DeleteBehavior.Restrict);

        orderConfiguration.HasOne<Buyer>()
            .WithMany()
            .IsRequired(false)
            .HasForeignKey("_buyerId");

        orderConfiguration.HasOne(o => o.OrderStatus)
            .WithMany()
            .HasForeignKey("_orderStatusId");
    }
}
```

<span data-ttu-id="35909-211">동일한 `OnModelCreating` 메서드 내에서 모든 흐름 API 매핑을 설정할 수 있지만, 예제에 보이는 것처럼 해당 코드를 분할하여 여러 구성 클래스를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-211">You could set all the Fluent API mappings within the same `OnModelCreating` method, but it's advisable to partition that code and have multiple configuration classes, one per entity, as shown in the example.</span></span> <span data-ttu-id="35909-212">특히 대형 모델의 경우 여러 엔터티 형식을 구성하기 위한 별도의 클래스를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-212">Especially for large models, it is advisable to have separate configuration classes for configuring different entity types.</span></span>

<span data-ttu-id="35909-213">예제의 코드는 몇 가지 명시적 선언 및 매핑을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="35909-213">The code in the example shows a few explicit declarations and mapping.</span></span> <span data-ttu-id="35909-214">그러나 EF Core 규칙에서 이러한 매핑의 상당수를 자동으로 처리하므로 필요한 실제 코드 크기는 더 작아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-214">However, EF Core conventions do many of those mappings automatically, so the actual code you would need in your case might be smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="35909-215">EF Core의 Hi/Lo 알고리즘</span><span class="sxs-lookup"><span data-stu-id="35909-215">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="35909-216">앞의 예제에서 본 코드의 흥미로운 점은 키 생성 전략으로 [Hi/Lo 알고리즘](https://vladmihalcea.com/the-hilo-algorithm/)을 사용한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-216">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="35909-217">Hi/Lo 알고리즘은 변경 내용을 커밋하기 전에 고유 키가 필요한 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-217">The Hi/Lo algorithm is useful when you need unique keys before committing changes.</span></span> <span data-ttu-id="35909-218">요약하자면, Hi-Lo 알고리즘은 테이블 행에 고유 식별자를 할당하지만 행을 데이터베이스에 즉시 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-218">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="35909-219">따라서 일반 순차적 데이터베이스 ID와 마찬가지로 식별자를 사용하여 바로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-219">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="35909-220">Hi/Lo 알고리즘은 관련 데이터베이스 시퀀스에서 고유 ID의 일괄 처리를 가져오기 위한 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-220">The Hi/Lo algorithm describes a mechanism for getting a batch of unique IDs from a related database sequence.</span></span> <span data-ttu-id="35909-221">이러한 ID는 데이터베이스가 고유성을 보장하기 때문에 사용자 간에 충돌이 일어나지 않으므로 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-221">These IDs are safe to use because the database guarantees the uniqueness, so there will be no collisions between users.</span></span> <span data-ttu-id="35909-222">이 알고리즘이 흥미로운 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-222">This algorithm is interesting for these reasons:</span></span>

- <span data-ttu-id="35909-223">작업 단위 패턴을 중단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-223">It does not break the Unit of Work pattern.</span></span>

- <span data-ttu-id="35909-224">데이터베이스에 대한 왕복을 최소화하기 위해 일괄 처리로 시퀀스 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35909-224">It gets sequence IDs in batches, to minimize round trips to the database.</span></span>

- <span data-ttu-id="35909-225">GUID를 사용하는 기술은 달리, 사람이 읽을 수 있는 식별자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-225">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="35909-226">EF Core는 위 예제와 같이 `UseHiLo` 메서드를 사용하여 [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-226">EF Core supports [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the `UseHiLo` method, as shown in the preceding example.</span></span>

### <a name="map-fields-instead-of-properties"></a><span data-ttu-id="35909-227">속성 대신 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="35909-227">Map fields instead of properties</span></span>

<span data-ttu-id="35909-228">EF Core 1.1부터 제공되는 이 기능을 사용하면 열을 필드로 직접 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-228">With this feature, available since EF Core 1.1, you can directly map columns to fields.</span></span> <span data-ttu-id="35909-229">엔터티 클래스에서 속성을 사용하지 않고 테이블에서 필드로 열을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-229">It is possible to not use properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="35909-230">엔터티 외부에서 액세스할 필요가 없는 내부 상태에 대한 전용 필드가 대표적인 사용 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-230">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="35909-231">단일 필드를 사용하여 또는 `List<>` 필드 같은 컬렉션을 사용하여 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-231">You can do this with single fields or also with collections, like a `List<>` field.</span></span> <span data-ttu-id="35909-232">이 부분은 도메인 모델 클래스 모델링에 대해 토론할 때 살펴보았지만, 여기서는 이전 코드에서 강조 표시된 `PropertyAccessMode.Field` 구성을 통해 매핑이 수행되는 방식을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-232">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the `PropertyAccessMode.Field` configuration highlighted in the previous code.</span></span>

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a><span data-ttu-id="35909-233">인프라 수준에서 숨겨진 EF Core의 섀도 속성 사용</span><span class="sxs-lookup"><span data-stu-id="35909-233">Use shadow properties in EF Core, hidden at the infrastructure level</span></span>

<span data-ttu-id="35909-234">EF Core의 섀도 속성은 엔터티 클래스 모델에 존재하지 않는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-234">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="35909-235">이러한 속성의 값과 상태는 인프라 수준에서 [ChangeTracker](/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) 클래스에 순수하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-235">The values and states of these properties are maintained purely in the [ChangeTracker](/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

## <a name="implement-the-query-specification-pattern"></a><span data-ttu-id="35909-236">쿼리 사양 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="35909-236">Implement the Query Specification pattern</span></span>

<span data-ttu-id="35909-237">디자인 섹션에 앞서 언급했듯이, 쿼리 사양 패턴은 선택적 정렬과 페이징 논리를 사용해 쿼리를 정의 내릴 수 있는 공간으로 디자인된 도메인 기반 디자인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-237">As introduced earlier in the design section, the Query Specification pattern is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span>

<span data-ttu-id="35909-238">쿼리 사양 패턴은 개체에서 쿼리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-238">The Query Specification pattern defines a query in an object.</span></span> <span data-ttu-id="35909-239">예를 들어 일부 제품을 검색하는 페이징된 쿼리를 캡슐화하려면 필요한 입력 매개 변수(pageNumber, pageSize, 필터 등)를 사용하는 PagedProduct 사양을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-239">For example, in order to encapsulate a paged query that searches for some products you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="35909-240">그런 다음, 모든 리포지토리 메서드(일반적으로 목록() 오버로드) 내에서 IQuerySpecification을 수용하고 해당 사양을 기반으로 필요한 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-240">Then, within any Repository method (usually a List() overload) it would accept an IQuerySpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="35909-241">제네릭 사양 인터페이스의 예제는 [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb)의 다음 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="35909-241">An example of a generic Specification interface is the following code from [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).</span></span>

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

<span data-ttu-id="35909-242">그런 다음, 제네릭 사양 기본 클래스의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-242">Then, the implementation of a generic specification base class is the following.</span></span>

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb

public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } =
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();

    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }

    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

<span data-ttu-id="35909-243">다음 사양은 장바구니의 ID 또는 장바구니가 속한 구매자의 ID가 지정된 단일 장바구니 엔터티를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-243">The following specification loads a single basket entity given either the basket's ID or the ID of the buyer to whom the basket belongs.</span></span> <span data-ttu-id="35909-244">장바구니의 `Items` 컬렉션을 [즉시 로드](/ef/core/querying/related-data)합니다.</span><span class="sxs-lookup"><span data-stu-id="35909-244">It will [eagerly load](/ef/core/querying/related-data) the basket's `Items` collection.</span></span>

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }

    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

<span data-ttu-id="35909-245">마지막으로, 아래를 보시면 제네릭 EF 리포지토리가 사양을 사용하여 특정 엔터티 형식 T와 관련된 데이터를 필터링하고 즉시 로드하는 원리를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-245">And finally, you can see below how a generic EF Repository can use such a specification to filter and eager-load data related to a given entity type T.</span></span>

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));

    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));

    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```

<span data-ttu-id="35909-246">사양은 필터링 논리를 캡슐화할 뿐 아니라 채울 속성을 포함하여 반환될 데이터의 모양을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-246">In addition to encapsulating filtering logic, the specification can specify the shape of the data to be returned, including which properties to populate.</span></span>

<span data-ttu-id="35909-247">리포지토리에서 `IQueryable`을 반환하는 것을 권장하지는 않지만, 리포지토리 내에서 사용하여 결과 세트를 빌드하는 데 사용하는 것은 아무 문제 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35909-247">Although we don't recommend returning `IQueryable` from a repository, it's perfectly fine to use them within the repository to build up a set of results.</span></span> <span data-ttu-id="35909-248">위의 List 메서드에 이 접근 방식이 사용된 것을 볼 수 있습니다. 중간 `IQueryable` 식을 사용하여 쿼리의 포함 목록을 빌드한 후 마지막 줄에서 사양의 기준을 사용하여 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="35909-248">You can see this approach used in the List method above, which uses intermediate `IQueryable` expressions to build up the query's list of includes before executing the query with the specification's criteria on the last line.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="35909-249">추가 자료</span><span class="sxs-lookup"><span data-stu-id="35909-249">Additional resources</span></span>

- <span data-ttu-id="35909-250">**테이블 매핑** </span><span class="sxs-lookup"><span data-stu-id="35909-250">**Table Mapping** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- <span data-ttu-id="35909-251">**Entity Framework Core를 사용하여 키를 생성하도록 HiLo 사용** </span><span class="sxs-lookup"><span data-stu-id="35909-251">**Use HiLo to generate keys with Entity Framework Core** </span></span>\
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- <span data-ttu-id="35909-252">**지원 필드** </span><span class="sxs-lookup"><span data-stu-id="35909-252">**Backing Fields** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- <span data-ttu-id="35909-253">**Steve Smith. Entity Framework Core에서 캡슐화된 컬렉션** </span><span class="sxs-lookup"><span data-stu-id="35909-253">**Steve Smith. Encapsulated Collections in Entity Framework Core** </span></span>\
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- <span data-ttu-id="35909-254">**섀도 속성** </span><span class="sxs-lookup"><span data-stu-id="35909-254">**Shadow Properties** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- <span data-ttu-id="35909-255">**사양 패턴** </span><span class="sxs-lookup"><span data-stu-id="35909-255">**The Specification pattern** </span></span>\
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> <span data-ttu-id="35909-256">[이전](infrastructure-persistence-layer-design.md)
> [다음](nosql-database-persistence-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="35909-256">[Previous](infrastructure-persistence-layer-design.md)
[Next](nosql-database-persistence-infrastructure.md)</span></span>
