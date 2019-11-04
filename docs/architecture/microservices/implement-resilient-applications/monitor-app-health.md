---
title: 상태 모니터링
description: 상태 모니터링을 구현하는 한 가지 방법을 살펴봅니다.
ms.date: 01/07/2019
ms.openlocfilehash: 2d43efa7b6cfb855a033ee4d766c64c2472ceb36
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094075"
---
# <a name="health-monitoring"></a><span data-ttu-id="b59d9-103">상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="b59d9-103">Health monitoring</span></span>

<span data-ttu-id="b59d9-104">상태 모니터링은 컨테이너 및 마이크로 서비스의 상태에 대해 거의 실시간으로 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="b59d9-105">상태 모니터링은 마이크로 서비스를 작동하는 데 있어 여러 가지 측면에서 매우 중요하며, 나중에 설명하는 대로 오케스트레이터에서 애플리케이션을 부분적으로 업그레이드할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="b59d9-106">마이크로 서비스 기반 애플리케이션은 종종 하트비트 또는 상태 검사를 사용하여 성능 모니터, 스케줄러 및 오케스트레이터에서 다양한 서비스를 추적할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="b59d9-107">서비스에서 요청 시 또는 일정에 따라 “활성(I’m alive)” 신호를 보낼 수 없는 경우, 업데이트를 배포할 때 애플리케이션이 위험에 직면할 수 있고, 단순히 오류를 너무 늦게 검색해서 연속 오류를 방지하지 못해 심각한 중단 상태에 놓일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might just detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="b59d9-108">일반적인 모델에서 서비스는 상태에 대한 보고서를 보내고, 해당 정보를 집계하여 애플리케이션 상태 전체에 대한 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="b59d9-109">오케스트레이터를 사용하는 경우 클러스터가 적절하게 작동할 수 있도록 오케스트레이터의 클러스터에 상태 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-109">If you're using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="b59d9-110">애플리케이션에 맞게 사용자 지정된 고품질 상태 보고에 투자하는 경우 실행 중인 애플리케이션에 대한 문제를 훨씬 쉽게 검색하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-110">If you invest in high-quality health reporting that's customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implement-health-checks-in-aspnet-core-services"></a><span data-ttu-id="b59d9-111">ASP.NET Core 서비스에서 상태 검사 구현</span><span class="sxs-lookup"><span data-stu-id="b59d9-111">Implement health checks in ASP.NET Core services</span></span>

<span data-ttu-id="b59d9-112">ASP.NET Core 마이크로 서비스나 웹 애플리케이션을 개발하는 경우 ASP .NET Core 2.2에 릴리스된 기본 제공 상태 검사 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-112">When developing an ASP.NET Core microservice or web application, you can use the built-in health checks feature that was released in ASP .NET Core 2.2.</span></span> <span data-ttu-id="b59d9-113">다수의 ASP.NET Core 기능과 마찬가지로 상태 검사에는 일련의 서비스와 미들웨어가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-113">Like many ASP.NET Core features, health checks come with a set of services and a middleware.</span></span>

<span data-ttu-id="b59d9-114">상태 검사 서비스와 미들웨어는 사용하기 쉽고 SQL Server 데이터베이스 또는 원격 API와 같은 애플리케이션에 필요한 외부 리소스가 제대로 작동하는지 확인하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-114">Health check services and middleware are easy to use and provide capabilities that let you validate if any external resource needed for your application (like a SQL Server database or a remote API) is working properly.</span></span> <span data-ttu-id="b59d9-115">이 기능을 사용하면 리소스가 정상이라는 의미를 결정할 수 있으며, 이 내용은 나중에 설명하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-115">When you use this feature, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="b59d9-116">이 기능을 효과적으로 사용하려면 먼저 마이크로 서비스에서 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-116">To use this feature effectively, you need to first configure services in your microservices.</span></span> <span data-ttu-id="b59d9-117">다음으로, 상태 보고서를 쿼리하는 프런트 엔드 애플리케이션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-117">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="b59d9-118">프런트 엔드 애플리케이션은 사용자 지정 보고 애플리케이션이거나 성능 상태에 따라 대응할 수 있는 오케스트레이터 자체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-118">That front-end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="b59d9-119">백 엔드 ASP.NET 마이크로 서비스에서 HealthChecks 기능 사용</span><span class="sxs-lookup"><span data-stu-id="b59d9-119">Use the HealthChecks feature in your back-end ASP.NET microservices</span></span>

