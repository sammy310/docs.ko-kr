---
ms.openlocfilehash: 51ac10e6b4cc9c757cb7f68d7d665982bcb57d4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497758"
---
### <a name="systemactivities-is-now-aptca"></a>System.Activities는 이제 APTCA

#### <a name="details"></a>설명

이 어셈블리는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 특성으로 표시되어 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

파생 클래스는 <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>로 표시할 수 없습니다. 이전에는 파생된 형식을 <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>로 표시해야 했습니다. 그러나 이 변경은 실제로 영향을 주어서는 안 됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
