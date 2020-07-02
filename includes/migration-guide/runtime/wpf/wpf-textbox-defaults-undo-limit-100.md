---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620480"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF TextBox 기본값이 100개의 제한을 실행 취소

#### <a name="details"></a>설명

.NET Framework 4.5에서는 WPF TextBox에 대한 실행 취소 제한 기본값은 100(.NET Framework 4.0에서 무제한이던 것과 반대)

#### <a name="suggestion"></a>제안 해결 방법

100개의 실행 취소 제한이 너무 낮으면 제한을 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>로 명시적으로 설정할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
