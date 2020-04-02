---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291663"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="ff447-101">SignalR: UseSignalR 및 UseConnections 메서드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="ff447-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="ff447-102">ASP.NET Core 3.0에서 SignalR이 엔드포인트 라우팅을 채택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="ff447-103">이러한 변경의 일부로 <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> 및 일부 관련 메서드가 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="ff447-104">ASP.NET Core 5.0에서는 사용되지 않는 메서드가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="ff447-105">전체 메서드 목록은 [영향을 받는 API](#affected-apis)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff447-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="ff447-106">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff447-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ff447-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ff447-107">Version introduced</span></span>

<span data-ttu-id="ff447-108">5.0 미리 보기 3</span><span class="sxs-lookup"><span data-stu-id="ff447-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ff447-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ff447-109">Old behavior</span></span>

<span data-ttu-id="ff447-110">`UseSignalR` 또는 `UseConnections` 메서드를 사용하여 미들웨어 파이프라인에 SignalR 허브 및 연결 처리기를 등록할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ff447-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="ff447-111">New behavior</span></span>

<span data-ttu-id="ff447-112"><xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>에서 <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> 및 <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> 확장 메서드를 사용하여 <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> 내에 SignalR 허브 및 연결 처리기를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ff447-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ff447-113">Reason for change</span></span>

<span data-ttu-id="ff447-114">이전 메서드에는 ASP.NET Core의 다른 라우팅 구성 요소와 상호 작용하지 않는 사용자 지정 라우팅 논리가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="ff447-115">ASP.NET Core 3.0에서는 엔드포인트 라우팅이라는 새로운 범용 라우팅 시스템이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="ff447-116">엔드포인트 라우팅에서 SignalR이 다른 라우팅 구성 요소와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="ff447-117">이 모델로 전환하면 사용자가 엔드포인트 라우팅의 모든 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="ff447-118">따라서 이전 메서드가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ff447-119">권장 작업</span><span class="sxs-lookup"><span data-stu-id="ff447-119">Recommended action</span></span>

<span data-ttu-id="ff447-120">프로젝트의 `Startup.Configure` 메서드에서 `UseSignalR` 또는 `UseConnections`를 호출하는 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="ff447-121">`UseEndpoints` 호출의 본문에서 이를 각각 `MapHub` 또는 `MapConnectionHandler` 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="ff447-122">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-122">For example:</span></span>

<span data-ttu-id="ff447-123">**이전 코드:**</span><span class="sxs-lookup"><span data-stu-id="ff447-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ff447-124">**새 코드:**</span><span class="sxs-lookup"><span data-stu-id="ff447-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ff447-125">일반적으로 이전 `MapHub` 및 `MapConnectionHandler` 호출을 거의 또는 아무 변경 없이 `UseSignalR` 또는 `UseConnections` 본문에서 직접 `UseEndpoints`로 이전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff447-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="ff447-126">Category</span><span class="sxs-lookup"><span data-stu-id="ff447-126">Category</span></span>

<span data-ttu-id="ff447-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ff447-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff447-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ff447-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
