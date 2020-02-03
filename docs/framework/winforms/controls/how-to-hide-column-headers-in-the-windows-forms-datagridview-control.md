---
title: DataGridView 컨트롤에서 열 머리글 숨기기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: d84c93b0ad1c9ef456c73dd29af1de4857778999
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736590"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기
경우에 따라 열 머리글이 없는 <xref:System.Windows.Forms.DataGridView>를 표시 하는 것이 좋습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤에서 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성 값은 열 머리글이 표시 되는지 여부를 결정 합니다.  
  
### <a name="to-hide-the-column-headers"></a>열 머리글을 숨기려면  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> 속성을 `false`로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
