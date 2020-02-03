---
title: DataGridView 컨트롤의 열에 대 한 정렬 모드 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743003"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 텍스트 상자 열은 기본적으로 자동 정렬을 사용 하지만 다른 열 형식은 자동으로 정렬 되지 않습니다. 경우에 따라 이러한 기본값을 재정의 해야 합니다. 예를 들어 텍스트, 숫자 또는 열거 셀 값 대신 이미지를 표시할 수 있습니다. 이미지를 정렬할 수는 없지만 표시 되는 기본 값은 정렬할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성 값은 정렬 동작을 결정 합니다.  
  
 다음 절차에서는 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)의 `Priority` 열을 보여 줍니다. 이 열은 이미지 열 이며 기본적으로 정렬할 수 없습니다. 그러나 문자열에 해당 하는 실제 셀 값을 포함 하므로 자동으로 정렬할 수 있습니다.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>열에 대 한 정렬 모드를 설정 하려면  
  
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- 이름이 <xref:System.Windows.Forms.DataGridView>인 열을 포함하는 이름이 `dataGridView1`인 `Priority` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 데이터 정렬](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 열 정렬 모드](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
