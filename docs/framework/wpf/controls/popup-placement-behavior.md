---
title: Popup 배치 동작
description: 속성을 사용하여 컨트롤, 마우스 또는 화면을 기준으로 Windows Presentation Foundation Popup을 배치하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 8184805518bc56693ead4c7d1f0e9a1bff9bff8f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167740"
---
# <a name="popup-placement-behavior"></a>Popup 배치 동작
<xref:System.Windows.Controls.Primitives.Popup> 컨트롤은 콘텐츠를 애플리케이션 위에 떠 있는 별도의 창에 표시합니다. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용하여 컨트롤, 마우스 또는 화면을 기준으로 <xref:System.Windows.Controls.Primitives.Popup>을 배치할 수 있습니다.  해당 속성을 함께 사용하여 <xref:System.Windows.Controls.Primitives.Popup>의 위치를 유연하게 지정할 수 있습니다.  
  
> [!NOTE]
> <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ContextMenu> 클래스도 이러한 다섯 가지 속성을 정의하고 비슷하게 동작합니다.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Popup 위치 지정  
 <xref:System.Windows.Controls.Primitives.Popup>은 <xref:System.Windows.UIElement> 또는 전체 화면을 기준으로 배치할 수 있습니다.  다음 예에서는 <xref:System.Windows.UIElement>(이 경우 이미지)를 기준으로 하는 네 개의 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 만듭니다. 모든 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 `image1`로 설정된 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이 있지만, 각 <xref:System.Windows.Controls.Primitives.Popup>에 있는 배치 속성의 값은 서로 다릅니다.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 다음 그림에서는 이미지와 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 보여 줍니다.  
  
 ![네 개의 Popup 컨트롤이 있는 이미지](./media/popup-placement-behavior/popup-placement-intro.png "네 개의 Popup이 있는 이미지")
  
 이 간단한 예에서는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 설정하는 방법을 보여 주지만 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용하면 <xref:System.Windows.Controls.Primitives.Popup>을 배치하는 위치를 더 많이 제어할 수 있습니다.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>용어 정의: Popup 분석  
 다음 용어는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성이 서로 관련되는 방식 및 <xref:System.Windows.Controls.Primitives.Popup>을 이해하는 데 유용합니다.  
  
- 대상 개체  
  
- 대상 영역  
  
- 대상 원점  
  
- Popup 맞춤 지점  
  
 해당 용어를 사용하여 <xref:System.Windows.Controls.Primitives.Popup> 및 이와 연결된 컨트롤의 다양한 측면을 편리하게 나타낼 수 있습니다.  
  
### <a name="target-object"></a>대상 개체  
 ‘대상 개체’는 <xref:System.Windows.Controls.Primitives.Popup>과 연결된 요소입니다. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이 설정되면 대상 개체를 지정합니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이 설정되지 않았고 <xref:System.Windows.Controls.Primitives.Popup>에 부모가 있는 경우 부모가 대상 개체입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 값이 없고 부모가 없는 경우에는 대상 개체가 없으며 <xref:System.Windows.Controls.Primitives.Popup>이 화면을 기준으로 배치됩니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Canvas>의 자식인 <xref:System.Windows.Controls.Primitives.Popup>을 만듭니다.  이 예에서는 <xref:System.Windows.Controls.Primitives.Popup>에 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성을 설정하지 않습니다. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>이므로 <xref:System.Windows.Controls.Primitives.Popup>이 <xref:System.Windows.Controls.Canvas>아래에 나타납니다.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup>이 <xref:System.Windows.Controls.Canvas>를 기준으로 배치된 것을 보여 줍니다.  
  
 ![PlacementTarget이 없는 Popup 컨트롤](./media/popup-placement-behavior/popup-placement-no-placement-target.png "PlacementTarget을 사용한 Popup")  

 다음 예에서는 <xref:System.Windows.Controls.Canvas>의 자식인 <xref:System.Windows.Controls.Primitives.Popup>을 만들지만 이번에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>이 `ellipse1`로 설정되었으므로 팝업이 <xref:System.Windows.Shapes.Ellipse> 아래에 나타납니다.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup>이 <xref:System.Windows.Shapes.Ellipse>를 기준으로 배치된 것을 보여 줍니다.  
  
 ![타원을 기준으로 배치되는 Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "PlacementTarget이 있는 Popup 컨트롤")
  