<span data-ttu-id="b59d9-120">이 섹션에서는 샘플 ASP.NET Core 2.2 Web API 애플리케이션에서 HealthChecks 기능을 사용하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-120">In this section, you will learn how the HealthChecks feature is used in a sample ASP.NET Core 2.2 Web API application.</span></span> <span data-ttu-id="b59d9-121">eShopOnContainers와 같은 대규모 마이크로 서비스에 이러한 기능을 구현하는 방법은 뒷부분 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-121">Implementation of this feature in a large scale microservices like the eShopOnContainers is explained in the later section.</span></span> <span data-ttu-id="b59d9-122">시작하려면 각 마이크로 서비스에 대한 성능 상태를 구성하는 항목을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="b59d9-123">샘플 애플리케이션에서 마이크로 서비스 API가 HTTP를 통해 액세스할 수 있고 관련 SQL Server 데이터베이스도 사용할 수 있으면 마이크로 서비스가 정상입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and its related SQL Server database is also available.</span></span>

<span data-ttu-id="b59d9-124">기본 제공 API가 있는 .NET Core 2.2에서는 다음과 같은 방법으로 서비스를 구성하고 마이크로 서비스 및 종속 SQL Server 데이터베이스에 대한 상태 검사를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-124">In .NET Core 2.2, with the built-in APIs, you can configure the services, add a Health Check for the microservice and its dependent SQL Server database in this way:</span></span>

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
    // Add a health check for a SQL database
    .AddCheck("MyDatabase", new SqlConnectionHealthCheck(Configuration["ConnectionStrings:DefaultConnection"]));
}
```

<span data-ttu-id="b59d9-125">이전 코드에서 `services.AddHealthChecks()` 메서드는 "정상"상태 코드 **200**을 반환하는 기본 HTTP 검사를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-125">In the previous code, the `services.AddHealthChecks()` method configures a basic HTTP check that returns a status code **200** with “Healthy”.</span></span>  <span data-ttu-id="b59d9-126">또한 `AddCheck()` 확장 메서드는 관련 SQL Database의 상태를 검사하는 사용자 지정 `SqlConnectionHealthCheck`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-126">Further, the `AddCheck()` extension method configures a custom `SqlConnectionHealthCheck` that checks the related SQL Database’s health.</span></span>

<span data-ttu-id="b59d9-127">`AddCheck()` 메서드는 지정된 이름의 새 상태 검사와 `IHealthCheck` 형식의 구현을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-127">The `AddCheck()` method adds a new health check with a specified name and the implementation of type `IHealthCheck`.</span></span> <span data-ttu-id="b59d9-128">AddCheck 메서드를 사용하여 여러 상태 검사를 추가할 수 있기 때문에 모든 검사가 정상 상태가 될 때까지 마이크로 서비스는 "정상" 상태를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-128">You can add multiple Health Checks using AddCheck method, so a microservice won't provide a “healthy” status until all its checks are healthy.</span></span>

<span data-ttu-id="b59d9-129">`SqlConnectionHealthCheck`는 `IHealthCheck`를 구현하는 사용자 지정 클래스입니다. 이것은 연결 문자열을 생성자 매개 변수로 사용하고 간단한 쿼리를 실행하여 SQL 데이터베이스에 대한 연결이 성공했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-129">`SqlConnectionHealthCheck` is a custom class that implements `IHealthCheck`, which takes a connection string as a constructor parameter and executes a simple query to check if the connection to the SQL database is successful.</span></span> <span data-ttu-id="b59d9-130">쿼리가 성공적으로 실행될 경우 `HealthCheckResult.Healthy()`를 반환하고 실패할 경우 실제 예외와 함께 `FailureStatus`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-130">It returns `HealthCheckResult.Healthy()` if the query was executed successfully and a `FailureStatus` with the actual exception when it fails.</span></span>

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

<span data-ttu-id="b59d9-131">이전 코드에서 `Select 1`은 데이터베이스의 상태를 확인하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-131">Note that in the previous code, `Select 1` is the query used to check the Health of the database.</span></span> <span data-ttu-id="b59d9-132">Kubernetes 및 Service Fabric과 같은 오케스트레이션은 마이크로 서비스의 가용성을 모니터링하기 위해 정기적으로 마이크로 서비스 테스트 요청을 보내 상태 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-132">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="b59d9-133">이러한 작업이 신속하고 리소스 사용률이 높아지지 않도록 데이터베이스 쿼리를 효율적으로 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-133">It's important to keep your database queries efficient so that these operations are quick and don’t result in a higher utilization of resources.</span></span>

<span data-ttu-id="b59d9-134">마지막으로 url 경로, "/hc"에 응답하는 미들웨어를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-134">Finally, create a middleware that responds to the url path “/hc”:</span></span>

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecks("/hc");
    //…
}
```

