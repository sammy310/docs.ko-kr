---
title: .NET에서 종속성 주입
description: .NET에서 종속성 주입을 구현하는 방법 및 사용 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/28/2020
ms.topic: overview
ms.openlocfilehash: cc030e32846690b6544b99030800b50055a3113e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "102402104"
---
# <a name="dependency-injection-in-net"></a><span data-ttu-id="43846-103">.NET에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="43846-103">Dependency injection in .NET</span></span>

<span data-ttu-id="43846-104">.NET는 클래스와 해당 종속성 간의 [IoC(Inversion of Control)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion)를 실현하는 기술인 DI(종속성 주입) 소프트웨어 디자인 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-104">.NET supports the dependency injection (DI) software design pattern, which is a technique for achieving [Inversion of Control (IoC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) between classes and their dependencies.</span></span> <span data-ttu-id="43846-105">.NET에서 종속성 주입은 구성, 로깅, 옵션 패턴과 함께 [주요 구성 요소](https://en.wikipedia.org/wiki/First-class_citizen)입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-105">Dependency injection in .NET is a [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen), along with configuration, logging, and the options pattern.</span></span>

<span data-ttu-id="43846-106">‘종속성’은 다른 개체가 종속된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-106">A *dependency* is an object that another object depends on.</span></span> <span data-ttu-id="43846-107">다른 클래스가 종속된 `MessageWriter` 클래스에서 `Write` 메서드를 사용하는 다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="43846-107">Examine the following `MessageWriter` class with a `Write` method that other classes depend on:</span></span>

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

<span data-ttu-id="43846-108">클래스에서 `MessageWriter` 클래스의 인스턴스를 만들어 `Write` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-108">A class can create an instance of the `MessageWriter` class to make use of its `Write` method.</span></span> <span data-ttu-id="43846-109">다음 예제에서 `MessageWriter` 클래스는 `Worker` 클래스의 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-109">In the following example, the `MessageWriter` class is a dependency of the `Worker` class:</span></span>

