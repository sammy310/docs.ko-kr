---
ms.openlocfilehash: beaac7b14535335a665add4fa056a60793879753
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620406"
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
