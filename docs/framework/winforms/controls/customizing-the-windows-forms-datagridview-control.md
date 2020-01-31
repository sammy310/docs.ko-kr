---
title: DataGridView 컨트롤 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744031"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤 사용자 지정
`DataGridView` 컨트롤은 셀, 행 및 열의 모양 및 기본 동작 (모양 및 느낌)을 조정 하는 데 사용할 수 있는 몇 가지 속성을 제공 합니다. 그러나 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 기능 외에도 특별 한 요구 사항이 있는 경우 컨트롤에 대 한 소유자 그리기를 구현 하거나 사용자 지정 셀, 열 및 행을 만들어 해당 기능을 확장할 수 있습니다.  
  
 셀과 행을 직접 그리려면 다양 한 `DataGridView` 그리기 이벤트를 처리할 수 있습니다. 기존 기능을 수정 하거나 새로운 기능을 제공 하기 위해 기존 `DataGridViewCell`, `DataGridViewColumn`및 `DataGridViewRow` 형식에서 파생 된 고유한 형식을 만들 수 있습니다. 셀이 편집 모드에 있을 때 선택한 컨트롤을 표시 하는 파생 형식을 만들어 새로운 편집 기능을 제공할 수도 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md)  
 셀을 수동으로 그리기 위해 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](customize-the-appearance-of-rows-in-the-datagrid.md)  
 여러 열에 걸쳐 있는 사용자 지정, 그라데이션 배경 및 콘텐츠를 사용 하 여 행을 그리기 위해 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트를 처리 하는 방법을 설명 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 마우스 포인터가 위에 있을 때 셀을 강조 표시 하기 위해 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 단추 열에 비활성화 된 단추를 표시 하기 위해 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn>에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.  
  
 [방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 셀이 편집 모드에 있을 때 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 표시 하기 위해 `IDataGridViewEditingControl` 인터페이스를 구현 하 고 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell> 클래스에 대 한 참조 설명서를 제공 합니다.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow> 클래스에 대 한 참조 설명서를 제공 합니다.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewColumn> 클래스에 대 한 참조 설명서를 제공 합니다.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스에 대 한 참조 설명서를 제공 합니다.  
  
## <a name="related-sections"></a>관련 섹션  
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.  
  
## <a name="see-also"></a>참조

- [DataGridView 컨트롤](datagridview-control-windows-forms.md)
- [Windows Forms DataGridView 컨트롤의 열 형식](column-types-in-the-windows-forms-datagridview-control.md)