```csharp
public class Worker : BackgroundService
{
    private readonly MessageWriter _messageWriter = new MessageWriter();

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _messageWriter.Write($"Worker running at: {DateTimeOffset.Now}");
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

<span data-ttu-id="43846-110">이 클래스는 `MessageWriter` 클래스를 만들고 이 클래스에 직접 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-110">The class creates and directly depends on the `MessageWriter` class.</span></span> <span data-ttu-id="43846-111">이전 예제와 같은 하드 코딩된 종속성은 문제가 있으며 다음과 같은 이유로 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-111">Hard-coded dependencies, such as in the previous example, are problematic and should be avoided for the following reasons:</span></span>

- <span data-ttu-id="43846-112">`MessageWriter`를 다른 구현으로 바꾸려면 `Worker` 클래스를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-112">To replace `MessageWriter` with a different implementation, the `Worker` class must be modified.</span></span>
- <span data-ttu-id="43846-113">`MessageWriter`에 종속성이 있으면 `Worker` 클래스에서 해당 종속성도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-113">If `MessageWriter` has dependencies, they must also be configured by the `Worker` class.</span></span> <span data-ttu-id="43846-114">여러 클래스가 `MessageWriter`에 종속되어 있는 대형 프로젝트에서는 구성 코드가 앱 전체에 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-114">In a large project with multiple classes depending on `MessageWriter`, the configuration code becomes scattered across the app.</span></span>
- <span data-ttu-id="43846-115">이 구현은 단위 테스트하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-115">This implementation is difficult to unit test.</span></span> <span data-ttu-id="43846-116">앱에서 모의 또는 스텁 `MessageWriter` 클래스를 사용해야 하지만, 이 방법에서는 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-116">The app should use a mock or stub `MessageWriter` class, which isn't possible with this approach.</span></span>

<span data-ttu-id="43846-117">종속성 주입은 다음을 통해 이러한 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-117">Dependency injection addresses these problems through:</span></span>

- <span data-ttu-id="43846-118">인퍼테이스 또는 기본 클래스를 사용하여 종속성 구현을 추상화합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-118">The use of an interface or base class to abstract the dependency implementation.</span></span>
- <span data-ttu-id="43846-119">서비스 컨테이너에 종속성 등록.</span><span class="sxs-lookup"><span data-stu-id="43846-119">Registration of the dependency in a service container.</span></span> <span data-ttu-id="43846-120">.NET는 서비스 컨테이너인 <xref:System.IServiceProvider>를 기본 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-120">.NET provides a built-in service container, <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="43846-121">서비스는 일반적으로 앱 시작 시 등록되고 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-121">Services are typically registered at the app's start-up, and appended to an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="43846-122">모든 서비스가 추가되면 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 사용하여 서비스 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43846-122">Once all services are added, you use <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> to create the service container.</span></span>
- <span data-ttu-id="43846-123">서비스가 사용되는 클래스의 생성자에 주입됨.</span><span class="sxs-lookup"><span data-stu-id="43846-123">*Injection* of the service into the constructor of the class where it's used.</span></span> <span data-ttu-id="43846-124">프레임워크가 종속성의 인스턴스를 만들고 더 이상 필요하지 않으면 삭제하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-124">The framework takes on the responsibility of creating an instance of the dependency and disposing of it when it's no longer needed.</span></span>

<span data-ttu-id="43846-125">예를 들어 `IMessageWriter` 인터페이스는 `Write` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-125">As an example, the `IMessageWriter` interface defines the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

<span data-ttu-id="43846-126">이 인터페이스는 구체적인 형식 `MessageWriter`에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-126">This interface is implemented by a concrete type, `MessageWriter`:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

<span data-ttu-id="43846-127">샘플 코드에서는 `IMessageWriter` 서비스를 구체적인 형식 `MessageWriter`로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-127">The sample code registers the `IMessageWriter` service with the concrete type `MessageWriter`.</span></span> <span data-ttu-id="43846-128"><xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> 메서드는 단일 요청의 수명인 범위가 지정된 수명으로 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-128">The <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> method registers the service with a scoped lifetime, the lifetime of a single request.</span></span> <span data-ttu-id="43846-129">[서비스 수명](#service-lifetimes)에 대해서는 이 문서의 뒷부분에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-129">[Service lifetimes](#service-lifetimes) are described later in this article.</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

<span data-ttu-id="43846-130">샘플 앱에서는 `IMessageWriter` 서비스가 요청되며 이 서비스는 `Write` 메서드를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-130">In the sample app, the `IMessageWriter` service is requested and used to call the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

<span data-ttu-id="43846-131">DI 패턴을 사용하여 작업자 서비스는</span><span class="sxs-lookup"><span data-stu-id="43846-131">By using the DI pattern, the worker service:</span></span>

- <span data-ttu-id="43846-132">구체적인 형식 `MessageWriter`를 사용하지 않고 구현되는 `IMessageWriter` 인터페이스만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-132">Doesn't use the concrete type `MessageWriter`, only the `IMessageWriter` interface that implements it.</span></span> <span data-ttu-id="43846-133">따라서 컨트롤러에서 사용하는 구현을 컨트롤러를 수정하지 않고 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-133">That makes it easy to change the implementation that the controller uses without modifying the controller.</span></span>
- <span data-ttu-id="43846-134">`MessageWriter`의 인스턴스를 만들지 않습니다. 해당 인스턴스는 DI 컨테이너에 의해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="43846-134">Doesn't create an instance of `MessageWriter`, it's created by the DI container.</span></span>

<span data-ttu-id="43846-135">`IMessageWriter` 인터페이스의 구현을 기본 제공 로깅 API를 사용하여 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-135">The implementation of the `IMessageWriter` interface can be improved by using the built-in logging API:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

<span data-ttu-id="43846-136">업데이트된 `ConfigureServices` 메서드는 새 `IMessageWriter` 구현을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-136">The updated `ConfigureServices` method registers the new `IMessageWriter` implementation:</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

<span data-ttu-id="43846-137">`LoggingMessageWriter`는 생성자에서 요청하는 <xref:Microsoft.Extensions.Logging.ILogger%601>에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-137">`LoggingMessageWriter` depends on <xref:Microsoft.Extensions.Logging.ILogger%601>, which it requests in the constructor.</span></span> <span data-ttu-id="43846-138">`ILogger<TCategoryName>`은 [프레임워크에서 제공하는 서비스](#framework-provided-services)입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-138">`ILogger<TCategoryName>` is a [framework-provided service](#framework-provided-services).</span></span>

<span data-ttu-id="43846-139">종속성 주입을 연결된 방식으로 사용하는 일은 특별한 경우가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="43846-139">It's not unusual to use dependency injection in a chained fashion.</span></span> <span data-ttu-id="43846-140">요청된 각 종속성은 차례로 자체 종속성을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-140">Each requested dependency in turn requests its own dependencies.</span></span> <span data-ttu-id="43846-141">컨테이너는 그래프의 종속성을 해결하고 완전히 해결된 서비스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-141">The container resolves the dependencies in the graph and returns the fully resolved service.</span></span> <span data-ttu-id="43846-142">해결해야 하는 종속성이 모인 집합은 일반적으로 종속성 트리, 종속성 그래프 또는 개체 그래프라고 합니다  .</span><span class="sxs-lookup"><span data-stu-id="43846-142">The collective set of dependencies that must be resolved is typically referred to as a *dependency tree*, *dependency graph*, or *object graph*.</span></span>

<span data-ttu-id="43846-143">컨테이너는 [개방형 형식(제네릭)](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types)을 활용하여 `ILogger<TCategoryName>`을 해결하므로 모든 [생성된 형식(제네릭)](/dotnet/csharp/language-reference/language-specification/types#constructed-types)을 등록하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-143">The container resolves `ILogger<TCategoryName>` by taking advantage of [(generic) open types](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), eliminating the need to register every [(generic) constructed type](/dotnet/csharp/language-reference/language-specification/types#constructed-types).</span></span>

<span data-ttu-id="43846-144">종속성 주입 용어에서 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-144">In dependency injection terminology, a service:</span></span>

- <span data-ttu-id="43846-145">일반적으로 다른 개체에 `IMessageWriter` 서비스와 같은 서비스를 제공하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-145">Is typically an object that provides a service to other objects, such as the `IMessageWriter` service.</span></span>
- <span data-ttu-id="43846-146">서비스에서 웹 서비스를 사용할 수 있지만 웹 서비스와 관련 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="43846-146">Is not related to a web service, although the service may use a web service.</span></span>

<span data-ttu-id="43846-147">해당 프레임워크는 강력한 로깅 시스템을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-147">The framework provides a robust logging system.</span></span> <span data-ttu-id="43846-148">이전 예제에 표시된 `IMessageWriter` 구현은 로깅을 구현하는 것이 아니라 기본 DI를 보여 주기 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-148">The `IMessageWriter` implementations shown in the preceding examples were written to demonstrate basic DI, not to implement logging.</span></span> <span data-ttu-id="43846-149">대부분의 앱에서는 로거를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-149">Most apps shouldn't need to write loggers.</span></span> <span data-ttu-id="43846-150">다음 코드에서는 `Worker`를 `ConfigureServices`에서 호스팅된 서비스 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>로 등록해야 하는 기본 로깅을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43846-150">The following code demonstrates using the default logging, which only requires the `Worker` to be registered in `ConfigureServices` as a hosted service <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>:</span></span>

```csharp
public class Worker : BackgroundService
{
    private readonly ILogger<Worker> _logger;

