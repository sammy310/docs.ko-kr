---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025266"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>WCF PipeConnection.GetHashAlgorithm은 이제 SHA256을 사용

#### <a name="details"></a>설명

.NET Framework 4.7.1부터 Windows Communication Foundation은 명명 된 파이프에 대한 임의 이름을 생성하기 위해 SHA256 해시를 사용합니다. .NET Framework 4.7 및 이전 버전에서는 SHA1 해시를 사용했습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.7.1 이상에서 이러한 변경 내용과의 호환성 문제가 발생하면 app.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 옵트아웃할 수 있습니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
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
