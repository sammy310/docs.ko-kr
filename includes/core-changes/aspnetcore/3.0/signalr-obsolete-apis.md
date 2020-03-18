---
ms.openlocfilehash: 2a65caedea2af65796267aa145e275ebff814bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394018"
---
### <a name="signalr-usesignalr-and-useconnections-methods-marked-obsolete"></a><span data-ttu-id="a1749-101">SignalR: 사용되지 않는 것으로 표시된 UseSignalR 및 UseConnections 메서드</span><span class="sxs-lookup"><span data-stu-id="a1749-101">SignalR: UseSignalR and UseConnections methods marked obsolete</span></span>

<span data-ttu-id="a1749-102">`UseConnections` 및 `UseSignalR` 메서드와 `ConnectionsRouteBuilder` 및 `HubRouteBuilder` 클래스는 ASP.NET Core 3.0에서 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1749-102">The methods `UseConnections` and `UseSignalR` and the classes `ConnectionsRouteBuilder` and `HubRouteBuilder` are marked as obsolete in ASP.NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a1749-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a1749-103">Version introduced</span></span>

<span data-ttu-id="a1749-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a1749-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a1749-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="a1749-105">Old behavior</span></span>

<span data-ttu-id="a1749-106">`UseSignalR` 또는 `UseConnections`를 사용하여 SignalR 허브 라우팅이 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1749-106">SignalR hub routing was configured using `UseSignalR` or `UseConnections`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a1749-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="a1749-107">New behavior</span></span>

<span data-ttu-id="a1749-108">라우팅을 구성하는 이전 방법은 사용되지 않으며 엔드포인트 라우팅으로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1749-108">The old way of configuring routing has been obsoleted and replaced with endpoint routing.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a1749-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="a1749-109">Reason for change</span></span>

<span data-ttu-id="a1749-110">미들웨어가 새 엔드포인트 라우팅 시스템으로 이동되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1749-110">Middleware is being moved to the new endpoint routing system.</span></span> <span data-ttu-id="a1749-111">미들웨어를 추가하는 이전 방법은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1749-111">The old way of adding middleware is being obsoleted.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a1749-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a1749-112">Recommended action</span></span>

<span data-ttu-id="a1749-113">`UseSignalR` 및 `UseEndpoints` 교체:</span><span class="sxs-lookup"><span data-stu-id="a1749-113">Replace `UseSignalR` with `UseEndpoints`:</span></span>

<span data-ttu-id="a1749-114">**이전 코드:**</span><span class="sxs-lookup"><span data-stu-id="a1749-114">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="a1749-115">**새 코드:**</span><span class="sxs-lookup"><span data-stu-id="a1749-115">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

#### <a name="category"></a><span data-ttu-id="a1749-116">범주</span><span class="sxs-lookup"><span data-stu-id="a1749-116">Category</span></span>

<span data-ttu-id="a1749-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a1749-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a1749-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a1749-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder})`
- `M:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR(Microsoft.AspNetCore.Builder.IApplicationBuilder,System.Action{Microsoft.AspNetCore.SignalR.HubRouteBuilder})`
- `T:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder`
- `T:Microsoft.AspNetCore.SignalR.HubRouteBuilder`

-->
