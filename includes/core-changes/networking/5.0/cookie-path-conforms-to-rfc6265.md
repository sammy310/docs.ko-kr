---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465517"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>이제 쿠키 경로 처리가 RFC 6265를 준수함

[RFC 6265](https://tools.ietf.org/html/rfc6265)에 정의된 경로 처리 알고리즘은 <xref:System.Net.Cookie> 및 <xref:System.Net.CookieContainer> 클래스에 대해 구현되었습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="change-description"></a>변경 내용 설명

- 이제 <xref:System.Net.Cookie.Path> 속성에 요청 경로를 접두사로 사용하지 않아도 됩니다.
- <xref:System.Net.Cookie.Path>의 기본값 계산과 경로 일치 알고리즘은 RFC 6265의 [섹션 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4)에 정의된 대로 구현되었습니다.

#### <a name="recommended-action"></a>권장 조치

대부분의 경우 아무 동작도 수행할 필요가 없습니다. 그러나 코드가 <xref:System.Net.Cookie.Path> 유효성 검사에 종속된 경우 코드에서 필요한 유효성 검사를 구현해야 합니다. 코드가 <xref:System.Net.Cookie.Path>의 기본값 계산에 종속된 경우 기본값을 사용하는 대신 <xref:System.Net.Cookie.Path> 값을 수동으로 지정하는 것이 좋습니다.

#### <a name="category"></a>범주

네트워킹

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
