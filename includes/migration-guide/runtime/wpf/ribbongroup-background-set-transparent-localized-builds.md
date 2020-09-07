---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496743"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.

#### <a name="details"></a>세부 정보

지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다. 이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>의 지역화된 리소스를 업데이트하여 해결되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

NET Framework 4.7로 업그레이드

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6.2|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
