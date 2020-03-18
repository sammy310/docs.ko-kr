---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567360"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>도구 설명이 표시되면 CellFormatting 이벤트가 발생하지 않습니다.

이제 마우스로 가리키는 경우와 키보드를 통해 선택하는 경우 <xref:System.Windows.Forms.DataGridView>에 셀 텍스트 및 오류의 도구 설명이 표시됩니다. 도구 설명이 표시되는 경우 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트는 발생하지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.1 이전에는, 셀을 마우스로 가리킬 때 <xref:System.Windows.Forms.DataGridView> 속성이 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>(으)로 설정된 `true`에서 셀 텍스트 및 오류에 대한 도구 설명이 표시되었습니다. 키보드에서 셀을 선택한 경우(예: Tab 키, 바로 가기 키 또는 화살표 탐색 사용) 도구 설명이 표시되지 않았습니다. 사용자가 셀을 편집한 후 <xref:System.Windows.Forms.DataGridView>이(가) 아직 편집 모드 상태인 동안 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> 속성이 설정되지 않은 셀을 마우스로 가리키는 경우, <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트가 발생하여 셀에 표시할 셀 텍스트의 서식을 지정합니다.

.NET Core 3.1부터 접근성 표준을 충족하기 위해, <xref:System.Windows.Forms.DataGridView> 속성이 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>(으)로 설정된 `true`에서 셀을 가리킬 때뿐 아니라, 키보드에서 선택한 경우에도 셀 텍스트 및 오류의 도구 설명이 표시됩니다. 이 변경으로 인해 <xref:System.Windows.Forms.DataGridView.CellFormatting>이(가) 편집 모드에 있는 동안 *속성이 설정되지 않은 셀을 가리키는 경우에는* 이벤트가 발생되지 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>않습니다<xref:System.Windows.Forms.DataGridView>. 가리킨 셀의 내용이 셀에 표시되지 않고 도구 설명으로 표시되므로 이 이벤트가 발생하지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.1

#### <a name="recommended-action"></a>권장 조치

<xref:System.Windows.Forms.DataGridView.CellFormatting>이(가) 편집 모드에 있는 동안 <xref:System.Windows.Forms.DataGridView> 이벤트에 종속된 모든 코드를 리팩터링합니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
