---
title: '호환성이 손상되는 변경: Blazor: Blazor 앱의 라우팅 논리 변경 내용'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: Blazor 앱의 라우팅 논리 변경 내용'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513510"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a><span data-ttu-id="c9fa1-103">Blazor: Blazor 앱에서 경로 우선 순위 논리가 변경됨</span><span class="sxs-lookup"><span data-stu-id="c9fa1-103">Blazor: Route precedence logic changed in Blazor apps</span></span>

<span data-ttu-id="c9fa1-104">Blazor 라우팅 구현의 버그로 경로의 우선 순위를 결정하는 방법이 영향을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-104">A bug in the Blazor routing implementation affected how the precedence of routes was determined.</span></span> <span data-ttu-id="c9fa1-105">이 버그는 Blazor 앱 내에서 catch-all 경로나 선택적 매개 변수를 사용하는 경로에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-105">This bug affects catch-all routes or routes with optional parameters within your Blazor app.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c9fa1-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c9fa1-106">Version introduced</span></span>

<span data-ttu-id="c9fa1-107">5.0.1</span><span class="sxs-lookup"><span data-stu-id="c9fa1-107">5.0.1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="c9fa1-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="c9fa1-108">Old behavior</span></span>

<span data-ttu-id="c9fa1-109">잘못된 동작으로 우선 순위가 낮은 경로가 우선 순위가 높은 경로보다 우선 고려되고 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-109">With the erroneous behavior, routes with lower precedence are considered and matched over routes with higher precedence.</span></span> <span data-ttu-id="c9fa1-110">예를 들어 `{*slug}` 경로가 `/customer/{id}`보다 먼저 일치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-110">For example, the `{*slug}` route is matched before `/customer/{id}`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="c9fa1-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="c9fa1-111">New behavior</span></span>

<span data-ttu-id="c9fa1-112">현재 동작은 ASP.NET Core 앱에 정의된 라우팅 동작과 더 가깝게 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-112">The current behavior more closely matches the routing behavior defined in ASP.NET Core apps.</span></span> <span data-ttu-id="c9fa1-113">먼저 프레임워크에 따라 각 세그먼트의 경로 우선 순위가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-113">The framework determines the route precedence for each segment first.</span></span> <span data-ttu-id="c9fa1-114">경로의 길이는 동률을 깨기 위한 두 번째 기준으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-114">The route's length is used only as a second criteria to break ties.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c9fa1-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="c9fa1-115">Reason for change</span></span>

<span data-ttu-id="c9fa1-116">원래 동작은 구현에서 버그로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-116">The original behavior is considered a bug in the implementation.</span></span> <span data-ttu-id="c9fa1-117">목표는 Blazor 앱의 라우팅 시스템이 나머지 ASP.NET Core의 라우팅 시스템과 동일한 방식으로 동작하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-117">As a goal, the routing system in Blazor apps should behave the same way as the routing system in the rest of ASP.NET Core.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c9fa1-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="c9fa1-118">Recommended action</span></span>

<span data-ttu-id="c9fa1-119">5\.x 이전의 Blazor 버전에서 업그레이드하는 경우 `Router` 구성 요소에서 `PreferExactMatches` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-119">If upgrading from previous versions of Blazor to 5.x, use the `PreferExactMatches` attribute on the `Router` component.</span></span> <span data-ttu-id="c9fa1-120">이 특성을 사용하여 올바른 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-120">This attribute can be used to opt into the correct behavior.</span></span> <span data-ttu-id="c9fa1-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-121">For example:</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

<span data-ttu-id="c9fa1-122">`PreferExactMatches`을 `true`로 설정하면 경로 일치에서 와일드카드보다 정확한 일치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fa1-122">When `PreferExactMatches` is set to `true`, route matching prefers exact matches over wildcards.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c9fa1-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c9fa1-123">Affected APIs</span></span>

<span data-ttu-id="c9fa1-124">없음</span><span class="sxs-lookup"><span data-stu-id="c9fa1-124">None</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
