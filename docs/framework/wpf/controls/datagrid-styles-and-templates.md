---
title: DataGrid 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: 066e8c9ce1112399be8128d0821498f0d56a3dc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283799"
---
# <a name="datagrid-styles-and-templates"></a>DataGrid 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.  
  
## <a name="datagrid-parts"></a>DataGrid 파트  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|부분|형식|설명|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|열 머리글을 포함 하는 행입니다.|  
  
 <xref:System.Windows.Controls.DataGrid>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다. <xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.DataGrid>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.  
  
 <xref:System.Windows.Controls.DataGrid>에 대 한 기본 템플릿에는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤이 포함 되어 있습니다. <xref:System.Windows.Controls.ScrollViewer>에서 정의 되는 파트에 대 한 자세한 내용은 [ScrollViewer 스타일 및 템플릿](scrollviewer-styles-and-templates.md)을 참조 하세요.  
  
## <a name="datagrid-states"></a>DataGrid 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridcell-parts"></a>DataGridCell 파트  
 <xref:System.Windows.Controls.DataGridCell> 요소에는 명명 된 파트가 없습니다.  
  
## <a name="datagridcell-states"></a>DataGridCell 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGridCell> 요소에 대 한 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 셀 위에 배치 됩니다.|  
|포커스 있음|FocusStates|셀에 포커스가 있습니다.|  
|포커스 없음|FocusStates|셀에 포커스가 없습니다.|  
|현재|CurrentStates|현재 셀이 셀입니다.|  
|Regular|CurrentStates|셀이 현재 셀이 아닙니다.|  
|표시|InteractionStates|셀이 표시 모드에 있습니다.|  
|편집|InteractionStates|셀이 편집 모드에 있습니다.|  
|선택|SelectionStates|셀이 선택 됩니다.|  
|선택 취소|SelectionStates|셀이 선택 되지 않았습니다.|  
|InvalidFocused|ValidationStates|셀이 잘못 되었으며 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀이 잘못 되었으며 포커스가 없습니다.|  
|유효|ValidationStates|셀이 유효 합니다.|  
  
## <a name="datagridrow-parts"></a>DataGridRow 파트  
 <xref:System.Windows.Controls.DataGridRow> 요소에는 명명 된 파트가 없습니다.  
  
## <a name="datagridrow-states"></a>DataGridRow 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGridRow> 요소에 대 한 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 배치 됩니다.|  
|MouseOver_Editing|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 편집 모드에 있습니다.|  
|MouseOver_Selected|CommonStates|마우스 포인터가 행 위에 배치 되 고 행이 선택 됩니다.|  
|MouseOver_Unfocused_Editing|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 편집 모드에 있으며 포커스가 없는 경우|  
|MouseOver_Unfocused_Selected|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 선택 되며 포커스가 없습니다.|  
|Normal_AlternatingRow|CommonStates|행이 교대로 반복 되는 행입니다.|  
|Normal_Editing|CommonStates|행이 편집 모드에 있습니다.|  
|Normal_Selected|CommonStates|행이 선택 됩니다.|  
|Unfocused_Editing|CommonStates|행이 편집 모드에 있고 포커스가 없는 경우|  
|Unfocused_Selected|CommonStates|행이 선택 되어 있고 포커스가 없습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridrowheader-parts"></a>DataGridRowHeader 파트  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소에 대 한 명명 된 파트를 나열 합니다.  
  
|부분|형식|설명|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|위쪽에서 행 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|아래쪽에서 행 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
  
## <a name="datagridrowheader-states"></a>DataGridRowHeader 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소에 대 한 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 배치 됩니다.|  
|MouseOver_CurrentRow|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 현재 행 인 경우|  
|MouseOver_CurrentRow_Selected|CommonStates|마우스 포인터가 행 위에 배치 되 고 행이 현재 및 선택 됩니다.|  
|MouseOver_EditingRow|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 편집 모드에 있습니다.|  
|MouseOver_Selected|CommonStates|마우스 포인터가 행 위에 배치 되 고 행이 선택 됩니다.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|마우스 포인터가 행 위로 이동 하 고, 현재 행 이며, 선택 되어 있으며, 포커스가 없습니다.|  
|MouseOver_Unfocused_EditingRow|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 편집 모드에 있으며 포커스가 없는 경우|  
|MouseOver_Unfocused_Selected|CommonStates|마우스 포인터가 행 위에 위치 하 고 행이 선택 되며 포커스가 없습니다.|  
|Normal_CurrentRow|CommonStates|행이 현재 행입니다.|  
|Normal_CurrentRow_Selected|CommonStates|행이 현재 행 이며 선택 됩니다.|  
|Normal_EditingRow|CommonStates|행이 편집 모드에 있습니다.|  
|Normal_Selected|CommonStates|행이 선택 됩니다.|  
|Unfocused_CurrentRow_Selected|CommonStates|현재 행이 선택 되어 있고 포커스가 없는 경우|  
|Unfocused_EditingRow|CommonStates|행이 편집 모드에 있고 포커스가 없는 경우|  
|Unfocused_Selected|CommonStates|행이 선택 되어 있고 포커스가 없습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>DataGridColumnHeadersPresenter 파트  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소에 대 한 명명 된 파트를 나열 합니다.  
  
|부분|형식|설명|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|열 머리글의 자리 표시자입니다.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>DataGridColumnHeadersPresenter 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소에 대 한 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|InvalidFocused|ValidationStates|셀이 잘못 되었으며 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀이 잘못 되었으며 포커스가 없습니다.|  
|유효|ValidationStates|셀이 유효 합니다.|  
  
## <a name="datagridcolumnheader-parts"></a>DataGridColumnHeader 파트  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소에 대 한 명명 된 파트를 나열 합니다.  
  
|부분|형식|설명|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|왼쪽에서 열 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|오른쪽에서 열 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
  
## <a name="datagridcolumnheader-states"></a>DataGridColumnHeader 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소에 대 한 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|누름|CommonStates|컨트롤을 눌렀습니다.|  
|SortAscending|SortStates|열이 오름차순으로 정렬 됩니다.|  
|SortDescending|SortStates|열이 내림차순으로 정렬 됩니다.|  
|계층이|SortStates|열이 정렬 되어 있지 않습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagrid-controltemplate-example"></a>DataGrid ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤 및 관련 형식에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