<span data-ttu-id="b59d9-135">`<yourmicroservice>/hc` 엔드포인트가 호출되면 Startup 클래스의 `AddHealthChecks()` 메서드에 구성된 상태 검사를 모두 실행하고 그 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-135">When the endpoint `<yourmicroservice>/hc` is invoked, it runs all the health checks that are configured in the `AddHealthChecks()` method in the Startup class and shows the result.</span></span>

### <a name="healthchecks-implementation-in-eshoponcontainers"></a><span data-ttu-id="b59d9-136">eShopOnContainers의 HealthChecks 구현</span><span class="sxs-lookup"><span data-stu-id="b59d9-136">HealthChecks implementation in eShopOnContainers</span></span>

<span data-ttu-id="b59d9-137">eShopOnContainers의 마이크로 서비스는 여러 가지 서비스에 의존하여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-137">Microservices in eShopOnContainers rely on multiple services to perform its task.</span></span> <span data-ttu-id="b59d9-138">예를 들어, eShopOnContainers의 `Catalog.API` 마이크로 서비스는 Azure Blob Storage, SQL Server 및 RabbitMQ와 같은 많은 서비스에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-138">For example, the `Catalog.API` microservice from eShopOnContainers depends on many services, such as Azure Blob Storage, SQL Server, and RabbitMQ.</span></span> <span data-ttu-id="b59d9-139">따라서 `AddCheck()` 메서드를 사용하여 몇 가지 상태 검사가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-139">Therefore, it has several health checks added using the `AddCheck()` method.</span></span> <span data-ttu-id="b59d9-140">모든 종석 서비스에 대해, 각 상태를 정의하는 사용자 지정 `IHealthCheck` 구현을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-140">For every dependent service, a custom `IHealthCheck` implementation that defines its respective health status needs to be added.</span></span>

<span data-ttu-id="b59d9-141">오픈 소스 프로젝트 [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks)는 .NET Core 2.2를 기반으로 구축된 이러한 엔터프라이즈 서비스마다 사용자 지정 상태 검사 구현을 제공하여 이 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-141">The open-source project [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) solves this problem by providing custom health check implementations for each of these enterprise services that are built on top of .NET Core 2.2.</span></span> <span data-ttu-id="b59d9-142">각 상태 검사는 개별 NuGet 패키지로 제공되기 때문에 프로젝트에 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-142">Each health check is available as an individual NuGet package that can be easily added to the project.</span></span> <span data-ttu-id="b59d9-143">eShopOnContainers는 이것을 모든 마이크로 서비스에 광범위하게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-143">eShopOnContainers use them extensively in all its microservices.</span></span>

<span data-ttu-id="b59d9-144">예를 들어, `Catalog.API` 마이크로 서비스에는 다음과 같은 NuGet 패키지가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-144">For instance, in the `Catalog.API` microservice, the following NuGet packages were added:</span></span>

