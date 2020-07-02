---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614806"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>WCF 메시지 보안이 이제 TLS1.1 및 TLS1.2를 사용할 수 있음

#### <a name="details"></a>설명

.NET Framework 4.7부터 고객은 애플리케이션 구성 설정을 통해 SSL3.0 및 TLS1.0 외에도 WCF 메시지 보안에 TLS1.1 또는 TLS1.2를 구성할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.7에서는 WCF 메시지 보안의 TLS1.1 및 TLS1.2에 대한 지원은 기본적으로 사용할 수 없습니다. app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 행을 추가하여 사용할 수 있습니다.

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7         |
| 형식    | 대상 변경 |
