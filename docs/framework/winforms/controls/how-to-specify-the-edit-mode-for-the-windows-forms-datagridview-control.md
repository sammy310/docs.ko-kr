---
title: DataGridView 컨트롤에 편집 모드 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743770"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정
기본적으로 사용자는 입력 하거나 F2 키를 눌러 현재 <xref:System.Windows.Forms.DataGridView> 텍스트 상자 셀의 내용을 편집할 수 있습니다. 이렇게 하면 다음 조건이 모두 충족 될 경우 셀이 편집 모드로 전환 됩니다.  
  
- 기본 데이터 소스에서 편집을 지원 합니다.  
  
- <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있습니다.  
  
- <xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>가 아닌 경우  
  
- 셀, 행, 열 및 컨트롤의 `ReadOnly` 속성은 모두 `false`로 설정 됩니다.  
  
 편집 모드에서 사용자는 셀 값을 변경 하 고 ENTER 키를 눌러 변경 내용을 커밋하거나 ESC 키를 눌러 셀을 원래 값으로 되돌릴 수 있습니다.  
  
 현재 셀이 되는 즉시 셀이 편집 모드로 전환 되도록 <xref:System.Windows.Forms.DataGridView> 컨트롤을 구성할 수 있습니다. 이 경우에는 ENTER 키와 ESC 키의 동작이 변경 되지 않지만 값이 커밋되거나 되돌아간 후에는 셀이 편집 모드로 유지 됩니다. 사용자가 셀을 입력 하거나 F2 키를 누를 때만 셀이 편집 모드로 전환 되도록 컨트롤을 구성할 수도 있습니다. 마지막으로 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 메서드를 호출 하는 경우를 제외 하 고 셀이 편집 모드로 전환 되지 않도록 할 수 있습니다.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>DataGridView 컨트롤의 편집 모드를 변경 하려면  
  
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> 속성을 적절 한 <xref:System.Windows.Forms.DataGridViewEditMode> 열거형으로 설정 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤  
  
- <xref:System> 및 <xref:System.Windows.Forms> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 데이터 입력](data-entry-in-the-windows-forms-datagridview-control.md)
