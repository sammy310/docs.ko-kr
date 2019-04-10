---
title: Windows Forms DataGridView 컨트롤의 선택 모드
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 79e13e65938252015e43b59a962d40f20963a5df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097280"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 선택 모드
응용 프로그램 내에서 사용자 선택에 따라 작업을 수행 하려는 경우에 따라는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 작업에 따라 사용할 수 있는 선택 항목의 종류를 제한 하는 것이 좋습니다. 예를 들어, 응용 프로그램에서 현재 선택된 된 레코드에 대 한 보고서를 인쇄할 수 있습니다. 구성 하려는 경우에 <xref:System.Windows.Forms.DataGridView> 컨트롤 항상 행 내에서 아무 곳 이나 클릭 하 여 전체 행을 선택한 다음 이므로 한 번에 하나의 행을 선택할 수 있습니다.  
  
 설정 하 여 허용 되는 선택을 지정할 수 있습니다 합니다 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 다음 중 하나로 <xref:System.Windows.Forms.DataGridViewSelectionMode> 열거형 값입니다.  
  
|DataGridViewSelectionMode 값|설명|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|셀을 클릭 하 고 선택 합니다. 행 및 열 머리글 선택에 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|셀을 클릭 하 고 선택 합니다. 열 머리글을 클릭 하면 전체 열을 선택 합니다. 정렬에 대 한 열 헤더를 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|셀 또는 열 머리글을 클릭 하면 전체 열을 선택 합니다. 정렬에 대 한 열 헤더를 사용할 수 없습니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|셀 또는 행 머리글을 클릭 하면 전체 행을 선택 합니다.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|기본 선택 모드입니다. 셀을 클릭 하 고 선택 합니다. 행 머리글을 클릭 하 여 전체 행을 선택 합니다.|  
  
> [!NOTE]
>  현재 선택을 취소 런타임에 선택 모드를 자동으로 변경 합니다.  
  
 기본적으로 선택할 수 있습니다 여러 행, 열 또는 셀을 마우스로 끌어 확장 하거나 원하는 항목을 수정 하도록 선택 하거나 컨트롤의 모든 셀을 선택 하려면 왼쪽 위 머리글 셀을 클릭 하는 동안 CTRL 또는 shift 키를 눌러. 이 동작을 방지 하려면 설정 합니다 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성을 `false`입니다.  
  
 합니다 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 고 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> 모드 선택 하 고 DELETE 키를 눌러 행을 삭제 하는 작업을 할 수 있습니다. 현재 셀이 편집 모드에 있는 경우에 사용자가 행을 삭제할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성이 `true`, 데이터 원본 사용자 기반 행 삭제를 지원 합니다. 이러한 설정을 프로그래밍 방식으로 행을 삭제 해도 참고 합니다.  
  
## <a name="programmatic-selection"></a>프로그래밍 방식 선택  
 현재 선택 모드를 프로그래밍 방식 선택 뿐만 아니라 사용자 선택의 동작을 제한합니다. 설정 하 여 현재 선택 영역을 프로그래밍 방식으로 변경할 수 있습니다는 `Selected` 셀, 행 또는 열에 속성을 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 통해 해당 컨트롤의 모든 셀을 선택할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectAll%2A> 선택 모드에 따라 메서드. 사용 하 여 선택을 <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> 메서드.  
  
 경우는 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> 속성이로 설정 된 `true`를 추가할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 요소를 하거나 변경 하 여 선택 영역에서 제거를 `Selected` 요소의 속성입니다. 그렇지 않은 경우 설정 합니다 `Selected` 속성을 `true` 하나의 요소만 선택 영역에서 다른 요소를 자동으로 제거에 대 한 합니다.  
  
 값을 변경 합니다 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성은 현재 선택 영역을 변경 하지 않습니다.  
  
 컬렉션의 현재 선택된 된 셀, 행 또는 열을 검색할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 의 속성을 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 이러한 속성에 액세스은 비효율적 컨트롤의 모든 셀이 선택 합니다. 이 경우 성능 저하를 방지, 사용 된 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드 첫 번째입니다. 또한 선택된 된 셀의 수를 확인 하려면 이러한 컬렉션을 액세스, 행 또는 열 비효율적일 수 있습니다. 대신 사용 해야 합니다 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, 또는 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> 전달 하는 메서드는 <xref:System.Windows.Forms.DataGridViewElementStates.Selected> 값입니다.  
  
> [!TIP]
>  선택된 된 셀의 프로그래밍 방식으로 사용을 보여 주는 예제 코드에서 확인할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 클래스 개요입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
