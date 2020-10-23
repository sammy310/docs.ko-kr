---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050526"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream 및 SslStream은 연속 Begin 작업을 허용합니다.

보안 스트림의 오류 사례는 다르게 처리되며, `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 후속 호출이 더 이상 실패하지 않을 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 RC1

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 먼저 `EndAuthenticateAsServer` 또는 `EndAuthenticateAsClient`를 호출하지 않고 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`를 연속적으로 호출하면 <xref:System.NotSupportedException>이 됩니다. .NET 5.0부터는 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 연속적인 호출이 더 이상 <xref:System.NotSupportedException>을 생성하지 않습니다. 이러한 API는 <xref:System.Threading.Tasks.Task> 기반 구현에서 지원되기 때문입니다.

#### <a name="reason-for-change"></a>변경 이유

내부 구현을 APM(비동기 프로그래밍 모델)에서 <xref:System.Threading.Tasks.Task> 기반으로 전환하면 성능이 향상되고 코드 복잡성도 줄어듭니다.

#### <a name="recommended-action"></a>권장 조치

개발자는 아무 작업도 수행하지 않아도 됩니다.

#### <a name="category"></a>범주

네트워킹

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
