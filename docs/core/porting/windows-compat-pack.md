---
title: Windows 호환성 팩을 사용하여 코드 포팅
description: Windows 호환성 팩에 대해 알아보고 이를 사용하여 기존 .NET Framework 코드를 .NET 5 및 .NET Core 3.1로 포팅하는 방법을 알아봅니다.
author: terrajobst
ms.date: 03/04/2021
ms.openlocfilehash: c90cc960cd9ff3707877afc023f95e0e03716aab
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604816"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-5"></a><span data-ttu-id="7051e-103">Windows 호환성 팩을 사용하여 코드를 .NET 5 이상으로 포팅</span><span class="sxs-lookup"><span data-stu-id="7051e-103">Use the Windows Compatibility Pack to port code to .NET 5+</span></span>

<span data-ttu-id="7051e-104">기존 코드를 .NET Framework에서 .NET으로 포팅할 때 가장 일반적인 문제 중 일부는 .NET Framework에만 있는 API 및 기술에 대한 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-104">Some of the most common issues found when porting existing code from .NET Framework to .NET are dependencies on APIs and technologies that are only found in .NET Framework.</span></span> <span data-ttu-id="7051e-105">*Windows 호환성 팩* 은 이러한 기술을 대부분 제공하므로 .NET 애플리케이션과 .NET Standard 라이브러리를 훨씬 쉽게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET applications and .NET Standard libraries.</span></span>

<span data-ttu-id="7051e-106">호환성 팩은 API 집합을 크게 늘리는 [.NET Standard 2.0의 논리적 확장](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support)입니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-106">The compatibility pack is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases the API set.</span></span> <span data-ttu-id="7051e-107">기존 코드는 거의 수정하지 않고 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-107">Existing code compiles with almost no modifications.</span></span> <span data-ttu-id="7051e-108">"모든 .NET 구현이 제공하는 API 집합" 약속을 지키기 위해 .NET Standard에는 레지스트리, WMI(Windows Management Instrumentation) 또는 리플렉션 내보내기 API와 같은 모든 플랫폼에서 작동할 수 없는 기술은 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-108">To keep its promise of "the set of APIs that all .NET implementations provide", .NET Standard doesn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span> <span data-ttu-id="7051e-109">Windows 호환 기능 팩은 .NET Standard의 위에 있으며 해당 Windows 전용 기술에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-109">The Windows Compatibility Pack sits on top of .NET Standard and provides access to these Windows-only technologies.</span></span> <span data-ttu-id="7051e-110">.NET으로 이동하려고 하지만 적어도 첫 번째 단계로 Windows에 머물려는 고객에게 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-110">It's especially useful for customers that want to move to .NET but plan to stay on Windows, at least as a first step.</span></span> <span data-ttu-id="7051e-111">이 시나리오에서는 Windows 전용 기술을 사용하여 마이그레이션 장애물을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-111">In that scenario, you can use Windows-only technologies removes the migration hurdle.</span></span>

## <a name="package-contents"></a><span data-ttu-id="7051e-112">패키지 내용</span><span class="sxs-lookup"><span data-stu-id="7051e-112">Package contents</span></span>

