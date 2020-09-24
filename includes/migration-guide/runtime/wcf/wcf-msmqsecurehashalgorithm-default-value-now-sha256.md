---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770837"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>WCF MsmqSecureHashAlgorithm 기본값은 이제 SHA256입니다.

#### <a name="details"></a>설명

.NET Framework 4.7.1부터 Msmq 메시지에 대한 WCF의 기본 메시지 서명 알고리즘은 SHA256입니다. .NET Framework 4.7 및 이전 버전에서 기본 메시지 서명 알고리즘은 SHA1입니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.7.1 이상에서 이러한 변경 내용과의 호환성 문제가 발생하면 app.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 변경 내용을 옵트아웃할 수 있습니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| Name    | 값   |
|:--------|:--------|
| Scope   | 부   |
| 버전 | 4.7.1   |
| 형식    | 런타임 |

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
