---
title: Menu 스타일 및 템플릿
description: 메뉴 컨트롤 Windows Presentation Foundation 스타일 및 템플릿에 대해 알아봅니다. ControlTemplate를 수정 하 여 컨트롤에 고유한 모양을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 5187e4a479609686e39e043808931141ca52078c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164547"
---
# <a name="menu-styles-and-templates"></a>Menu 스타일 및 템플릿
이 항목에서는 컨트롤의 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Menu> . 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.  
  
## <a name="menu-parts"></a>메뉴 파트  
 <xref:System.Windows.Controls.Menu>컨트롤에 명명 된 파트가 없습니다.  
  
 에 대해를 만들 때 <xref:System.Windows.Controls.ControlTemplate> 템플릿에는 내에 <xref:System.Windows.Controls.Menu> 이 포함 될 수 있습니다 <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer> . 는의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목을 표시 하 <xref:System.Windows.Controls.Menu> 고,는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>이의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ScrollViewer> 이름을 지정 해야 합니다 <xref:System.Windows.Controls.ItemsPresenter> `ItemsPresenter` .  
  
## <a name="menu-states"></a>메뉴 상태  
 다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.Menu> .  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|Valid|ValidationStates|컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="menuitem-parts"></a>MenuItem 부분  
 다음 표에서는 컨트롤의 명명 된 파트를 나열 합니다 <xref:System.Windows.Controls.Menu> .  
  
|부분|Type|Description|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|하위 메뉴의 영역입니다.|  
  
 에 대해를 만들 때 <xref:System.Windows.Controls.ControlTemplate> 템플릿에는 내에 <xref:System.Windows.Controls.MenuItem> 이 포함 될 수 있습니다 <xref:System.Windows.Controls.ItemsPresenter> <xref:System.Windows.Controls.ScrollViewer> . 는의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목을 표시 하 <xref:System.Windows.Controls.MenuItem> 고,는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>이의 직계 자식이 아닌 경우 <xref:System.Windows.Controls.ScrollViewer> 이름을 지정 해야 합니다 <xref:System.Windows.Controls.ItemsPresenter> `ItemsPresenter` .  
  
## <a name="menuitem-states"></a>MenuItem 상태  
 다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.MenuItem> .  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|Valid|ValidationStates|컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성은 `true` 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이 `true` 컨트롤에 포커스가 없는 경우|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Menu 및 MenuItem ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Menu> .  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.MenuItem> .  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 다음 예제에서는 `MenuScrollViewer` 이전 예제에서 사용 되는을 정의 합니다.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 이 <xref:System.Windows.Controls.ControlTemplate> 예제에서는 다음 리소스 중 하나 이상을 사용 합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [컨트롤의 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)
