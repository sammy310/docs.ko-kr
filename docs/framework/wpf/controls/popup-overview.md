---
title: Popup 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 53283619d1bd2727bdca1df6a3a408ec0ce873a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625704"
---
# <a name="popup-overview"></a>Popup 개요
<xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 지정 된 요소 또는 화면 좌표를 기준으로 현재 응용 프로그램 창 위에 떠 있는 별도 창에서 콘텐츠를 표시 하는 방법을 제공 합니다. 이 항목에서는 소개를 <xref:System.Windows.Controls.Primitives.Popup> 제어 하 고 해당 사용에 대 한 정보를 제공 합니다.  

<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Popup이란?  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤 요소 또는 화면에서 점을 기준으로 별도 창에서 콘텐츠를 표시 합니다. 경우는 <xref:System.Windows.Controls.Primitives.Popup> 표시 되는 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 `true`.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Primitives.Popup> 자동으로 열리지 않으면 부모 개체 위로 마우스 포인터를 움직이면 합니다. 하려는 경우는 <xref:System.Windows.Controls.Primitives.Popup> 자동으로 열도록 하려면 사용 합니다 <xref:System.Windows.Controls.ToolTip> 또는 <xref:System.Windows.Controls.ToolTipService> 클래스입니다. 자세한 내용은 [ToolTip 개요](tooltip-overview.md)를 참조하세요.  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>팝업 만들기  
 다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 자식 요소인은 <xref:System.Windows.Controls.Button> 제어 합니다. 때문에 <xref:System.Windows.Controls.Button> 자식 요소가 하나만 있을 수 있습니다에 대 한 텍스트를 저장 하는이 예제는 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 <xref:System.Windows.Controls.StackPanel>입니다. 콘텐츠를 <xref:System.Windows.Controls.Primitives.Popup> 나타나는 <xref:System.Windows.Controls.TextBlock> 거의 관련 응용 프로그램 창 위에 떠 있는 별도 창에서 해당 텍스트를 표시 하는 컨트롤 <xref:System.Windows.Controls.Button> 컨트롤입니다.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Popup을 구현하는 컨트롤  
 빌드할 수 있습니다 <xref:System.Windows.Controls.Primitives.Popup> 다른 컨트롤에는 컨트롤입니다. 다음 컨트롤은 구현는 <xref:System.Windows.Controls.Primitives.Popup> 특정 용도 대 한 제어 합니다.  
  
- <xref:System.Windows.Controls.ToolTip>. 요소에 대 한 도구 설명을 만들려면 하려는 경우 사용 합니다 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스입니다. 자세한 내용은 [ToolTip 개요](tooltip-overview.md)를 참조하세요.  
  
- <xref:System.Windows.Controls.ContextMenu>. 요소에 대 한 상황에 맞는 메뉴를 만들려는 경우 사용 된 <xref:System.Windows.Controls.ContextMenu> 제어 합니다. 자세한 내용은 [ContextMenu 개요](contextmenu-overview.md)를 참조하세요.  
  
- <xref:System.Windows.Controls.ComboBox>. 표시 되거나 숨겨진를 사용할 수 있는 드롭다운 목록 상자가 포함 된 선택 컨트롤을 만들려는 경우를 <xref:System.Windows.Controls.ComboBox> 제어 합니다.  
  
- <xref:System.Windows.Controls.Expander>. 콘텐츠를 표시 하는 축소 가능한 영역을 사용 하 여 헤더를 표시 하는 컨트롤을 만들려는 경우, 사용 된 <xref:System.Windows.Controls.Expander> 제어 합니다. 자세한 내용은 [Expander 개요](expander-overview.md)를 참조하세요.  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Popup 동작 및 모양  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤의 동작과 모양을 사용자 지정할 수 있도록 하는 기능을 제공 합니다. 예를 들어 열기 및 닫기 동작, 애니메이션, 불투명도 및 비트맵 효과 설정할 수 있습니다 및 <xref:System.Windows.Controls.Primitives.Popup> 크기 및 위치입니다.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>열기 및 닫기 동작  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤 콘텐츠를 표시 합니다. 때 합니다 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 `true`합니다. 기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 될 때까지 열린 상태로 유지 됩니다 합니다 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성이 `false`합니다. 설정 하 여 기본 동작을 변경할 수는 있지만 합니다 <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> 속성을 `false`입니다. 이 속성을 설정 하면 `false`, <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창에 마우스 캡처가 합니다. 합니다 <xref:System.Windows.Controls.Primitives.Popup> 마우스 캡처가 사라지고 창이 닫힙니다 외부에서 마우스 이벤트를 발생 하는 경우는 <xref:System.Windows.Controls.Primitives.Popup> 창입니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup.Opened> 하 고 <xref:System.Windows.Controls.Primitives.Popup.Closed> 이벤트가 때는 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창이 열렸는지 닫혔는지 합니다.  
  
