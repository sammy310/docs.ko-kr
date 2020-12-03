---
title: '호환성이 손상되는 변경: Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759731"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="6dbeb-103">Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함</span><span class="sxs-lookup"><span data-stu-id="6dbeb-103">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="6dbeb-104">ASP.NET Core 5.0 RC2 릴리스의 일부로 `ProtectedBrowserStorage` 기능을 ASP.NET Core 공유 프레임워크로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-104">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6dbeb-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6dbeb-105">Version introduced</span></span>

<span data-ttu-id="6dbeb-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="6dbeb-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6dbeb-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6dbeb-107">Old behavior</span></span>

<span data-ttu-id="6dbeb-108">ASP.NET Core 5.0 Preview 8에서 이 기능은 [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) 패키지의 일부로 사용할 수 있지만 Blazor WebAssembly에서만 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-108">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="6dbeb-109">ASP.NET Core 5.0 RC1에서는 이 기능을 `Microsoft.AspNetCore.App` 공유 프레임워크를 참조하는 [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) 패키지의 일부로 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-109">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6dbeb-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="6dbeb-110">New behavior</span></span>

<span data-ttu-id="6dbeb-111">ASP.NET Core 5.0 RC2에서는 이 기능을 참조하고 사용하는 데 NuGet 패키지 참조가 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-111">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6dbeb-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6dbeb-112">Reason for change</span></span>

<span data-ttu-id="6dbeb-113">고객에게 공유 프레임워크로의 이동이 필요한 사용자 환경에 더욱 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-113">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6dbeb-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6dbeb-114">Recommended action</span></span>

<span data-ttu-id="6dbeb-115">ASP.NET Core 5.0 RC1에서 업그레이드하는 경우 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-115">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="6dbeb-116">프로젝트에서 `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-116">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="6dbeb-117">`using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-117">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6dbeb-118">`Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-118">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="6dbeb-119">ASP.NET Core 5.0 Preview 8에서 업그레이드하는 경우 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-119">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="6dbeb-120">프로젝트에서 `Microsoft.AspNetCore.Components.Web.Extensions` 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-120">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="6dbeb-121">`using Microsoft.AspNetCore.Components.Web.Extensions;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-121">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6dbeb-122">`Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6dbeb-122">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6dbeb-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6dbeb-123">Affected APIs</span></span>

<span data-ttu-id="6dbeb-124">없음</span><span class="sxs-lookup"><span data-stu-id="6dbeb-124">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
