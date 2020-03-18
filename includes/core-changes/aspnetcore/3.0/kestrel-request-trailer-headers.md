---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394372"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a>Kestrel: 요청 트레일러 헤더가 새 컬렉션으로 이동됨

이전 버전에서 Kestrel은 요청 본문을 끝까지 읽을 때 HTTP/1.1 청크 처리된 트레일러 헤더를 요청 헤더 컬렉션에 추가했습니다. 이 동작은 헤더와 트레일러 사이의 모호성에 대한 문제를 발생시켰습니다. 트레일러를 새 컬렉션으로 이동하기로 결정했습니다.

HTTP/2 요청 트레일러는 ASP.NET Core 2.2에서 사용할 수 없었지만 이제 ASP.NET Core 3.0의 이 새 컬렉션에서도 사용할 수 있습니다.

이러한 트레일러에 액세스하기 위해 새 요청 확장 메서드가 추가되었습니다.

HTTP/1.1 트레일러는 전체 요청 본문을 읽은 후에 사용할 수 있습니다.

HTTP/2 트레일러는 클라이언트에서 수신한 후 사용할 수 있습니다. 클라이언트는 전체 요청 본문이 최소한 서버에 의해 버퍼링될 때까지 트레일러를 보내지 않습니다. 버퍼 공간을 확보하기 위해 요청 본문을 읽어야 할 수도 있습니다. 트레일러는 요청 본문을 끝까지 읽으면 항상 사용할 수 있습니다. 트레일러는 본문의 끝을 표시합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

요청 트레일러 헤더가 `HttpRequest.Headers` 컬렉션에 추가됩니다.

#### <a name="new-behavior"></a>새 동작

요청 트레일러 헤더가 `HttpRequest.Headers` 컬렉션에 **존재하지 않습니다**. `HttpRequest`에서 다음 확장 메서드를 사용하여 액세스합니다.

- `GetDeclaredTrailers()` - 본문 다음에 사용할 트레일러를 나열하는 요청 "트레일러" 헤더를 가져옵니다.
- `SupportsTrailers()` - 요청에서 트레일러 헤더 수신을 지원하는지 여부를 나타냅니다.
- `CheckTrailersAvailable()` - 요청에서 트레일러를 지원하는지 여부와 읽을 수 있는지 여부를 확인합니다.
- `GetTrailer(string trailerName)` - 응답에서 요청된 후행 헤더를 가져옵니다.

#### <a name="reason-for-change"></a>변경 이유

트레일러는 gRPC와 같은 시나리오의 주요 기능입니다. 트레일러를 병합하여 헤더를 요청하는 것은 사용자에게 혼동을 줍니다.

#### <a name="recommended-action"></a>권장 조치

`HttpRequest`에서 트레일러 관련 확장 메서드를 사용하여 트레일러에 액세스합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
