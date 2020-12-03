---
title: '호환성이 손상되는 변경: 확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759727"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="493ef-103">확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용</span><span class="sxs-lookup"><span data-stu-id="493ef-103">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="493ef-104">[aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411)에 설명된 대로 [dotnet/extensions](https://github.com/dotnet/extensions) 리포지토리에서 [dotnet/runtime](https://github.com/dotnet/runtime)으로 일부 `Microsoft.Extensions.*` NuGet 패키지를 마이그레이션하면 패키징 변경 내용이 마이그레이션된 일부 패키지에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-104">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="493ef-105">이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="493ef-105">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="493ef-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="493ef-106">Version introduced</span></span>

<span data-ttu-id="493ef-107">5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="493ef-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="493ef-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="493ef-108">Old behavior</span></span>

<span data-ttu-id="493ef-109">일부 `Microsoft.Extensions.*` 패키지에는 앱이 사용하는 API의 패키지 참조가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-109">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="493ef-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="493ef-110">New behavior</span></span>

<span data-ttu-id="493ef-111">앱이 `Microsoft.Extensions.*` 패키지 종속성을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-111">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="493ef-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="493ef-112">Reason for change</span></span>

<span data-ttu-id="493ef-113">*dotnet/runtime* 리포지토리에 더 잘 맞도록 패키징 정책이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-113">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="493ef-114">새 정책에 따라 사용되지 않는 패키지 참조는 패키징 중에 *.nupkg* 파일에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-114">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="493ef-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="493ef-115">Recommended action</span></span>

<span data-ttu-id="493ef-116">제거된 패키지 종속성의 API를 사용하는 경우 영향을 받는 패키지의 소비자는 프로젝트에서 제거된 패키지 종속성에 대한 직접 종속성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-116">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="493ef-117">다음 표에는 영향을 받는 패키지와 해당 변경 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-117">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="493ef-118">패키지 이름</span><span class="sxs-lookup"><span data-stu-id="493ef-118">Package name</span></span>|<span data-ttu-id="493ef-119">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="493ef-119">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="493ef-120">Microsoft.Extensions.Configuration.Binder</span><span class="sxs-lookup"><span data-stu-id="493ef-120">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="493ef-121">`Microsoft.Extensions.Configuration`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-121">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="493ef-122">Microsoft.Extensions.Configuration.Json</span><span class="sxs-lookup"><span data-stu-id="493ef-122">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="493ef-123">`System.Threading.Tasks.Extensions`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-123">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="493ef-124">Microsoft.Extensions.Hosting.Abstractions</span><span class="sxs-lookup"><span data-stu-id="493ef-124">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="493ef-125">`Microsoft.Extensions.Logging.Abstractions`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-125">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="493ef-126">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="493ef-126">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="493ef-127">`Microsoft.Extensions.Configuration.Binder`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-127">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="493ef-128">Microsoft.Extensions.Logging.Console</span><span class="sxs-lookup"><span data-stu-id="493ef-128">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="493ef-129">`Microsoft.Extensions.Configuration.Abstractions`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-129">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="493ef-130">Microsoft.Extensions.Logging.EventLog</span><span class="sxs-lookup"><span data-stu-id="493ef-130">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="493ef-131">.NET Framework 4.6.1 대상 프레임워크 모니커의 `System.Diagnostics.EventLog`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-131">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="493ef-132">Microsoft.Extensions.Logging.EventSource</span><span class="sxs-lookup"><span data-stu-id="493ef-132">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="493ef-133">`System.Threading.Tasks.Extensions`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-133">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="493ef-134">Microsoft.Extensions.Options</span><span class="sxs-lookup"><span data-stu-id="493ef-134">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="493ef-135">`System.ComponentModel.Annotations`에 대한 참조가 제거됨</span><span class="sxs-lookup"><span data-stu-id="493ef-135">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="493ef-136">예를 들어 `Microsoft.Extensions.Configuration`에 대한 패키지 참조가 `Microsoft.Extensions.Configuration.Binder`에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-136">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="493ef-137">종속성의 API가 패키지에서 사용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-137">No API from the dependency was used in the package.</span></span> <span data-ttu-id="493ef-138">`Microsoft.Extensions.Configuration`의 API를 사용하는 `Microsoft.Extensions.Configuration.Binder`의 사용자는 프로젝트에서 이에 대한 직접 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="493ef-138">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="493ef-139">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="493ef-139">Affected APIs</span></span>

<span data-ttu-id="493ef-140">없음</span><span class="sxs-lookup"><span data-stu-id="493ef-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