    public Worker(ILogger<Worker> logger) =>
        _logger = logger;

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogInformation("Worker running at: {time}", DateTimeOffset.Now);
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

<span data-ttu-id="43846-151">위의 코드를 사용하여 프레임워크에서 로깅을 제공하므로 `ConfigureServices`를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-151">Using the preceding code, there is no need to update `ConfigureServices`, because logging is provided by the framework.</span></span>

## <a name="register-groups-of-services-with-extension-methods"></a><span data-ttu-id="43846-152">확장 메서드를 사용하여 서비스 그룹 등록</span><span class="sxs-lookup"><span data-stu-id="43846-152">Register groups of services with extension methods</span></span>

<span data-ttu-id="43846-153">Microsoft Extensions에서는 관련 서비스 그룹을 등록하는 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-153">Microsoft Extensions uses a convention for registering a group of related services.</span></span> <span data-ttu-id="43846-154">규칙은 단일 `Add{GROUP_NAME}` 확장 메서드를 사용하여 프레임워크 기능에 필요한 모든 서비스를 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-154">The convention is to use a single `Add{GROUP_NAME}` extension method to register all of the services required by a framework feature.</span></span> <span data-ttu-id="43846-155">예를 들어 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> 확장 메서드는 옵션을 사용하는 데 필요한 모든 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-155">For example, the <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> extension method registers all of the services required for using options.</span></span>

## <a name="framework-provided-services"></a><span data-ttu-id="43846-156">프레임워크에서 제공하는 서비스</span><span class="sxs-lookup"><span data-stu-id="43846-156">Framework-provided services</span></span>

<span data-ttu-id="43846-157">`ConfigureServices` 메서드는 플랫폼 기능을 비롯해 앱이 사용하는 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-157">The `ConfigureServices` method registers services that the app uses, including platform features.</span></span> <span data-ttu-id="43846-158">처음에 `ConfigureServices`에 제공되는 `IServiceCollection`에는 [호스트가 구성된 방법](generic-host.md#host-configuration)에 따라 달라지는 프레임워크에 의해 정의되는 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-158">Initially, the `IServiceCollection` provided to `ConfigureServices` has services defined by the framework depending on [how the host was configured](generic-host.md#host-configuration).</span></span> <span data-ttu-id="43846-159">.NET 템플릿을 기반으로 하는 앱의 경우 프레임워크에서 수백 개의 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-159">For apps based on the .NET templates, the framework registers hundreds of services.</span></span>

<span data-ttu-id="43846-160">다음 표에는 프레임워크에서 등록한 서비스들의 작은 샘플이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-160">The following table lists a small sample of these framework-registered services:</span></span>

| <span data-ttu-id="43846-161">서비스 종류</span><span class="sxs-lookup"><span data-stu-id="43846-161">Service Type</span></span>                                                                       | <span data-ttu-id="43846-162">수명</span><span class="sxs-lookup"><span data-stu-id="43846-162">Lifetime</span></span>  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | <span data-ttu-id="43846-163">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-163">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | <span data-ttu-id="43846-164">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-164">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | <span data-ttu-id="43846-165">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-165">Singleton</span></span> |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | <span data-ttu-id="43846-166">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-166">Singleton</span></span> |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | <span data-ttu-id="43846-167">Transient</span><span class="sxs-lookup"><span data-stu-id="43846-167">Transient</span></span> |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | <span data-ttu-id="43846-168">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-168">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | <span data-ttu-id="43846-169">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-169">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | <span data-ttu-id="43846-170">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-170">Singleton</span></span> |

## <a name="service-lifetimes"></a><span data-ttu-id="43846-171">서비스 수명</span><span class="sxs-lookup"><span data-stu-id="43846-171">Service lifetimes</span></span>

<span data-ttu-id="43846-172">다음 수명 중 하나를 사용하여 서비스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-172">Services can be registered with one of the following lifetimes:</span></span>

- <span data-ttu-id="43846-173">Transient</span><span class="sxs-lookup"><span data-stu-id="43846-173">Transient</span></span>
- <span data-ttu-id="43846-174">Scoped</span><span class="sxs-lookup"><span data-stu-id="43846-174">Scoped</span></span>
- <span data-ttu-id="43846-175">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-175">Singleton</span></span>

<span data-ttu-id="43846-176">다음 섹션에서는 위의 각 수명에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-176">The following sections describe each of the preceding lifetimes.</span></span> <span data-ttu-id="43846-177">등록된 각 서비스의 수명을 적절히 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-177">Choose an appropriate lifetime for each registered service.</span></span>

### <a name="transient"></a><span data-ttu-id="43846-178">Transient</span><span class="sxs-lookup"><span data-stu-id="43846-178">Transient</span></span>

<span data-ttu-id="43846-179">Transient 수명 서비스는 서비스 컨테이너에서 요청할 때마다 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="43846-179">Transient lifetime services are created each time they're requested from the service container.</span></span> <span data-ttu-id="43846-180">이 수명은 간단한 상태 비저장 서비스에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-180">This lifetime works best for lightweight, stateless services.</span></span> <span data-ttu-id="43846-181"><xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>를 사용하여 임시 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-181">Register transient services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>.</span></span>

<span data-ttu-id="43846-182">요청을 처리하는 앱에서 Transient 서비스는 요청이 끝날 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-182">In apps that process requests, transient services are disposed at the end of the request.</span></span>

### <a name="scoped"></a><span data-ttu-id="43846-183">Scoped</span><span class="sxs-lookup"><span data-stu-id="43846-183">Scoped</span></span>

<span data-ttu-id="43846-184">웹 애플리케이션의 경우 범위가 지정된 수명은 클라이언트 요청(연결)마다 한 번씩 서비스가 생성됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43846-184">For web applications, a scoped lifetime indicates that services are created once per client request (connection).</span></span> <span data-ttu-id="43846-185"><xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>를 사용하여 범위 지정된 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-185">Register scoped services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>.</span></span>

<span data-ttu-id="43846-186">요청을 처리하는 앱에서 Scoped 서비스는 요청이 끝날 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-186">In apps that process requests, scoped services are disposed at the end of the request.</span></span>

<span data-ttu-id="43846-187">Entity Framework Core를 사용하는 경우 <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> 확장 메서드는 기본적으로 범위가 지정된 수명으로 `DbContext` 형식을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-187">When using Entity Framework Core, the <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> extension method registers `DbContext` types with a scoped lifetime by default.</span></span>

> [!NOTE]
> <span data-ttu-id="43846-188">singleton에서 범위가 지정된 서비스를 해결하지 \***마세요**._ 예를 들어 임시 서비스를 통해 간접적으로 해결하지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-188">Do \***not** _ resolve a scoped service from a singleton and be careful not to do so indirectly, for example, through a transient service.</span></span> <span data-ttu-id="43846-189">이 경우 후속 요청을 처리할 때 서비스가 잘못된 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-189">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="43846-190">다음 작업은 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-190">It's fine to:</span></span>
>
> - <span data-ttu-id="43846-191">범위가 지정된 서비스 또는 임시 서비스에서 싱클톤 서비스를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-191">Resolve a singleton service from a scoped or transient service.</span></span>
> - <span data-ttu-id="43846-192">다른 범위가 지정된 서비스 또는 임시 서비스에서 범위가 지정된 서비스를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-192">Resolve a scoped service from another scoped or transient service.</span></span>

<span data-ttu-id="43846-193">기본적으로 개발 환경에서 수명이 더 긴 다른 서비스에서 서비스를 해결하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-193">By default, in the development environment, resolving a service from another service with a longer lifetime throws an exception.</span></span> <span data-ttu-id="43846-194">자세한 내용은 [범위 유효성 검사](#scope-validation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43846-194">For more information, see [Scope validation](#scope-validation).</span></span>

### <a name="singleton"></a><span data-ttu-id="43846-195">Singleton</span><span class="sxs-lookup"><span data-stu-id="43846-195">Singleton</span></span>

<span data-ttu-id="43846-196">싱클톤 수명 서비스는 다음과 같은 경우 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-196">Singleton lifetime services are created either:</span></span>

- <span data-ttu-id="43846-197">처음 요청되는 경우</span><span class="sxs-lookup"><span data-stu-id="43846-197">The first time they're requested.</span></span>
- <span data-ttu-id="43846-198">개발자가 구현 인스턴스를 컨테이너에 직접 제공하는 경우</span><span class="sxs-lookup"><span data-stu-id="43846-198">By the developer, when providing an implementation instance directly to the container.</span></span> <span data-ttu-id="43846-199">(이 방법은 거의 필요하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="43846-199">This approach is rarely needed.</span></span>

<span data-ttu-id="43846-200">종속성 주입 컨테이너로부터 서비스 구현에 대한 모든 후속 요청은 동일한 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-200">Every subsequent request of the service implementation from the dependency injection container uses the same instance.</span></span> <span data-ttu-id="43846-201">앱에 싱글톤 동작이 필요한 경우 서비스 컨테이너가 서비스 수명을 관리하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-201">If the app requires singleton behavior, allow the service container to manage the service's lifetime.</span></span> <span data-ttu-id="43846-202">싱글톤 디자인 패턴을 구현하지 말고 싱글톤을 삭제하는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-202">Don't implement the singleton design pattern and provide code to dispose of the singleton.</span></span> <span data-ttu-id="43846-203">컨테이너에서 서비스를 해결한 코드에서는 서비스를 삭제하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-203">Services should never be disposed by code that resolved the service from the container.</span></span> <span data-ttu-id="43846-204">형식 또는 팩터리가 싱글톤으로 등록된 경우 컨테이너에서 싱글톤을 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-204">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="43846-205"><xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>를 사용하여 싱글톤 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-205">Register singleton services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>.</span></span> <span data-ttu-id="43846-206">싱글톤 서비스는 스레드로부터 안전해야 하며 상태 비저장 서비스에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-206">Singleton services must be thread safe and are often used in stateless services.</span></span>

<span data-ttu-id="43846-207">요청을 처리하는 앱에서 싱글톤 서비스는 애플리케이션 종료 시 <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider>가 삭제될 때 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-207">In apps that process requests, singleton services are disposed when the <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> is disposed on application shutdown.</span></span> <span data-ttu-id="43846-208">앱이 종료될 때까지 메모리가 해제되지 않으므로 싱글톤 서비스에서 메모리 사용을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-208">Because memory is not released until the app is shut down, consider memory use with a singleton service.</span></span>

> [!WARNING]
> <span data-ttu-id="43846-209">싱글톤에서 범위가 지정된 서비스를 확인하지 ‘마세요’.</span><span class="sxs-lookup"><span data-stu-id="43846-209">Do _*_not_*_ resolve a scoped service from a singleton.</span></span> <span data-ttu-id="43846-210">이 경우 후속 요청을 처리할 때 서비스가 잘못된 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-210">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="43846-211">범위가 지정된 서비스 또는 임시 서비스에서 싱글톤 서비스를 해결하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-211">It's fine to resolve a singleton service from a scoped or transient service.</span></span>

## <a name="service-registration-methods"></a><span data-ttu-id="43846-212">서비스 등록 메서드</span><span class="sxs-lookup"><span data-stu-id="43846-212">Service registration methods</span></span>

<span data-ttu-id="43846-213">프레임워크는 특정 시나리오에 유용한 서비스 등록 확장 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-213">The framework provides service registration extension methods that are useful in specific scenarios:</span></span>

| <span data-ttu-id="43846-214">메서드</span><span class="sxs-lookup"><span data-stu-id="43846-214">Method</span></span> | <span data-ttu-id="43846-215">자동</span><span class="sxs-lookup"><span data-stu-id="43846-215">Automatic</span></span><br><span data-ttu-id="43846-216">개체</span><span class="sxs-lookup"><span data-stu-id="43846-216">object</span></span><br><span data-ttu-id="43846-217">삭제</span><span class="sxs-lookup"><span data-stu-id="43846-217">disposal</span></span> | <span data-ttu-id="43846-218">여러</span><span class="sxs-lookup"><span data-stu-id="43846-218">Multiple</span></span><br><span data-ttu-id="43846-219">구현</span><span class="sxs-lookup"><span data-stu-id="43846-219">implementations</span></span> | <span data-ttu-id="43846-220">인수 전달</span><span class="sxs-lookup"><span data-stu-id="43846-220">Pass args</span></span> |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br><span data-ttu-id="43846-221">예제:</span><span class="sxs-lookup"><span data-stu-id="43846-221">Example:</span></span><br><br>`services.AddSingleton<IMyDep, MyDep>();` | <span data-ttu-id="43846-222">예</span><span class="sxs-lookup"><span data-stu-id="43846-222">Yes</span></span> | <span data-ttu-id="43846-223">예</span><span class="sxs-lookup"><span data-stu-id="43846-223">Yes</span></span> | <span data-ttu-id="43846-224">예</span><span class="sxs-lookup"><span data-stu-id="43846-224">No</span></span> |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br><span data-ttu-id="43846-225">예제:</span><span class="sxs-lookup"><span data-stu-id="43846-225">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | <span data-ttu-id="43846-226">예</span><span class="sxs-lookup"><span data-stu-id="43846-226">Yes</span></span> | <span data-ttu-id="43846-227">예</span><span class="sxs-lookup"><span data-stu-id="43846-227">Yes</span></span> | <span data-ttu-id="43846-228">예</span><span class="sxs-lookup"><span data-stu-id="43846-228">Yes</span></span> |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br><span data-ttu-id="43846-229">예제:</span><span class="sxs-lookup"><span data-stu-id="43846-229">Example:</span></span><br><br>`services.AddSingleton<MyDep>();` | <span data-ttu-id="43846-230">예</span><span class="sxs-lookup"><span data-stu-id="43846-230">Yes</span></span> | <span data-ttu-id="43846-231">예</span><span class="sxs-lookup"><span data-stu-id="43846-231">No</span></span> | <span data-ttu-id="43846-232">예</span><span class="sxs-lookup"><span data-stu-id="43846-232">No</span></span> |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br><span data-ttu-id="43846-233">예제:</span><span class="sxs-lookup"><span data-stu-id="43846-233">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | <span data-ttu-id="43846-234">예</span><span class="sxs-lookup"><span data-stu-id="43846-234">No</span></span> | <span data-ttu-id="43846-235">예</span><span class="sxs-lookup"><span data-stu-id="43846-235">Yes</span></span> | <span data-ttu-id="43846-236">예</span><span class="sxs-lookup"><span data-stu-id="43846-236">Yes</span></span> |
| `AddSingleton(new {IMPLEMENTATION})`<br><br><span data-ttu-id="43846-237">예제:</span><span class="sxs-lookup"><span data-stu-id="43846-237">Examples:</span></span><br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | <span data-ttu-id="43846-238">예</span><span class="sxs-lookup"><span data-stu-id="43846-238">No</span></span> | <span data-ttu-id="43846-239">예</span><span class="sxs-lookup"><span data-stu-id="43846-239">No</span></span> | <span data-ttu-id="43846-240">예</span><span class="sxs-lookup"><span data-stu-id="43846-240">Yes</span></span> |

<span data-ttu-id="43846-241">형식 삭제에 대한 자세한 내용은 [서비스의 삭제](dependency-injection-guidelines.md#disposal-of-services) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43846-241">For more information on type disposal, see the [Disposal of services](dependency-injection-guidelines.md#disposal-of-services) section.</span></span>

<span data-ttu-id="43846-242">구현 형식만으로 서비스를 등록하는 것은 동일한 구현 및 서비스 형식으로 해당 서비스를 등록하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-242">Registering a service with only an implementation type is equivalent to registering that service with the same implementation and service type.</span></span> <span data-ttu-id="43846-243">따라서 명시적 서비스 형식을 사용하지 않는 메서드를 사용하여 서비스의 여러 구현을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-243">This is why multiple implementations of a service cannot be registered using the methods that don't take an explicit service type.</span></span> <span data-ttu-id="43846-244">이러한 메서드는 서비스의 여러 ‘인스턴스’를 등록할 수 있지만 모두 동일한 ‘구현’ 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-244">These methods can register multiple _instances\* of a service, but they will all have the same *implementation* type.</span></span>

<span data-ttu-id="43846-245">위의 서비스 등록 메서드 중 하나를 사용하여 동일한 서비스 형식의 여러 서비스 인스턴스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-245">Any of the above service registration methods can be used to register multiple service instances of the same service type.</span></span> <span data-ttu-id="43846-246">다음 예제에서는 `IMessageWriter`를 서비스 형식으로 사용하여 `AddSingleton`을 두 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-246">In the following example, `AddSingleton` is called twice with `IMessageWriter` as the service type.</span></span> <span data-ttu-id="43846-247">두 번째 `AddSingleton` 호출은 `IMessageWriter`로 확인되면 이전 호출을 재정의하고 `IEnumerable<IMessageWriter>`를 통해 여러 서비스가 확인되면 이전 호출에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-247">The second call to `AddSingleton` overrides the previous one when resolved as `IMessageWriter` and adds to the previous one when multiple services are resolved via `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="43846-248">서비스는 `IEnumerable<{SERVICE}>`를 통해 해결될 때 등록된 순서로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="43846-248">Services appear in the order they were registered when resolved via `IEnumerable<{SERVICE}>`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/Program.cs" highlight="19-24":::

<span data-ttu-id="43846-249">위의 샘플 소스 코드는 `IMessageWriter`의 두 가지 구현을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-249">The preceding sample source code registers two implementations of the `IMessageWriter`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/ExampleService.cs" highlight="9-18":::

<span data-ttu-id="43846-250">`ExampleService`는 두 가지 생성자 매개 변수인 단일 `IMessageWriter` 및 `IEnumerable<IMessageWriter>`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-250">The `ExampleService` defines two constructor parameters; a single `IMessageWriter`, and an `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="43846-251">단일 `IMessageWriter`는 등록된 마지막 구현이고, `IEnumerable<IMessageWriter>`는 등록된 모든 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43846-251">The single `IMessageWriter` is the last implementation to have been registered, whereas the `IEnumerable<IMessageWriter>` represents all registered implementations.</span></span>

<span data-ttu-id="43846-252">또한 프레임워크에서는 아직 등록된 구현이 없는 경우에만 서비스를 등록하는 `TryAdd{LIFETIME}` 확장 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-252">The framework also provides `TryAdd{LIFETIME}` extension methods, which register the service only if there isn't already an implementation registered.</span></span>

<span data-ttu-id="43846-253">다음 예제에서 `AddSingleton`을 호출하면 `ConsoleMessageWriter`가 `IMessageWriter`에 대한 구현으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-253">In the following example, the call to `AddSingleton` registers `ConsoleMessageWriter` as an implementation for `IMessageWriter`.</span></span> <span data-ttu-id="43846-254">`TryAddSingleton`에 대한 호출은 `IMessageWriter`에 이미 등록된 구현이 있으므로 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-254">The call to `TryAddSingleton` has no effect because `IMessageWriter` already has a registered implementation:</span></span>

```csharp
services.AddSingleton<IMessageWriter, ConsoleMessageWriter>();
services.TryAddSingleton<IMessageWriter, LoggingMessageWriter>();
```

<span data-ttu-id="43846-255">`TryAddSingleton`은 이미 추가되었기 때문에 ‘시도’가 실패하므로 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-255">The `TryAddSingleton` has no effect, as it was already added and the "try" will fail.</span></span> <span data-ttu-id="43846-256">`ExampleService`는 다음을 어설션합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-256">The `ExampleService` would assert the following:</span></span>

```csharp
public class ExampleService
{
    public ExampleService(
        IMessageWriter messageWriter,
        IEnumerable<IMessageWriter> messageWriters)
    {
        Trace.Assert(messageWriter is ConsoleMessageWriter);
        Trace.Assert(messageWriters.Single() is ConsoleMessageWriter);
    }
}
```

<span data-ttu-id="43846-257">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43846-257">For more information, see:</span></span>

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

<span data-ttu-id="43846-258">[TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) 메서드는 ‘동일한 형식’의 구현이 아직 없는 경우에만 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-258">The [TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) methods register the service only if there isn't already an implementation *of the same type*.</span></span> <span data-ttu-id="43846-259">여러 서비스가 `IEnumerable<{SERVICE}>`를 통해 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-259">Multiple services are resolved via `IEnumerable<{SERVICE}>`.</span></span> <span data-ttu-id="43846-260">서비스를 등록할 때 동일한 형식 중 하나가 아직 추가되지 않은 경우 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-260">When registering services, add an instance if one of the same types hasn't already been added.</span></span> <span data-ttu-id="43846-261">라이브러리 작성자는 컨테이너에 있는 특정 구현의 여러 복사본이 등록되지 않도록 `TryAddEnumerable`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-261">Library authors use `TryAddEnumerable` to avoid registering multiple copies of an implementation in the container.</span></span>

<span data-ttu-id="43846-262">다음 예제에서 `TryAddEnumerable`을 처음 호출하면 `MessageWriter`가 `IMessageWriter1`에 대한 구현으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-262">In the following example, the first call to `TryAddEnumerable` registers `MessageWriter` as an implementation for `IMessageWriter1`.</span></span> <span data-ttu-id="43846-263">두 번째 호출에서는 `IMessageWriter2`에 대한 `MessageWriter`를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-263">The second call registers `MessageWriter` for `IMessageWriter2`.</span></span> <span data-ttu-id="43846-264">세 번째 호출은 `IMessageWriter1`에 `MessageWriter`의 등록된 구현이 이미 있으므로 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-264">The third call has no effect because `IMessageWriter1` already has a registered implementation of `MessageWriter`:</span></span>

```csharp
public interface IMessageWriter1 { }
public interface IMessageWriter2 { }

public class MessageWriter : IMessageWriter1, IMessageWriter2
{
}

services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter2, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
```

<span data-ttu-id="43846-265">서비스 등록은 동일한 형식의 여러 구현을 등록하는 경우를 제외하고 일반적으로 순서와 상관이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-265">Service registration is generally order independent except when registering multiple implementations of the same type.</span></span>

<span data-ttu-id="43846-266">`IServiceCollection`은 <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-266">`IServiceCollection` is a collection of <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> objects.</span></span> <span data-ttu-id="43846-267">다음 예에서는 `ServiceDescriptor`을 만든 후 추가하여 서비스를 등록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43846-267">The following example shows how to register a service by creating and adding a `ServiceDescriptor`:</span></span>

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

<span data-ttu-id="43846-268">기본 제공 `Add{LIFETIME}` 메서드는 같은 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-268">The built-in `Add{LIFETIME}` methods use the same approach.</span></span> <span data-ttu-id="43846-269">예를 들어 [AddScoped 소스 코드](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43846-269">For example, see the [AddScoped source code](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).</span></span>

### <a name="constructor-injection-behavior"></a><span data-ttu-id="43846-270">생성자 주입 동작</span><span class="sxs-lookup"><span data-stu-id="43846-270">Constructor injection behavior</span></span>

<span data-ttu-id="43846-271">다음을 사용하여 서비스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-271">Services can be resolved by using:</span></span>

- <xref:System.IServiceProvider>
- <span data-ttu-id="43846-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span><span class="sxs-lookup"><span data-stu-id="43846-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span></span>
  - <span data-ttu-id="43846-273">컨테이너에 등록되지 않은 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43846-273">Creates objects that aren't registered in the container.</span></span>
  - <span data-ttu-id="43846-274">일부 프레임워크 기능과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-274">Used with some framework features.</span></span>

<span data-ttu-id="43846-275">생성자에는 종속성 주입으로 제공되지 않는 인수를 사용할 수 있지만, 인수에 기본값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-275">Constructors can accept arguments that aren't provided by dependency injection, but the arguments must assign default values.</span></span>

<span data-ttu-id="43846-276">`IServiceProvider` 또는 `ActivatorUtilities`로 서비스를 해결하는 경우 생성자 주입에 *public* 생성자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-276">When services are resolved by `IServiceProvider` or `ActivatorUtilities`, constructor injection requires a *public* constructor.</span></span>

<span data-ttu-id="43846-277">`ActivatorUtilities`로 서비스를 해결하는 경우 생성자 주입을 위해서는 적합한 생성자가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-277">When services are resolved by `ActivatorUtilities`, constructor injection requires that only one applicable constructor exists.</span></span> <span data-ttu-id="43846-278">생성자 오버로드가 지원되지만, 해당 인수가 모두 종속성 주입으로 처리될 수 있는 하나의 오버로드만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-278">Constructor overloads are supported, but only one overload can exist whose arguments can all be fulfilled by dependency injection.</span></span>

## <a name="scope-validation"></a><span data-ttu-id="43846-279">범위 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="43846-279">Scope validation</span></span>

<span data-ttu-id="43846-280">앱이 `Development` 환경에서 실행되고 호스트를 빌드하기 위해 [CreateDefaultBuilder](generic-host.md#default-builder-settings)를 호출하는 경우 기본 서비스 공급자가 다음을 확인하는 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-280">When the app runs in the `Development` environment and calls [CreateDefaultBuilder](generic-host.md#default-builder-settings) to build the host, the default service provider performs checks to verify that:</span></span>

- <span data-ttu-id="43846-281">범위가 지정된 서비스는 루트 서비스 공급자에서 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-281">Scoped services aren't resolved from the root service provider.</span></span>
- <span data-ttu-id="43846-282">범위가 지정된 서비스는 싱글톤에 삽입되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43846-282">Scoped services aren't injected into singletons.</span></span>

<span data-ttu-id="43846-283">루트 서비스 공급자는 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 호출할 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="43846-283">The root service provider is created when <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> is called.</span></span> <span data-ttu-id="43846-284">루트 서비스 공급자의 수명은 공급자가 앱과 함께 시작되고 앱이 종료될 때 삭제되는 앱의 수명에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-284">The root service provider's lifetime corresponds to the app's lifetime when the provider starts with the app and is disposed when the app shuts down.</span></span>

<span data-ttu-id="43846-285">범위가 지정된 서비스는 서비스를 만든 컨테이너에 의해 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="43846-285">Scoped services are disposed by the container that created them.</span></span> <span data-ttu-id="43846-286">범위가 지정된 서비스가 루트 컨테이너에서 만들어지는 경우 서비스의 수명은 사실상 싱글톤으로 승격됩니다. 해당 서비스는 앱이 종료될 때 루트 컨테이너에 의해서만 삭제되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="43846-286">If a scoped service is created in the root container, the service's lifetime is effectively promoted to singleton because it's only disposed by the root container when the app shuts down.</span></span> <span data-ttu-id="43846-287">서비스 범위의 유효성 검사는 `BuildServiceProvider`가 호출될 경우 이러한 상황을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-287">Validating service scopes catches these situations when `BuildServiceProvider` is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="43846-288">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43846-288">See also</span></span>

- [<span data-ttu-id="43846-289">.NET에서 종속성 주입 사용</span><span class="sxs-lookup"><span data-stu-id="43846-289">Use dependency injection in .NET</span></span>](dependency-injection-usage.md)
- [<span data-ttu-id="43846-290">종속성 주입 지침</span><span class="sxs-lookup"><span data-stu-id="43846-290">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
- [<span data-ttu-id="43846-291">ASP.NET Core에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="43846-291">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
- [<span data-ttu-id="43846-292">DI 앱 개발을 위한 NDC 컨퍼런스 패턴</span><span class="sxs-lookup"><span data-stu-id="43846-292">NDC Conference Patterns for DI app development</span></span>](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [<span data-ttu-id="43846-293">명시적 종속성 원칙</span><span class="sxs-lookup"><span data-stu-id="43846-293">Explicit dependencies principle</span></span>](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [<span data-ttu-id="43846-294">Inversion of Control 컨테이너 및 종속성 주입 패턴(Martin Fowler)</span><span class="sxs-lookup"><span data-stu-id="43846-294">Inversion of control containers and the dependency injection pattern (Martin Fowler)</span></span>](https://www.martinfowler.com/articles/injection.html)
- <span data-ttu-id="43846-295">DI 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43846-295">DI bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
