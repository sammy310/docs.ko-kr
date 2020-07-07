---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615682"
---
### <a name="certificate-eku-oid-validation"></a>인증서 EKU OID 유효성 검사

#### <a name="details"></a>설명

.NET Framework 4.6부터는 <xref:System.Net.Security.SslStream> 또는 <xref:System.Net.ServicePointManager> 클래스가 EKU(향상된 키 사용) OID(개체 식별자) 유효성 검사를 수행합니다. EKU(향상된 키 사용) 확장은 키를 사용하는 애플리케이션을 나타내는 OID(개체 식별자)의 모음입니다. EKU OID 유효성 검사는 원격 인증서 콜백을 사용하여 원격 인증서가 원하는 용도에 맞는 올바른 OID를 갖도록 합니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경이 바람직하지 않은 경우 다음 스위치를 앱 구성 파일의 [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)에 있는 [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)에 추가하여 인증서 EKU OID 유효성 검사를 해제할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> 이 설정은 이전 버전과의 호환성을 위해서만 제공됩니다. 그러나 사용하지 않는 것이 좋습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
