---
title: .NET 라이브러리 작성자를 위한 옵션 패턴 지침
author: IEvangelist
description: .NET 라이브러리 작성자로서 옵션 패턴을 노출하는 방법을 알아봅니다.
ms.author: dapine
ms.date: 01/28/2021
ms.openlocfilehash: d0da94a8f25c9e5aba6093fab07ccca6a0a7c345
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "102402140"
---
# <a name="options-pattern-guidance-for-net-library-authors"></a><span data-ttu-id="c5c4f-103">.NET 라이브러리 작성자를 위한 옵션 패턴 지침</span><span class="sxs-lookup"><span data-stu-id="c5c4f-103">Options pattern guidance for .NET library authors</span></span>

<span data-ttu-id="c5c4f-104">종속성 주입의 도움으로 서비스 및 해당 구성을 등록하면 ‘옵션 패턴’을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-104">With the help of dependency injection, registering your services and their corresponding configurations can make use of the *options pattern*.</span></span> <span data-ttu-id="c5c4f-105">옵션 패턴을 사용하면 라이브러리(및 서비스)의 소비자가 [옵션 인터페이스](options.md#options-interfaces) 인스턴스를 요구할 수 있습니다. 여기서 `TOptions`는 옵션 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-105">The options pattern enables consumers of your library (and your services) to require instances of [options interfaces](options.md#options-interfaces) where `TOptions` is your options class.</span></span> <span data-ttu-id="c5c4f-106">강력한 형식의 개체를 통해 구성 옵션을 사용하면 일관된 값 표시가 보장되고 문자열 값을 수동으로 구문 분석하는 부담이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-106">Consuming configuration options through strongly-typed objects helps to ensure consistent value representation, and removes the burden of manually parsing string values.</span></span> <span data-ttu-id="c5c4f-107">라이브러리의 소비자가 사용할 수 있는 [구성 공급자](configuration-providers.md)가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-107">There are many [configuration providers](configuration-providers.md) for consumers of your library to use.</span></span> <span data-ttu-id="c5c4f-108">이러한 공급자를 통해 소비자는 여러 방법으로 라이브러리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-108">With these providers, consumers can configure your library in many ways.</span></span>

<span data-ttu-id="c5c4f-109">이 문서에서는 .NET 라이브러리 작성자가 라이브러리의 소비자에게 옵션 패턴을 올바르게 노출하는 방법에 대한 일반적인 지침을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-109">As a .NET library author, you'll learn general guidance on how to correctly expose the options pattern to consumers of your library.</span></span> <span data-ttu-id="c5c4f-110">여러 방법으로 동일한 목적을 달성할 수 있으며 몇 가지 고려할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-110">There are various ways to achieve the same thing, and several considerations to make.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="c5c4f-111">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="c5c4f-111">Naming conventions</span></span>

<span data-ttu-id="c5c4f-112">규칙에 따라 서비스 등록을 담당하는 확장 메서드는 이름이 `Add{Service}`로 지정됩니다. 여기서 `{Service}`는 의미 있고 설명이 포함된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-112">By convention, extension methods responsible for registering services are named `Add{Service}`, where `{Service}` is a meaningful and descriptive name.</span></span> <span data-ttu-id="c5c4f-113">패키지에 따라 서비스 등록에 `Use{Service}` 확장 메서드가 함께 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-113">Depending on the package, the registration of services may be accompanied by `Use{Service}` extension methods.</span></span> <span data-ttu-id="c5c4f-114">`Use{Service}` 확장 메서드는 [ASP.NET Core](/aspnet)에서 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-114">The `Use{Service}` extension methods are commonplace in [ASP.NET Core](/aspnet).</span></span>

<span data-ttu-id="c5c4f-115">✔️ 서비스를 다른 제품과 명확하게 구분하는 이름을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-115">✔️ CONSIDER names that disambiguate your service from other offerings.</span></span>

<span data-ttu-id="c5c4f-116">❌ 공식 Microsoft 패키지의 .NET 에코시스템에 이미 포함된 이름은 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-116">❌ DO NOT use names that are already part of the .NET ecosystem from official Microsoft packages.</span></span>

<span data-ttu-id="c5c4f-117">✔️ 확장 메서드를 노출하는 정적 클래스의 이름을 `{Type}Extensions`로 지정하는 것이 좋습니다. 여기서 `{Type}`는 확장하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-117">✔️ CONSIDER naming static classes that expose extension methods as `{Type}Extensions`, where `{Type}` is the type that you're extending.</span></span>

### <a name="namespace-guidance"></a><span data-ttu-id="c5c4f-118">네임스페이스 지침</span><span class="sxs-lookup"><span data-stu-id="c5c4f-118">Namespace guidance</span></span>

<span data-ttu-id="c5c4f-119">Microsoft 패키지는 `Microsoft.Extensions.DependencyInjection` 네임스페이스를 활용하여 다양한 서비스 제품의 등록을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-119">Microsoft packages make use of the `Microsoft.Extensions.DependencyInjection` namespace to unify the registration of various service offerings.</span></span>

<span data-ttu-id="c5c4f-120">✔️ 패키지 제품을 명확하게 식별하는 네임스페이스를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-120">✔️ CONSIDER a namespace that clearly identifies your package offering.</span></span>

<span data-ttu-id="c5c4f-121">❌ 비공식 Microsoft 패키지에 `Microsoft.Extensions.DependencyInjection` 네임스페이스를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-121">❌ DO NOT use the `Microsoft.Extensions.DependencyInjection` namespace for non-official Microsoft packages.</span></span>

## <a name="parameterless"></a><span data-ttu-id="c5c4f-122">매개 변수가 없음</span><span class="sxs-lookup"><span data-stu-id="c5c4f-122">Parameterless</span></span>

<span data-ttu-id="c5c4f-123">서비스를 최소한의 구성으로 또는 명시적 구성 없이 사용할 수 있는 경우에는 매개 변수가 없는 확장 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-123">If your service can work with minimal or no explicit configuration, consider a parameterless extension method.</span></span>

:::code language="csharp" source="snippets/configuration/options-noparams/ServiceCollectionExtensions.cs" highlight="10-14":::

<span data-ttu-id="c5c4f-124">위의 코드에서 `AddMyLibraryService`는</span><span class="sxs-lookup"><span data-stu-id="c5c4f-124">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="c5c4f-125"><xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-125">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="c5c4f-126">`LibraryOptions`의 형식 매개 변수를 사용하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-126">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> with the type parameter of `LibraryOptions`</span></span>
- <span data-ttu-id="c5c4f-127">기본 옵션 값을 지정하는 <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>에 대한 호출을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-127">Chains a call to <xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A>, which specifies the default option values</span></span>

## <a name="iconfiguration-parameter"></a><span data-ttu-id="c5c4f-128">`IConfiguration` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5c4f-128">`IConfiguration` parameter</span></span>

<span data-ttu-id="c5c4f-129">소비자에게 많은 옵션을 노출하는 라이브러리를 작성하는 경우 `IConfiguration` 매개 변수 확장 메서드를 요구하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-129">When you author a library that exposes many options to consumers, you may want to consider requiring an `IConfiguration` parameter extension method.</span></span> <span data-ttu-id="c5c4f-130">필요한 `IConfiguration` 인스턴스는 <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType> 함수를 사용하여 구성의 명명된 섹션으로 범위가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-130">The expected `IConfiguration` instance should be scoped to a named section of the configuration by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A?displayProperty=nameWithType> function.</span></span>

:::code language="csharp" source="snippets/configuration/options-configparam/ServiceCollectionExtensions.cs" highlight="10,12-16":::

<span data-ttu-id="c5c4f-131">위의 코드에서 `AddMyLibraryService`는</span><span class="sxs-lookup"><span data-stu-id="c5c4f-131">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="c5c4f-132"><xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-132">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="c5c4f-133"><xref:Microsoft.Extensions.Configuration.IConfiguration> 매개 변수 `namedConfigurationSection`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-133">Defines an <xref:Microsoft.Extensions.Configuration.IConfiguration> parameter `namedConfigurationSection`</span></span>
- <span data-ttu-id="c5c4f-134"><xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)>를 호출하여 구성이 바인딩되는 옵션 인스턴스를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-134">Calls <xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind(Microsoft.Extensions.Configuration.IConfiguration,System.Object)> passing an options instance that the configuration binds to</span></span>

