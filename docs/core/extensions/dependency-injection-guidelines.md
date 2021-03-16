---
title: 종속성 주입 지침
description: .NET 애플리케이션 개발을 위한 다양한 종속성 주입 지침 및 모범 사례를 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/29/2020
ms.topic: guide
ms.openlocfilehash: 105536df873829dc79dcca1b86d080360e71303f
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "102402146"
---
# <a name="dependency-injection-guidelines"></a><span data-ttu-id="839ba-103">종속성 주입 지침</span><span class="sxs-lookup"><span data-stu-id="839ba-103">Dependency injection guidelines</span></span>

<span data-ttu-id="839ba-104">이 문서에서는 .NET 애플리케이션에서 종속성 주입을 구현하기 위한 일반적인 지침 및 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-104">This article provides general guidelines and best practices for implementing dependency injection in .NET applications.</span></span>

## <a name="design-services-for-dependency-injection"></a><span data-ttu-id="839ba-105">종속성 주입을 위한 서비스 디자인</span><span class="sxs-lookup"><span data-stu-id="839ba-105">Design services for dependency injection</span></span>

<span data-ttu-id="839ba-106">종속성 주입을 위한 서비스를 디자인하는 경우</span><span class="sxs-lookup"><span data-stu-id="839ba-106">When designing services for dependency injection:</span></span>

- <span data-ttu-id="839ba-107">상태 저장 정적 클래스 및 멤버를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-107">Avoid stateful, static classes and members.</span></span> <span data-ttu-id="839ba-108">대신 싱글톤 서비스를 사용하도록 앱을 설계하여 전역 상태를 만들지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-108">Avoid creating global state by designing apps to use singleton services instead.</span></span>
- <span data-ttu-id="839ba-109">서비스 내의 종속 클래스를 직접 인스턴스화하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-109">Avoid direct instantiation of dependent classes within services.</span></span> <span data-ttu-id="839ba-110">직접 인스턴스화는 코드를 특정 구현에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-110">Direct instantiation couples the code to a particular implementation.</span></span>
- <span data-ttu-id="839ba-111">서비스를 작고 잘 구성되고 쉽게 테스트할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-111">Make services small, well-factored, and easily tested.</span></span>

<span data-ttu-id="839ba-112">클래스에 주입된 종속성이 많은 경우 클래스가 역할이 너무 많고 [SRP(단일 책임 원칙)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility)을 위반하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-112">If a class has many injected dependencies, it might be a sign that the class has too many responsibilities and violates the [Single Responsibility Principle (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility).</span></span> <span data-ttu-id="839ba-113">해당 책임 몇 가지를 새로운 클래스로 이동하여 클래스를 리팩터링해 보세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-113">Attempt to refactor the class by moving some of its responsibilities into new classes.</span></span>

### <a name="disposal-of-services"></a><span data-ttu-id="839ba-114">서비스 삭제</span><span class="sxs-lookup"><span data-stu-id="839ba-114">Disposal of services</span></span>

<span data-ttu-id="839ba-115">컨테이너는 자신이 만든 형식을 정리하며 <xref:System.IDisposable> 인스턴스에서 <xref:System.IDisposable.Dispose%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-115">The container is responsible for cleanup of types it creates, and calls <xref:System.IDisposable.Dispose%2A> on <xref:System.IDisposable> instances.</span></span> <span data-ttu-id="839ba-116">개발자는 컨테이너에서 확인된 서비스는 삭제해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-116">Services resolved from the container should never be disposed by the developer.</span></span> <span data-ttu-id="839ba-117">형식 또는 팩터리가 싱글톤으로 등록된 경우 컨테이너에서 싱글톤을 자동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-117">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="839ba-118">다음 예제에서는 서비스가 서비스 컨테이너에 의해 만들어지고 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-118">In the following example, the services are created by the service container and disposed automatically:</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

<span data-ttu-id="839ba-119">위의 삭제 가능한 형식은 임시 수명을 갖도록 만들어진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-119">The preceding disposable is intended to have a transient lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

<span data-ttu-id="839ba-120">위의 삭제 가능한 형식은 범위가 지정된 수명을 갖도록 만들어진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-120">The preceding disposable is intended to have a scoped lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

