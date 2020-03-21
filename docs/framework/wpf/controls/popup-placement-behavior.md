---
title: Popup 배치 동작
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 063b309ebaf0944787ce40725eed250e59f09dff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176762"
---
# <a name="popup-placement-behavior"></a>Popup 배치 동작
컨트롤은 <xref:System.Windows.Controls.Primitives.Popup> 응용 프로그램 위에 떠 있는 별도의 창에 콘텐츠를 표시합니다. 을 사용하여 컨트롤, <xref:System.Windows.Controls.Primitives.Popup> 마우스 또는 화면상대의 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>위치를 지정할 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 수 있습니다.  이러한 속성은 함께 작동하여 <xref:System.Windows.Controls.Primitives.Popup>의 위치를 유연하게 지정할 수 있습니다.  
  
> [!NOTE]
> 및 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ContextMenu> 클래스는 또한 이러한 다섯 가지 속성을 정의하고 유사하게 행동합니다.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Popup 위치 지정  
 a의 <xref:System.Windows.Controls.Primitives.Popup> 배치는 전체 화면을 <xref:System.Windows.UIElement> 기준으로 할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.UIElement>-이 경우 이미지를 기준으로 하는 4개의 컨트롤을 만듭니다. 모든 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 속성이 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> `image1`설정되지만 각각 <xref:System.Windows.Controls.Primitives.Popup> 배치 속성에 대해 서로 다른 값이 있습니다.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 다음 그림에서는 이미지와 컨트롤을 <xref:System.Windows.Controls.Primitives.Popup> 보여 주며  
  
 ![네 개의 Popup 컨트롤이 있는 이미지](./media/popup-placement-behavior/popup-placement-intro.png "4개의 팝업이 있는 이미지")
  
 이 간단한 예제에서는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 설정하는 방법을 보여 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>주지만 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> , 에서 및 속성을 사용하여 <xref:System.Windows.Controls.Primitives.Popup> 위치 위치를 더 많이 제어할 수 있습니다.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>용어 정의: Popup 분석  
 다음 용어는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>" <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성이 서로 어떻게 관련되는지 및 <xref:System.Windows.Controls.Primitives.Popup>다음 을 이해하는 데 유용합니다.  
  
- 대상 개체  
  
- 대상 영역  
  
- 대상 원점  
  
- Popup 맞춤 지점  
  
 이러한 용어들은 연관된 제어의 <xref:System.Windows.Controls.Primitives.Popup> 다양한 양상을 참조하는 편리한 방법을 제공한다.  
  
### <a name="target-object"></a>대상 개체  
 *대상 개체는* 와 연결된 <xref:System.Windows.Controls.Primitives.Popup> 요소입니다. 속성이 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 설정된 경우 대상 개체를 지정합니다.  설정되지 않고 부모가 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup> 있는 경우 부모가 대상 개체입니다.  값이 없고 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 부모가 없는 경우 대상 개체가 없으며 <xref:System.Windows.Controls.Primitives.Popup> 화면을 기준으로 배치됩니다.  
  
 다음 예제는 <xref:System.Windows.Controls.Primitives.Popup> 의 자식인 <xref:System.Windows.Controls.Canvas>a를 만듭니다.  이 예제에서 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성을 설정하지 <xref:System.Windows.Controls.Primitives.Popup>않습니다. 의 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>에서 <xref:System.Windows.Controls.Primitives.Popup> 이렇게 <xref:System.Windows.Controls.Canvas>표시됩니다.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>을 기준으로 배치되어 있음을 보여 주시면 됩니다.  
  
 ![PlacementTarget이 없는 Popup 컨트롤](./media/popup-placement-behavior/popup-placement-no-placement-target.png "배치 대상 없음으로 팝업합니다.")  

 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>의 자식인 a를 만들지만 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 이번에는 `ellipse1`에 대해 설정하므로 팝업이 <xref:System.Windows.Shapes.Ellipse>아래에 나타납니다.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Shapes.Ellipse>을 기준으로 배치되어 있음을 보여 주시면 됩니다.  
  
 ![타원을 기준으로 배치되는 Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "PlacementTarget이 있는 Popup 컨트롤")
  
> [!NOTE]
> 의 <xref:System.Windows.Controls.ToolTip>경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>입니다.  의 <xref:System.Windows.Controls.ContextMenu>경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>입니다. 이러한 값은 나중에 "속성을 함께 사용하는 방법"에서 설명합니다.  
  
