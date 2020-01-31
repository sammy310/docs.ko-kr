---
title: .NET 라이브러리에 대한 플랫폼 간 대상 지정
description: 플랫폼 간 .NET 라이브러리를 만드는 모범 사례 권장 사항입니다.
ms.date: 08/12/2019
ms.openlocfilehash: 61adff3759984554bb83531b4f9d8a49e29c929c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731455"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="11dae-103">플랫폼 간 대상 지정</span><span class="sxs-lookup"><span data-stu-id="11dae-103">Cross-platform targeting</span></span>

<span data-ttu-id="11dae-104">최신 .NET은 여러 운영 체제와 디바이스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="11dae-105">.NET 오픈 소스 라이브러리는 Azure에 호스트되는 ASP.NET 웹 사이트를 빌드하든, Unity에서 .NET 게임을 빌드하든 간에, 가능한 한 많은 개발자를 지원하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="11dae-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="11dae-106">.NET Standard</span></span>

<span data-ttu-id="11dae-107">.NET Standard는 .NET 라이브러리에 플랫폼 간 지원을 추가하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="11dae-108">[.NET Standard](../net-standard.md)는 모든 .NET 구현에서 사용할 수 있는 .NET API 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="11dae-109">.NET Standard를 대상으로 지정하면, 지정된 .NET Standard 버전에 있는 API를 사용하도록 제한된 라이브러리를 생성할 수 있습니다. 이 경우, 해당 버전의 .NET Standard를 구현하는 모든 플랫폼에서 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of the .NET Standard.</span></span>

<span data-ttu-id="11dae-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="11dae-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="11dae-111">.NET Standard를 대상으로 지정하고 프로젝트를 성공적으로 컴파일한다고 해서 라이브러리가 모든 플랫폼에서 실행되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="11dae-112">플랫폼 특정 API는 다른 플랫폼에서 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="11dae-113">예를 들어 <xref:Microsoft.Win32.Registry?displayProperty=nameWithType>은 Windows에서 성공하지만, 다른 OS에서 사용할 때는 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="11dae-114">API가 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-114">APIs can behave differently.</span></span> <span data-ttu-id="11dae-115">예를 들어 애플리케이션이 iOS 또는 UWP에서 Ahead-Of-Time 컴파일을 사용할 때 리플렉션 API는 서로 다른 성능 특성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="11dae-116">.NET 팀은 가능한 문제 검색에 도움이 되는 [Roslyn 분석기를 제공](../analyzers/api-analyzer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="11dae-117">✔️ `netstandard2.0` 대상을 포함하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-117">✔️ DO start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="11dae-118">대부분의 범용 라이브러리는 .NET Standard 2.0 외부의 API가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="11dae-119">.NET Standard 2.0은 모든 최신 플랫폼에서 지원되며, 하나의 대상으로 여러 플랫폼을 지원하는 권장 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="11dae-120">❌`netstandard1.x` 대상을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-120">❌ AVOID including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="11dae-121">.NET Standard 1.x는 세분화된 NuGet 패키지 집합으로 배포되어 큰 패키지 종속성 그래프를 만들기 때문에 개발자가 빌드 시 많은 패키지를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="11dae-122">.NET Framework 4.6.1, UWP 및 Xamarin을 포함한 최신 .NET 플랫폼은 모두 .NET Standard 2.0을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="11dae-123">특별히 이전 플랫폼을 대상으로 지정해야 하는 경우에만 .NET Standard 1.x를 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="11dae-124">✔️ `netstandard1.x` 대상이 필요한 경우 `netstandard2.0` 대상을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-124">✔️ DO include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="11dae-125">이전 플랫폼도 계속 작동하고 `netstandard1.x` 대상을 사용하도록 대체되는 동시에, .NET Standard 2.0을 지원하는 모든 플랫폼은 `netstandard2.0` 대상을 사용하고 더 작은 패키지 그래프의 혜택을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="11dae-126">❌ 라이브러리가 플랫폼 특정 앱 모델을 사용하는 경우 .NET Standard 대상을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-126">❌ DO NOT include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="11dae-127">예를 들어 UWP 제어 도구 키트 라이브러리는 UWP에서만 사용할 수 있는 앱 모델에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="11dae-128">앱 모델 특정 API는 .NET Standard에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="11dae-129">멀티 타기팅</span><span class="sxs-lookup"><span data-stu-id="11dae-129">Multi-targeting</span></span>