![AspNetCore.Diagnostics.HealthChecks NuGet 패키지가 참조된 Catalog.API 프로젝트의 솔루션 탐색기 뷰](./media/image6.png)

<span data-ttu-id="b59d9-146">**그림 8-7**.</span><span class="sxs-lookup"><span data-stu-id="b59d9-146">**Figure 8-7**.</span></span> <span data-ttu-id="b59d9-147">AspNetCore.Diagnostics.HealthChecks를 사용하여 Catalog.API에 구현된 사용자 지정 상태 검사</span><span class="sxs-lookup"><span data-stu-id="b59d9-147">Custom Health Checks implemented in Catalog.API using AspNetCore.Diagnostics.HealthChecks</span></span>

<span data-ttu-id="b59d9-148">다음 코드에서는 각 종속 서비스에 대해 상태 검사 구현이 추가된 다음, 미들웨어가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-148">In the following code, the health check implementations are added for each dependent service and then the middleware is configured:</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

<span data-ttu-id="b59d9-149">마지막으로 “/hc” 엔드포인트를 수신할 HealthCheck 미들웨어를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-149">Finally, we add the HealthCheck middleware to listen to “/hc” endpoint:</span></span>

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
}
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="b59d9-150">마이크로 서비스를 쿼리하여 성능 상태에 대해 보고</span><span class="sxs-lookup"><span data-stu-id="b59d9-150">Query your microservices to report about their health status</span></span>

<span data-ttu-id="b59d9-151">이 문서에 설명된 대로 상태 검사를 구성했으며 Docker에서 마이크로 서비스가 실행 중인 경우 브라우저에서 정상인지 여부를 직접 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-151">When you've configured health checks as described in this article and you have the microservice running in Docker, you can directly check from a browser if it's healthy.</span></span> <span data-ttu-id="b59d9-152">그림 8-8과 같이 컨테이너 포트를 Docker 호스트에 게시해야 외부 Docker 호스트 IP 또는 `localhost`를 통해 컨테이너에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-152">You have to publish the container port in the Docker host, so you can access the container through the external Docker host IP or through `localhost`, as shown in figure 8-8.</span></span>

![상태 검사에서 반환된 JSON 응답의 브라우저 보기](./media/image7.png)

<span data-ttu-id="b59d9-154">**그림 8-8**.</span><span class="sxs-lookup"><span data-stu-id="b59d9-154">**Figure 8-8**.</span></span> <span data-ttu-id="b59d9-155">브라우저에서 단일 서비스의 성능 상태 검사</span><span class="sxs-lookup"><span data-stu-id="b59d9-155">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="b59d9-156">이 테스트에서는 `Catalog.API` 마이크로 서비스(5101 포트에서 실행 중)가 정상이며, JSON에서 200 HTTP 상태 및 상태 정보를 반환한다는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-156">In that test, you can see that the `Catalog.API` microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="b59d9-157">이 서비스는 SQL Server 데이터베이스 종속성과 RabbitMQ의 상태를 검사하여 상태 검사에서 직접 정상이라고 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-157">The service also checked the health of its SQL Server database dependency and RabbitMQ, so the health check reported itself as healthy.</span></span>

## <a name="use-watchdogs"></a><span data-ttu-id="b59d9-158">Watchdog 사용</span><span class="sxs-lookup"><span data-stu-id="b59d9-158">Use watchdogs</span></span>

<span data-ttu-id="b59d9-159">Watchdog는 앞에서 소개한 `HealthChecks` 라이브러리로 쿼리하여 서비스 전반의 상태와 로드를 감시하고 마이크로 서비스에 대한 상태를 보고할 수 있는 별도의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-159">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the `HealthChecks` library introduced earlier.</span></span> <span data-ttu-id="b59d9-160">이렇게 하면 단일 서비스 보기를 기반으로 하여 감지되지 않는 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-160">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="b59d9-161">또한 Watchdog은 사용자가 개입하지 않아도 알려진 조건에 대한 수정 작업을 수행할 수 있는 코드를 호스팅하기에 좋은 출발점이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-161">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="b59d9-162">eShopOnContainers 샘플에는 그림 8-9와 같이 샘플 상태 검사 보고서를 표시하는 웹 페이지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-162">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 8-9.</span></span> <span data-ttu-id="b59d9-163">단지 eShopOnContainers의 마이크로 서비스 및 웹 애플리케이션 상태만 표시하므로 가장 간단한 Watchdog입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-163">This is the simplest watchdog you could have since it only shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="b59d9-164">일반적으로 비정상 상태가 검색되면 Watchdog에서 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-164">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

