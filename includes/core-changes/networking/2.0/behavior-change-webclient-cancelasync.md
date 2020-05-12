---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859627"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a>WebClient.CancelAsync가 항상 즉시 취소되지는 않음

.NET Core 2.0부터 응답을 가져오기 시작한 경우 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소되었습니다. .NET Core 2.0부터 응답을 가져오기 시작하지 않은 경우에만 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소됩니다. 응답을 가져오기 시작한 경우에는 전체 응답을 읽은 후에만 요청이 취소됩니다.

<xref:System.Net.WebClient> API가 사용되지 않고 <xref:System.Net.Http.HttpClient>로 대체되었기 때문에 이러한 변경이 구현되었습니다.

#### <a name="version-introduced"></a>도입된 버전

2.0

#### <a name="recommended-action"></a>권장 조치

더 이상 사용되지 않는 <xref:System.Net.WebClient?displayProperty=fullName> 대신 <xref:System.Net.Http.HttpClient?displayProperty=fullName> 클래스를 사용합니다.

#### <a name="category"></a>범주

네트워킹

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
