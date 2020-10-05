---
title: 플랫폼 호환성 분석기
description: 플랫폼 간 앱 및 라이브러리에서 플랫폼 호환성 문제를 감지하는 데 도움이 되는 Roslyn 분석기입니다.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406590"
---
# <a name="platform-compatibility-analyzer"></a><span data-ttu-id="0bcc6-103">플랫폼 호환성 분석기</span><span class="sxs-lookup"><span data-stu-id="0bcc6-103">Platform compatibility analyzer</span></span>

<span data-ttu-id="0bcc6-104">"One .NET": 모든 유형의 애플리케이션을 빌드하기 위한 단일 통합 플랫폼이라는 모토를 들어 보셨을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-104">You've probably heard the motto of "One .NET": a single, unified platform for building any type of application.</span></span> <span data-ttu-id="0bcc6-105">.NET 5.0 SDK에는 ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin 및 ML.NET가 포함되어 있으며, 향후 더 많은 플랫폼에 대한 지원이 추가될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-105">The .NET 5.0 SDK includes ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin, and ML.NET, and will add support for more platforms over time.</span></span> <span data-ttu-id="0bcc6-106">.NET 5.0은 .NET의 다양한 플랫폼을 일일이 고려하지 않아도 없는 환경을 제공하기 위해 노력하고 있지만, 기본 OS(운영 체제)를 완전히 추상화하려고 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-106">.NET 5.0 strives to provide an experience where you don't have to reason about the different flavors of .NET, but doesn't attempt to fully abstract away the underlying operating system (OS).</span></span> <span data-ttu-id="0bcc6-107">플랫폼별 API(예: P/Invoke, WinRT 또는 iOS 및 Android용 Xamarin 바인딩)를 계속해서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-107">You'll continue to be able to call platform-specific APIs, for example, P/Invokes, WinRT, or the Xamarin bindings for iOS and Android.</span></span>

<span data-ttu-id="0bcc6-108">그러나 한 구성 요소에서 플랫폼별 API를 사용하면 코드는 더 이상 모든 플랫폼에서 작동하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-108">But using platform-specific APIs on a component means the code no longer works across all platforms.</span></span> <span data-ttu-id="0bcc6-109">개발자가 플랫폼별 API를 실수로 사용하는 경우 진단을 받을 수 있도록 디자인 타임에 이를 감지하는 방법이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-109">We needed a way to detect this at design time so developers get diagnostics when they inadvertently use platform-specific APIs.</span></span> <span data-ttu-id="0bcc6-110">이러한 목표를 달성하기 위해 .NET 5.0에서 개발자가 적절한 플랫폼별 API를 식별하고 사용하는 데 도움이 되는 [플랫폼 호환성 분석기](/visualstudio/code-quality/ca1416) 및 보완 API를 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-110">To achieve this goal, .NET 5.0 introduces the [platform compatibility analyzer](/visualstudio/code-quality/ca1416) and complementary APIs to help developers identify and use platform-specific APIs where appropriate.</span></span>
<span data-ttu-id="0bcc6-111">새 API의 구성 내용:</span><span class="sxs-lookup"><span data-stu-id="0bcc6-111">The new APIs include:</span></span>

