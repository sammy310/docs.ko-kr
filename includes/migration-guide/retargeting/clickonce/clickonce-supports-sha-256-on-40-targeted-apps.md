---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615656"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce가 4.0 대상 앱에서 SHA-256 지원

#### <a name="details"></a>세부 정보

이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET Framework 4.5 이상이 필요했습니다. 이제 .NET Framework 4.0을 대상으로 하는 ClickOnce 앱을 SHA-256으로 서명한 경우에도 .NET Framework 4.0에서 실행할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |
