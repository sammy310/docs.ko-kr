---
title: '호환성이 손상되는 변경: Blazor 업데이트된 브라우저 지원'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 관해 알아보기. Blazor: 업데이트된 브라우저 지원'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
no-loc:
- Blazor
- Blazor WebAssembly
- Blazor Server
ms.openlocfilehash: a14ab8d1afd4b662f61e30136d23e28ffbe2d496
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431479"
---
# <a name="blazor-updated-browser-support"></a><span data-ttu-id="40526-103">Blazor: 업데이트된 브라우저 지원</span><span class="sxs-lookup"><span data-stu-id="40526-103">Blazor: Updated browser support</span></span>

<span data-ttu-id="40526-104">ASP.NET Core 5.0에는 [새로운 Blazor 기능](https://github.com/dotnet/aspnetcore/issues/21514)이 도입되었으며, 일부 기능은 이전 브라우저와 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-104">ASP.NET Core 5.0 introduces [new Blazor features](https://github.com/dotnet/aspnetcore/issues/21514), some of which are incompatible with older browsers.</span></span> <span data-ttu-id="40526-105">이에 따라 ASP.NET Core 5.0의 Blazor에서 지원되는 브라우저 목록이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-105">The list of browsers supported by Blazor in ASP.NET Core 5.0 has been updated accordingly.</span></span>

<span data-ttu-id="40526-106">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40526-106">For discussion, see GitHub issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="40526-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="40526-107">Version introduced</span></span>

<span data-ttu-id="40526-108">5.0</span><span class="sxs-lookup"><span data-stu-id="40526-108">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="40526-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="40526-109">Old behavior</span></span>

<span data-ttu-id="40526-110">Blazor Server가 충분한 폴리필로 Microsoft Internet Explorer 11을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="40526-110">Blazor Server supports Microsoft Internet Explorer 11 with sufficient polyfills.</span></span> <span data-ttu-id="40526-111">Blazor Server 및 Blazor WebAssembly도 [Microsoft Edge 레거시](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="40526-111">Blazor Server and Blazor WebAssembly are also functional in [Microsoft Edge Legacy](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="40526-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="40526-112">New behavior</span></span>

<span data-ttu-id="40526-113">ASP.NET Core 5.0의 Blazor Server가 Microsoft Internet Explorer 11에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-113">Blazor Server in ASP.NET Core 5.0 isn't supported with Microsoft Internet Explorer 11.</span></span> <span data-ttu-id="40526-114">Blazor Server 및 Blazor WebAssembly는 Microsoft Edge 레거시에서 완전하게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-114">Blazor Server and Blazor WebAssembly aren't fully functional in Microsoft Edge Legacy.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="40526-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="40526-115">Reason for change</span></span>

<span data-ttu-id="40526-116">ASP.NET Core 5.0의 새로운 Blazor 기능은 이전 브라우저와 호환되지 않으며, 이전 브라우저 사용이 감소하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-116">New Blazor features in ASP.NET Core 5.0 are incompatible with these older browsers, and use of these older browsers is diminishing.</span></span> <span data-ttu-id="40526-117">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40526-117">For more information, see the following resources:</span></span>

* [<span data-ttu-id="40526-118">Microsoft Edge 레거시에 대한 Windows 지원도 2021년 3월 9일에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="40526-118">Windows support for Microsoft Edge Legacy is also ending on March 9, 2021</span></span>](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [<span data-ttu-id="40526-119">Microsoft Internet Explorer 11에 대한 Microsoft 365 앱과 서비스 지원이 2021년 8월 17일에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="40526-119">Microsoft 365 apps and services will end support for Microsoft Internet Explorer 11 by August 17, 2021</span></span>](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

## <a name="recommended-action"></a><span data-ttu-id="40526-120">권장 조치</span><span class="sxs-lookup"><span data-stu-id="40526-120">Recommended action</span></span>

<span data-ttu-id="40526-121">이전 브라우저에서 [Chromium 기반의 새로운 Microsoft Edge](https://www.microsoft.com/edge)로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="40526-121">Upgrade from these older browsers to the [new, Chromium-based Microsoft Edge](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="40526-122">이전 브라우저를 지원해야 하는 Blazor 앱의 경우 ASP.NET Core 3.1을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40526-122">For Blazor apps that need to support these older browsers, use ASP.NET Core 3.1.</span></span> <span data-ttu-id="40526-123">ASP.NET Core 3.1에서는 Blazor 지원 브라우저 목록이 변경되지 않았으며 [지원되는 플랫폼](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1)에 문서화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40526-123">The supported browsers list for Blazor in ASP.NET Core 3.1 hasn't changed and is documented at [Supported platforms](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="40526-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="40526-124">Affected APIs</span></span>

<span data-ttu-id="40526-125">없음</span><span class="sxs-lookup"><span data-stu-id="40526-125">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