<span data-ttu-id="7051e-113">Windows 호환성 팩은 [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 통해 제공되며 .NET 또는 .NET Standard를 대상으로 하는 프로젝트에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-113">The Windows Compatibility Pack is provided via the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects that target .NET or .NET Standard.</span></span>

<span data-ttu-id="7051e-114">다음 기술 영역에서 Windows 전용 및 플랫폼 간 API를 포함하여 약 20,000개의 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-114">It provides about 20,000 APIs, including Windows-only and cross-platform APIs from the following technology areas:</span></span>

- <span data-ttu-id="7051e-115">코드 페이지</span><span class="sxs-lookup"><span data-stu-id="7051e-115">Code Pages</span></span>
- <span data-ttu-id="7051e-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="7051e-116">CodeDom</span></span>
- <span data-ttu-id="7051e-117">구성</span><span class="sxs-lookup"><span data-stu-id="7051e-117">Configuration</span></span>
- <span data-ttu-id="7051e-118">디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="7051e-118">Directory Services</span></span>
- <span data-ttu-id="7051e-119">그리기</span><span class="sxs-lookup"><span data-stu-id="7051e-119">Drawing</span></span>
- <span data-ttu-id="7051e-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="7051e-120">ODBC</span></span>
- <span data-ttu-id="7051e-121">권한</span><span class="sxs-lookup"><span data-stu-id="7051e-121">Permissions</span></span>
- <span data-ttu-id="7051e-122">포트</span><span class="sxs-lookup"><span data-stu-id="7051e-122">Ports</span></span>
- <span data-ttu-id="7051e-123">Windows ACL(액세스 제어 목록)</span><span class="sxs-lookup"><span data-stu-id="7051e-123">Windows Access Control Lists (ACL)</span></span>
- <span data-ttu-id="7051e-124">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="7051e-124">Windows Communication Foundation (WCF)</span></span>
- <span data-ttu-id="7051e-125">Windows Cryptography</span><span class="sxs-lookup"><span data-stu-id="7051e-125">Windows Cryptography</span></span>
- <span data-ttu-id="7051e-126">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="7051e-126">Windows EventLog</span></span>
- <span data-ttu-id="7051e-127">Windows Management Instrumentation(WMI)</span><span class="sxs-lookup"><span data-stu-id="7051e-127">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="7051e-128">Windows 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="7051e-128">Windows Performance Counters</span></span>
- <span data-ttu-id="7051e-129">Windows 레지스트리</span><span class="sxs-lookup"><span data-stu-id="7051e-129">Windows Registry</span></span>
- <span data-ttu-id="7051e-130">Windows 런타임 캐싱</span><span class="sxs-lookup"><span data-stu-id="7051e-130">Windows Runtime Caching</span></span>
- <span data-ttu-id="7051e-131">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="7051e-131">Windows Services</span></span>

<span data-ttu-id="7051e-132">자세한 내용은 [호환성 팩의 사양](https://github.com/dotnet/designs/blob/master/accepted/2018/compat-pack/compat-pack.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7051e-132">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/2018/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="7051e-133">시작하기</span><span class="sxs-lookup"><span data-stu-id="7051e-133">Get started</span></span>

1. <span data-ttu-id="7051e-134">이식하기 전에 [이식 프로세스](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7051e-134">Before porting, make sure to take a look at the [Porting process](index.md).</span></span>

2. <span data-ttu-id="7051e-135">기존 코드를 .NET 또는 .NET Standard로 이식하는 경우 [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-135">When porting existing code to .NET or .NET Standard, install the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

   <span data-ttu-id="7051e-136">Windows에서 유지하려는 경우 모두 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-136">If you want to stay on Windows, you're all set.</span></span>

3. <span data-ttu-id="7051e-137">Linux 또는 macOS에서 .NET 애플리케이션 또는 .NET Standard 라이브러리를 실행하려는 경우 [API 분석기](../../standard/analyzers/api-analyzer.md)를 사용하여 플랫폼 간에 작동하지 않는 API의 사용량을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-137">If you want to run the .NET application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

4. <span data-ttu-id="7051e-138">이러한 API의 사용량을 제거하거나 플랫폼 간 대체 방법으로 바꾸거나 다음과 같은 플랫폼 검사를 사용하여 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7051e-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="7051e-139">데모의 경우 [Windows 호환 기능 팩의 Channel 9 비디오](https://channel9.msdn.com/Events/Connect/2017/T123)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7051e-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

## <a name="see-also"></a><span data-ttu-id="7051e-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7051e-140">See also</span></span>

- [<span data-ttu-id="7051e-141">.NET Framework에서 .NET으로 포팅 개요</span><span class="sxs-lookup"><span data-stu-id="7051e-141">Overview of porting from .NET Framework to .NET</span></span>](index.md)
- [<span data-ttu-id="7051e-142">ASP.NET에서 ASP.NET Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7051e-142">ASP.NET to ASP.NET Core migration</span></span>](/aspnet/core/migration/proper-to-2x)
- [<span data-ttu-id="7051e-143">.NET Framework WPF 앱을 .NET으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7051e-143">Migrate .NET Framework WPF apps to .NET</span></span>](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [<span data-ttu-id="7051e-144">.NET Framework Windows Forms 앱을 .NET으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7051e-144">Migrate .NET Framework Windows Forms apps to .NET</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
- [<span data-ttu-id="7051e-145">.NET으로 .NET Framework 라이브러리 포팅</span><span class="sxs-lookup"><span data-stu-id="7051e-145">Port .NET Framework libraries to .NET</span></span>](libraries.md)
