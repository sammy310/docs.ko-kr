---
ms.openlocfilehash: d598d8d3203e804e5e935c3564b0053f9fc2e9a6
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84145005"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a><span data-ttu-id="0b75d-101">공유 프레임워크: Microsoft.AspNetCore.App에서 제거되는 어셈블리</span><span class="sxs-lookup"><span data-stu-id="0b75d-101">Shared framework: Assemblies removed from Microsoft.AspNetCore.App</span></span>

<span data-ttu-id="0b75d-102">ASP.NET Core 3.0부터 ASP.NET Core 공유 프레임워크(`Microsoft.AspNetCore.App`)에는 Microsoft에서 완전히 개발하고, 지원하고, 서비스를 제공하는 자사 어셈블리만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-102">Starting in ASP.NET Core 3.0, the ASP.NET Core shared framework (`Microsoft.AspNetCore.App`) only contains first-party assemblies that are fully developed, supported, and serviceable by Microsoft.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0b75d-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0b75d-103">Change description</span></span>

<span data-ttu-id="0b75d-104">이러한 변경은 ASP.NET Core "플랫폼"의 경계를 다시 정의하는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-104">Think of the change as the redefining of boundaries for the ASP.NET Core "platform."</span></span> <span data-ttu-id="0b75d-105">공유 프레임워크는 [GitHub를 통해 누구나 원본으로 빌드](https://github.com/dotnet/source-build)할 수 있으며, .NET Core 공유 프레임워크의 기존 이점을 앱에 계속 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-105">The shared framework will be [source-buildable by anybody via GitHub](https://github.com/dotnet/source-build) and will continue to offer the existing benefits of .NET Core shared frameworks to your apps.</span></span> <span data-ttu-id="0b75d-106">몇 가지 이점으로 더 작은 배포 크기, 중앙 집중식 패치, 더 빠른 시작 시간 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-106">Some benefits include smaller deployment size, centralized patching, and faster startup time.</span></span>

<span data-ttu-id="0b75d-107">변경의 일부로 몇 가지 주목할 만한 호환성이 손상되는 변경이 `Microsoft.AspNetCore.App`에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-107">As part of the change, some notable breaking changes are introduced in `Microsoft.AspNetCore.App`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0b75d-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0b75d-108">Version introduced</span></span>

<span data-ttu-id="0b75d-109">3.0</span><span class="sxs-lookup"><span data-stu-id="0b75d-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0b75d-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="0b75d-110">Old behavior</span></span>

<span data-ttu-id="0b75d-111">프로젝트는 프로젝트 파일의 `<PackageReference>` 요소를 통해 `Microsoft.AspNetCore.App`을 참조했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-111">Projects referenced `Microsoft.AspNetCore.App` via a `<PackageReference>` element in the project file.</span></span>

<span data-ttu-id="0b75d-112">또한 `Microsoft.AspNetCore.App`에는 다음과 같은 하위 구성 요소가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-112">Additionally, `Microsoft.AspNetCore.App` contained the following subcomponents:</span></span>

- <span data-ttu-id="0b75d-113">Json.NET(`Newtonsoft.Json`)</span><span class="sxs-lookup"><span data-stu-id="0b75d-113">Json.NET (`Newtonsoft.Json`)</span></span>
- <span data-ttu-id="0b75d-114">Entity Framework Core(접두사가 `Microsoft.EntityFrameworkCore.`인 어셈블리)</span><span class="sxs-lookup"><span data-stu-id="0b75d-114">Entity Framework Core (assemblies prefixed with `Microsoft.EntityFrameworkCore.`)</span></span>
- <span data-ttu-id="0b75d-115">Roslyn(`Microsoft.CodeAnalysis`)</span><span class="sxs-lookup"><span data-stu-id="0b75d-115">Roslyn (`Microsoft.CodeAnalysis`)</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0b75d-116">새 동작</span><span class="sxs-lookup"><span data-stu-id="0b75d-116">New behavior</span></span>

<span data-ttu-id="0b75d-117">`Microsoft.AspNetCore.App`에 대한 참조에는 더 이상 프로젝트 파일의 `<PackageReference>` 요소가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-117">A reference to `Microsoft.AspNetCore.App` no longer requires a `<PackageReference>` element in the project file.</span></span> <span data-ttu-id="0b75d-118">.NET Core SDK는 `<PackageReference>`의 사용을 대체하는 `<FrameworkReference>`라는 새 요소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-118">The .NET Core SDK supports a new element called `<FrameworkReference>`, which replaces the use of `<PackageReference>`.</span></span>

<span data-ttu-id="0b75d-119">자세한 내용은 [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-119">For more information, see [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span></span>

<span data-ttu-id="0b75d-120">Entity Framework Core는 NuGet 패키지로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-120">Entity Framework Core ships as NuGet packages.</span></span> <span data-ttu-id="0b75d-121">이 변경은 배송 모델을 .NET의 다른 모든 데이터 액세스 라이브러리와 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-121">This change aligns the shipping model with all other data access libraries on .NET.</span></span> <span data-ttu-id="0b75d-122">다양한 .NET 플랫폼을 지원하면서 계속 혁신할 수 있는 가장 간단한 경로인 Entity Framework Core를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-122">It provides Entity Framework Core the simplest path to continue innovating while supporting the various .NET platforms.</span></span> <span data-ttu-id="0b75d-123">Entity Framework Core를 공유 프레임워크 밖으로 이동하더라도 Microsoft에서 개발하고, 지원하고, 서비스를 제공하는 라이브러리의 상태에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-123">The move of Entity Framework Core out of the shared framework has no impact on its status as a Microsoft-developed, supported, and serviceable library.</span></span> <span data-ttu-id="0b75d-124">[.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)에서는 이를 계속 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-124">The [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) continues to cover it.</span></span>

<span data-ttu-id="0b75d-125">Json.NET 및 Entity Framework Core는 ASP.NET Core를 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-125">Json.NET and Entity Framework Core continue to work with ASP.NET Core.</span></span> <span data-ttu-id="0b75d-126">그러나 공유 프레임워크에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-126">They won't, however, be included in the shared framework.</span></span>

<span data-ttu-id="0b75d-127">자세한 내용은 [.NET Core 3.0에서 JSON의 미래](https://github.com/dotnet/announcements/issues/90)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-127">For more information, see [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90).</span></span> <span data-ttu-id="0b75d-128">또한 공유 프레임워크에서 제거된 [이진 파일의 전체 목록](https://github.com/dotnet/aspnetcore/issues/3755)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-128">Also see [the complete list of binaries](https://github.com/dotnet/aspnetcore/issues/3755) removed from the shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0b75d-129">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0b75d-129">Reason for change</span></span>

<span data-ttu-id="0b75d-130">이 변경으로 인해 `Microsoft.AspNetCore.App`의 사용이 간소화되고 NuGet 패키지와 공유 프레임워크 간의 중복이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-130">This change simplifies the consumption of `Microsoft.AspNetCore.App` and reduces the duplication between NuGet packages and shared frameworks.</span></span>

<span data-ttu-id="0b75d-131">이 변경의 동기에 대한 자세한 내용은 [이 블로그 게시물](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-131">For more information on the motivation for this change, see [this blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0b75d-132">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0b75d-132">Recommended action</span></span>

<span data-ttu-id="0b75d-133">프로젝트에서 `Microsoft.AspNetCore.App`의 어셈블리를 NuGet 패키지로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-133">It won't be necessary for projects to consume assemblies in `Microsoft.AspNetCore.App` as NuGet packages.</span></span> <span data-ttu-id="0b75d-134">ASP.NET Core 공유 프레임워크의 대상 지정 및 사용을 간소화하기 위해 ASP.NET Core 1.0 이후에 제공된 많은 NuGet 패키지가 더 이상 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-134">To simplify the targeting and usage of the ASP.NET Core shared framework, many NuGet packages shipped since ASP.NET Core 1.0 are no longer produced.</span></span> <span data-ttu-id="0b75d-135">이러한 패키지에서 제공하는 API는 `<FrameworkReference>`를 `Microsoft.AspNetCore.App`에 사용하여 앱에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-135">The APIs those packages provide are still available to apps by using a `<FrameworkReference>` to `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="0b75d-136">일반적인 API의 예로 Kestrel, MVC 및 Razor가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-136">Common API examples include Kestrel, MVC, and Razor.</span></span>

<span data-ttu-id="0b75d-137">이 변경은 ASP.NET Core 2.x의 `Microsoft.AspNetCore.App`을 통해 참조되는 모든 이진 파일에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-137">This change doesn't apply to all binaries referenced via `Microsoft.AspNetCore.App` in ASP.NET Core 2.x.</span></span> <span data-ttu-id="0b75d-138">주목할 만한 예외는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-138">Notable exceptions include:</span></span>

- <span data-ttu-id="0b75d-139">.NET Standard를 계속 대상으로 하는 `Microsoft.Extensions` 라이브러리는 NuGet 패키지로 사용할 수 있습니다(<https://github.com/dotnet/extensions> 참조).</span><span class="sxs-lookup"><span data-stu-id="0b75d-139">`Microsoft.Extensions` libraries that continue to target .NET Standard will be available as NuGet packages (see <https://github.com/dotnet/extensions>).</span></span>
- <span data-ttu-id="0b75d-140">`Microsoft.AspNetCore.App`의 일부가 아닌 ASP.NET Core 팀에서 생성한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-140">APIs produced by the ASP.NET Core team that aren't part of `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="0b75d-141">예를 들어 NuGet 패키지로 사용할 수 있는 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-141">For example, the following components are available as NuGet packages:</span></span>
  - <span data-ttu-id="0b75d-142">Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="0b75d-142">Entity Framework Core</span></span>
  - <span data-ttu-id="0b75d-143">타사 통합 기능을 제공하는 API</span><span class="sxs-lookup"><span data-stu-id="0b75d-143">APIs that provide third-party integration</span></span>
  - <span data-ttu-id="0b75d-144">실험적 기능</span><span class="sxs-lookup"><span data-stu-id="0b75d-144">Experimental features</span></span>
  - <span data-ttu-id="0b75d-145">[공유 프레임워크에 있어야 하는 요구 사항을 충족](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)시킬 수 없는 종속성이 있는 API</span><span class="sxs-lookup"><span data-stu-id="0b75d-145">APIs with dependencies that couldn't [fulfill the requirements to be in the shared framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span></span>
- <span data-ttu-id="0b75d-146">Json.NET 지원을 유지하는 MVC 확장.</span><span class="sxs-lookup"><span data-stu-id="0b75d-146">Extensions to MVC that maintain support for Json.NET.</span></span> <span data-ttu-id="0b75d-147">API는 Json.NET 및 MVC 사용을 지원하기 위해 NuGet 패키지로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-147">An API will be provided as a NuGet package to support using Json.NET and MVC.</span></span>
- <span data-ttu-id="0b75d-148">SignalR .NET 클라이언트는 .NET Standard를 계속 지원하며 NuGet 패키지로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-148">The SignalR .NET client will continue to support .NET Standard and ship as a NuGet package.</span></span> <span data-ttu-id="0b75d-149">이는 Xamarin 및 UWP와 같은 많은 .NET 런타임에서 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b75d-149">It's intended for use on many .NET runtimes, such as Xamarin and UWP.</span></span>

<span data-ttu-id="0b75d-150">자세한 내용은 [3.0에서 공유 프레임워크 어셈블리용 패키지 생성 중지](https://github.com/dotnet/aspnetcore/issues/3756)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-150">For more information, see [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756).</span></span> <span data-ttu-id="0b75d-151">토론은 [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b75d-151">For discussion, see [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span></span>

#### <a name="category"></a><span data-ttu-id="0b75d-152">범주</span><span class="sxs-lookup"><span data-stu-id="0b75d-152">Category</span></span>

<span data-ttu-id="0b75d-153">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0b75d-153">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0b75d-154">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0b75d-154">Affected APIs</span></span>

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
