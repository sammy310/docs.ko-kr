---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614731"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>TransportWithMessageCredential 보안 모드로 WCF 바인딩

#### <a name="details"></a>설명

.NET Framework 4.6.1부터는 TransportWithMessageCredential 보안 모드를 사용하는 WCF 바인딩이 비대칭 보안 키의 헤더에 대해 서명되지 않은 &quot;to&quot; 헤더가 있는 메시지를 받도록 설정할 수 있습니다. 기본적으로 서명되지 않은 &quot;to&quot; 헤더는 .NET Framework 4.6.1에서 계속 거부됩니다. 애플리케이션이 Switch.System.ServiceModel.AllowUnsignedToHeader 구성 스위치를 사용하여 이 새로운 작업 모드를 옵트인하는 경우에만 허용됩니다.

#### <a name="suggestion"></a>제안 해결 방법

이 기능은 옵트인 기능이기 때문에 기존 앱의 동작에는 영향을 주지 않습니다.<br/>새 동작을 사용할지 여부를 제어하려면 다음 구성 설정을 사용합니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 투명 |
| 버전 | 4.6.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
