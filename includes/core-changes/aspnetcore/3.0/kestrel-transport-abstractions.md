---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393917"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel: 전송 추상화 제거 및 공개

"pubternal" API에서 벗어나 이동하는 과정에서 Kestrel 전송 계층 API는 `Microsoft.AspNetCore.Connections.Abstractions` 라이브러리의 공용 인터페이스로 노출됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

- 전송 관련 추상화는 `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` 라이브러리에서 사용할 수 있었습니다.
- `ListenOptions.NoDelay` 속성을 사용할 수 있었습니다.

#### <a name="new-behavior"></a>새 동작

- `IConnectionListener` 인터페이스는 `...Transport.Abstractions` 라이브러리에서 가장 많이 사용되는 기능을 노출하기 위해 `Microsoft.AspNetCore.Connections.Abstractions` 라이브러리에 도입되었습니다.
- 이제 `NoDelay`는 전송 옵션(`LibuvTransportOptions` 및 `SocketTransportOptions`)에서 사용할 수 있습니다.
- `SchedulingMode`를 더 이상 사용할 수 없습니다.

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 3.0은 "pubternal" API에서 벗어나 이동했습니다.

#### <a name="recommended-action"></a>권장 작업

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

### Affected APIs

Not detectable via API analysis

-->