### <a name="target-area"></a>대상 영역  
 *대상 영역은* 화면의 <xref:System.Windows.Controls.Primitives.Popup> 상대영역입니다. 이전 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> 대상 개체의 경계와 정렬되지만 경우에 따라 대상 오브젝트가 <xref:System.Windows.Controls.Primitives.Popup> 있는 경우에도 다른 경계에 <xref:System.Windows.Controls.Primitives.Popup> 정렬됩니다.  속성이 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우 대상 영역은 대상 개체의 경계와 다릅니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 두 개의 개체를 <xref:System.Windows.Shapes.Rectangle> 만듭니다. <xref:System.Windows.Controls.Primitives.Popup>  두 경우 모두 의 대상 <xref:System.Windows.Controls.Primitives.Popup> 개체는 을 입니다. <xref:System.Windows.Controls.Canvas> 첫 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas> 번째 의 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 집합에는 <xref:System.Windows.Rect.X%2A>의 <xref:System.Windows.Rect.Y%2A>" <xref:System.Windows.Rect.Width%2A>및 <xref:System.Windows.Rect.Height%2A> 속성이 각각 50, 50, 50 및 100으로 설정됩니다. <xref:System.Windows.Controls.Primitives.Popup> 두 번째 <xref:System.Windows.Controls.Canvas> 에는 세트가 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 없습니다.  <xref:System.Windows.Controls.Primitives.Popup> 결과적으로 첫 번째는 아래에 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 위치하고 두 번째는 <xref:System.Windows.Controls.Primitives.Popup> 아래에 <xref:System.Windows.Controls.Canvas>배치됩니다. 각각에는 <xref:System.Windows.Controls.Canvas> 첫 <xref:System.Windows.Shapes.Rectangle> 번째 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup>에 대한 경계가 같은 a도 포함되어 있습니다.  응용 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 프로그램에서 표시되는 요소를 만들지 않습니다. 이 예제는 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>을 나타내는 a를 만듭니다.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![PlacementRectangle이 있을 때와 없을 때의 팝업](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "배치 직각을 가지고 또는 없이 팝업.")  

