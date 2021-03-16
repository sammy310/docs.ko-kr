---
title: .NET의 옵션 패턴
author: IEvangelist
description: .NET 앱에서 옵션 패턴을 사용하여 관련된 설정의 그룹을 나타내는 방법을 알아봅니다.
ms.author: dapine
ms.date: 02/18/2021
ms.openlocfilehash: df30928cdb1832e94f89abbdf8cc41e1304f8e2e
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102402164"
---
# <a name="options-pattern-in-net"></a><span data-ttu-id="7c75d-103">.NET의 옵션 패턴</span><span class="sxs-lookup"><span data-stu-id="7c75d-103">Options pattern in .NET</span></span>

<span data-ttu-id="7c75d-104">옵션 패턴은 클래스를 사용하여 관련 설정 그룹에 대한 강력한 형식의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-104">The options pattern uses classes to provide strongly-typed access to groups of related settings.</span></span> <span data-ttu-id="7c75d-105">[구성 설정](configuration.md)이 시나리오에 따라 별도 클래스로 격리된 경우 앱은 두 가지 중요한 소프트웨어 엔지니어링 원칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-105">When [configuration settings](configuration.md) are isolated by scenario into separate classes, the app adheres to two important software engineering principles:</span></span>

- <span data-ttu-id="7c75d-106">[ISP(Interface Segregation Principle, 인터페이스 분리 원칙) 또는 캡슐화](../../architecture/modern-web-apps-azure/architectural-principles.md#encapsulation): 구성 설정에 종속된 시나리오(클래스)는 사용하는 구성 설정에 의해서만 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-106">The [Interface Segregation Principle (ISP) or Encapsulation](../../architecture/modern-web-apps-azure/architectural-principles.md#encapsulation): Scenarios (classes) that depend on configuration settings depend only on the configuration settings that they use.</span></span>
- <span data-ttu-id="7c75d-107">[문제의 분리](../../architecture/modern-web-apps-azure/architectural-principles.md#separation-of-concerns) 앱의 다른 부분에 대한 설정은 다른 설정에 종속되거나 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-107">[Separation of Concerns](../../architecture/modern-web-apps-azure/architectural-principles.md#separation-of-concerns): Settings for different parts of the app aren't dependent or coupled to one another.</span></span>

<span data-ttu-id="7c75d-108">옵션은 구성 데이터의 유효성을 검사하는 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-108">Options also provide a mechanism to validate configuration data.</span></span> <span data-ttu-id="7c75d-109">자세한 내용은 [옵션 유효성 검사](#options-validation) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c75d-109">For more information, see the [Options validation](#options-validation) section.</span></span>

## <a name="bind-hierarchical-configuration"></a><span data-ttu-id="7c75d-110">계층적 구성 바인딩</span><span class="sxs-lookup"><span data-stu-id="7c75d-110">Bind hierarchical configuration</span></span>

<span data-ttu-id="7c75d-111">관련 구성 값을 읽는 기본 방법은 옵션 패턴를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-111">The preferred way to read related configuration values is using the options pattern.</span></span> <span data-ttu-id="7c75d-112">옵션 패턴은 제네릭 형식 매개 변수 `TOptions`가 `class`로 제한되는 <xref:Microsoft.Extensions.Options.IOptions%601> 인터페이스를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-112">The options pattern is possible through the <xref:Microsoft.Extensions.Options.IOptions%601> interface, where the generic type parameter `TOptions` is constrained to `class`.</span></span> <span data-ttu-id="7c75d-113">`IOptions<TOptions>`는 나중에 종속성 주입을 통해 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-113">The `IOptions<TOptions>` can later be provided through dependency injection.</span></span> <span data-ttu-id="7c75d-114">자세한 내용은 [.NET에서 종속성 주입](dependency-injection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c75d-114">For more information, see [Dependency injection in .NET](dependency-injection.md).</span></span>

<span data-ttu-id="7c75d-115">예를 들어 다음 구성 값을 읽으려면:</span><span class="sxs-lookup"><span data-stu-id="7c75d-115">For example, to read the following configuration values:</span></span>

:::code language="json" source="snippets/configuration/console-json/appsettings.json" range="3-6":::

<span data-ttu-id="7c75d-116">다음 `TransientFaultHandlingOptions` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-116">Create the following `TransientFaultHandlingOptions` class:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/TransientFaultHandlingOptions.cs" range="5-9":::

<span data-ttu-id="7c75d-117"><span id="options-class"></span> 옵션 패턴을 사용하는 경우 옵션 클래스는</span><span class="sxs-lookup"><span data-stu-id="7c75d-117"><span id="options-class"></span> When using the options pattern, an options class:</span></span>

- <span data-ttu-id="7c75d-118">매개 변수가 없는 공용 생성자를 사용하는 비추상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-118">Must be non-abstract with a public parameterless constructor</span></span>
- <span data-ttu-id="7c75d-119">바인딩할 공용 읽기/쓰기 속성을 포함합니다(필드는 바인딩되지 ‘않음’).</span><span class="sxs-lookup"><span data-stu-id="7c75d-119">Contain public read-write properties to bind (fields are ***not*** bound)</span></span>

<span data-ttu-id="7c75d-120">코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-120">The following code:</span></span>

* <span data-ttu-id="7c75d-121">[ConfigurationBinder.Bind](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind%2A)를 호출하여 `TransientFaultHandlingOptions` 클래스를 `"TransientFaultHandlingOptions"` 섹션에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-121">Calls [ConfigurationBinder.Bind](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Bind%2A) to bind the `TransientFaultHandlingOptions` class to the `"TransientFaultHandlingOptions"` section.</span></span>
* <span data-ttu-id="7c75d-122">구성 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-122">Displays the configuration data.</span></span>

:::code language="csharp" source="snippets/configuration/console-json/Program.cs" range="31-38":::

<span data-ttu-id="7c75d-123">위 코드에서는 앱을 시작한 후 JSON 구성 파일 변경 사항을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-123">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

<span data-ttu-id="7c75d-124">[`ConfigurationBinder.Get<T>`](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Get%2A)는 지정된 형식을 바인딩하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-124">[`ConfigurationBinder.Get<T>`](xref:Microsoft.Extensions.Configuration.ConfigurationBinder.Get%2A) binds and returns the specified type.</span></span> <span data-ttu-id="7c75d-125">`ConfigurationBinder.Get<T>`가 `ConfigurationBinder.Bind`를 사용하는 것보다 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-125">`ConfigurationBinder.Get<T>` may be more convenient than using `ConfigurationBinder.Bind`.</span></span> <span data-ttu-id="7c75d-126">다음 코드에서는 `ConfigurationBinder.Get<T>`와 `TransientFaultHandlingOptions` 클래스를 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-126">The following code shows how to use `ConfigurationBinder.Get<T>` with the `TransientFaultHandlingOptions` class:</span></span>

```csharp
IConfigurationRoot configurationRoot = configuration.Build();

var options =
    configurationRoot.GetSection(nameof(TransientFaultHandlingOptions))
                     .Get<TransientFaultHandlingOptions>();

Console.WriteLine($"TransientFaultHandlingOptions.Enabled={options.Enabled}");
Console.WriteLine($"TransientFaultHandlingOptions.AutoRetryDelay={options.AutoRetryDelay}");
```

<span data-ttu-id="7c75d-127">위 코드에서는 앱을 시작한 후 JSON 구성 파일 변경 사항을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-127">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c75d-128"><xref:Microsoft.Extensions.Configuration.ConfigurationBinder> 클래스는 `.Bind(object instance)` 및 `.Get<T>()`와 같이 `class`로 제한되지 ‘않는’ 여러 API를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-128">The <xref:Microsoft.Extensions.Configuration.ConfigurationBinder> class exposes several APIs, such as `.Bind(object instance)` and `.Get<T>()` that are ***not*** constrained to `class`.</span></span> <span data-ttu-id="7c75d-129">[옵션 인터페이스](#options-interfaces)를 사용하는 경우 앞서 언급한 [옵션 클래스 제약 조건](#options-class)을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-129">When using any of the [Options interfaces](#options-interfaces), you must adhere to aforementioned [options class constraints](#options-class).</span></span>

<span data-ttu-id="7c75d-130">옵션 패턴을 사용하는 경우 한 가지 대체 방법은 `"TransientFaultHandlingOptions"` 섹션을 바인딩하고 [종속성 주입 서비스 컨테이너](dependency-injection.md)에 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-130">An alternative approach when using the options pattern is to bind the `"TransientFaultHandlingOptions"` section and add it to the [dependency injection service container](dependency-injection.md).</span></span> <span data-ttu-id="7c75d-131">다음 코드에서 `TransientFaultHandlingOptions`는 <xref:Microsoft.Extensions.DependencyInjection.OptionsConfigurationServiceCollectionExtensions.Configure%2A>를 통해 서비스 컨테이너에 추가되고 구성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-131">In the following code, `TransientFaultHandlingOptions` is added to the service container with <xref:Microsoft.Extensions.DependencyInjection.OptionsConfigurationServiceCollectionExtensions.Configure%2A> and bound to configuration:</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        key: nameof(TransientFaultHandlingOptions)));
```

> [!TIP]
> <span data-ttu-id="7c75d-132">`key` 매개 변수는 검색할 구성 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-132">The `key` parameter is the name of the configuration section to search for.</span></span> <span data-ttu-id="7c75d-133">이를 표현하는 형식의 이름과 일치할 필요가 ‘없습니다’.</span><span class="sxs-lookup"><span data-stu-id="7c75d-133">It does *not* have to match the name of the type that represents it.</span></span> <span data-ttu-id="7c75d-134">예를 들어 `"FaultHandling"`라는 섹션이 `TransientFaultHandlingOptions` 클래스에 의해 표현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-134">For example, you could have a section named `"FaultHandling"` and it could be represented by the `TransientFaultHandlingOptions` class.</span></span> <span data-ttu-id="7c75d-135">이 인스턴스에서는 `"FaultHandling"`을 <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> 함수에 대신 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-135">In this instance, you'd pass `"FaultHandling"` to the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> function instead.</span></span> <span data-ttu-id="7c75d-136">`nameof` 연산자는 명명된 섹션이 해당하는 형식과 일치하는 경우 편의를 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-136">The `nameof` operator is used as a convenience when the named section matches the type it corresponds to.</span></span>

<span data-ttu-id="7c75d-137">위의 코드를 사용하여 다음 코드는 위치 옵션을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-137">Using the preceding code, the following code reads the position options:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ExampleService.cs":::

<span data-ttu-id="7c75d-138">위 코드에서는 앱을 시작한 후의 JSON 구성 파일의 변경 사항을 읽지 ***않습니다***.</span><span class="sxs-lookup"><span data-stu-id="7c75d-138">In the preceding code, changes to the JSON configuration file after the app has started are ***not*** read.</span></span> <span data-ttu-id="7c75d-139">앱을 시작한 후의 변경 사항을 읽으려면 [IOptionsSnapshot](#use-ioptionssnapshot-to-read-updated-data)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-139">To read changes after the app has started, use [IOptionsSnapshot](#use-ioptionssnapshot-to-read-updated-data).</span></span>

## <a name="options-interfaces"></a><span data-ttu-id="7c75d-140">옵션 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c75d-140">Options interfaces</span></span>

<span data-ttu-id="7c75d-141"><xref:Microsoft.Extensions.Options.IOptions%601>:</span><span class="sxs-lookup"><span data-stu-id="7c75d-141"><xref:Microsoft.Extensions.Options.IOptions%601>:</span></span>

- <span data-ttu-id="7c75d-142">다음을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-142">Does ***not*** support:</span></span>
  - <span data-ttu-id="7c75d-143">앱이 시작된 후 구성 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="7c75d-143">Reading of configuration data after the app has started.</span></span>
  - [<span data-ttu-id="7c75d-144">명명된 옵션</span><span class="sxs-lookup"><span data-stu-id="7c75d-144">Named options</span></span>](#named-options-support-using-iconfigurenamedoptions)
- <span data-ttu-id="7c75d-145">[Singleton](dependency-injection.md#singleton)으로 등록되며 [서비스 수명](dependency-injection.md#service-lifetimes)에 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-145">Is registered as a [Singleton](dependency-injection.md#singleton) and can be injected into any [service lifetime](dependency-injection.md#service-lifetimes).</span></span>

<span data-ttu-id="7c75d-146"><xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>:</span><span class="sxs-lookup"><span data-stu-id="7c75d-146"><xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>:</span></span>

- <span data-ttu-id="7c75d-147">[범위가 지정된 수명 또는 임시 수명](dependency-injection.md#service-lifetimes)에서 모든 주입 확인마다 옵션을 다시 계산하는 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-147">Is useful in scenarios where options should be recomputed on every injection resolution, in [scoped or transient lifetimes](dependency-injection.md#service-lifetimes).</span></span> <span data-ttu-id="7c75d-148">자세한 내용은 [IOptionsSnapshot을 사용하여 업데이트된 데이터](#use-ioptionssnapshot-to-read-updated-data)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c75d-148">For more information, see [Use IOptionsSnapshot to read updated data](#use-ioptionssnapshot-to-read-updated-data).</span></span>
- <span data-ttu-id="7c75d-149">[범위 지정됨](dependency-injection.md#scoped)으로 등록되므로 Singleton 서비스에 주입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-149">Is registered as [Scoped](dependency-injection.md#scoped) and therefore cannot be injected into a Singleton service.</span></span>
- <span data-ttu-id="7c75d-150">[명명된 옵션](#named-options-support-using-iconfigurenamedoptions)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-150">Supports [named options](#named-options-support-using-iconfigurenamedoptions)</span></span>

<span data-ttu-id="7c75d-151"><xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span><span class="sxs-lookup"><span data-stu-id="7c75d-151"><xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span></span>

- <span data-ttu-id="7c75d-152">옵션을 검색하고 `TOptions` 인스턴스에 대한 옵션 알림을 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-152">Is used to retrieve options and manage options notifications for `TOptions` instances.</span></span>
- <span data-ttu-id="7c75d-153">[Singleton](dependency-injection.md#singleton)으로 등록되며 [서비스 수명](dependency-injection.md#service-lifetimes)에 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-153">Is registered as a [Singleton](dependency-injection.md#singleton) and can be injected into any [service lifetime](dependency-injection.md#service-lifetimes).</span></span>
- <span data-ttu-id="7c75d-154">지원:</span><span class="sxs-lookup"><span data-stu-id="7c75d-154">Supports:</span></span>
  - <span data-ttu-id="7c75d-155">변경 알림</span><span class="sxs-lookup"><span data-stu-id="7c75d-155">Change notifications</span></span>
  - [<span data-ttu-id="7c75d-156">명명된 옵션</span><span class="sxs-lookup"><span data-stu-id="7c75d-156">Named options</span></span>](#named-options-support-using-iconfigurenamedoptions)
  - [<span data-ttu-id="7c75d-157">다시 로드할 수 있는 구성</span><span class="sxs-lookup"><span data-stu-id="7c75d-157">Reloadable configuration</span></span>](#use-ioptionssnapshot-to-read-updated-data)
  - <span data-ttu-id="7c75d-158">선택적 옵션 무효화(<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>)</span><span class="sxs-lookup"><span data-stu-id="7c75d-158">Selective options invalidation (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>)</span></span>

<span data-ttu-id="7c75d-159"><xref:Microsoft.Extensions.Options.IOptionsFactory%601>는 새로운 옵션 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-159"><xref:Microsoft.Extensions.Options.IOptionsFactory%601> is responsible for creating new options instances.</span></span> <span data-ttu-id="7c75d-160">단일 <xref:Microsoft.Extensions.Options.IOptionsFactory%601.Create%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-160">It has a single <xref:Microsoft.Extensions.Options.IOptionsFactory%601.Create%2A> method.</span></span> <span data-ttu-id="7c75d-161">기본 구현에서는 등록된 모든 <xref:Microsoft.Extensions.Options.IConfigureOptions%601> 및 <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>를 사용하며 먼저 구성을 모두 실행한 다음, 사후 구성을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-161">The default implementation takes all registered <xref:Microsoft.Extensions.Options.IConfigureOptions%601> and <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601> and runs all the configurations first, followed by the post-configuration.</span></span> <span data-ttu-id="7c75d-162"><xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>와 <xref:Microsoft.Extensions.Options.IConfigureOptions%601>를 구별하며 적절한 인터페이스만 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-162">It distinguishes between <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> and <xref:Microsoft.Extensions.Options.IConfigureOptions%601> and only calls the appropriate interface.</span></span>

<span data-ttu-id="7c75d-163"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>는 <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>에서 `TOptions` 인스턴스를 캐시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-163"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> is used by <xref:Microsoft.Extensions.Options.IOptionsMonitor%601> to cache `TOptions` instances.</span></span> <span data-ttu-id="7c75d-164"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601>는 모니터의 옵션 인스턴스를 무효화하므로 값이 다시 계산됩니다(<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryRemove%2A>).</span><span class="sxs-lookup"><span data-stu-id="7c75d-164">The <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601> invalidates options instances in the monitor so that the value is recomputed (<xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryRemove%2A>).</span></span> <span data-ttu-id="7c75d-165"><xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryAdd%2A>를 사용하여 값을 수동으로 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-165">Values can be manually introduced with <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.TryAdd%2A>.</span></span> <span data-ttu-id="7c75d-166">모든 명명된 인스턴스를 필요에 따라 다시 만들어야 하는 경우 <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.Clear%2A> 메서드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-166">The <xref:Microsoft.Extensions.Options.IOptionsMonitorCache%601.Clear%2A> method is used when all named instances should be recreated on demand.</span></span>

### <a name="options-interfaces-benefits"></a><span data-ttu-id="7c75d-167">옵션 인터페이스의 이점</span><span class="sxs-lookup"><span data-stu-id="7c75d-167">Options interfaces benefits</span></span>

<span data-ttu-id="7c75d-168">제네릭 래퍼 형식을 사용하면 옵션의 수명을 DI 컨테이너에서 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-168">Using a generic wrapper type gives you the ability to decouple the lifetime of the option from the DI container.</span></span> <span data-ttu-id="7c75d-169"><xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType> 인터페이스는 일반 제약 조건을 포함하여 옵션 형식에 대한 추상화 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-169">The <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType> interface provides a layer of abstraction, including generic constraints, on your options type.</span></span> <span data-ttu-id="7c75d-170">이 기능은 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-170">This provides the following benefits:</span></span>

- <span data-ttu-id="7c75d-171">`T` 구성 인스턴스의 평가는 <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType>가 주입될 때가 아니라 액세스될 때로 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-171">The evaluation of the `T` configuration instance is deferred to the accessing of <xref:Microsoft.Extensions.Options.IOptions%601.Value?displayProperty=nameWithType>, rather than when it is injected.</span></span> <span data-ttu-id="7c75d-172">이는 `T` 옵션을 다양한 위치에서 사용하고 `T`에 대한 변경 없이 수명 의미 체계를 선택할 수 있기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-172">This is important because you can consume the `T` option from various places and choose the lifetime semantics without changing anything about `T`.</span></span>
- <span data-ttu-id="7c75d-173">`T` 형식의 옵션을 등록하는 경우 `T` 형식을 명시적으로 등록할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-173">When registering options of type `T`, you do not need to explicitly register the `T` type.</span></span> <span data-ttu-id="7c75d-174">이는 간단한 기본값을 사용하여 [라이브러리를 작성](options-library-authors.md)하고 호출자가 특정 수명을 갖는 옵션을 DI 컨테이너에 등록하도록 강제하지 않으려는 경우에 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-174">This is a convenience when you're [authoring a library](options-library-authors.md) with simple defaults, and you don't want to force the caller to register options into the DI container with a specific lifetime.</span></span>
- <span data-ttu-id="7c75d-175">API의 관점에서 보면 `T` 형식에 제약 조건을 사용할 수 있습니다(이 경우 `T`가 참조 형식으로 제한됨).</span><span class="sxs-lookup"><span data-stu-id="7c75d-175">From the perspective of the API, it allows for constraints on the type `T` (in this case, `T` is constrained to a reference type).</span></span>

## <a name="use-ioptionssnapshot-to-read-updated-data"></a><span data-ttu-id="7c75d-176">IOptionsSnapshot을 사용하여 업데이트된 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="7c75d-176">Use IOptionsSnapshot to read updated data</span></span>

<span data-ttu-id="7c75d-177"><xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>을 사용하면, 옵션은 액세스될 때 요청당 한 번씩 계산되고 요청의 수명 동안 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-177">When you use <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>, options are computed once per request when accessed and are cached for the lifetime of the request.</span></span> <span data-ttu-id="7c75d-178">업데이트된 구성 값 읽기를 지원하는 구성 공급자를 사용하는 경우 앱을 시작한 후 구성 변경 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-178">Changes to the configuration are read after the app starts when using configuration providers that support reading updated configuration values.</span></span>

<span data-ttu-id="7c75d-179">`IOptionsMonitor`와 `IOptionsSnapshot`의 차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-179">The difference between `IOptionsMonitor` and `IOptionsSnapshot` is that:</span></span>

- <span data-ttu-id="7c75d-180">`IOptionsMonitor`는 언제든지 현재 옵션 값을 검색하는 [싱글톤 서비스](dependency-injection.md#singleton)로, 싱글톤 종속성에서 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-180">`IOptionsMonitor` is a [singleton service](dependency-injection.md#singleton) that retrieves current option values at any time, which is especially useful in singleton dependencies.</span></span>
- <span data-ttu-id="7c75d-181">`IOptionsSnapshot`은 [범위가 지정된 서비스](dependency-injection.md#scoped)이며 `IOptionsSnapshot<T>` 개체가 생성될 때 옵션의 스냅샷을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-181">`IOptionsSnapshot` is a [scoped service](dependency-injection.md#scoped) and provides a snapshot of the options at the time the `IOptionsSnapshot<T>` object is constructed.</span></span> <span data-ttu-id="7c75d-182">옵션 스냅숏은 임시 및 범위가 지정된 종속성과 함께 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-182">Options snapshots are designed for use with transient and scoped dependencies.</span></span>

<span data-ttu-id="7c75d-183">다음 코드에서는 <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-183">The following code uses <xref:Microsoft.Extensions.Options.IOptionsSnapshot%601>.</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ScopedService.cs":::

<span data-ttu-id="7c75d-184">다음 코드에서는 `TransientFaultHandlingOptions`가 바인딩되는 구성 인스턴스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-184">The following code registers a configuration instance which `TransientFaultHandlingOptions` binds against:</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

<span data-ttu-id="7c75d-185">위 코드에서는 앱을 시작한 후 JSON 구성 파일 변경 사항을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-185">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

## <a name="ioptionsmonitor"></a><span data-ttu-id="7c75d-186">IOptionsMonitor</span><span class="sxs-lookup"><span data-stu-id="7c75d-186">IOptionsMonitor</span></span>

<span data-ttu-id="7c75d-187">다음 코드는 `TransientFaultHandlingOptions`가 바인딩되는 구성 인스턴스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-187">The following code registers a configuration instance which `TransientFaultHandlingOptions` binds against.</span></span>

```csharp
services.Configure<TransientFaultHandlingOptions>(
    configurationRoot.GetSection(
        nameof(TransientFaultHandlingOptions)));
```

<span data-ttu-id="7c75d-188">다음 예제에서는 <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-188">The following example uses <xref:Microsoft.Extensions.Options.IOptionsMonitor%601>:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/MonitorService.cs":::

<span data-ttu-id="7c75d-189">위 코드에서는 앱을 시작한 후 JSON 구성 파일 변경 사항을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-189">In the preceding code, changes to the JSON configuration file after the app has started are read.</span></span>

## <a name="named-options-support-using-iconfigurenamedoptions"></a><span data-ttu-id="7c75d-190">명명된 옵션은 IConfigureNamedOptions 사용을 지원</span><span class="sxs-lookup"><span data-stu-id="7c75d-190">Named options support using IConfigureNamedOptions</span></span>

<span data-ttu-id="7c75d-191">명명된 옵션:</span><span class="sxs-lookup"><span data-stu-id="7c75d-191">Named options:</span></span>

- <span data-ttu-id="7c75d-192">여러 구성 섹션이 동일한 속성에 바인딩되는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-192">Are useful when multiple configuration sections bind to the same properties.</span></span>
- <span data-ttu-id="7c75d-193">대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-193">Are case-sensitive.</span></span>

<span data-ttu-id="7c75d-194">다음 *appsettings.json* 파일을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7c75d-194">Consider the following *appsettings.json* file:</span></span>

```json
{
  "Features": {
    "Personalize": {
      "Enabled": true,
      "ApiKey": "aGEgaGEgeW91IHRob3VnaHQgdGhhdCB3YXMgcmVhbGx5IHNvbWV0aGluZw=="
    },
    "WeatherStation": {
      "Enabled": true,
      "ApiKey": "QXJlIHlvdSBhdHRlbXB0aW5nIHRvIGhhY2sgdXM/"
    }
  }
}
```

<span data-ttu-id="7c75d-195">`Features:Personalize` 및 `Features:WeatherStation`를 바인딩하는 두 개의 클래스를 만드는 대신 각 섹션에 다음 클래스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-195">Rather than creating two classes to bind `Features:Personalize` and `Features:WeatherStation`, the following class is used for each section:</span></span>

```csharp
public class Features
{
    public const string Personalize = nameof(Personalize);
    public const string WeatherStation = nameof(WeatherStation);

    public bool Enabled { get; set; }
    public string ApiKey { get; set; }
}
```

<span data-ttu-id="7c75d-196">다음 코드는 명명된 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-196">The following code configures the named options:</span></span>

```csharp
ConfigureServices(services =>
{
    services.Configure<Features>(
        Features.Personalize,
        Configuration.GetSection("Features:Personalize"));

    services.Configure<Features>(
        Features.WeatherStation,
        Configuration.GetSection("Features:WeatherStation"));
});
```

<span data-ttu-id="7c75d-197">다음 코드는 명명된 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-197">The following code displays the named options:</span></span>

```csharp
public class Service
{
    private readonly Features _personalizeFeature;
    private readonly Features _weatherStationFeature;

    public Service(IOptionsSnapshot<Features> namedOptionsAccessor)
    {
        _personalizeFeature = namedOptionsAccessor.Get(Features.Personalize);
        _weatherStationFeature = namedOptionsAccessor.Get(Features.WeatherStation);
    }
}
```

<span data-ttu-id="7c75d-198">모든 옵션은 명명된 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-198">All options are named instances.</span></span> <span data-ttu-id="7c75d-199"><xref:Microsoft.Extensions.Options.IConfigureOptions%601> 인스턴스는 `string.Empty`인 `Options.DefaultName` 인스턴스를 대상으로 지정한 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-199"><xref:Microsoft.Extensions.Options.IConfigureOptions%601> instances are treated as targeting the `Options.DefaultName` instance, which is `string.Empty`.</span></span> <span data-ttu-id="7c75d-200"><xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>는 <xref:Microsoft.Extensions.Options.IConfigureOptions%601>도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-200"><xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> also implements <xref:Microsoft.Extensions.Options.IConfigureOptions%601>.</span></span> <span data-ttu-id="7c75d-201"><xref:Microsoft.Extensions.Options.IOptionsFactory%601>의 기본 구현에는 각 옵션을 적절하게 사용하기 위한 논리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-201">The default implementation of the <xref:Microsoft.Extensions.Options.IOptionsFactory%601> has logic to use each appropriately.</span></span> <span data-ttu-id="7c75d-202">`null` 명명된 옵션은 특정 명명된 인스턴스 대신 모든 명명된 인스턴스를 대상으로 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-202">The `null` named option is used to target all of the named instances instead of a specific named instance.</span></span> <span data-ttu-id="7c75d-203"><xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.ConfigureAll%2A> 및 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A>에서 이 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-203"><xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.ConfigureAll%2A> and <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> use this convention.</span></span>

## <a name="optionsbuilder-api"></a><span data-ttu-id="7c75d-204">OptionsBuilder API</span><span class="sxs-lookup"><span data-stu-id="7c75d-204">OptionsBuilder API</span></span>

<span data-ttu-id="7c75d-205"><xref:Microsoft.Extensions.Options.OptionsBuilder%601>는 `TOptions` 인스턴스를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-205"><xref:Microsoft.Extensions.Options.OptionsBuilder%601> is used to configure `TOptions` instances.</span></span> <span data-ttu-id="7c75d-206">`OptionsBuilder`는 `AddOptions<TOptions>(string optionsName)` 호출에 대한 단일 매개 변수이므로 모든 후속 호출에 나타나는 대신 명명된 옵션 생성을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-206">`OptionsBuilder` streamlines creating named options as it's only a single parameter to the initial `AddOptions<TOptions>(string optionsName)` call instead of appearing in all of the subsequent calls.</span></span> <span data-ttu-id="7c75d-207">옵션 유효성 검사 및 서비스 종속성을 허용하는 `ConfigureOptions` 오버로드는 `OptionsBuilder`를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-207">Options validation and the `ConfigureOptions` overloads that accept service dependencies are only available via `OptionsBuilder`.</span></span>

<span data-ttu-id="7c75d-208">`OptionsBuilder`는 [옵션 유효성 검사](#options-validation) 섹션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-208">`OptionsBuilder` is used in the [Options validation](#options-validation) section.</span></span>

## <a name="use-di-services-to-configure-options"></a><span data-ttu-id="7c75d-209">DI 서비스를 사용하여 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="7c75d-209">Use DI services to configure options</span></span>

<span data-ttu-id="7c75d-210">다음 두 가지 방법으로 옵션을 구성하는 동안 종속성 주입에서 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-210">Services can be accessed from dependency injection while configuring options in two ways:</span></span>

- <span data-ttu-id="7c75d-211">구성 대리자를 [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601)의 [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A)에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-211">Pass a configuration delegate to [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) on [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601).</span></span> <span data-ttu-id="7c75d-212">`OptionsBuilder<TOptions>`는 최대 5개의 서비스를 사용하여 옵션을 구성할 수 있는 [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A)의 오버로드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-212">`OptionsBuilder<TOptions>` provides overloads of [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) that allow use of up to five services to configure options:</span></span>

  ```csharp
  services.AddOptions<MyOptions>("optionalName")
      .Configure<ExampleService, ScopedService, MonitorService>(
          (options, es, ss, ms) =>
              options.Property = DoSomethingWith(es, ss, ms));
  ```

- <span data-ttu-id="7c75d-213"><xref:Microsoft.Extensions.Options.IConfigureOptions%601> 또는 <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>를 구현하는 형식을 만들고 해당 형식을 서비스로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-213">Create a type that implements <xref:Microsoft.Extensions.Options.IConfigureOptions%601> or <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601> and register the type as a service.</span></span>

<span data-ttu-id="7c75d-214">서비스를 만드는 것이 더 복잡하기 때문에 구성 대리자를 [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A)에 전달하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-214">We recommend passing a configuration delegate to [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A), since creating a service is more complex.</span></span> <span data-ttu-id="7c75d-215">형식을 만드는 작업은 [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A)를 호출할 때 프레임워크에서 수행하는 작업에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-215">Creating a type is equivalent to what the framework does when calling [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A).</span></span> <span data-ttu-id="7c75d-216">[Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A)을 호출하면 지정된 일반 서비스 유형을 허용하는 생성자가 있는 일시적인 일반 <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-216">Calling [Configure](xref:Microsoft.Extensions.Options.OptionsBuilder%601.Configure%2A) registers a transient generic <xref:Microsoft.Extensions.Options.IConfigureNamedOptions%601>, which has a constructor that accepts the generic service types specified.</span></span>

## <a name="options-validation"></a><span data-ttu-id="7c75d-217">옵션 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="7c75d-217">Options validation</span></span>

<span data-ttu-id="7c75d-218">옵션 유효성 검사를 통해 옵션 값의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-218">Options validation enables option values to be validated.</span></span>

<span data-ttu-id="7c75d-219">다음 *appsettings.json* 파일을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="7c75d-219">Consider the following *appsettings.json* file:</span></span>

```json
{
  "Settings": {
    "SiteTitle": "Amazing docs from Awesome people!",
    "Scale": 10,
    "VerbosityLevel": 32
  }
}
```

<span data-ttu-id="7c75d-220">다음 클래스는 `"Settings"` 구성 섹션에 바인딩되고 몇 가지 `DataAnnotations` 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-220">The following class binds to the `"Settings"` configuration section and applies a couple of `DataAnnotations` rules:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/SettingsOptions.cs":::

<span data-ttu-id="7c75d-221">코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-221">The following code:</span></span>

- <span data-ttu-id="7c75d-222"><xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A>를 호출하여 `SettingsOptions` 클래스에 바인딩되는 [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-222">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> to get an [OptionsBuilder\<TOptions>](xref:Microsoft.Extensions.Options.OptionsBuilder%601) that binds to the `SettingsOptions` class.</span></span>
- <span data-ttu-id="7c75d-223"><xref:Microsoft.Extensions.DependencyInjection.OptionsBuilderDataAnnotationsExtensions.ValidateDataAnnotations%2A>를 호출하여 `DataAnnotations`를 사용한 유효성 검사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-223">Calls <xref:Microsoft.Extensions.DependencyInjection.OptionsBuilderDataAnnotationsExtensions.ValidateDataAnnotations%2A> to enable validation using `DataAnnotations`.</span></span>

```csharp
services.AddOptions<SettingsOptions>()
    .Bind(Configuration.GetSection(SettingsOptions.Settings))
    .ValidateDataAnnotations();
```

<span data-ttu-id="7c75d-224">`ValidateDataAnnotations` 확장 메서드는 [Microsoft.Extensions.Options.DataAnnotations](https://www.nuget.org/packages/Microsoft.Extensions.Options.DataAnnotations) NuGet 패키지에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-224">The `ValidateDataAnnotations` extension method is defined in the [Microsoft.Extensions.Options.DataAnnotations](https://www.nuget.org/packages/Microsoft.Extensions.Options.DataAnnotations) NuGet package.</span></span>

<span data-ttu-id="7c75d-225">다음 코드는 구성 값 또는 유효성 검사 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-225">The following code displays the configuration values or the validation errors:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ValidationService.cs":::

<span data-ttu-id="7c75d-226">다음 코드는 대리자를 사용하여 보다 복잡한 유효성 검사 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-226">The following code applies a more complex validation rule using a delegate:</span></span>

```csharp
services.AddOptions<SettingsOptions>()
    .Bind(Configuration.GetSection(SettingsOptions.Settings))
    .ValidateDataAnnotations()
    .Validate(config =>
    {
        if (config.Scale != 0)
        {
            return config.VerbosityLevel > config.Scale;
        }

        return true;
    }, "VerbosityLevel must be > than Scale.");
```

### <a name="ivalidateoptions-for-complex-validation"></a><span data-ttu-id="7c75d-227">복잡한 유효성 검사를 위한 IValidateOptions</span><span class="sxs-lookup"><span data-stu-id="7c75d-227">IValidateOptions for complex validation</span></span>

<span data-ttu-id="7c75d-228">다음 클래스는 <xref:Microsoft.Extensions.Options.IValidateOptions%601>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-228">The following class implements <xref:Microsoft.Extensions.Options.IValidateOptions%601>:</span></span>

:::code language="csharp" source="snippets/configuration/console-json/ValidateSettingsOptions.cs":::

<span data-ttu-id="7c75d-229">`IValidateOptions`를 사용하면 유효성 검사 코드를 클래스로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-229">`IValidateOptions` enables moving the validation code into a class.</span></span>

<span data-ttu-id="7c75d-230">위의 코드에서는 다음 코드를 사용하여 `ConfigureServices`에서 유효성 검사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-230">Using the preceding code, validation is enabled in `ConfigureServices` with the following code:</span></span>

```csharp
services.Configure<SettingsOptions>(
    Configuration.GetSection(
        SettingsOptions.Settings));
services.TryAddEnumerable(
    ServiceDescriptor.Singleton
        <IValidateOptions<SettingsOptions>, ValidateSettingsOptions>());
```

## <a name="options-post-configuration"></a><span data-ttu-id="7c75d-231">옵션 사후 구성</span><span class="sxs-lookup"><span data-stu-id="7c75d-231">Options post-configuration</span></span>

<span data-ttu-id="7c75d-232"><xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>를 사용하여 사후 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-232">Set post-configuration with <xref:Microsoft.Extensions.Options.IPostConfigureOptions%601>.</span></span> <span data-ttu-id="7c75d-233">사후 구성은 모든 <xref:Microsoft.Extensions.Options.IConfigureOptions%601> 구성이 발생한 후에 실행되며, 구성을 재정의해야 하는 시나리오에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-233">Post-configuration runs after all <xref:Microsoft.Extensions.Options.IConfigureOptions%601> configuration occurs, and can be useful in scenarios when you need to override configuration:</span></span>

```csharp
services.PostConfigure<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

<span data-ttu-id="7c75d-234"><xref:Microsoft.Extensions.Options.IPostConfigureOptions%601.PostConfigure%2A>를 사용하여 명명된 옵션을 사후 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-234"><xref:Microsoft.Extensions.Options.IPostConfigureOptions%601.PostConfigure%2A> is available to post-configure named options:</span></span>

```csharp
services.PostConfigure<CustomOptions>("named_options_1", customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

<span data-ttu-id="7c75d-235">모든 구성 인스턴스를 사후 구성하려면 <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c75d-235">Use <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.PostConfigureAll%2A> to post-configure all configuration instances:</span></span>

```csharp
services.PostConfigureAll<CustomOptions>(customOptions =>
{
    customOptions.Option1 = "post_configured_option1_value";
});
```

## <a name="see-also"></a><span data-ttu-id="7c75d-236">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c75d-236">See also</span></span>

- [<span data-ttu-id="7c75d-237">.NET의 구성</span><span class="sxs-lookup"><span data-stu-id="7c75d-237">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="7c75d-238">.NET 라이브러리 작성자를 위한 옵션 패턴 지침</span><span class="sxs-lookup"><span data-stu-id="7c75d-238">Options pattern guidance for .NET library authors</span></span>](options-library-authors.md)