> [!NOTE]
> <xref:System.Windows.Controls.ToolTip>의 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>입니다.  <xref:System.Windows.Controls.ContextMenu>의 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>입니다. 이러한 값은 나중에 "속성을 함께 사용하는 방법"에서 설명합니다.  
  
### <a name="target-area"></a>대상 영역  
 ‘대상 영역’은 <xref:System.Windows.Controls.Primitives.Popup>을 기준으로 하는 화면 영역입니다. 이전 예에서 <xref:System.Windows.Controls.Primitives.Popup>은 대상 개체의 경계에 맞춰지지만 일부 경우에는 <xref:System.Windows.Controls.Primitives.Popup>에 대상 개체가 있더라도 <xref:System.Windows.Controls.Primitives.Popup>이 다른 경계에 맞춰집니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 속성이 설정된 경우 대상 영역은 대상 개체의 경계와 다릅니다.  
  
 다음 예에서는 각각 <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Controls.Primitives.Popup>을 포함하는 두 개의 <xref:System.Windows.Controls.Canvas> 개체를 만듭니다.  두 경우 모두 <xref:System.Windows.Controls.Primitives.Popup>의 대상 개체는 <xref:System.Windows.Controls.Canvas>입니다. 첫 번째 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Primitives.Popup>에는 <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, <xref:System.Windows.Rect.Height%2A> 속성이 각각 50, 50, 50, 100으로 설정된 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>이 설정되어 있습니다. 두 번째 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Primitives.Popup>에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>이 설정되어 있지 않습니다.  그 결과, 첫 번째 <xref:System.Windows.Controls.Primitives.Popup>은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 아래에 배치되고 두 번째 <xref:System.Windows.Controls.Primitives.Popup>은 <xref:System.Windows.Controls.Canvas> 아래에 배치됩니다. 각 <xref:System.Windows.Controls.Canvas>에는 첫 번째 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>과 동일한 경계를 가진 <xref:System.Windows.Shapes.Rectangle>도 포함됩니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 애플리케이션에서 시각적 요소를 만들지 않습니다. 예에서는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>을 나타내는 <xref:System.Windows.Shapes.Rectangle>을 만듭니다.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![PlacementRectangle이 있을 때와 없을 때의 Popup](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "PlacementRectangle을 사용한 Popup과 사용하지 않은 Popup")  

### <a name="target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점  
 *대상 원점* 및 *Popup 맞춤 지점*은 각각 대상 영역 및 Popup에서 위치 지정에 사용되는 참조 지점입니다. <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용하여 대상 영역에서 팝업을 오프셋할 수 있습니다.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>은 대상 원점과 Popup 맞춤 지점을 기준으로 합니다. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성의 값은 대상 원점 및 Popup 맞춤 지점의 위치를 결정합니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Primitives.Popup>을 만들고 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 20으로 설정합니다.  <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>(기본값)으로 설정되어 대상 원점이 대상 영역의 왼쪽 아래 모퉁이에 위치하고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이에 위치합니다.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![대상 원점 맞춤 지점을 사용한 Popup 배치](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "HorizontalOffset 및 VerticalOffset을 사용한 Popup")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>속성을 함께 사용하는 방법  
 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 값을 함께 고려하여 올바른 대상 영역, 대상 원점 및 Popup 맞춤 지점을 파악해야 합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 값이 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>인 경우 대상 개체는 없으며 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 무시되고 대상 영역은 마우스 포인터의 경계입니다. 반면, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>인 경우에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모가 대상 개체를 결정하고 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>이 대상 영역을 결정합니다.  
  
 다음 표에서는 대상 개체, 대상 영역, 대상 원점 및 Popup 맞춤 지점에 대해 설명하고 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 열거형 값에 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>이 사용되는지를 나타냅니다.  
  
