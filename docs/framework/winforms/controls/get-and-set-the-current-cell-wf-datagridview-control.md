---
title: '방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: fb71a6e3259d3007e11f528377c95a9c4cbeb023
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096981"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정
와 상호 작용을 <xref:System.Windows.Forms.DataGridView> 를 프로그래밍 방식으로 검색 된 셀을 현재 활성 종종 필요 합니다. 현재 셀을 변경 해야 합니다. 이러한 작업을 수행할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성입니다.  
  
> [!NOTE]
>  현재 셀의 행 이나 열에 설정할 수 없습니다 해당 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성이 설정 `false`합니다.  
  
 에 따라는 <xref:System.Windows.Forms.DataGridView> 현재 셀 변경 되는 컨트롤의 선택 모드 선택을 변경할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)합니다.  
  
### <a name="to-get-the-current-cell-programmatically"></a>현재 셀을 프로그래밍 방식으로 가져오려면  
  
-   사용 된 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>현재 셀을 프로그래밍 방식으로 설정 하려면  
  
-   설정 합니다 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 의 속성을 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 다음 코드 예제에서 현재 셀의 행 0, 1 열에 설정 됩니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Windows.Forms.Button> 명명 된 컨트롤 `getCurrentCellButton` 고 `setCurrentCellButton`입니다. 시각적 개체의 C#에 연결 해야 합니다는 <xref:System.Windows.Forms.Control.Click> 예제 코드에 연결 된 이벤트 처리기에 각 단추에 대 한 이벤트입니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)