<a name="Animation"></a>   
### <a name="animation"></a>애니메이션  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 대개 페이드 인 및 슬라이드 인 같은 동작과 연관 되는 애니메이션을 기본적으로 지원 합니다. 이러한 애니메이션을 설정 하 여 켤 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> 속성을 <xref:System.Windows.Controls.Primitives.PopupAnimation> 열거형 값입니다. 에 대 한 <xref:System.Windows.Controls.Primitives.Popup> 제대로 작동 하려면 애니메이션을 설정 해야 합니다 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`.  
  
 등의 애니메이션을 적용할 수도 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 에 <xref:System.Windows.Controls.Primitives.Popup> 제어 합니다.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>불투명도 및 비트맵 효과  
 <xref:System.Windows.UIElement.Opacity%2A> 에 대 한 속성을 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 해당 내용에 영향을 주지 않습니다. 기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠 창은 불투명 합니다. 투명 하 게 만들려면 <xref:System.Windows.Controls.Primitives.Popup>로 설정 합니다 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`입니다.  
  
 콘텐츠를 <xref:System.Windows.Controls.Primitives.Popup> 같은 비트맵 효과 상속 하지 않습니다 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>에서 직접 설정 하는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤 또는 부모 창에 있는 다른 요소. 내용에 표시할 비트맵 효과 <xref:System.Windows.Controls.Primitives.Popup>를 내용에 직접 비트맵 효과 설정 해야 합니다. 예를 들어 경우의 자식을 <xref:System.Windows.Controls.Primitives.Popup> 는 <xref:System.Windows.Controls.StackPanel>, 비트맵 효과 설정 합니다 <xref:System.Windows.Controls.StackPanel>합니다.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Popup 크기  
 기본적으로 <xref:System.Windows.Controls.Primitives.Popup> 크기가 콘텐츠에 맞게 자동으로 조정 합니다. 자동 크기 조정 되는 경우 일부 비트맵 효과가 숨겨질 수 있습니다에 대해 정의 된 화면 영역의 기본 크기는 <xref:System.Windows.Controls.Primitives.Popup> 콘텐츠에 비트맵 효과를 표시할 공간이 충분 하지 않습니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup> 설정 하는 경우 콘텐츠가 가려질 수도 있습니다는 <xref:System.Windows.UIElement.RenderTransform%2A> 콘텐츠입니다. 이 시나리오에서는 일부 콘텐츠가 숨겨질 수 있습니다 하는 경우 변환 된 내용의 <xref:System.Windows.Controls.Primitives.Popup> 원본 영역을 넘어가는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 비트맵 효과 또는 변환에 추가 공간이 필요한 경우 주위에 여백을 정의할 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 대 한 더 많은 영역을 제공 하기 위해 콘텐츠입니다.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Popup 위치 정의  
 설정 하 여 팝업을 배치할 수는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> 속성입니다. 자세한 내용은 [Popup 배치 동작](popup-placement-behavior.md)을 참조하세요. 때 <xref:System.Windows.Controls.Primitives.Popup> 표시 되는 화면에서 이전 위치를 자체 나면 부모가 재배치 된 경우.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 배치를 사용자 지정할 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 하는 좌표 집합을 지정 하 여 컨트롤을 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 하려는 <xref:System.Windows.Controls.Primitives.Popup> 표시.  
  
 배치를 사용자 지정을 설정 합니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>입니다. 그런 다음 정의 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 에 대 한 가능한 배치 지점 및 기본 축을 (기본 설정의 순서로)의 집합을 반환 하는 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 가장 큰 부분을 표시 하는 지점이 <xref:System.Windows.Controls.Primitives.Popup> 자동으로 선택 됩니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Popup 및 시각적 트리  
 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 자체 시각적 트리가; 0 크기를 대신 반환 될 때 (0)를 <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> 에 대 한 메서드 <xref:System.Windows.Controls.Primitives.Popup> 라고 합니다. 그러나 설정한 경우에 합니다 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> 속성을 <xref:System.Windows.Controls.Primitives.Popup> 를 `true`, 자체 시각적 트리를 사용 하 여 새 창이 만들어집니다. 새 창에 포함 된 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 내용의 <xref:System.Windows.Controls.Primitives.Popup>합니다. 새 창의 너비와 높이는 화면 너비 또는 높이의 75%를 초과할 수 없습니다.  
  
 합니다 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 대 한 참조를 유지 관리는 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 논리 자식으로 콘텐츠. 새 창이 만들어지면, 내용의 <xref:System.Windows.Controls.Primitives.Popup> 창의 시각적 자식이 되 고의 논리적 자식 남아 <xref:System.Windows.Controls.Primitives.Popup>합니다. 반대로 <xref:System.Windows.Controls.Primitives.Popup> 의 논리적 부모를 유지 해당 <xref:System.Windows.Controls.Primitives.Popup.Child%2A> 콘텐츠입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [방법 항목](popup-how-to-topics.md)
- [방법 항목](tooltip-how-to-topics.md)
