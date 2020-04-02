---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291663"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a>SignalR: UseSignalR 및 UseConnections 메서드가 제거됨

ASP.NET Core 3.0에서 SignalR이 엔드포인트 라우팅을 채택합니다. 이러한 변경의 일부로 <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> 및 일부 관련 메서드가 사용되지 않는 것으로 표시되었습니다. ASP.NET Core 5.0에서는 사용되지 않는 메서드가 제거되었습니다. 전체 메서드 목록은 [영향을 받는 API](#affected-apis)를 참조하세요.

이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 3

#### <a name="old-behavior"></a>이전 동작

`UseSignalR` 또는 `UseConnections` 메서드를 사용하여 미들웨어 파이프라인에 SignalR 허브 및 연결 처리기를 등록할 수 있었습니다.

#### <a name="new-behavior"></a>새 동작

<xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>에서 <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> 및 <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> 확장 메서드를 사용하여 <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> 내에 SignalR 허브 및 연결 처리기를 등록해야 합니다.

#### <a name="reason-for-change"></a>변경 이유

이전 메서드에는 ASP.NET Core의 다른 라우팅 구성 요소와 상호 작용하지 않는 사용자 지정 라우팅 논리가 있었습니다. ASP.NET Core 3.0에서는 엔드포인트 라우팅이라는 새로운 범용 라우팅 시스템이 도입되었습니다. 엔드포인트 라우팅에서 SignalR이 다른 라우팅 구성 요소와 상호 작용할 수 있습니다. 이 모델로 전환하면 사용자가 엔드포인트 라우팅의 모든 이점을 활용할 수 있습니다. 따라서 이전 메서드가 제거되었습니다.

#### <a name="recommended-action"></a>권장 작업

프로젝트의 `Startup.Configure` 메서드에서 `UseSignalR` 또는 `UseConnections`를 호출하는 코드를 제거합니다. `UseEndpoints` 호출의 본문에서 이를 각각 `MapHub` 또는 `MapConnectionHandler` 호출로 바꿉니다. 다음은 그 예입니다.

**이전 코드:**

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

**새 코드:**

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

일반적으로 이전 `MapHub` 및 `MapConnectionHandler` 호출을 거의 또는 아무 변경 없이 `UseSignalR` 또는 `UseConnections` 본문에서 직접 `UseEndpoints`로 이전할 수 있습니다.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

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
