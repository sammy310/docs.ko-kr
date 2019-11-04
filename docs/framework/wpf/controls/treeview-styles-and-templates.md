---
title: TreeView 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: f6dbe54324a5ad5e2f85719d819c035abfd644b1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460191"
---
# <a name="treeview-styles-and-templates"></a>TreeView 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.TreeView> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="treeview-parts"></a>TreeView 파트  
 <xref:System.Windows.Controls.TreeView> 컨트롤에는 명명 된 파트가 없습니다.  
  
 <xref:System.Windows.Controls.TreeView>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다. <xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.TreeView>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.  
  
## <a name="treeview-states"></a>TreeView 상태  
 다음 표에서는 <xref:System.Windows.Controls.TreeView> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem 파트  
 다음 표에서는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 명명 된 파트를 나열 합니다.  
  
|파트|Type|설명|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.Controls.TreeView> 컨트롤의 머리글 내용을 포함 하는 시각적 요소입니다.|  
  
## <a name="treeviewitem-states"></a>TreeViewItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.TreeViewItem>위에 배치 됩니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.TreeViewItem> 사용 하지 않도록 설정 되었습니다.|  
|포커스 있음|FocusStates|<xref:System.Windows.Controls.TreeViewItem>에 포커스가 있습니다.|  
|포커스 없음|FocusStates|<xref:System.Windows.Controls.TreeViewItem>에 포커스가 없습니다.|  
|넓게|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem> 컨트롤이 확장 됩니다.|  
|Collapsed|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem> 컨트롤이 축소 됩니다.|  
|HasItems|Hasstates 상태|<xref:System.Windows.Controls.TreeViewItem>에 항목이 있습니다.|  
|NoItems|Hasstates 상태|<xref:System.Windows.Controls.TreeViewItem>에 항목이 없습니다.|  
|선택함|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 선택 됩니다.|  
|SelectedInactive|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 선택 되어 있지만 활성화 되어 있지 않습니다.|  
|선택 취소|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 선택 되지 않았습니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="treeview-controltemplate-example"></a>TreeView ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.TreeView> 컨트롤 및 관련 형식에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)
