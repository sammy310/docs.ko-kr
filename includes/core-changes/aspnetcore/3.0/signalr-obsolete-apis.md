---
ms.openlocfilehash: 2a65caedea2af65796267aa145e275ebff814bf8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394018"
---
### <a name="signalr-usesignalr-and-useconnections-methods-marked-obsolete"></a>SignalR: 사용되지 않는 것으로 표시된 UseSignalR 및 UseConnections 메서드

`UseConnections` 및 `UseSignalR` 메서드와 `ConnectionsRouteBuilder` 및 `HubRouteBuilder` 클래스는 ASP.NET Core 3.0에서 사용되지 않는 것으로 표시됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`UseSignalR` 또는 `UseConnections`를 사용하여 SignalR 허브 라우팅이 구성되었습니다.

#### <a name="new-behavior"></a>새 동작

라우팅을 구성하는 이전 방법은 사용되지 않으며 엔드포인트 라우팅으로 바뀌었습니다.

#### <a name="reason-for-change"></a>변경 이유

미들웨어가 새 엔드포인트 라우팅 시스템으로 이동되고 있습니다. 미들웨어를 추가하는 이전 방법은 사용되지 않습니다.

#### <a name="recommended-action"></a>권장 작업

`UseSignalR` 및 `UseEndpoints` 교체:

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

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

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