<span data-ttu-id="11dae-130">라이브러리에서 프레임워크 특정 API에 액세스해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="11dae-131">프레임워크 특정 API를 호출하는 가장 좋은 방법은 단일 프레임워크가 아니라 많은 [.NET 대상 프레임워크](../frameworks.md)용으로 사용자 프로젝트를 빌드하는 멀티 타기팅을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="11dae-132">소비자가 개별 프레임워크용으로 빌드할 필요가 없도록 보호하려면 .NET Standard 출력과 하나 이상의 프레임워크 특정 출력을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="11dae-133">멀티 타기팅을 사용하면 모든 어셈블리가 단일 NuGet 패키지 안에 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="11dae-134">그러면 소비자가 동일한 패키지를 참조할 수 있으며, NuGet이 적절한 구현을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="11dae-135">NuGet 패키지가 프레임워크 특정 구현을 제공하는 경우를 제외하고, 사용자 .NET Standard 라이브러리는 모든 곳에서 사용되는 대체 라이브러리 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="11dae-136">멀티 타기팅을 통해 코드에서 조건부 컴파일을 사용하고 프레임워크 특정 API를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="11dae-137">![여러 어셈블리를 포함하는 NuGet 패키지](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "여러 어셈블리를 포함하는 NuGet 패키지")</span><span class="sxs-lookup"><span data-stu-id="11dae-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="11dae-138">✔️ .NET Standard 외에도 .NET 구현을 대상으로 지정하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-138">✔️ CONSIDER targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="11dae-139">.NET 구현을 대상으로 지정하면 .NET Standard 외부에 있는 플랫폼 특정 API를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="11dae-140">이때 .NET Standard에 대한 지원을 삭제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="11dae-141">대신, 구현에서 throw하고 기능 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="11dae-142">이렇게 하면 사용자 라이브러리를 어느 곳에서나 사용할 수 있으며 런타임 기능 강화가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="11dae-143">❌ 모든 대상에 대해 소스 코드가 동일한 경우 .NET Standard 대상 지정뿐만 아니라 멀티 타기팅도 피하세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-143">❌ AVOID multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="11dae-144">NuGet에서 자동으로 .NET Standard 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="11dae-145">개별 .NET 구현을 대상으로 지정하면 아무 혜택 없이 `*.nupkg` 크기만 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="11dae-146">✔️ `netstandard2.0` 대상을 제공할 때 `net461`의 대상을 추가하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-146">✔️ CONSIDER adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="11dae-147">.NET Framework의 .NET Standard 2.0을 사용하는 경우 .NET Framework 4.7.2에서 해결된 몇 가지 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="11dae-148">.NET Framework 4.6.1용으로 빌드된 이진을 제공하면 여전히 .NET Framework 4.6.1 - 4.7.1을 사용 중인 개발자의 경험을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="11dae-149">✔️ NuGet 패키지를 사용하여 라이브러리를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-149">✔️ DO distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="11dae-150">NuGet은 개발자에게 가장 적합한 대상을 선택하여 적절한 구현을 선택할 필요가 없도록 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="11dae-151">✔️ 멀티 타기팅 시 프로젝트 파일의 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-151">✔️ DO use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="11dae-152">✔️ UWP 및 Xamarin에 대한 멀티 타기팅 시 [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras)를 사용합니다. 그러면 프로젝트 파일이 훨씬 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-152">✔️ CONSIDER using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="11dae-153">이전 대상</span><span class="sxs-lookup"><span data-stu-id="11dae-153">Older targets</span></span>

<span data-ttu-id="11dae-154">.NET은 더 이상 일반적으로 사용되지 않는 플랫폼뿐만 아니라 오래전에 지원이 중단된 .NET Framework 버전을 대상으로 지정할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="11dae-155">가능한 한 많은 대상에서 라이브러리가 작동하도록 하는 것은 중요하지만, 누락된 API를 해결하기 위해 상당한 오버헤드가 추가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="11dae-156">특정 프레임워크는 도달률 및 제한 사항을 고려할 때 더 이상 대상으로 지정할 가치가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="11dae-157">❌ PCL(이식 가능한 클래스 라이브러리) 대상을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-157">❌ DO NOT include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="11dae-158">예: `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="11dae-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="11dae-159">.NET Standard는 플랫폼 간 .NET 라이브러리를 지원하는 최신 방법으로, PCL을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="11dae-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="11dae-160">❌ 더 이상 지원되지 않는 .NET 플랫폼의 대상을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="11dae-160">❌ DO NOT include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="11dae-161">예: `SL4`, `WP`</span><span class="sxs-lookup"><span data-stu-id="11dae-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="11dae-162">[이전](get-started.md)
>[다음](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="11dae-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