|PlacementMode|대상 개체|대상 영역|대상 원점|Popup 맞춤 지점|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 화면을 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 화면을 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 아래 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 가운데.|<xref:System.Windows.Controls.Primitives.Popup>의 가운데입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>에서 정의됩니다.|<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>에서 정의됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 상단 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>는 무시됩니다.|대상 영역의 왼쪽 아래 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>는 무시됩니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 오른쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>(설정된 경우)입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>은 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|<xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이입니다.|  
  
 다음 그림에서는 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대한 <xref:System.Windows.Controls.Primitives.Popup>, 대상 영역, 대상 원점 및 Popup 맞춤 지점을 보여 줍니다. 각 그림에서 대상 영역은 노란색이고 <xref:System.Windows.Controls.Primitives.Popup>은 파란색입니다.  
  
 ![Absolute 또는 AbsolutePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-absolute.png "Placement가 Absolute 또는 AbsolutePoint임")
  
 ![Bottom 배치의 Popup](./media/popup-placement-behavior/popup-placement-bottom.png "Placement가 Bottom임")
  
 ![Center 배치의 Popup](./media/popup-placement-behavior/popup-placement-center.png "Placement가 Center임")
  
 ![Left 배치의 Popup](./media/popup-placement-behavior/popup-placement-left.png "Placement가 Left임")
  
 ![Mouse 배치의 Popup](./media/popup-placement-behavior/popup-placement-mouse.png "Placement가 Mouse임")  
  
 ![MousePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-mousepoint.png "Placement가 MousePoint임")  
  
 ![Relative 또는 RelativePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-relative.png "Placement가 Relative 또는 RelativePoint임")
  
 ![Right 배치의 Popup](./media/popup-placement-behavior/popup-placement-right.png "Placement가 Right임")
  
 ![Top 배치의 Popup](./media/popup-placement-behavior/popup-placement-top.png "Placement가 Top임")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Popup이 화면 가장자리와 만나는 경우  
 보안상의 이유로 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup>을 숨길 수 없습니다. <xref:System.Windows.Controls.Primitives.Popup>이 화면 가장자리와 만나면 다음 세 가지 중 하나가 발생합니다.  
  
- <xref:System.Windows.Controls.Primitives.Popup>을 숨기는 화면 가장자리를 따라 팝업이 자체적으로 다시 조정됩니다.  
  
- Popup에 다른 Popup 맞춤 지점이 사용됩니다.  
  
- Popup에 다른 대상 원점 및 Popup 맞춤 지점이 사용됩니다.  
  
 이러한 옵션은 이 섹션의 뒷부분에서 설명합니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup>이 화면 가장자리와 만날 때 동작은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성의 값과 팝업이 만나는 가장자리에 따라 다릅니다. 다음 표에서는 <xref:System.Windows.Controls.Primitives.Popup>이 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대한 화면 가장자리와 만날 때 동작을 요약해 보여 줍니다.  
  
|PlacementMode|위쪽 가장자리|아래쪽 가장자리|왼쪽 가장자리|오른쪽 가장자리|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 오른쪽 위 모퉁이로 변경되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이로 변경됩니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역(마우스 포인터의 경계)의 왼쪽 위 모퉁이로 변경되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|대상 원점이 대상 영역의 왼쪽 아래 모퉁이로 변경되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이로 변경됩니다. 실제로 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>인 경우와 동일합니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
  
### <a name="aligning-to-the-screen-edge"></a>화면 가장자리에 맞춤  
 전체 <xref:System.Windows.Controls.Primitives.Popup>이 화면에 표시되도록 자체적으로 재배치되어 <xref:System.Windows.Controls.Primitives.Popup>을 화면 가장자리에 맞출 수 있습니다.  이 경우 대상 원점과 Popup 맞춤 지점 간의 거리가 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>의 값과 다를 수도 있습니다. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>인 경우 <xref:System.Windows.Controls.Primitives.Popup>은 모든 화면 가장자리에 맞춰집니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>로, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>이 100으로 설정되어 있다고 가정하겠습니다.  화면의 아래쪽 가장자리가 전체 또는 일부 <xref:System.Windows.Controls.Primitives.Popup>을 가리면 <xref:System.Windows.Controls.Primitives.Popup>은 화면의 아래쪽 가장자리를 따라 재배치되고 대상 원점과 Popup 맞춤 지점 간의 세로 거리는 100보다 작습니다. 다음 그림에서 이 경우를 보여 줍니다.  
  
 ![화면 가장자리에 맞춰진 Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "화면 가장자리에 맞춰진 Popup")
  