<span data-ttu-id="839ba-121">위의 삭제 가능한 형식은 싱글톤 수명을 갖도록 만들어진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-121">The preceding disposable is intended to have a singleton lifetime.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60" highlight="":::

<span data-ttu-id="839ba-122">디버그 콘솔은 실행 후 다음 샘플 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-122">The debug console shows the following sample output after running:</span></span>

```console
Scope 1...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

Scope 2...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

info: Microsoft.Hosting.Lifetime[0]
      Application started.Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
     Hosting environment: Production
info: Microsoft.Hosting.Lifetime[0]
     Content root path: .\configuration\console-di-disposable\bin\Debug\net5.0
info: Microsoft.Hosting.Lifetime[0]
     Application is shutting down...
SingletonDisposable.Dispose()
```

### <a name="services-not-created-by-the-service-container"></a><span data-ttu-id="839ba-123">서비스 컨테이너에서 만들지 않은 서비스</span><span class="sxs-lookup"><span data-stu-id="839ba-123">Services not created by the service container</span></span>

<span data-ttu-id="839ba-124">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-124">Consider the following code:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

<span data-ttu-id="839ba-125">위의 코드에서</span><span class="sxs-lookup"><span data-stu-id="839ba-125">In the preceding code:</span></span>

- <span data-ttu-id="839ba-126">`ExampleService` 인스턴스가 서비스 컨테이너에서 만들어지지 **않았습니다**.</span><span class="sxs-lookup"><span data-stu-id="839ba-126">The `ExampleService` instance is **not** created by the service container.</span></span>
- <span data-ttu-id="839ba-127">프레임워크가 서비스를 자동으로 삭제하지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="839ba-127">The framework does **not** dispose of the services automatically.</span></span>
- <span data-ttu-id="839ba-128">개발자가 서비스 삭제를 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-128">The developer is responsible for disposing the services.</span></span>

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a><span data-ttu-id="839ba-129">임시 및 공유 인스턴스에 대한 IDisposable 지침</span><span class="sxs-lookup"><span data-stu-id="839ba-129">IDisposable guidance for Transient and shared instances</span></span>

#### <a name="transient-limited-lifetime"></a><span data-ttu-id="839ba-130">임시적인 제한 수명</span><span class="sxs-lookup"><span data-stu-id="839ba-130">Transient, limited lifetime</span></span>

<span data-ttu-id="839ba-131">**시나리오**</span><span class="sxs-lookup"><span data-stu-id="839ba-131">**Scenario**</span></span>

<span data-ttu-id="839ba-132">앱에는 다음 시나리오 중 하나에 대해 임시 수명으로 <xref:System.IDisposable> 인스턴스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-132">The app requires an <xref:System.IDisposable> instance with a transient lifetime for either of the following scenarios:</span></span>

- <span data-ttu-id="839ba-133">인스턴스가 루트 범위(루트 컨테이너)에서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-133">The instance is resolved in the root scope (root container).</span></span>
- <span data-ttu-id="839ba-134">범위가 끝나기 전에 인스턴스를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-134">The instance should be disposed before the scope ends.</span></span>

<span data-ttu-id="839ba-135">**해결 방법**</span><span class="sxs-lookup"><span data-stu-id="839ba-135">**Solution**</span></span>

<span data-ttu-id="839ba-136">부모 범위 밖에서 인스턴스를 생성하려면 팩터리 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-136">Use the factory pattern to create an instance outside of the parent scope.</span></span> <span data-ttu-id="839ba-137">이 경우 앱에는 일반적으로 최종 형식의 생성자를 직접 호출하는 `Create` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-137">In this situation, the app would generally have a `Create` method that calls the final type's constructor directly.</span></span> <span data-ttu-id="839ba-138">최종 형식에 다른 종속성이 있는 경우 팩터리는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-138">If the final type has other dependencies, the factory can:</span></span>

- <span data-ttu-id="839ba-139">해당 생성자에서 <xref:System.IServiceProvider>을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-139">Receive an <xref:System.IServiceProvider> in its constructor.</span></span>
- <span data-ttu-id="839ba-140">해당 종속성에서 컨테이너를 사용하는 동안 컨테이너 외부의 인스턴스를 인스턴스화하기 위해 <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-140">Use <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> to instantiate the instance outside of the container, while using the container for its dependencies.</span></span>

