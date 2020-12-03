---
title: '호환성이 손상되는 변경: 권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760008"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="2ba9a-103">권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임</span><span class="sxs-lookup"><span data-stu-id="2ba9a-103">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="2ba9a-104">ASP.NET Core 3.1에서 엔드포인트 라우팅을 사용하는 경우 권한 부여에 사용되는 리소스는 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-104">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="2ba9a-105">이 방법만으로 경로 데이터(<xref:Microsoft.AspNetCore.Routing.RouteData>)에 대한 액세스 권한을 얻을 수는 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-105">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="2ba9a-106">이전에는 MVC에서 엔드포인트(<xref:Microsoft.AspNetCore.Http.Endpoint>) 및 경로 데이터 둘 다에 대한 액세스를 허용하는 <xref:Microsoft.AspNetCore.Http.HttpContext> 리소스가 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-106">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="2ba9a-107">이렇게 변경하면 권한 부여에 전달되는 리소스가 항상 `HttpContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-107">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2ba9a-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2ba9a-108">Version introduced</span></span>

<span data-ttu-id="2ba9a-109">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="2ba9a-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="2ba9a-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="2ba9a-110">Old behavior</span></span>

<span data-ttu-id="2ba9a-111">엔드포인트 라우팅과 권한 부여 미들웨어(<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) 또는 [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) 특성을 사용하는 경우 권한 부여에 전달되는 리소스는 일치하는 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-111">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="2ba9a-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="2ba9a-112">New behavior</span></span>

<span data-ttu-id="2ba9a-113">엔드포인트 라우팅이 권한 부여에 `HttpContext`를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-113">Endpoint routing passes the `HttpContext` to authorization.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2ba9a-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2ba9a-114">Reason for change</span></span>

<span data-ttu-id="2ba9a-115">`HttpContext`에서 엔드포인트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-115">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="2ba9a-116">그러나 엔드포인트에서 경로 데이터 등에 액세스할 수 있는 방법이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-116">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="2ba9a-117">비엔드포인트 라우팅의 기능이 손실되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-117">There was a loss in functionality from non-endpoint routing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2ba9a-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="2ba9a-118">Recommended action</span></span>

<span data-ttu-id="2ba9a-119">앱에서 엔드포인트 리소스를 사용하는 경우 `HttpContext`에 대해 <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A>를 호출하여 엔드포인트에 계속 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-119">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="2ba9a-120">ASP.NET Core 5.0 미리 보기 8 이상에서는 <xref:System.AppContext.SetSwitch%2A>를 사용하여 이전 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba9a-120">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="2ba9a-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2ba9a-121">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a><span data-ttu-id="2ba9a-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2ba9a-122">Affected APIs</span></span>

<span data-ttu-id="2ba9a-123">없음</span><span class="sxs-lookup"><span data-stu-id="2ba9a-123">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