<span data-ttu-id="b59d9-165">다행히도 [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks)는 [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) NuGet 패키지도 제공합니다. 이것을 사용하여 구성된 URI의 상태 검사 결과를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-165">Fortunately, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) also provides [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) NuGet package that can be used to display the health check results from the configured URIs.</span></span>

![eShopOnContainers에서 모든 마이크로 서비스의 상태를 보여주는 WebStatus 앱의 브라우저 보기](./media/image8.png)

<span data-ttu-id="b59d9-167">**그림 8-9**.</span><span class="sxs-lookup"><span data-stu-id="b59d9-167">**Figure 8-9**.</span></span> <span data-ttu-id="b59d9-168">eShopOnContainers의 샘플 상태 검사 보고서</span><span class="sxs-lookup"><span data-stu-id="b59d9-168">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="b59d9-169">요약하자면,이 watchdog 서비스는 각 마이크로 서비스의 "/hc" 엔드포인트를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-169">In summary, this watchdog service queries each microservice’s "/hc" endpoint.</span></span> <span data-ttu-id="b59d9-170">이렇게 하면 내부에 정의된 모든 상태 검사가 실행되고, 모든 검사에 따라 전체 성능 상태가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-170">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span> <span data-ttu-id="b59d9-171">HealthChecksUI는 watchdog 서비스의 Startup.cs에 추가해야 하는 몇 가지 구성 항목과 두 줄의 코드로 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-171">The HealthChecksUI is easy to consume with a few configuration entries and two lines of code that needs to be added into the Startup.cs of the watchdog service.</span></span>

<span data-ttu-id="b59d9-172">상태 검사 UI의 샘플 구성 파일:</span><span class="sxs-lookup"><span data-stu-id="b59d9-172">Sample configuration file for health check UI:</span></span>

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

<span data-ttu-id="b59d9-173">HealthChecksUI를 추가하는 Startup.cs 파일:</span><span class="sxs-lookup"><span data-stu-id="b59d9-173">Startup.cs file that adds HealthChecksUI:</span></span>

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config=> config.UIPath = “/hc-ui”);
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="b59d9-174">오케스트레이터 사용 시의 상태 검사</span><span class="sxs-lookup"><span data-stu-id="b59d9-174">Health checks when using orchestrators</span></span>

