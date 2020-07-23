---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441554"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="f939d-101">권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임</span><span class="sxs-lookup"><span data-stu-id="f939d-101">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="f939d-102">ASP.NET Core 3.1에서 엔드포인트 라우팅을 사용하는 경우 권한 부여에 사용되는 리소스는 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-102">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="f939d-103">이 방법만으로 경로 데이터(<xref:Microsoft.AspNetCore.Routing.RouteData>)에 대한 액세스 권한을 얻을 수는 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-103">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="f939d-104">이전에는 MVC에서 엔드포인트(<xref:Microsoft.AspNetCore.Http.Endpoint>) 및 경로 데이터 둘 다에 대한 액세스를 허용하는 <xref:Microsoft.AspNetCore.Http.HttpContext> 리소스가 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-104">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="f939d-105">이렇게 변경하면 권한 부여에 전달되는 리소스가 항상 `HttpContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-105">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f939d-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f939d-106">Version introduced</span></span>

<span data-ttu-id="f939d-107">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="f939d-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f939d-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="f939d-108">Old behavior</span></span>

<span data-ttu-id="f939d-109">엔드포인트 라우팅과 권한 부여 미들웨어(<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) 또는 [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) 특성을 사용하는 경우 권한 부여에 전달되는 리소스는 일치하는 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-109">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f939d-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="f939d-110">New behavior</span></span>

<span data-ttu-id="f939d-111">엔드포인트 라우팅이 권한 부여에 `HttpContext`를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-111">Endpoint routing passes the `HttpContext` to authorization.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f939d-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f939d-112">Reason for change</span></span>

<span data-ttu-id="f939d-113">`HttpContext`에서 엔드포인트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-113">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="f939d-114">그러나 엔드포인트에서 경로 데이터 등에 액세스할 수 있는 방법이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-114">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="f939d-115">비엔드포인트 라우팅의 기능이 손실되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-115">There was a loss in functionality from non-endpoint routing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f939d-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f939d-116">Recommended action</span></span>

<span data-ttu-id="f939d-117">앱에서 엔드포인트 리소스를 사용하는 경우 `HttpContext`에 대해 <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A>를 호출하여 엔드포인트에 계속 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-117">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="f939d-118">ASP.NET Core 5.0 미리 보기 8 이상에서는 <xref:System.AppContext.SetSwitch%2A>를 사용하여 이전 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939d-118">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="f939d-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f939d-119">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a><span data-ttu-id="f939d-120">범주</span><span class="sxs-lookup"><span data-stu-id="f939d-120">Category</span></span>

<span data-ttu-id="f939d-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f939d-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f939d-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f939d-122">Affected APIs</span></span>

<span data-ttu-id="f939d-123">없음</span><span class="sxs-lookup"><span data-stu-id="f939d-123">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
