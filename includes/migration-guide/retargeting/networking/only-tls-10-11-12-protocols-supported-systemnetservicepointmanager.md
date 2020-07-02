---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615696"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>System.Net.ServicePointManager 및 System.Net.Security.SslStream에서는 Tls 1.0, 1.1 및 1.2 프로토콜만 지원됨

#### <a name="details"></a>세부 정보

.NET Framework 4.6부터 <xref:System.Net.ServicePointManager> 및 <xref:System.Net.Security.SslStream> 클래스에서 Tls1.0, Tls1.1 또는 Tls1.2 프로토콜 중 하나만 사용할 수 있습니다. SSL3.0 프로토콜 및 RC4 암호화는 지원되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

권장되는 완화 방법은 Tls1.0, Tls1.1 또는 Tls1.2로 서버 쪽 앱을 업그레이드하는 것입니다. 이 작업이 불가능하거나 클라이언트 앱이 손상된 경우 <xref:System.AppContext?displayProperty=fullName> 클래스를 사용하여 다음 두 방법 중 하나로 이 기능을 옵트아웃(opt out)할 수 있습니다.

- [여기](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)에 설명된 대로 <xref:System.AppContext?displayProperty=fullName>에서 compat 스위치를 프로그래밍 방식으로 설정되었습니다.
- 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
