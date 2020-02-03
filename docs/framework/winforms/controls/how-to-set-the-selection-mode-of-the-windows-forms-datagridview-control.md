---
title: DataGridView 컨트롤의 선택 모드 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: da866aac3ac5b08a06ec71744aadb4260bd0cfc4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743508"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정
다음 코드 예제에서는 행의 아무 곳 이나 클릭 하 여 자동으로 전체 행을 선택 하 고 한 번에 한 행씩 선택할 수 있도록 <xref:System.Windows.Forms.DataGridView> 컨트롤을 구성 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)
