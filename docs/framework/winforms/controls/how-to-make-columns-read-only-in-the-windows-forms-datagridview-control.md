---
title: DataGridView 컨트롤에서 열을 읽기 전용으로 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736191"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정
일부 데이터는 편집할 수 없습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성 값은 사용자가 해당 열의 셀을 편집할 수 있는지 여부를 결정합니다. 컨트롤을 완전히 읽기 전용으로 설정 하는 방법에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 행 추가 및 삭제 방지](prevent-row-addition-and-deletion-datagridview.md)를 참조 하세요.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정을](make-columns-read-only-in-the-datagrid-using-the-designer.md)참조 하세요.  
  
### <a name="to-make-a-column-read-only-programmatically"></a>프로그래밍 방식으로 열을 읽기 전용으로 설정하려면  
  
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- 이름이 <xref:System.Windows.Forms.DataGridView>인 열을 포함하는 이름이 `dataGridView1`인 `CompanyName` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](prevent-row-addition-and-deletion-datagridview.md)
