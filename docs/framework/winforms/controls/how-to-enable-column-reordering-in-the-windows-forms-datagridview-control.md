---
title: DataGridView 컨트롤에서 열 다시 정렬 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 681489cdb874677079e2577140040921e587d21e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745490"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 열 다시 정렬을 사용하도록 설정하면 사용자가 마우스로 열 머리글을 끌어서 열을 새 위치로 이동할 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성 값은 사용자가 열을 다른 위치로 이동할 수 있는지 여부를 결정합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬을 사용 하도록 설정을](enable-column-reordering-in-the-datagrid-using-the-designer.md)참조 하세요.  
  
### <a name="to-enable-column-reordering-programmatically"></a>프로그래밍 방식으로 열 다시 정렬을 사용하도록 설정하려면 다음을 수행합니다.  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 열 고정](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
