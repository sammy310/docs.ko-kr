---
title: DataGridView 컨트롤에서 행 추가 및 삭제 방지
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: de8e0412faf8c3731f9356771b35a4a5d31b6ec7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728729"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지
때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다. <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성은 컨트롤 아래쪽에 새 레코드에 대한 행이 있는지를 나타내는 반면, <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성은 행을 제거할 수 있는지를 나타냅니다. 다음 코드 예제에서는 이들 속성을 사용하고 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> 속성을 설정하여 컨트롤을 전체적으로 읽기 전용으로 지정합니다.  
  
 Visual Studio에서는 이 작업이 지원됩니다. 또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 방지를](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)참조 하세요.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
