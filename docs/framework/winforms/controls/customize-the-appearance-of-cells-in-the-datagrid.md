---
title: DataGridView 컨트롤에서 셀 모양 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744048"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리 하 여 모든 셀의 모양을 사용자 지정할 수 있습니다. <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 속성에서 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Drawing.Graphics>을 추출할 수 있습니다. 이 <xref:System.Drawing.Graphics>사용 하면 전체 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양에 영향을 줄 수 있지만 일반적으로 현재 칠하는 중인 셀의 모양에만 영향을 줍니다. <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>의 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 속성을 사용 하면 그리기 작업을 현재 칠하는 셀로 제한할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 색 구성표를 사용 하 여 `ContactName` 열의 모든 셀을 그립니다. 각 셀의 텍스트 콘텐츠는 <xref:System.Drawing.Color.Crimson%2A>그려집니다. 삽입 사각형은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성과 동일한 색으로 그려집니다.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- Northwind 샘플 데이터베이스의 Customers 테이블에 있는 것과 같은 `ContactName` 열과 함께 `dataGridView1` 라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
- System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)