#### <a name="shared-instance-limited-lifetime"></a><span data-ttu-id="839ba-141">공유 인스턴스 및 제한 수명</span><span class="sxs-lookup"><span data-stu-id="839ba-141">Shared instance, limited lifetime</span></span>

<span data-ttu-id="839ba-142">**시나리오**</span><span class="sxs-lookup"><span data-stu-id="839ba-142">**Scenario**</span></span>

<span data-ttu-id="839ba-143">앱은 여러 서비스에서 공유 <xref:System.IDisposable> 인스턴스가 필요하지만 <xref:System.IDisposable> 인스턴스는 수명이 제한되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-143">The app requires a shared <xref:System.IDisposable> instance across multiple services, but the <xref:System.IDisposable> instance should have a limited lifetime.</span></span>

<span data-ttu-id="839ba-144">**해결 방법**</span><span class="sxs-lookup"><span data-stu-id="839ba-144">**Solution**</span></span>

<span data-ttu-id="839ba-145">인스턴스를 범위가 지정된 수명으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-145">Register the instance with a scoped lifetime.</span></span> <span data-ttu-id="839ba-146"><xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType>을 사용하여 새 <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-146">Use <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> to create a new <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>.</span></span> <span data-ttu-id="839ba-147">범위의 <xref:System.IServiceProvider>를 사용하여 필요한 서비스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-147">Use the scope's <xref:System.IServiceProvider> to get required services.</span></span> <span data-ttu-id="839ba-148">더 이상 필요하지 않은 범위를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-148">Dispose the scope when it's no longer needed.</span></span>

#### <a name="general-idisposable-guidelines"></a><span data-ttu-id="839ba-149">일반 `IDisposable` 지침</span><span class="sxs-lookup"><span data-stu-id="839ba-149">General `IDisposable` guidelines</span></span>

- <span data-ttu-id="839ba-150">임시 수명에 <xref:System.IDisposable> 인스턴스를 등록하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-150">Don't register <xref:System.IDisposable> instances with a transient lifetime.</span></span> <span data-ttu-id="839ba-151">대신 팩터리 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-151">Use the factory pattern instead.</span></span>
- <span data-ttu-id="839ba-152">루트 범위에서 임시 또는 범위가 지정된 수명으로 <xref:System.IDisposable> 인스턴스를 확인하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-152">Don't resolve <xref:System.IDisposable> instances with a transient or scoped lifetime in the root scope.</span></span> <span data-ttu-id="839ba-153">앱이 <xref:System.IServiceProvider>를 생성/재생성 및 삭제하는 경우만 예외이지만, 이상적인 패턴이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-153">The only exception to this is if the app creates/recreates and disposes <xref:System.IServiceProvider>, but this isn't an ideal pattern.</span></span>
- <span data-ttu-id="839ba-154">DI를 통한 <xref:System.IDisposable> 종속성 수신은 수신자가 자체적으로 <xref:System.IDisposable>를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-154">Receiving an <xref:System.IDisposable> dependency via DI doesn't require that the receiver implement <xref:System.IDisposable> itself.</span></span> <span data-ttu-id="839ba-155"><xref:System.IDisposable> 종속성의 수신자는 해당 종속성에서 <xref:System.IDisposable.Dispose%2A>를 호출하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-155">The receiver of the <xref:System.IDisposable> dependency shouldn't call <xref:System.IDisposable.Dispose%2A> on that dependency.</span></span>
- <span data-ttu-id="839ba-156">범위를 사용하여 서비스 수명을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-156">Use scopes to control the lifetimes of services.</span></span> <span data-ttu-id="839ba-157">범위는 계층적이지 않으며 범위 간 특수 연결이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-157">Scopes aren't hierarchical, and there's no special connection among scopes.</span></span>

