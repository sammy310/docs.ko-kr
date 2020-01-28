---
title: DataGridView 컨트롤의 개별 셀에 도구 설명 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732187"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가
기본적으로 도구 설명을 사용 하 여 <xref:System.Windows.Forms.DataGridView> 셀의 값을 표시 하는 데 사용 됩니다 .이 값이 너무 작아 전체 내용을 표시할 수 없습니다. 그러나이 동작을 재정의 하 여 개별 셀에 대 한 도구 설명 텍스트 값을 설정할 수 있습니다. 이 기능은 사용자에 게 셀에 대 한 추가 정보를 표시 하거나 사용자에 게 셀 내용에 대 한 대체 설명을 제공 하는 데 유용 합니다. 예를 들어 상태 아이콘을 표시 하는 행이 있는 경우 도구 설명을 사용 하 여 텍스트 설명을 제공할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> 속성을 `false`설정 하 여 셀 수준 도구 설명의 표시를 사용 하지 않도록 설정할 수도 있습니다.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>셀에 도구 설명을 추가 하려면  
  
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 속성을 설정합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- 이 예제에는 다음 사항이 필요합니다.  
  
- 1에서 4 개의 별표 ("*") 기호 사이의 문자열 값을 표시 하는 `Rating` 이라는 열이 포함 된 `dataGridView1` 이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 예제에 표시 된 이벤트 처리기 메서드와 연결 되어야 합니다.  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 외부 데이터 원본에 바인딩하거나 가상 모드를 구현 하 여 고유한 데이터 원본을 제공 하는 경우 성능 문제가 발생할 수 있습니다. 많은 양의 데이터로 작업할 때 성능 저하를 방지 하려면 여러 셀의 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 속성을 설정 하는 대신 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 이벤트를 처리 합니다. 이 이벤트를 처리할 때 셀 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 속성 값을 가져오면 이벤트가 발생 하 고 이벤트 처리기에 지정 된 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> 속성 값이 반환 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](programming-with-cells-rows-and-columns-in-the-datagrid.md)
