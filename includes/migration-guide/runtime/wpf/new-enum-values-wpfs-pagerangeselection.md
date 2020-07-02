---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620456"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>WPF의 PageRangeSelection에 새 열거형 값

#### <a name="details"></a>설명

두 개의 새 멤버(<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> 및 <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>)가 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 열거형에 추가되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

대부분의 경우 이러한 변경은 사용자 코드에 영향을 주지 않습니다. 다만 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 형식의 <xref:System.Enum.GetNames(System.Type)> 또는 <xref:System.Enum.GetValues(System.Type)> 호출에 존재하는 요소의 특정 수에 종속된 코드는 수정되어야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
