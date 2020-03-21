---
title: Popup 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185948"
---
# <a name="popup-overview"></a>Popup 개요
컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 지정된 요소 또는 화면 좌표를 기준으로 현재 응용 프로그램 창 위에 떠 있는 별도의 창에 콘텐츠를 표시하는 방법을 제공합니다. 이 항목에서는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 소개하고 해당 컨트롤의 사용에 대한 정보를 제공합니다.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Popup이란?  
 컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 화면의 요소 또는 점을 기준으로 별도의 창에 콘텐츠를 표시합니다. 이 <xref:System.Windows.Controls.Primitives.Popup> 표시되면 속성이 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 로 `true`설정됩니다.  
  
> [!NOTE]
> 마우스 <xref:System.Windows.Controls.Primitives.Popup> 포인터가 상위 개체 위로 이동할 때 A가 자동으로 열리지 않습니다. 를 <xref:System.Windows.Controls.Primitives.Popup> 자동으로 열려면 또는 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> 클래스를 사용합니다. 자세한 내용은 [ToolTip 개요](tooltip-overview.md)를 참조하세요.  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>팝업 만들기  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Button> 컨트롤의 자식 요소인 컨트롤을 정의하는 방법을 보여 주며 있습니다. a에는 <xref:System.Windows.Controls.Button> 자식 요소가 하나만 있을 수 있으므로 <xref:System.Windows.Controls.Button> 이 <xref:System.Windows.Controls.Primitives.Popup> 예제에서는 <xref:System.Windows.Controls.StackPanel>에 대한 텍스트와 컨트롤을 에 배치합니다. 의 내용은 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.TextBlock> 관련 <xref:System.Windows.Controls.Button> 컨트롤 근처의 응용 프로그램 창 위에 떠 있는 별도의 창에 텍스트를 표시하는 컨트롤에 나타납니다.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Popup을 구현하는 컨트롤  
 컨트롤을 <xref:System.Windows.Controls.Primitives.Popup> 다른 컨트롤로 빌드할 수 있습니다. 다음 컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 특정 용도에 대한 컨트롤을 구현합니다.  
  
- <xref:System.Windows.Controls.ToolTip>. 요소에 대한 도구 설명을 만들려면 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스를 사용합니다. 자세한 내용은 [ToolTip 개요](tooltip-overview.md)를 참조하세요.  
  
- <xref:System.Windows.Controls.ContextMenu>. 요소에 대한 컨텍스트 메뉴를 만들려면 컨트롤을 <xref:System.Windows.Controls.ContextMenu> 사용합니다. 자세한 내용은 [ContextMenu 개요](contextmenu-overview.md)를 참조하세요.  
  
- <xref:System.Windows.Controls.ComboBox>. 표시하거나 숨길 수 있는 드롭다운 목록 상자가 있는 선택 컨트롤을 만들려면 컨트롤을 <xref:System.Windows.Controls.ComboBox> 사용합니다.  
  
- <xref:System.Windows.Controls.Expander>. 콘텐츠를 표시하는 축소 가능한 영역이 있는 헤더를 표시하는 컨트롤을 만들려면 컨트롤을 <xref:System.Windows.Controls.Expander> 사용합니다. 자세한 내용은 [Expander 개요](expander-overview.md)를 참조하세요.  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Popup 동작 및 모양  
 컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 동작 및 모양을 사용자 지정할 수 있는 기능을 제공합니다. 예를 들어 열린 동작과 닫기 동작, 애니메이션, 불투명도 및 <xref:System.Windows.Controls.Primitives.Popup> 비트맵 효과, 크기 및 위치를 설정할 수 있습니다.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>열기 및 닫기 동작  
 컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 로 설정될 `true`때 해당 내용을 표시합니다. 기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 속성이 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 로 설정될 `false`때까지 열려 있습니다. 그러나 <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> 속성을 로 설정하여 기본 동작을 `false`변경할 수 있습니다. 이 속성을 `false`로 설정하면 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창에 마우스 캡처가 있습니다. 마우스 <xref:System.Windows.Controls.Primitives.Popup> 캡처가 손실되고 창 외부에서 마우스 이벤트가 <xref:System.Windows.Controls.Primitives.Popup> 발생하면 창이 닫힙납니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup.Opened> 및 <xref:System.Windows.Controls.Primitives.Popup.Closed> 및 이벤트는 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창이 열려 있거나 닫혀 있을 때 발생합니다.  
  