<span data-ttu-id="c5c4f-135">이 패턴의 소비자는 명명된 섹션의 범위가 지정된 `IConfiguration` 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-135">Consumers in this pattern provide the scoped `IConfiguration` instance of the named section:</span></span>

:::code language="csharp" source="snippets/configuration/options-configparam/Program.cs" highlight="22-23":::

<span data-ttu-id="c5c4f-136">`.AddMyLibraryService`에 대한 호출은 <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A> 메서드에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-136">The call to `.AddMyLibraryService` is made in the <xref:Microsoft.Extensions.Hosting.IHostBuilder.ConfigureServices%2A> method.</span></span> <span data-ttu-id="c5c4f-137">`Startup` 클래스를 사용할 때에도 마찬가지입니다. 등록하는 서비스의 추가가 `ConfigureServices`에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-137">The same is true when using a `Startup` class, the addition of services being registered occurs in `ConfigureServices`.</span></span>

<span data-ttu-id="c5c4f-138">기본값 지정은 라이브러리 작성자가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-138">As the library author, specifying default values is up to you.</span></span>

> [!NOTE]
> <span data-ttu-id="c5c4f-139">구성을 옵션 인스턴스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-139">It is possible to bind configuration to an options instance.</span></span> <span data-ttu-id="c5c4f-140">그러나 이름 충돌 때문에 오류가 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-140">However, there is a risk of name collisions - which will cause errors.</span></span> <span data-ttu-id="c5c4f-141">또한 이렇게 수동으로 바인딩하는 경우 옵션 패턴 소비를 한 번만 읽기로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-141">Additionally, when manually binding in this way, you limit the consumption of your options pattern to read-once.</span></span> <span data-ttu-id="c5c4f-142">이러한 소비자는 [IOptionsMonitor](options.md#ioptionsmonitor) 인터페이스를 사용할 수 없기 때문에 설정 변경 사항이 다시 바인딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-142">Changes to settings will not be re-bound, as such consumers will not be able to use the [IOptionsMonitor](options.md#ioptionsmonitor) interface.</span></span>
>
> ```csharp
> services.AddOptions<LibraryOptions>()
>     .Configure<IConfiguration>(
>         (options, configuration) =>
>             configuration.GetSection("LibraryOptions").Bind(options));
> ```

## <a name="actiontoptions-parameter"></a><span data-ttu-id="c5c4f-143">`Action<TOptions>` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5c4f-143">`Action<TOptions>` parameter</span></span>

<span data-ttu-id="c5c4f-144">라이브러리 소비자가 옵션 클래스의 인스턴스를 생성하는 람다 식을 제공하는 데 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-144">Consumers of your library may be interested in providing a lambda expression that yields an instance of your options class.</span></span> <span data-ttu-id="c5c4f-145">이 시나리오에서는 확장 메서드에서 `Action<LibraryOptions>` 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-145">In this scenario, you define an `Action<LibraryOptions>` parameter in your extension method.</span></span>

:::code language="csharp" source="snippets/configuration/options-action/ServiceCollectionExtensions.cs" highlight="10,12":::

<span data-ttu-id="c5c4f-146">위의 코드에서 `AddMyLibraryService`는</span><span class="sxs-lookup"><span data-stu-id="c5c4f-146">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="c5c4f-147"><xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-147">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="c5c4f-148"><xref:System.Action%601>를 정의합니다. 여기서 `T`는 `LibraryOptions` 매개 변수 `configureOptions`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-148">Defines an <xref:System.Action%601> where `T` is `LibraryOptions` parameter `configureOptions`</span></span>
- <span data-ttu-id="c5c4f-149">`configureOptions` 작업이 지정되면 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-149">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A> given the `configureOptions` action</span></span>

<span data-ttu-id="c5c4f-150">이 패턴의 소비자는 람다 식(또는 `Action<LibraryOptions>` 매개 변수를 충족하는 대리자)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-150">Consumers in this pattern provide a lambda expression (or a delegate that satisfies the `Action<LibraryOptions>` parameter):</span></span>

:::code language="csharp" source="snippets/configuration/options-action/Program.cs" highlight="22-26":::

## <a name="options-instance-parameter"></a><span data-ttu-id="c5c4f-151">옵션 인스턴스 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5c4f-151">Options instance parameter</span></span>

<span data-ttu-id="c5c4f-152">라이브러리 소비자가 인라인 옵션 인스턴스를 제공하는 것을 선호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-152">Consumers of your library might prefer to provide an inlined options instance.</span></span> <span data-ttu-id="c5c4f-153">이 시나리오에서는 옵션 개체 `LibraryOptions`의 인스턴스를 사용하는 확장 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-153">In this scenario, you expose an extension method that takes an instance of your options object, `LibraryOptions`.</span></span>

:::code language="csharp" source="snippets/configuration/options-object/ServiceCollectionExtensions.cs" highlight="9,11-17":::

<span data-ttu-id="c5c4f-154">위의 코드에서 `AddMyLibraryService`는</span><span class="sxs-lookup"><span data-stu-id="c5c4f-154">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="c5c4f-155"><xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-155">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="c5c4f-156">`LibraryOptions`의 형식 매개 변수를 사용하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-156">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%60%601(Microsoft.Extensions.DependencyInjection.IServiceCollection)?displayProperty=nameWithType> with the type parameter of `LibraryOptions`</span></span>
- <span data-ttu-id="c5c4f-157">지정된 `userOptions` 인스턴스에서 재정의할 수 있는 기본 옵션 값을 지정하는 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>에 대한 호출을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-157">Chains a call to <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.Configure%2A>, which specifies default option values that can be overridden from the given `userOptions` instance</span></span>

<span data-ttu-id="c5c4f-158">이 패턴의 소비자는 `LibraryOptions` 클래스의 인스턴스를 제공하여 원하는 속성 값을 인라인으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-158">Consumers in this pattern provide an instance of the `LibraryOptions` class, defining desired property values inline:</span></span>

:::code language="csharp" source="snippets/configuration/options-object/Program.cs" highlight="22-26":::

## <a name="post-configuration"></a><span data-ttu-id="c5c4f-159">구성 후</span><span class="sxs-lookup"><span data-stu-id="c5c4f-159">Post configuration</span></span>

<span data-ttu-id="c5c4f-160">모든 구성 옵션 값을 바인딩하거나 지정한 후에는 사후 구성 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-160">After all configuration option values are bound or specified, post configuration functionality is available.</span></span> <span data-ttu-id="c5c4f-161">앞서 설명한 것과 동일한 [`Action<TOptions>` 매개 변수](#actiontoptions-parameter)를 노출하여 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>를 호출하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-161">Exposing the same [`Action<TOptions>` parameter](#actiontoptions-parameter) detailed earlier, you could choose to call <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>.</span></span> <span data-ttu-id="c5c4f-162">사후 구성은 모든 `.Configure` 호출 후에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-162">Post configure runs after all `.Configure` calls.</span></span>

:::code language="csharp" source="snippets/configuration/options-postconfig/ServiceCollectionExtensions.cs" highlight="10,12":::

<span data-ttu-id="c5c4f-163">위의 코드에서 `AddMyLibraryService`는</span><span class="sxs-lookup"><span data-stu-id="c5c4f-163">In the preceding code, the `AddMyLibraryService`:</span></span>

- <span data-ttu-id="c5c4f-164"><xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>의 인스턴스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-164">Extends an instance of <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection></span></span>
- <span data-ttu-id="c5c4f-165"><xref:System.Action%601>를 정의합니다. 여기서 `T`는 `LibraryOptions` 매개 변수 `configureOptions`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-165">Defines an <xref:System.Action%601> where `T` is `LibraryOptions` parameter `configureOptions`</span></span>
- <span data-ttu-id="c5c4f-166">`configureOptions` 작업이 지정되면 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-166">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigure%2A> given the `configureOptions` action</span></span>

<span data-ttu-id="c5c4f-167">이 패턴의 소비자는 사후 구성을 사용하지 않는 시나리오의 [`Action<TOptions>` 매개 변수]와 마찬가지로 람다 식(또는 `Action<LibraryOptions>` 매개 변수를 충족하는 대리자)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-167">Consumers in this pattern provide a lambda expression (or a delegate that satisfies the `Action<LibraryOptions>` parameter), just as they would with the [`Action<TOptions>` parameter] in a non-post configuration scenario:</span></span>

:::code language="csharp" source="snippets/configuration/options-postconfig/Program.cs" highlight="22-26":::

## <a name="see-also"></a><span data-ttu-id="c5c4f-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5c4f-168">See also</span></span>

- [<span data-ttu-id="c5c4f-169">.NET의 옵션 패턴</span><span class="sxs-lookup"><span data-stu-id="c5c4f-169">Options pattern in .NET</span></span>](options.md)
- [<span data-ttu-id="c5c4f-170">.NET에서 종속성 주입</span><span class="sxs-lookup"><span data-stu-id="c5c4f-170">Dependency injection in .NET</span></span>](dependency-injection.md)
- [<span data-ttu-id="c5c4f-171">종속성 주입 지침</span><span class="sxs-lookup"><span data-stu-id="c5c4f-171">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