### <a name="target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점  
 *대상 원점* 및 *Popup 맞춤 지점*은 각각 대상 영역 및 Popup에서 위치 지정에 사용되는 참조 지점입니다. <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용하여 대상 영역에서 팝업을 오프셋할 수 있습니다.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 대상 원점 및 팝업 정렬 점을 상대합니다. 속성 값은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 대상 원점 및 팝업 선형 점이 있는 위치를 결정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> 가져오거나 설정 합니다 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 20 속성.  속성이 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> (기본값)으로 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 설정되므로 대상 원점은 대상 영역의 왼쪽 아래 모서리이고 팝업 정렬 점은 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모서리입니다.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![대상 원점 맞춤 지점을 사용한 Popup 배치](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "수평 오프셋 및 수직 오프셋이있는 팝업.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>속성을 함께 사용하는 방법  
 의 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>값은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 올바른 대상 영역, 대상 원점 및 팝업 정렬 점을 파악하기 위해 함께 고려해야 합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>의 값이 있는 경우 는 대상 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 개체가 없고, 대상 영역은 무시되고, 대상 영역은 마우스 포인터의 경계입니다. 한편, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 있는 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 경우, 또는 부모는 대상 객체를 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 결정하고 대상 영역을 결정한다.  
  
 다음 표에서는 대상 개체, 대상 영역, 대상 원점 및 팝업 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 정렬 점에 <xref:System.Windows.Controls.Primitives.PlacementMode> 대해 설명하고 각 열거값에 대해 사용되는지 여부를 나타냅니다.  
  
|PlacementMode|대상 개체|대상 영역|대상 원점|Popup 맞춤 지점|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|해당 사항 없음 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면을 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|해당 사항 없음 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면을 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 아래 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 가운데.|의 중심입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|에 의해 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>정의됩니다.|에 의해 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>정의됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|의 오른쪽 상단 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|해당 사항 없음 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>는 무시됩니다.|대상 영역의 왼쪽 아래 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|해당 사항 없음 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>는 무시됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>는 무시됩니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 오른쪽 위 모퉁이.|의 왼쪽 위 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>또는 부모.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정된 경우  은 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|의 왼쪽 아래 모서리입니다. <xref:System.Windows.Controls.Primitives.Popup>|  
  
 다음 그림에서는 각 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대한 , 대상 영역, 대상 원점 및 팝업 정렬 점을 보여 준다. 각 그림에서 대상 영역은 노란색이고 <xref:System.Windows.Controls.Primitives.Popup> 파란색입니다.  
  
 ![Absolute 또는 AbsolutePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-absolute.png "배치는 절대 점 또는 절대점입니다.")
  
 ![Bottom 배치의 Popup](./media/popup-placement-behavior/popup-placement-bottom.png "배치는 아래쪽입니다.")
  
 ![Center 배치의 Popup](./media/popup-placement-behavior/popup-placement-center.png "배치는 중심입니다.")
  
 ![Left 배치의 Popup](./media/popup-placement-behavior/popup-placement-left.png "배치가 남아 있습니다.")
  
 ![Mouse 배치의 Popup](./media/popup-placement-behavior/popup-placement-mouse.png "배치는 마우스입니다.")  
  
 ![MousePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-mousepoint.png "배치는 마우스 포인트입니다.")  
  
 ![Relative 또는 RelativePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-relative.png "배치는 상대 또는 상대점입니다.")
  
 ![Right 배치의 Popup](./media/popup-placement-behavior/popup-placement-right.png "배치가 맞습니다.")
  
 ![Top 배치의 Popup](./media/popup-placement-behavior/popup-placement-top.png "배치는 맨 위입니다.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Popup이 화면 가장자리와 만나는 경우  
 보안상의 이유로 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리에 는 숨길 수 없습니다. 다음 세 가지 중 하나는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리를 만날 때 발생합니다.  
  
- 팝업은 화면 가장자리를 따라 다시 정렬되어 을 <xref:System.Windows.Controls.Primitives.Popup>가릴 수 있습니다.  
  
- Popup에 다른 Popup 맞춤 지점이 사용됩니다.  
  
- Popup에 다른 대상 원점 및 Popup 맞춤 지점이 사용됩니다.  
  
 이러한 옵션은 이 섹션의 뒷부분에서 설명합니다.  
  
 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 발생하는 경우의 동작은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성값과 팝업이 발생하는 화면 가장자리에 따라 달라집니다. 다음 표는 각 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대한 화면 가장자리를 만날 때의 동작을 요약합니다.  
  
|PlacementMode|위쪽 가장자리|아래쪽 가장자리|왼쪽 가장자리|오른쪽 가장자리|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|위쪽 가장자리에 맞춥니다.|팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|팝업 정렬 점은 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 상단 모서리로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모서리로 변경되고 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 오른쪽 위 모서리로 변경되고 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모서리로 변경됩니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모서리(마우스 포인터의 경계)로 변경되고 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|위쪽 가장자리에 맞춥니다.|팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|위쪽 가장자리에 맞춥니다.|팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리로 변경됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모서리로 변경되고 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 상단 모서리로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|대상 원점이 대상 영역의 왼쪽 아래 모서리로 변경되고 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모서리로 변경됩니다. 실제로 이것은 때와 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 동일합니다. <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
  
### <a name="aligning-to-the-screen-edge"></a>화면 가장자리에 맞춤  
 A는 <xref:System.Windows.Controls.Primitives.Popup> 전체 를 화면에 표시하도록 <xref:System.Windows.Controls.Primitives.Popup> 자체 위치를 지정하여 화면 가장자리에 정렬할 수 있습니다.  이 경우 대상 원점과 팝업 정렬 점 사이의 거리가 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 의 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>값과 다를 수 있습니다. 의 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>경우 <xref:System.Windows.Controls.Primitives.PlacementMode.Center>또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> 모든 화면 가장자리에 자체가 정렬됩니다.  예를 들어 a가 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 100으로 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> 설정되었다고 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 가정합니다.  화면의 아래쪽 가장자리가 화면의 <xref:System.Windows.Controls.Primitives.Popup>전체 또는 <xref:System.Windows.Controls.Primitives.Popup> 일부를 숨기는 경우 화면의 아래쪽 가장자리를 따라 위치가 바삭바삭하고 대상 원점과 팝업 정렬 점 사이의 수직 거리가 100보다 작습니다. 다음 그림에서 이 경우를 보여 줍니다.  
  
 ![화면 가장자리에 맞춰진 Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "팝업은 화면 가장자리에 정렬됩니다.")
  
### <a name="changing-the-popup-alignment-point"></a>Popup 맞춤 지점 변경  
 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>팝업 정렬 점이 팝업이 아래쪽 또는 오른쪽 화면 가장자리와 마주치는 경우 변경됩니다. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint> <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>  
  
 다음 그림에서는 아래쪽 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup>의 전체 또는 일부를 숨길 때 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모서리임을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "팝업은 화면의 아래쪽 가장자리를 발견하고 팝업 정렬 지점을 변경합니다.")  

 다음 <xref:System.Windows.Controls.Primitives.Popup> 그림에서는 오른쪽 화면 가장자리에 의해 숨겨지면 팝업 정렬 점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 상단 모서리임을 보여 줍니다.  
  
 ![화면 가장자리로 인한 새로운 Popup 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "팝업은 화면의 오른쪽 가장자리를 발견하고 팝업 정렬 지점을 변경합니다.")
  
 아래쪽과 오른쪽 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 발생하는 경우 팝업 정렬 점은 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 아래 모서리입니다.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점 변경  
 은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>" <xref:System.Windows.Controls.Primitives.PlacementMode.Right>또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, 특정 화면 가장자리가 발생하면 대상 원점 및 팝업 정렬 점이 변경됩니다.  위치를 변경하는 화면 가장자리는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 따라 다릅니다.  
  
 다음 그림에서는 아래쪽 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 화면 <xref:System.Windows.Controls.Primitives.Popup> 가장자리가 발생했을 때 대상 원점이 대상 영역의 왼쪽 위 모서리이고 팝업 정렬 지점이 왼쪽 <xref:System.Windows.Controls.Primitives.Popup>아래 모서리임을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "배치는 아래쪽이고 팝업은 화면의 아래쪽 가장자리를 발생합니다.")
  
 다음 그림에서는 왼쪽 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 화면 <xref:System.Windows.Controls.Primitives.PlacementMode.Left> 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 있는 경우 대상 원점이 대상 영역의 오른쪽 위 모서리이고 팝업 정렬 지점이 왼쪽 상단 <xref:System.Windows.Controls.Primitives.Popup>모서리임을 보여 줍니다.  
  
 ![왼쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "배치가 왼쪽이고 팝업이 화면의 왼쪽 가장자리에 나타납니다.")  
  
 다음 그림에서는 오른쪽 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 화면 <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 발생할 때 대상 원점이 대상 영역의 왼쪽 위 모서리이고 팝업 정렬 점이 의 오른쪽 상단 <xref:System.Windows.Controls.Primitives.Popup>모서리임을 보여 줍니다.  
  
 ![오른쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "배치가 오른쪽이고 팝업이 화면의 오른쪽 가장자리에 나타납니다.")  

 다음 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 그림에서는 상단 화면 <xref:System.Windows.Controls.Primitives.PlacementMode.Top> 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 나타나면 대상 원점이 대상 영역의 왼쪽 아래 모서리이고 팝업 정렬 지점이 왼쪽 위 모서리임을 보여 <xref:System.Windows.Controls.Primitives.Popup>줍니다.  
  
 ![위쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "배치는 맨 위이고 팝업은 화면의 위쪽 가장자리를 발생합니다.")  
  
 다음 그림에서는 아래쪽 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> 화면 <xref:System.Windows.Controls.Primitives.Popup> 가장자리가 발생했을 때 대상 원점이 대상 영역의 왼쪽 위 모서리(마우스 포인터의 경계)이고 팝업 정렬 지점이 왼쪽 아래 <xref:System.Windows.Controls.Primitives.Popup>모서리임을 보여 줍니다.  
  
 ![화면 가장자리 근처의 마우스로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "위치는 마우스이며 팝업은 화면의 아래쪽 가장자리를 발생합니다.")
  
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 로 설정하여 대상 원점 및 팝업 정렬 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>점을 사용자 지정할 수 있습니다. 그런 다음 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> <xref:System.Windows.Controls.Primitives.Popup>에 대해 가능한 배치 점 및 기본 축(기본 축 순서)의 집합을 반환하는 대리자를 정의합니다. 선택된 가장 큰 부분을 <xref:System.Windows.Controls.Primitives.Popup> 표시하는 점입니다.  화면 가장자리에 <xref:System.Windows.Controls.Primitives.Popup> 숨겨져 있으면 의 <xref:System.Windows.Controls.Primitives.Popup> 위치가 자동으로 조정됩니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)(Popup 배치 샘플)