<span data-ttu-id="b59d9-175">Kubernetes 및 Service Fabric과 같은 오케스트레이션은 마이크로 서비스의 가용성을 모니터링하기 위해 정기적으로 마이크로 서비스 테스트 요청을 보내 상태 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-175">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="b59d9-176">오케스트레이터에서 비정상 서비스/컨테이너로 인식하면 해당 인스턴스에 대한 요청 라우팅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-176">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="b59d9-177">또한 일반적으로 해당 컨테이너의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-177">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="b59d9-178">예를 들어 대부분의 오케스트레이터에서 상태 검사를 사용하여 가동 중지 시간이 없는 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-178">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="b59d9-179">서비스/컨테이너의 상태가 정상으로 변경될 때만 오케스트레이터에서 트래픽을 서비스/컨테이너 인스턴스로 라우팅하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-179">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="b59d9-180">상태 모니터링은 오케스트레이터에서 애플리케이션 업그레이드를 수행할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-180">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="b59d9-181">Azure Service Fabric과 같은 일부 오케스트레이터는 서비스를 단계별로 업데이트합니다. 예를 들어 애플리케이션 업그레이드마다 클러스터 표면의 1/5을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-181">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="b59d9-182">동시에 업그레이드되는 노드 집합을 ‘업그레이드 도메인’이라고 합니다. </span><span class="sxs-lookup"><span data-stu-id="b59d9-182">The set of nodes that's upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="b59d9-183">각 업그레이드 도메인을 업그레이드하고 사용자가 사용할 수 있게 되면, 먼저 해당 업그레이드 도메인이 상태 검사를 통과한 후에 배포가 다음 업그레이드 도메인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-183">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="b59d9-184">서비스 상태의 또 다른 측면은 서비스의 메트릭을 보고하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-184">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="b59d9-185">이는 Service Fabric과 같은 일부 오케스트레이터의 상태 모델에 대한 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-185">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="b59d9-186">메트릭은 리소스 사용량의 균형을 조정하는 데 사용되므로 오케스트레이터를 사용할 때 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-186">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="b59d9-187">또한 메트릭은 시스템 상태를 나타내는 지표가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-187">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="b59d9-188">예를 들어 많은 마이크로 서비스가 있는 애플리케이션이 있을 수 있으며, 각 인스턴스에서 RPS(초당 요청 수)를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-188">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="b59d9-189">한 서비스에서 다른 서비스보다 더 많은 리소스(메모리, 프로세서 등)를 사용하는 경우, 오케스트레이터는 클러스터에서 서비스 인스턴스를 이동하여 리소스 사용률을 유지하려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-189">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="b59d9-190">Azure Service Fabric은 단순한 상태 검사보다 더 향상된 고급 기능을 갖춘 자체의 [상태 모니터링 모델](/azure/service-fabric/service-fabric-health-introduction)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-190">Note that Azure Service Fabric provides its own [Health Monitoring model](/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="b59d9-191">고급 모니터링: 시각화, 분석 및 경고</span><span class="sxs-lookup"><span data-stu-id="b59d9-191">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="b59d9-192">모니터링의 마지막 부분은 이벤트 스트림을 시각화하고, 서비스 성능에 대해 보고하고, 문제가 검색되면 경고하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-192">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="b59d9-193">이러한 모니터링 측면에 대해 서로 다른 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-193">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="b59d9-194">[AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks)에 대해 설명할 때 보여 준 사용자 지정 페이지와 같이 서비스 상태를 표시하는 간단한 사용자 지정 애플리케이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-194">You can use simple custom applications showing the state of your services, like the custom page shown when explaining the [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks).</span></span> <span data-ttu-id="b59d9-195">또는 [Azure Monitor](https://azure.microsoft.com/services/monitor/)와 같은 고급 도구를 사용하여 이벤트 스트림에 따라 경고를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-195">Or you could use more advanced tools like [Azure Monitor](https://azure.microsoft.com/services/monitor/) to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="b59d9-196">마지막으로 모든 이벤트 스트림을 저장하는 경우 Microsoft Power BI 또는 기타 솔루션(예: Kibana 또는 Splunk)을 사용하여 데이터를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b59d9-196">Finally, if you're storing all the event streams, you can use Microsoft Power BI or other solutions like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b59d9-197">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="b59d9-197">Additional resources</span></span>

- <span data-ttu-id="b59d9-198">**ASP.NET Core용 HealthChecks 및 HealthChecks UI** </span><span class="sxs-lookup"><span data-stu-id="b59d9-198">**HealthChecks and HealthChecks UI for ASP.NET Core** </span></span>\
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- <span data-ttu-id="b59d9-199">**Service Fabric 상태 모니터링 소개** </span><span class="sxs-lookup"><span data-stu-id="b59d9-199">**Introduction to Service Fabric health monitoring** </span></span>\
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- <span data-ttu-id="b59d9-200">**Azure Monitor**</span><span class="sxs-lookup"><span data-stu-id="b59d9-200">**Azure Monitor**</span></span>  
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
><span data-ttu-id="b59d9-201">[이전](implement-circuit-breaker-pattern.md)
>[다음](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b59d9-201">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>