- <span data-ttu-id="0bcc6-112">API에 플랫폼별 주석을 달기 위한 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>와 API에 특정 OS에서 지원되지 않음 주석을 달기 위한 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> to annotate APIs as being platform-specific and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> to annotate APIs as being unsupported on a particular OS.</span></span> <span data-ttu-id="0bcc6-113">이러한 특성은 선택적으로 버전 번호를 포함할 수 있으며 핵심 .NET 라이브러리의 일부 플랫폼별 API에 이미 적용되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-113">These attributes can optionally include the version number, and have already been applied to some platform-specific APIs in the core .NET libraries.</span></span>
- <span data-ttu-id="0bcc6-114">플랫폼별 API를 안전하게 호출하기 위한 <xref:System.OperatingSystem?displayProperty=nameWithType> 클래스의 `Is<Platform>()` 및 `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` 정적 메서드.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-114">`Is<Platform>()` and `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` static methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class for safely calling platform-specific APIs.</span></span> <span data-ttu-id="0bcc6-115">예를 들어 <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>를 사용하여 Windows 관련 API에 대한 호출을 보호할 수 있으며, <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>()를 사용하여 버전이 지정된 Windows 관련 API 호출을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-115">For example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> can be used to guard a call to a Windows-specific API, and <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() can be used to guard a versioned Windows-specific API call.</span></span> <span data-ttu-id="0bcc6-116">이러한 메서드를 플랫폼별 API 참조의 가드로 사용할 수 있는 방법에 대해서는 [예제](#guard-platform-specific-apis-with-guard-methods)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-116">See these [examples](#guard-platform-specific-apis-with-guard-methods) of how these methods can be used as guards of platform-specific API references.</span></span>

> [!TIP]
> <span data-ttu-id="0bcc6-117">플랫폼 호환성 분석기는 [.NET API 분석기](../../standard/analyzers/api-analyzer.md)의 [플랫폼 간 문제 검색](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) 기능을 업그레이드하고 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-117">The platform compatibility analyzer upgrades and replaces the [Discovering cross-platform issues](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) feature of the [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bcc6-118">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bcc6-118">Prerequisites</span></span>

<span data-ttu-id="0bcc6-119">플랫폼 호환성 분석기는 Roslyn 코드 품질 분석기 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-119">The platform compatibility analyzer is one of the Roslyn code quality analyzers.</span></span> <span data-ttu-id="0bcc6-120">.NET 5.0부터 이러한 분석기는 [.NET SDK](../../fundamentals/productivity/code-analysis.md)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-120">Starting in .NET 5.0, these analyzers are [included with the .NET SDK](../../fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="0bcc6-121">플랫폼 호환성 분석기는 `net5.0` 이상 버전을 대상으로 하는 프로젝트에서만 기본으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-121">The platform compatibility analyzer is enabled by default only for projects that target `net5.0` or a later version.</span></span> <span data-ttu-id="0bcc6-122">그러나 다른 프레임워크를 대상으로 하는 프로젝트에도 [사용](/visualstudio/code-quality/ca1416.md#configurability)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-122">However, you can [enable](/visualstudio/code-quality/ca1416.md#configurability) it for projects that target other frameworks.</span></span>

## <a name="how-the-analyzer-determines-platform-dependency"></a><span data-ttu-id="0bcc6-123">분석기에서 플랫폼 종속성을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="0bcc6-123">How the analyzer determines platform dependency</span></span>

- <span data-ttu-id="0bcc6-124">**특성이 지정되지 않은 API**는 **모든 OS 플랫폼**에서 작동하는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-124">An **unattributed API** is considered to work on **all OS platforms**.</span></span>
- <span data-ttu-id="0bcc6-125">`[SupportedOSPlatform("platform")]`으로 표시된 API는 지정된 OS `platform`에만 이식할 수 있는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-125">An API marked with `[SupportedOSPlatform("platform")]` is considered only portable to the specified OS `platform`.</span></span>
  - <span data-ttu-id="0bcc6-126">이 특성을 여러 번 적용하여 **다중 플랫폼 지원**(`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`)을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-126">The attribute can be applied multiple times to indicate **multiple platform support** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span></span>
  - <span data-ttu-id="0bcc6-127">적절한 **플랫폼 컨텍스트** 없이 플랫폼별 API를 참조하는 경우 분석기가 **경고**를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-127">The analyzer will produce a **warning** if platform-specific APIs are referenced without a proper **platform context**:</span></span>
    - <span data-ttu-id="0bcc6-128">프로젝트가 지원되는 플랫폼을 대상으로 하지 않는 경우(예: 프로젝트가 `<TargetFramework>net5.0-ios14.0</TargetFramework>`를 대상으로 할 때 Windows 관련 API를 호출) **경고합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-128">**Warns** if the project doesn't target the supported platform (for example, a Windows-specific API call and the project targets `<TargetFramework>net5.0-ios14.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="0bcc6-129">프로젝트가 다중 대상으로 지정된 경우(`<TargetFramework>net5.0</TargetFramework>`) **경고합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-129">**Warns** if the project is multi-targeted (`<TargetFramework>net5.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="0bcc6-130">**지정된 플랫폼**을 대상으로 하는 프로젝트 내에서 플랫폼별 API를 참조하는 경우(예: 프로젝트가 `<TargetFramework>net5.0-windows</TargetFramework>`를 대상으로 할 때 Windows 관련 API를 호출) **경고하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-130">**Doesn't warn** if the platform-specific API is referenced within a project that targets any of the **specified platforms** (for example, for a Windows-specific API call and the project targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="0bcc6-131">플랫폼별 API 호출이 해당하는 플랫폼 검사 메서드(예: `if(OperatingSystem.IsWindows())`)로 보호되는 경우 **경고하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-131">**Doesn't warn** if the platform-specific API call is guarded by corresponding platform-check methods (for example, `if(OperatingSystem.IsWindows())`).</span></span>
    - <span data-ttu-id="0bcc6-132">플랫폼별 API가 동일한 플랫폼별 컨텍스트에서 참조되는 경우(**호출 사이트에도 `[SupportedOSPlatform("platform")` 특성이 지정됨**) **경고하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-132">**Doesn't warn** if the platform-specific API is referenced from the same platform-specific context (**call site also attributed** with `[SupportedOSPlatform("platform")`).</span></span>
- <span data-ttu-id="0bcc6-133">`[UnsupportedOSPlatform("platform")]`으로 표시된 API는 지정된 OS `platform`에서만 지원되지 않고 다른 모든 플랫폼에서는 지원되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-133">An API marked with `[UnsupportedOSPlatform("platform")]` is considered unsupported only on the specified OS `platform` but supported for all other platforms.</span></span>
  - <span data-ttu-id="0bcc6-134">이 특성은 서로 다른 플랫폼에서 여러 번 적용될 수 있습니다(예: `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-134">The attribute can be applied multiple times with different platforms, for example, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span></span>
  - <span data-ttu-id="0bcc6-135">분석기는 `platform`이 호출 사이트에 유효한 경우에만 **경고**를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-135">The analyzer produces a **warning** only if the `platform` is effective for the call site:</span></span>
    - <span data-ttu-id="0bcc6-136">프로젝트가 지원되지 않는 것으로 지정된 플랫폼을 대상으로 하는 경우(예: 호출 사이트가 `<TargetFramework>net5.0-windows</TargetFramework>`를 대상으로 할 때 API에 `[UnsupportedOSPlatform("windows")]` 특성이 지정됨) **경고합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-136">**Warns** if the project targets the platform that's attributed as unsupported (for example, if the API is attributed with `[UnsupportedOSPlatform("windows")]` and the call site targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="0bcc6-137">프로젝트가 다중 대상으로 지정되고 `platform`이 기본 [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) 항목 그룹에 포함되거나 `platform`이 수동으로 `MSBuild` \<SupportedPlatform> 항목 그룹에 포함된 경우 **경고합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-137">**Warns** if the project is multi-targeted and the `platform` is included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group, or the `platform` is manually included within the `MSBuild` \<SupportedPlatform> items group:</span></span>

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - <span data-ttu-id="0bcc6-138">지원되지 않는 플랫폼을 대상으로 하지 않거나 다중 대상으로 지정된 앱을 빌드하고 플랫폼이 기본 [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) 항목 그룹에 포함되지 않은 경우 **경고하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-138">**Doesn't warn** if you're building an app that doesn't target the unsupported platform or is multi-targeted and the platform is not included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group.</span></span>
- <span data-ttu-id="0bcc6-139">두 특성 모두 플랫폼 이름의 일부로 버전 번호를 사용하거나 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-139">Both attributes can be instantiated with or without version numbers as part of the platform name.</span></span>
  - <span data-ttu-id="0bcc6-140">버전 번호는 `major.minor[.build[.revision]]` 형식입니다. `major.minor`는 필수 항목이고 `build` 및 `revision` 부분은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-140">Version numbers are in the format of `major.minor[.build[.revision]]`; `major.minor` is required and the `build` and `revision` parts are optional.</span></span> <span data-ttu-id="0bcc6-141">예를 들어 "Windows 7.0"은 Windows 버전 7.0을 나타내지만 "Windows"는 Windows 0.0으로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-141">For example, "Windows7.0" indicates Windows version 7.0, but "Windows" is interpreted as Windows 0.0.</span></span>

<span data-ttu-id="0bcc6-142">자세한 내용은 [특성 작동 방식 및 관련 진단 예제](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-142">For more information, see [examples of how the attributes work and what diagnostics they cause](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span></span>

### <a name="advanced-scenarios-for-combining-attributes"></a><span data-ttu-id="0bcc6-143">특성 결합을 위한 고급 시나리오</span><span class="sxs-lookup"><span data-stu-id="0bcc6-143">Advanced scenarios for combining attributes</span></span>

- <span data-ttu-id="0bcc6-144">`[SupportedOSPlatform]` 및 `[UnsupportedOSPlatform]` 특성의 조합이 있는 경우 모든 특성은 OS 플랫폼 식별자로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-144">If a combination of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are present, all attributes are grouped by OS platform identifier:</span></span>
  - <span data-ttu-id="0bcc6-145">**지원 목록**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-145">**Supported only list**.</span></span> <span data-ttu-id="0bcc6-146">각 OS 플랫폼의 가장 낮은 버전이 `[SupportedOSPlatform]` 특성인 경우 API는 나열된 플랫폼에서만 지원되고 다른 모든 플랫폼에서는 지원되지 않는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-146">If the lowest version for each OS platform is a `[SupportedOSPlatform]` attribute, the API is considered to only be supported by the listed platforms and unsupported by all other platforms.</span></span> <span data-ttu-id="0bcc6-147">각 플랫폼에 대한 선택적 `[UnsupportedOSPlatform]` 특성은 지원되는 최소 버전보다 상위 버전에만 적용될 수 있으며, 이는 지정된 버전부터 API가 제거됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-147">The optional `[UnsupportedOSPlatform]` attributes for each platform can only have higher version of the minimum supported version, which denotes that the API is removed starting from the specified version.</span></span>

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - <span data-ttu-id="0bcc6-148">**미지원 목록**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-148">**Unsupported only list**.</span></span> <span data-ttu-id="0bcc6-149">각 OS 플랫폼의 가장 낮은 버전이 `[UnsupportedOSPlatform]` 특성인 경우 API는 나열된 플랫폼에서만 지원되지 않고 다른 모든 플랫폼에서는 지원되는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-149">If the lowest version for each OS platform is an `[UnsupportedOSPlatform]` attribute, then the API is considered to only be unsupported by the listed platforms and supported by all other platforms.</span></span> <span data-ttu-id="0bcc6-150">이 목록에는 동일한 플랫폼의 상위 버전에 `[SupportedOSPlatform]` 특성이 지정될 수 있습니다. 이는 해당 버전부터 API가 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-150">The list could have `[SupportedOSPlatform]` attribute with the same platform but a higher version, which denotes that the API is supported starting from that version.</span></span>
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - <span data-ttu-id="0bcc6-151">**불일치 목록**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-151">**Inconsistent list**.</span></span> <span data-ttu-id="0bcc6-152">일부 플랫폼의 가장 낮은 버전이 `[SupportedOSPlatform]`이고 다른 플랫폼에 대해서 `[UnsupportedOSPlatform]`인 경우 불일치로 간주됩니다(분석기에 대해 지원되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-152">If the lowest version for some platforms is `[SupportedOSPlatform]` while it is `[UnsupportedOSPlatform]` for other platforms, is considered inconsistent, which is not supported for the analyzer.</span></span>
  - <span data-ttu-id="0bcc6-153">`[SupportedOSPlatform]` 및 `[UnsupportedOSPlatform]` 특성의 가장 낮은 버전이 동일한 경우 분석기는 해당 플랫폼을 **지원 목록**의 일부로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-153">If the lowest versions of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are equal, the analyzer considers the platform as part of the **Supported only list**.</span></span>
- <span data-ttu-id="0bcc6-154">플랫폼 특성은 다양한 플랫폼 이름 및/또는 버전을 사용하는 형식, 멤버(메서드, 필드, 속성 및 이벤트) 및 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-154">Platform attributes can be applied to types, members (methods, fields, properties, and events) and assemblies with different platform name and / or version.</span></span>
  - <span data-ttu-id="0bcc6-155">최상위 수준 `target`에서 적용된 특성은 모든 멤버 및 형식에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-155">Attributes applied at the top level `target` affect all of its members and types.</span></span>
  - <span data-ttu-id="0bcc6-156">자식 수준 특성은 "자식 주석은 플랫폼 지원 범위를 축소할 수 있지만 확장할 수 없음" 규칙을 준수하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-156">Child level attributes only apply if they adhere to the rule "child annotations can narrow the platforms support, but they cannot widen it".</span></span>
    - <span data-ttu-id="0bcc6-157">부모에 **지원** 목록만 지정된 경우 자식 멤버 특성은 새 플랫폼 지원을 추가할 수 없습니다(부모 지원 범위를 확장하기 때문). 새 플랫폼 지원은 부모 자체에만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-157">When parent has **Supported only** list, then child member attributes could not add a new platform support as that would be extending parent support, a new platform support can only added to the parent itself.</span></span> <span data-ttu-id="0bcc6-158">그러나 동일한 플랫폼의 상위 버전에 `Supported` 특성이 지정될 수 있으며 이 경우 지원 범위가 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-158">But it can have `Supported` attribute for same platform with later versions as that will narrow the support.</span></span> <span data-ttu-id="0bcc6-159">동일한 플랫폼에 `Unsupported` 특성도 지정될 수 있고 이러한 경우에도 부모 지원 범위가 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-159">Also it can have `Unsupported` attribute with same platform as that will also narrow parent support.</span></span>
    - <span data-ttu-id="0bcc6-160">부모에 **미지원** 목록이 지정된 경우 자식 멤버 특성은 새 플랫폼 지원을 추가할 수 있지만(부모 지원 범위를 축소하기 때문), 부모와 동일한 플랫폼에 `Supported` 특성이 지정될 수는 없습니다(부모 지원 범위를 확장하기 때문).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-160">When parent has **Unsupported only** list, then child member attributes could add a new platform support as that would be narrowing parent support, but it cannot have `Supported` attribute for same platform as in the parent, that would extend parent support.</span></span> <span data-ttu-id="0bcc6-161">동일한 플랫폼에 대한 지원은 원래 `Unsupported` 특성이 적용된 부모 수준에만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-161">Support for the same platform can be added only to parent level where the original `Unsupported` attribute applied.</span></span>
  - <span data-ttu-id="0bcc6-162">동일한 `platform` 이름의 API에 `[SupportedOSPlatform("platformVersion")]`를 두 번 이상 적용한 경우 분석기는 최소 버전을 사용하는 API만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-162">If `[SupportedOSPlatform("platformVersion")]` is applied more than once for an API with the same `platform` name only the one with minimum version is considered by the analyzer.</span></span>
  - <span data-ttu-id="0bcc6-163">동일한 `platform` 이름의 API에 `[UnsupportedOSPlatform("platformVersion")]`을 세 번 이상 적용한 경우 분석기는 최소 버전을 사용하는 API 두 개만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-163">If `[UnsupportedOSPlatform("platformVersion")]` is applied more than twice for an API with the same `platform` name, only the two with earliest versions are considered by the analyzer.</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="0bcc6-164">처음에는 지원되었지만 상위 버전에서 지원되지 않는(제거된) API는 이후 버전에서도 다시 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-164">An API that was supported initially but unsupported (removed) in a later version is not expected to get resupported in an even later version.</span></span>

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a><span data-ttu-id="0bcc6-165">특성 작동 방식 및 관련 진단 예제</span><span class="sxs-lookup"><span data-stu-id="0bcc6-165">Examples of how the attributes work and what diagnostics they produce</span></span>

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a><span data-ttu-id="0bcc6-166">보고된 경고 처리</span><span class="sxs-lookup"><span data-stu-id="0bcc6-166">Handle reported warnings</span></span>

<span data-ttu-id="0bcc6-167">이러한 진단을 처리하는 권장 방법은 적절한 플랫폼에서 실행되는 경우에만 플랫폼별 API를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-167">The recommended way to deal with these diagnostics is to make sure you only call platform-specific APIs when running on an appropriate platform.</span></span> <span data-ttu-id="0bcc6-168">다음은 경고를 해결하는 데 사용할 수 있는 옵션입니다. 상황에 가장 적합한 것을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-168">Following are the options you can use to address the warnings; choose whichever is most appropriate for your situation:</span></span>

- <span data-ttu-id="0bcc6-169">**호출를 보호합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-169">**Guard the call**.</span></span> <span data-ttu-id="0bcc6-170">런타임에 코드를 조건부로 호출하여 이를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-170">You can achieve this by conditionally calling the code at run time.</span></span> <span data-ttu-id="0bcc6-171">플랫폼 검사 방법 중 하나(예: `OperatingSystem.Is<Platform>()` 또는 `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`)를 사용하여 원하는 `Platform`에서 실행하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-171">Check whether you’re running on a desired `Platform` by using one of platform-check methods, for example, `OperatingSystem.Is<Platform>()` or `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span></span>

- <span data-ttu-id="0bcc6-172">**호출 사이트를 플랫폼별로 표시합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-172">**Mark the call site as platform-specific**.</span></span> <span data-ttu-id="0bcc6-173">사용자 고유의 API를 플랫폼별로 표시하여 요구 사항을 효과적으로 호출자에게 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-173">You can also choose to mark your own APIs as being platform-specific, thus effectively just forwarding the requirements to your callers.</span></span> <span data-ttu-id="0bcc6-174">참조되는 플랫폼 종속 호출과 동일한 특성을 사용하여 포함하는 메서드나 형식 또는 전체 어셈블리를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-174">Mark the containing method or type or the entire assembly with the same attributes as the referenced platform-dependent call.</span></span> <span data-ttu-id="0bcc6-175">[예제](#mark-call-site-as-platform-specific).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-175">[Examples](#mark-call-site-as-platform-specific).</span></span>

- <span data-ttu-id="0bcc6-176">**플랫폼 검사를 사용하여 호출 사이트를 어설션합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-176">**Assert the call site with platform check**.</span></span> <span data-ttu-id="0bcc6-177">런타임에 추가 `if` 문의 오버헤드를 원친 않는 경우 대신 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-177">If you don't want the overhead of an additional `if` statement at run time, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0bcc6-178">[예제](#assert-the-call-site-with-platform-check).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-178">[Example](#assert-the-call-site-with-platform-check).</span></span>

- <span data-ttu-id="0bcc6-179">**코드를 삭제합니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-179">**Delete the code**.</span></span> <span data-ttu-id="0bcc6-180">Windows 사용자가 코드를 사용할 때 충실도가 상실되다는 의미이므로 일반적으로 개발자가 원하는 옵션은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-180">Generally not what you want because it means you lose fidelity when your code is used by Windows users.</span></span> <span data-ttu-id="0bcc6-181">플랫폼 간 대안이 있는 경우 플랫폼별 API를 통해 사용하는 것이 더 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-181">For cases where a cross-platform alternative exists, you’re likely better off using that over platform-specific APIs.</span></span>

- <span data-ttu-id="0bcc6-182">**경고를 표시하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-182">**Suppress the warning**.</span></span> <span data-ttu-id="0bcc6-183">editor.config 또는 `#pragma warning disable ca1416`를 통해 경고를 표시하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-183">You can also simply suppress the warning, either via editor.config or `#pragma warning disable ca1416`.</span></span> <span data-ttu-id="0bcc6-184">그러나 플랫폼별 API를 사용하는 경우 이 옵션은 마지막 수단이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-184">However, this option should be a last resort when using platform-specific APIs.</span></span>

### <a name="guard-platform-specific-apis-with-guard-methods"></a><span data-ttu-id="0bcc6-185">가드 메서드를 사용하여 플랫폼별 API를 보호</span><span class="sxs-lookup"><span data-stu-id="0bcc6-185">Guard platform-specific APIs with guard methods</span></span>

<span data-ttu-id="0bcc6-186">가드 메서드의 플랫폼 이름은 호출하는 플랫폼 종속 API 플랫폼 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-186">The guard method's platform name should match with the calling platform-dependent API platform name.</span></span> <span data-ttu-id="0bcc6-187">호출하는 API의 플랫폼 문자열에 버전이 포함되는 경우</span><span class="sxs-lookup"><span data-stu-id="0bcc6-187">If the platform string of the calling API includes the version:</span></span>

- <span data-ttu-id="0bcc6-188">`[SupportedOSPlatform("platformVersion")]` 특성의 경우 가드 메서드 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-188">For the `[SupportedOSPlatform("platformVersion")]` attribute, the guard method platform `version` should be greater than or equal to the calling platform's `Version`.</span></span>
- <span data-ttu-id="0bcc6-189">`[UnsupportedOSPlatform("platformVersion")]` 특성의 경우 가드 메서드 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-189">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the guard method's platform `version` should be less than or equal to the calling platform's `Version`.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- <span data-ttu-id="0bcc6-190">새 <xref:System.OperatingSystem> API를 사용할 수 없는 netstandard.또는 netcoreapp을 대상으로 하는 코드를 보호해야 하는 경우 <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API를 사용할 수 있으며 분석기에서 이 API가 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-190">if you need to guard a code that targets netstandard or netcoreapp where new <xref:System.OperatingSystem> APIs are not available <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API can be used and will be respected by the analyzer.</span></span> <span data-ttu-id="0bcc6-191">하지만 <xref:System.OperatingSystem>에 추가된 새 API만큼 최적화되지는 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-191">But it's not as optimized as the new APIs added in <xref:System.OperatingSystem>.</span></span> <span data-ttu-id="0bcc6-192"><xref:System.Runtime.InteropServices.OSPlatform> 구조체에서 플랫폼이 지원되지 않는 경우 <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform")을 사용할 수 있습니다(분석기에서도 적용됨).</span><span class="sxs-lookup"><span data-stu-id="0bcc6-192">In case the platform is not supported in <xref:System.Runtime.InteropServices.OSPlatform> struct, you can use <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform") which is also respected by the analyzer.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a><span data-ttu-id="0bcc6-193">호출 사이트를 플랫폼별로 표시</span><span class="sxs-lookup"><span data-stu-id="0bcc6-193">Mark call site as platform-specific</span></span>

<span data-ttu-id="0bcc6-194">플랫폼 이름은 호출하는 플랫폼 종속 API와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-194">Platform names should match the calling platform-dependent API.</span></span> <span data-ttu-id="0bcc6-195">플랫폼 문자열에 버전이 포함되는 경우</span><span class="sxs-lookup"><span data-stu-id="0bcc6-195">If the platform string includes a version:</span></span>

- <span data-ttu-id="0bcc6-196">`[SupportedOSPlatform("platformVersion")]` 특성의 경우 호출 사이트 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-196">For the `[SupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be greater than or equal to the calling platform's `Version`</span></span>
- <span data-ttu-id="0bcc6-197">`[UnsupportedOSPlatform("platformVersion")]` 특성의 경우 호출 사이트 플랫폼 `version`이 호출하는 플랫폼의 `Version`보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-197">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be less than or equal to the calling platform's `Version`</span></span>

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a><span data-ttu-id="0bcc6-198">플랫폼 검사를 사용하여 호출 사이트를 어설션</span><span class="sxs-lookup"><span data-stu-id="0bcc6-198">Assert the call-site with platform check</span></span>

<span data-ttu-id="0bcc6-199">[플랫폼 가드 예제](#guard-platform-specific-apis-with-guard-methods)에서 사용되는 모든 조건부 검사는 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>에 대한 조건으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcc6-199">All the conditional checks used in the [platform guard examples](#guard-platform-specific-apis-with-guard-methods) can also be used as the condition for <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span>

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a><span data-ttu-id="0bcc6-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bcc6-200">See also</span></span>

- [<span data-ttu-id="0bcc6-201">.NET 5의 대상 프레임워크 이름</span><span class="sxs-lookup"><span data-stu-id="0bcc6-201">Target Framework Names in .NET 5</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [<span data-ttu-id="0bcc6-202">API에 플랫폼별 주석 달기 및 사용 검색</span><span class="sxs-lookup"><span data-stu-id="0bcc6-202">Annotating platform-specific APIs and detecting its use</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [<span data-ttu-id="0bcc6-203">API에 특정 플랫폼에서 지원되지 않음 주석 달기</span><span class="sxs-lookup"><span data-stu-id="0bcc6-203">Annotating APIs as unsupported on specific platforms</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [<span data-ttu-id="0bcc6-204">CA1416 플랫폼 호환성 분석기</span><span class="sxs-lookup"><span data-stu-id="0bcc6-204">CA1416 Platform compatibility analyzer</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="0bcc6-205">.NET API 분석기</span><span class="sxs-lookup"><span data-stu-id="0bcc6-205">.NET API analyzer</span></span>](../../standard/analyzers/api-analyzer.md)
