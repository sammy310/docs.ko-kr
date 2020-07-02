---
ms.openlocfilehash: 5c86be598ab6196ecf4da05451c7f22d2be52c12
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614698"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>ServicePointManager.SecurityProtocol의 기본값은 SecurityProtocolType.System.Default임

#### <a name="details"></a>설명

.NET Framework 4.7을 대상으로 하는 앱부터 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 기본값은 <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>됩니다. 이 변경으로 SslStream을 기반으로 하는 .NET Framework 네트워킹 API(예: FTP, HTTPS 및 SMTP)가 .NET Framework에서 정의한 하드 코드된 값을 사용하는 대신 운영 체제에서 기본 보안 프로토콜을 상속할 수 있습니다. 기본값은 운영 체제 및 시스템 관리자가 수행하는 사용자 정의 구성에 따라 다릅니다. 각 버전의 Windows 운영 체제에서 기본 SChannel 프로토콜에 대한 자세한 내용은 [TLS/SSL의 프로토콜(Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-)을 참조하세요.</p>이전 버전의 .NET Framework를 대상으로 하는 애플리케이션의 경우 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 기본값은 대상으로 하는 .NET Framework의 버전에 따라 달라집니다. 자세한 내용은 [.NET Framework 4.5.2에서 4.6으로 마이그레이션을 위해 대상 변경의 네트워킹 섹션](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking)을 참조하세요.

#### <a name="suggestion"></a>제안 해결 방법

이 변경은 .NET Framework 4.7 이상 버전을 대상으로 하는 애플리케이션에 영향을 줍니다. 시스템 기본값에 의존하는 대신 정의된 프로토콜을 사용하려는 경우 <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> 속성의 값을 명시적으로 설정할 수 있습니다. 이 변경을 원치 않을 경우 애플리케이션 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 옵트아웃할 수 있습니다. 다음 예제에서는 `<runtime>` 섹션 및 `Switch.System.Net.DontEnableSystemDefaultTlsVersions` 옵트아웃 스위치를 모두 보여줍니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
