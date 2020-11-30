---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032877"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: HubConnection ResetSendPing 및 ResetTimeout 메서드가 제거됨

`ResetSendPing` 및 `ResetTimeout` 메서드가 SignalR `HubConnection` API에서 제거되었습니다. 이러한 메서드는 원래 내부용으로만 사용되었지만 ASP.NET Core 2.2에서 공개되었습니다. 이러한 메서드는 ASP.NET Core 3.0 Preview 4 릴리스부터 사용할 수 없습니다. 토론은 [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

API를 사용할 수 있었습니다.

#### <a name="new-behavior"></a>새 동작

API가 제거되었습니다.

#### <a name="reason-for-change"></a>변경 이유

이러한 메서드는 원래 내부용으로만 사용되었지만 ASP.NET Core 2.2에서 공개되었습니다.

#### <a name="recommended-action"></a>권장 조치

이러한 메서드를 사용하지 마세요.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