### <a name="changing-the-popup-alignment-point"></a>Popup 맞춤 지점 변경  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>인 경우 팝업이 아래쪽 또는 오른쪽 화면 가장자리와 만나면 Popup 맞춤 지점이 변경됩니다.  
  
 다음 그림에서는 아래쪽 화면 가장자리가 전체 또는 일부 <xref:System.Windows.Controls.Primitives.Popup>을 숨길 경우 Popup 맞춤 지점은 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이임을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup이 화면의 아래쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함")  

 다음 그림에서는 오른쪽 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup>을 숨길 경우 Popup 맞춤 지점은 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이임을 보여 줍니다.  
  
 ![화면 가장자리로 인한 새로운 Popup 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup이 화면의 오른쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함")
  
 <xref:System.Windows.Controls.Primitives.Popup>이 아래쪽 및 오른쪽 화면 가장자리와 만나는 경우 Popup 맞춤 지점은 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 아래 모퉁이입니다.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점 변경  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Top>인 경우 특정 화면 가장자리와 만나면 대상 원점 및 Popup 맞춤 지점이 변경됩니다.  위치가 변경되도록 하는 화면 가장자리는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 따라 다릅니다.  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>이고 <xref:System.Windows.Controls.Primitives.Popup>이 아래쪽 화면 가장자리와 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이가 되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이가 되는 것을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Placement가 Bottom이고 Popup이 화면의 아래쪽 가장자리와 만남")
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Left>이고 <xref:System.Windows.Controls.Primitives.Popup>이 왼쪽 화면 가장자리와 만나면 대상 원점이 대상 영역의 오른쪽 위 모퉁이가 되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이가 되는 것을 보여 줍니다.  
  
 ![왼쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Placement가 Left이고 Popup이 화면의 왼쪽 가장자리와 만남")  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Right>이고 <xref:System.Windows.Controls.Primitives.Popup>이 오른쪽 화면 가장자리와 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이가 되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이가 되는 것을 보여 줍니다.  
  
 ![오른쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Placement가 Right이고 Popup이 화면의 오른쪽 가장자리와 만남")  

 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Top>이고 <xref:System.Windows.Controls.Primitives.Popup>이 위쪽 화면 가장자리와 만나면 대상 원점이 대상 영역의 왼쪽 아래 모퉁이가 되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이가 되는 것을 보여 줍니다.  
  
 ![위쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Placement가 Top이고 Popup이 화면의 위쪽 가장자리와 만남")  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>가 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>이고 <xref:System.Windows.Controls.Primitives.Popup>이 아래쪽 화면 가장자리와 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이(마우스 포인터의 경계)가 되고 Popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이가 되는 것을 보여 줍니다.  
  
 ![화면 가장자리 근처의 마우스로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Placement가 Mouse이고 Popup이 화면의 아래쪽 가장자리와 만남")
  
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>으로 설정하여 대상 원점 및 Popup 맞춤 지점을 사용자 지정할 수 있습니다. 그런 다음 <xref:System.Windows.Controls.Primitives.Popup>에 대한 가능한 일련의 배치 지점 및 기본 축을 기본 설정 순서로 반환하는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 정의합니다. <xref:System.Windows.Controls.Primitives.Popup>의 가장 큰 부분을 표시하는 지점이 선택됩니다.  화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup>을 숨기는 경우 <xref:System.Windows.Controls.Primitives.Popup>의 위치가 자동으로 조정됩니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)(Popup 배치 샘플)