<span data-ttu-id="839ba-158">리소스 정리에 대한 자세한 내용은 [`Dispose` 메서드 구현](../../standard/garbage-collection/implementing-dispose.md)또는 [`DisposeAsync` 메서드 구현](../../standard/garbage-collection/implementing-disposeasync.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-158">For more information on resource cleanup, see [Implement a `Dispose` method](../../standard/garbage-collection/implementing-dispose.md), or [Implement a `DisposeAsync` method](../../standard/garbage-collection/implementing-disposeasync.md).</span></span> <span data-ttu-id="839ba-159">또한 리소스 정리와 관련하여 [컨테이너가 삭제 가능한 임시 서비스를 캡처](#disposable-transient-services-captured-by-container) 시나리오를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-159">Additionally, consider the [Disposable transient services captured by container](#disposable-transient-services-captured-by-container) scenario as it relates to resource cleanup.</span></span>

## <a name="default-service-container-replacement"></a><span data-ttu-id="839ba-160">기본 서비스 컨테이너 바꾸기</span><span class="sxs-lookup"><span data-stu-id="839ba-160">Default service container replacement</span></span>

<span data-ttu-id="839ba-161">기본 제공 서비스 컨테이너는 프레임워크 및 대부분의 소비자 앱의 요구를 충족하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-161">The built-in service container is designed to serve the needs of the framework and most consumer apps.</span></span> <span data-ttu-id="839ba-162">다음과 같이 지원하지 않는 특정 기능이 필요하지 않는 한 기본 제공 컨테이너를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-162">We recommend using the built-in container unless you need a specific feature that it doesn't support, such as:</span></span>

- <span data-ttu-id="839ba-163">속성 삽입</span><span class="sxs-lookup"><span data-stu-id="839ba-163">Property injection</span></span>
- <span data-ttu-id="839ba-164">이름에 기반한 삽입</span><span class="sxs-lookup"><span data-stu-id="839ba-164">Injection based on name</span></span>
- <span data-ttu-id="839ba-165">자식 컨테이너</span><span class="sxs-lookup"><span data-stu-id="839ba-165">Child containers</span></span>
- <span data-ttu-id="839ba-166">사용자 지정 수명 관리</span><span class="sxs-lookup"><span data-stu-id="839ba-166">Custom lifetime management</span></span>
- <span data-ttu-id="839ba-167">초기화 지연에 대한 `Func<T>` 지원</span><span class="sxs-lookup"><span data-stu-id="839ba-167">`Func<T>` support for lazy initialization</span></span>
- <span data-ttu-id="839ba-168">규칙 기반 등록</span><span class="sxs-lookup"><span data-stu-id="839ba-168">Convention-based registration</span></span>

<span data-ttu-id="839ba-169">ASP.NET Core 앱에서 사용할 수 있는 타사 컨테이너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-169">The following third-party containers can be used with ASP.NET Core apps:</span></span>

- [<span data-ttu-id="839ba-170">Autofac</span><span class="sxs-lookup"><span data-stu-id="839ba-170">Autofac</span></span>](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [<span data-ttu-id="839ba-171">DryIoc</span><span class="sxs-lookup"><span data-stu-id="839ba-171">DryIoc</span></span>](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [<span data-ttu-id="839ba-172">유예</span><span class="sxs-lookup"><span data-stu-id="839ba-172">Grace</span></span>](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [<span data-ttu-id="839ba-173">LightInject</span><span class="sxs-lookup"><span data-stu-id="839ba-173">LightInject</span></span>](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [<span data-ttu-id="839ba-174">Lamar</span><span class="sxs-lookup"><span data-stu-id="839ba-174">Lamar</span></span>](https://jasperfx.github.io/lamar/)
- [<span data-ttu-id="839ba-175">Stashbox</span><span class="sxs-lookup"><span data-stu-id="839ba-175">Stashbox</span></span>](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [<span data-ttu-id="839ba-176">Unity</span><span class="sxs-lookup"><span data-stu-id="839ba-176">Unity</span></span>](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a><span data-ttu-id="839ba-177">스레드로부터의 안전성</span><span class="sxs-lookup"><span data-stu-id="839ba-177">Thread safety</span></span>

<span data-ttu-id="839ba-178">스레드로부터 안전한 싱글톤 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-178">Create thread-safe singleton services.</span></span> <span data-ttu-id="839ba-179">싱글톤 서비스가 Transient 서비스에 대한 종속성을 갖는 경우 Transient 서비스는 싱글톤에서 사용되는 방식에 따라 스레드 보안이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-179">If a singleton service has a dependency on a transient service, the transient service may also require thread safety depending on how it's used by the singleton.</span></span>

<span data-ttu-id="839ba-180">[AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A)의 두 번째 인수와 같은 싱글톤 서비스의 팩터리 메서드는 스레드로부터 안전하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-180">The factory method of a singleton service, such as the second argument to [AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), doesn't need to be thread-safe.</span></span> <span data-ttu-id="839ba-181">형식(`static`) 생성자와 같이 이 메서드는 단일 스레드에서 한 번만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-181">Like a type (`static`) constructor, it's guaranteed to be called only once by a single thread.</span></span>

## <a name="recommendations"></a><span data-ttu-id="839ba-182">권장 사항</span><span class="sxs-lookup"><span data-stu-id="839ba-182">Recommendations</span></span>

- <span data-ttu-id="839ba-183">`async/await` 및 `Task` 기반 서비스 확인은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-183">`async/await` and `Task` based service resolution isn't supported.</span></span> <span data-ttu-id="839ba-184">C#은 비동기 생성자를 지원하지 않으므로, 서비스를 동기식으로 확인한 후 비동기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-184">Because C# doesn't support asynchronous constructors, use asynchronous methods after synchronously resolving the service.</span></span>
- <span data-ttu-id="839ba-185">데이터 및 구성을 서비스 컨테이너에 직접 저장하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-185">Avoid storing data and configuration directly in the service container.</span></span> <span data-ttu-id="839ba-186">예를 들어 사용자의 쇼핑 카트는 일반적으로 서비스 컨테이너에 추가하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-186">For example, a user's shopping cart shouldn't typically be added to the service container.</span></span> <span data-ttu-id="839ba-187">구성은 옵션 패턴을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-187">Configuration should use the options pattern.</span></span> <span data-ttu-id="839ba-188">마찬가지로 다른 개체에 대한 액세스를 허용하기 위해서만 존재하는 “데이터 보유자” 개체를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-188">Similarly, avoid "data holder" objects that only exist to allow access to another object.</span></span> <span data-ttu-id="839ba-189">DI를 통해 실제 항목을 요청하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-189">It's better to request the actual item via DI.</span></span>
- <span data-ttu-id="839ba-190">서비스에 정적 액세스를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="839ba-190">Avoid static access to services.</span></span> <span data-ttu-id="839ba-191">예를 들어 다른 곳에 사용하기 위해 [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices)를 정적 필드 또는 속성으로 캡처하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-191">For example, avoid capturing [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) as a static field or property for use elsewhere.</span></span>
- <span data-ttu-id="839ba-192">[DI 팩터리](#async-di-factories-can-cause-deadlocks)를 빠르고 동기식으로 유지하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-192">Keep [DI factories](#async-di-factories-can-cause-deadlocks) fast and synchronous.</span></span>
- <span data-ttu-id="839ba-193">[‘서비스 로케이터 패턴’](#scoped-service-as-singleton)을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-193">Avoid using the [*service locator pattern*](#scoped-service-as-singleton).</span></span> <span data-ttu-id="839ba-194">예를 들어 DI를 대신 사용할 수 있는 경우 서비스 인스턴스를 가져오기 위해 <xref:System.IServiceProvider.GetService%2A>를 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-194">For example, don't invoke <xref:System.IServiceProvider.GetService%2A> to obtain a service instance when you can use DI instead.</span></span>
- <span data-ttu-id="839ba-195">피해야 하는 또 다른 서비스 로케이터 변형은 런타임에 종속성을 해결하는 팩터리를 주입하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-195">Another service locator variation to avoid is injecting a factory that resolves dependencies at runtime.</span></span> <span data-ttu-id="839ba-196">이러한 두 가지 방법 모두 [제어 반전](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) 전략을 혼합합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-196">Both of these practices mix [Inversion of Control](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion) strategies.</span></span>
- <span data-ttu-id="839ba-197">`ConfigureServices`에서 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>를 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-197">Avoid calls to <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> in `ConfigureServices`.</span></span> <span data-ttu-id="839ba-198">일반적으로 `BuildServiceProvider`는 개발자가 `ConfigureServices`에서 서비스를 해결하려는 경우 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-198">Calling `BuildServiceProvider` typically happens when the developer wants to resolve a service in `ConfigureServices`.</span></span>
- <span data-ttu-id="839ba-199">컨테이너가 삭제를 위해 [삭제 가능한 임시 서비스를 캡처](#disposable-transient-services-captured-by-container)합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-199">[Disposable transient services are captured](#disposable-transient-services-captured-by-container) by the container for disposal.</span></span> <span data-ttu-id="839ba-200">따라서 최상위 컨테이너에서 해결할 경우 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-200">This can turn into a memory leak if resolved from the top-level container.</span></span>
- <span data-ttu-id="839ba-201">범위 유효성 검사를 사용하여 범위가 지정된 서비스를 캡처하는 싱글톤이 앱에 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-201">Enable scope validation to make sure the app doesn't have singletons that capture scoped services.</span></span> <span data-ttu-id="839ba-202">자세한 내용은 [범위 유효성 검사](dependency-injection.md#scope-validation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-202">For more information, see [Scope validation](dependency-injection.md#scope-validation).</span></span>

<span data-ttu-id="839ba-203">모든 권장 사항과 마찬가지로, 권장 사항을 무시해야 하는 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-203">Like all sets of recommendations, you may encounter situations where ignoring a recommendation is required.</span></span> <span data-ttu-id="839ba-204">예외는 드물게 발생하며 대부분 프레임워크 자체 내에서 특별한 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-204">Exceptions are rare, mostly special cases within the framework itself.</span></span>

<span data-ttu-id="839ba-205">DI는 정적/전역 개체 액세스 패턴의 ‘대안’입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-205">DI is an *alternative* to static/global object access patterns.</span></span> <span data-ttu-id="839ba-206">고정 개체 액세스와 함께 사용할 경우 DI의 장점을 실현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-206">You may not be able to realize the benefits of DI if you mix it with static object access.</span></span>

## <a name="example-anti-patterns"></a><span data-ttu-id="839ba-207">안티 패턴 예제</span><span class="sxs-lookup"><span data-stu-id="839ba-207">Example anti-patterns</span></span>

<span data-ttu-id="839ba-208">이 문서의 지침 외에 ‘**지양** 해야 할’ 몇 가지 안티 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-208">In addition to the guidelines in this article, there are several anti-patterns *you **should** avoid*.</span></span> <span data-ttu-id="839ba-209">이러한 안티 패턴 중 일부는 런타임 자체를 개발하면서 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-209">Some of these anti-patterns are learnings from developing the runtimes themselves.</span></span>

> [!WARNING]
> <span data-ttu-id="839ba-210">다음은 안티 패턴 예제입니다. 코드를 복사하지 ‘말고’ 이러한 패턴을 사용하지 ‘않으며’ 어떤 경우에도 이러한 패턴을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-210">These are example anti-patterns, *do not* copy the code, *do not* use these patterns, and avoid these patterns at all costs.</span></span>

### <a name="disposable-transient-services-captured-by-container"></a><span data-ttu-id="839ba-211">컨테이너가 삭제 가능한 임시 서비스를 캡처</span><span class="sxs-lookup"><span data-stu-id="839ba-211">Disposable transient services captured by container</span></span>

<span data-ttu-id="839ba-212"><xref:System.IDisposable>을 구현하는 ‘임시’ 서비스를 등록하는 경우 기본적으로 DI 컨테이너는 이러한 참조를 유지하고 컨테이너에서 확인된 경우 애플리케이션이 중지하여 컨테이너가 삭제될 때까지 또는 범위에서 확인된 경우 범위가 삭제될 때까지는 <xref:System.IDisposable.Dispose>하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-212">When you register *Transient* services that implement <xref:System.IDisposable>, by default the DI container will hold onto these references, and not <xref:System.IDisposable.Dispose> of them until the container is disposed when application stops if they were resolved from the container, or until the scope is disposed if they were resolved from a scope.</span></span> <span data-ttu-id="839ba-213">따라서 컨테이너 수준에서 확인할 경우 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-213">This can turn into a memory leak if resolved from container level.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="18-30":::

<span data-ttu-id="839ba-214">위의 안티 패턴에서는 1,000개의 `ExampleDisposable` 개체가 인스턴스화되고 루팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-214">In the preceding anti-pattern, 1,000 `ExampleDisposable` objects are instantiated and rooted.</span></span> <span data-ttu-id="839ba-215">이들은 `serviceProvider` 인스턴스가 삭제될 때까지 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-215">They will not be disposed of until the `serviceProvider` instance is disposed.</span></span>

<span data-ttu-id="839ba-216">메모리 누수를 디버깅하는 방법에 대한 자세한 내용은 [.NET에서 메모리 누수 디버깅](../diagnostics/debug-memory-leak.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-216">For more information on debugging memory leaks, see [Debug a memory leak in .NET](../diagnostics/debug-memory-leak.md).</span></span>

### <a name="async-di-factories-can-cause-deadlocks"></a><span data-ttu-id="839ba-217">비동기 DI 팩터리에서 교착 상태가 발생할 수 있음</span><span class="sxs-lookup"><span data-stu-id="839ba-217">Async DI factories can cause deadlocks</span></span>

<span data-ttu-id="839ba-218">‘DI 팩터리’라는 용어는 `Add{LIFETIME}`을 호출할 때 존재하는 오버로드 메서드를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-218">The term "DI factories" refers to the overload methods that exist when calling `Add{LIFETIME}`.</span></span> <span data-ttu-id="839ba-219">`Func<IServiceProvider, T>`를 허용하는 오버로드가 있습니다. 여기서 `T`는 등록할 서비스이고, 매개 변수 이름은 `implementationFactory`입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-219">There are overloads accepting a `Func<IServiceProvider, T>` where `T` is the service being registered, and the parameter is named `implementationFactory`.</span></span> <span data-ttu-id="839ba-220">`implementationFactory`는 람다 식, 로컬 함수 또는 메서드로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-220">The `implementationFactory` can be provided as a lambda expression, local function, or method.</span></span> <span data-ttu-id="839ba-221">팩터리가 비동기식이고 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>를 사용하는 경우 교착 상태가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-221">If the factory is asynchronous, and you use <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>, this will cause a deadlock.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="32-45" highlight="4-8":::

<span data-ttu-id="839ba-222">위의 코드에서는 `implementationFactory`에 본문이 `Task<Bar>` 반환 메서드에서 <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>를 호출하는 람다 식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-222">In the preceding code, the `implementationFactory` is given a lambda expression where the body calls <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> on a `Task<Bar>` returning method.</span></span> <span data-ttu-id="839ba-223">이로 인해 ‘교착 상태가 발생’합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-223">This ***causes a deadlock***.</span></span> <span data-ttu-id="839ba-224">`GetBarAsync` 메서드는 단순히 <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>를 사용하여 비동기 작업을 에뮬레이트한 다음 <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-224">The `GetBarAsync` method simply emulates an asynchronous work operation with <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>, and then calls <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)>.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="47-53":::

<span data-ttu-id="839ba-225">비동기 지침에 대한 자세한 내용은 [비동기 프로그래밍: 중요 정보 및 조언](../../csharp/async.md#important-info-and-advice)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-225">For more information on asynchronous guidance, see [Asynchronous programming: Important info and advice](../../csharp/async.md#important-info-and-advice).</span></span> <span data-ttu-id="839ba-226">교착 상태 디버깅에 대한 자세한 내용은 [.NET에서 교착 상태 디버깅](../diagnostics/debug-deadlock.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-226">For more information debugging deadlocks, see [Debug a deadlock in .NET](../diagnostics/debug-deadlock.md).</span></span>

<span data-ttu-id="839ba-227">이 안티 패턴을 실행 중이고 교착 상태가 발생하는 경우 Visual Studio의 병렬 스택 창에서 두 개의 스레드가 대기하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-227">When you're running this anti-pattern and the deadlock occurs, you can view the two threads waiting from Visual Studio's Parallel Stacks window.</span></span> <span data-ttu-id="839ba-228">자세한 내용은 [병렬 스택 창에서 스레드 및 작업 보기](/visualstudio/debugger/using-the-parallel-stacks-window)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-228">For more information, see [View threads and tasks in the Parallel Stacks window](/visualstudio/debugger/using-the-parallel-stacks-window).</span></span>

### <a name="captive-dependency"></a><span data-ttu-id="839ba-229">조임 종속성</span><span class="sxs-lookup"><span data-stu-id="839ba-229">Captive dependency</span></span>

<span data-ttu-id="839ba-230">[‘조임 종속성’](https://blog.ploeh.dk/2014/06/02/captive-dependency)은 [Mark Seeman](https://blog.ploeh.dk/about)이 만든 용어로, 수명이 긴 서비스에서 수명이 짧은 서비스를 보유하는 잘못된 서비스 수명 구성을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-230">The term ["captive dependency"](https://blog.ploeh.dk/2014/06/02/captive-dependency) was coined by [Mark Seeman](https://blog.ploeh.dk/about), and refers to the misconfiguration of service lifetimes, where a longer-lived service holds a shorter-lived service captive.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="55-65":::

<span data-ttu-id="839ba-231">위의 코드에서 `Foo`는 싱글톤으로 등록되고 `Bar`는 범위가 지정되는데, 표면적으로는 유효한 것으로 보입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-231">In the preceding code, `Foo` is registered as a singleton and `Bar` is scoped - which on the surface seems valid.</span></span> <span data-ttu-id="839ba-232">그러나 `Foo`의 구현을 생각해보세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-232">However, consider the implementation of `Foo`.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Foo.cs" highlight="5":::

<span data-ttu-id="839ba-233">`Foo` 개체에는 `Bar` 개체가 필요하며, `Foo`는 싱글톤이고 `Bar`는 범위가 지정되므로 이는 잘못된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-233">The `Foo` object requires a `Bar` object, and since `Foo` is a singleton, and `Bar` is scoped - this is a misconfiguration.</span></span> <span data-ttu-id="839ba-234">`Foo`가 한 번만 인스턴스화되고 해당 수명 동안 `Bar`를 유지해야 하는데 이 수명이 `Bar`의 의도된 범위가 지정된 수명보다 길기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-234">As is, `Foo` would only be instantiated once, and it would hold onto `Bar` for its lifetime, which is longer than the intended scoped lifetime of `Bar`.</span></span> <span data-ttu-id="839ba-235">`validateScopes: true`를 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)>에 전달하여 범위 유효성 검사를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-235">You should consider validating scopes, by passing `validateScopes: true` to the <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)>.</span></span> <span data-ttu-id="839ba-236">범위의 유효성을 검사할 때 "싱글톤 'Foo'에서 범위가 지정된 서비스 'Bar'를 사용할 수 없음"과 비슷한 메시지가 포함된 <xref:System.InvalidOperationException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-236">When you validate the scopes, you'd get an <xref:System.InvalidOperationException> with a message similar to "Cannot consume scoped service 'Bar' from singleton 'Foo'.".</span></span>

<span data-ttu-id="839ba-237">자세한 내용은 [범위 유효성 검사](dependency-injection.md#scope-validation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839ba-237">For more information, see [Scope validation](dependency-injection.md#scope-validation).</span></span>

### <a name="scoped-service-as-singleton"></a><span data-ttu-id="839ba-238">범위가 지정된 서비스를 싱글톤으로</span><span class="sxs-lookup"><span data-stu-id="839ba-238">Scoped service as singleton</span></span>

<span data-ttu-id="839ba-239">범위가 지정된 서비스를 사용할 때 범위를 만들지 않거나 기존 범위 안에 들어가는 경우 해당 서비스는 싱글톤이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-239">When using scoped services, if you're not creating a scope or within an existing scope - the service becomes a singleton.</span></span>

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="68-82" highlight="13-14":::

<span data-ttu-id="839ba-240">위의 코드에서는 `Bar`가 <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> 내에서 검색되며 이는 올바른 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-240">In the preceding code, `Bar` is retrieved within an <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>, which is correct.</span></span> <span data-ttu-id="839ba-241">안티 패턴은 범위 밖에서 `Bar`를 검색하는 것입니다. 예제 검색이 잘못된 패턴임을 표시하기 위해 변수의 이름이 `avoid`로 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839ba-241">The anti-pattern is the retrieval of `Bar` outside of the scope, and the variable is named `avoid` to show which example retrieval is incorrect.</span></span>

## <a name="see-also"></a><span data-ttu-id="839ba-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="839ba-242">See also</span></span>

- [<span data-ttu-id="839ba-243">.NET에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="839ba-243">Dependency injection in .NET</span></span>](dependency-injection.md)
- [<span data-ttu-id="839ba-244">자습서: .NET에서 종속성 주입 사용</span><span class="sxs-lookup"><span data-stu-id="839ba-244">Tutorial: Use dependency injection in .NET</span></span>](dependency-injection-usage.md)
