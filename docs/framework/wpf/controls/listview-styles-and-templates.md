---
title: ListView 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ListView
- states [WPF], ListView
- ControlTemplate [WPF], ListView
- styles [WPF], ListView
- ListView [WPF], styles and templates
- templates [WPF], ListView
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
ms.openlocfilehash: 5f5a9d9f747246ee9b72b42a45291a42bb04cb88
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459384"
---
# <a name="listview-styles-and-templates"></a>ListView 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다. 기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="listview-parts"></a>ListView 파트  
 <xref:System.Windows.Controls.ListView> 컨트롤에는 명명 된 파트가 없습니다.  
  
 <xref:System.Windows.Controls.ListView>에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 만들 때 템플릿에 <xref:System.Windows.Controls.ScrollViewer>내에 <xref:System.Windows.Controls.ItemsPresenter> 포함 될 수 있습니다. <xref:System.Windows.Controls.ItemsPresenter>은 <xref:System.Windows.Controls.ListView>의 각 항목을 표시 하 고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ItemsPresenter> 이름 `ItemsPresenter`를 지정 해야 합니다.  
  
## <a name="listview-states"></a>ListView 상태  
 다음 표에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 시각적 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="listviewitem-parts"></a>ListViewItem 파트  
 <xref:System.Windows.Controls.ListViewItem> 컨트롤에는 명명 된 파트가 없습니다.  
  
## <a name="listviewitem-states"></a>ListViewItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.ListViewItem> 컨트롤의 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|컨트롤이 비활성화되었습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.ComboBox> 컨트롤 위에 있습니다.|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
|선택함|SelectionStates|항목이 현재 선택 되어 있습니다.|  
|선택 취소|SelectionStates|항목이 선택되어 있지 않습니다.|  
|SelectedUnfocused|SelectionStates|항목이 선택되었지만 항목에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.|  
|InvalidFocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="listview-controltemplate-examples"></a>ListView ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤 및 관련 형식에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[ControlTemplateExamples#ListView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 <xref:System.Windows.Controls.ControlTemplate> 예제에서는 다음 리소스 중 하나 이상을 사용 합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)
