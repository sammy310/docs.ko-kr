---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622372"
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