<a name="Animation"></a>
### <a name="animation"></a>애니메이션  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 일반적으로 페이드 인 및 슬라이드 인과 같은 동작과 관련된 애니메이션에 대한 기본 제공 지원이 있습니다. <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> 속성을 열거부 값으로 설정하여 이러한 <xref:System.Windows.Controls.Primitives.PopupAnimation> 애니메이션을 켤 수 있습니다. <xref:System.Windows.Controls.Primitives.Popup> 애니메이션이 올바르게 작동하려면 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`로 설정해야 합니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 같은 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 적용할 수도 있습니다.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>불투명도 및 비트맵 효과  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 <xref:System.Windows.UIElement.Opacity%2A> 속성은 해당 콘텐츠에 영향을 주지 않습니다. 기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창은 불투명합니다. 투명을 <xref:System.Windows.Controls.Primitives.Popup>만들려면 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`로 설정합니다.  
  
 a의 <xref:System.Windows.Controls.Primitives.Popup> 내용은 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> <xref:System.Windows.Controls.Primitives.Popup> 컨트롤또는 부모 창의 다른 요소에 직접 설정한 와 같은 비트맵 효과를 상속하지 않습니다. 의 콘텐츠에 <xref:System.Windows.Controls.Primitives.Popup>비트맵 효과가 나타나려면 해당 콘텐츠에 비트맵 효과를 직접 설정해야 합니다. 예를 들어 a의 자식이 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.StackPanel>"의 경우 에서 비트맵 효과를 <xref:System.Windows.Controls.StackPanel>설정합니다.  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Popup 크기  
 기본적으로 a는 <xref:System.Windows.Controls.Primitives.Popup> 해당 콘텐츠에 자동으로 크기가 조정됩니다. 자동 크기 조정이 발생하면 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠에 정의된 화면 영역의 기본 크기가 비트맵 효과를 표시할 충분한 공간을 제공하지 않기 때문에 일부 비트맵 효과가 숨뤄질 수 있습니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup>콘텐츠를 설정할 <xref:System.Windows.UIElement.RenderTransform%2A> 때 콘텐츠가 가려질 수도 있습니다. 이 시나리오에서는 변환된 <xref:System.Windows.Controls.Primitives.Popup> 내용이 원본 <xref:System.Windows.Controls.Primitives.Popup>영역을 초과하면 일부 콘텐츠가 숨질 수 있습니다. 비트맵 효과 또는 변환에 더 많은 공간이 필요한 <xref:System.Windows.Controls.Primitives.Popup> 경우 컨트롤에 더 많은 영역을 제공하기 위해 콘텐츠 주위의 여백을 정의할 수 있습니다.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Popup 위치 정의  
 설정 하 여 팝업을 배치할 수는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> 속성입니다. 자세한 내용은 [Popup 배치 동작](popup-placement-behavior.md)을 참조하세요. 때 <xref:System.Windows.Controls.Primitives.Popup> 표시 되는 화면에서 이전 위치를 자체 나면 부모가 재배치 된 경우.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 <xref:System.Windows.Controls.Primitives.Popup> 표시할 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 위치를 기준으로 하는 좌표 집합을 지정하여 컨트롤의 배치를 <xref:System.Windows.Controls.Primitives.Popup> 사용자 지정할 수 있습니다.  
  
 배치를 사용자 지정하려면 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>로 설정합니다. 그런 다음 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> <xref:System.Windows.Controls.Primitives.Popup>에 대해 가능한 배치 점 및 기본 축(기본 축 순서)의 집합을 반환하는 대리자를 정의합니다. 의 가장 큰 부분을 표시하는 <xref:System.Windows.Controls.Primitives.Popup> 점이 자동으로 선택됩니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Popup 및 시각적 트리  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 자체 시각적 트리가 없습니다. 대신 에 대 <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> <xref:System.Windows.Controls.Primitives.Popup> 한 메서드가 호출 될 때 0 (0)의 크기를 반환 합니다. 그러나 의 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성을 <xref:System.Windows.Controls.Primitives.Popup> 설정하면 `true`자체 시각적 트리가 있는 새 창이 만들어집니다. 새 창에는 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 의 <xref:System.Windows.Controls.Primitives.Popup>내용이 포함되어 있습니다. 새 창의 너비와 높이는 화면 너비 또는 높이의 75%를 초과할 수 없습니다.  
  
 컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 논리적 자식으로 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 해당 콘텐츠에 대한 참조를 유지 관리합니다. 새 창이 만들어지면 의 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠는 창의 시각적 자식이 되고 <xref:System.Windows.Controls.Primitives.Popup>의 논리적 자식으로 유지됩니다. 반대로 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 콘텐츠의 <xref:System.Windows.Controls.Primitives.Popup> 논리적 상위 로 유지됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [방법 주제](popup-how-to-topics.md)
- [방법 주제](tooltip-how-to-topics.md)
