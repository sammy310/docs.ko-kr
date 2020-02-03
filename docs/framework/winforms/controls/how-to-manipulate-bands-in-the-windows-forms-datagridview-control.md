---
title: DataGridView 컨트롤에서 밴드 조작
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], manipulating bands
- bands [Windows Forms], manipulating in Windows Forms
- DataGridView control [Windows Forms], manipulating bands
ms.assetid: 1ea3470e-480f-4edc-bcbd-51373eca3856
ms.openlocfilehash: 89fdf41a592ef241935f1f71157588a392320df3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736122"
---
# <a name="how-to-manipulate-bands-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 밴드 조작
다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.DataGridViewBand> 클래스가 파생되는 <xref:System.Windows.Forms.DataGridViewRow> 클래스의 속성을 사용하여 <xref:System.Windows.Forms.DataGridViewColumn> 행과 열을 조작하는 다양한 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewBandDemo.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewBandDemo.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewbanddemo.vb#0)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewBand>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](programming-with-cells-rows-and-columns-in-the-datagrid.md)
