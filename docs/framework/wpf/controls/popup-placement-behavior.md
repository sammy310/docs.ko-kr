---
title: Popup 배치 동작
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "69951728"
---
# <a name="popup-placement-behavior"></a>Popup 배치 동작
@No__t_0 컨트롤은 응용 프로그램 위에 배치 되는 별도의 창에 콘텐츠를 표시 합니다. @No__t_1, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용 하 여 컨트롤, 마우스 또는 화면을 기준으로 <xref:System.Windows.Controls.Primitives.Popup>의 위치를 지정할 수 있습니다.  이러한 속성은 함께 작동 하 여 <xref:System.Windows.Controls.Primitives.Popup> 위치를 유연 하 게 지정할 수 있습니다.  
  
> [!NOTE]
> 또한 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ContextMenu> 클래스는 이러한 다섯 가지 속성을 정의 하 고 비슷하게 동작 합니다.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Popup 위치 지정  
 @No__t_0 배치는 <xref:System.Windows.UIElement> 또는 전체 화면에 상대적일 수 있습니다.  다음 예제에서는 <xref:System.Windows.UIElement> (이 경우 이미지)를 기준으로 하는 네 개의 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 만듭니다. 모든 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에는 `image1`로 설정 된 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이 있지만 각 <xref:System.Windows.Controls.Primitives.Popup> 배치 속성의 값은 서로 다릅니다.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 다음 그림에서는 이미지 및 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 보여 줍니다.  
  
 ![네 개의 Popup 컨트롤이 있는 이미지](./media/popup-placement-behavior/popup-placement-intro.png "네 개의 팝업이 있는 이미지")    
  
 이 간단한 예제에서는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 설정 하는 방법을 보여 주지만 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.Primitives.Popup> 배치 위치를 더 많이 제어할 수 있습니다.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>용어 정의: Popup 분석  
 다음 용어는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성이 서로 관련 된 방법 및 <xref:System.Windows.Controls.Primitives.Popup>를 이해 하는 데 유용 합니다.  
  
- 대상 개체  
  
- 대상 영역  
  
- 대상 원점  
  
- Popup 맞춤 지점  
  
 이러한 용어는 <xref:System.Windows.Controls.Primitives.Popup>와 연결 된 컨트롤의 다양 한 측면을 쉽게 참조할 수 있는 방법을 제공 합니다.  
  
### <a name="target-object"></a>대상 개체  
 *대상 개체* 는 <xref:System.Windows.Controls.Primitives.Popup> 연결 된 요소입니다. @No__t_0 속성이 설정 된 경우 대상 개체를 지정 합니다.  @No__t_0 설정 되지 않은 경우 <xref:System.Windows.Controls.Primitives.Popup>에 부모가 있으면 부모는 대상 개체입니다.  @No__t_0 값이 없고 부모가 없는 경우 대상 개체가 없으며 <xref:System.Windows.Controls.Primitives.Popup> 화면에 상대적으로 배치 됩니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Canvas>의 자식인 <xref:System.Windows.Controls.Primitives.Popup>를 만듭니다.  이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup>의 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성을 설정 하지 않습니다. @No__t_0의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType> 이므로 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas> 아래에 나타납니다.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>를 기준으로 배치 됨을 보여 줍니다.  
  
 ![PlacementTarget이 없는 Popup 컨트롤](./media/popup-placement-behavior/popup-placement-no-placement-target.png "대상에 없는 Popup입니다.")  

 다음 예에서는 <xref:System.Windows.Controls.Canvas>의 자식인 <xref:System.Windows.Controls.Primitives.Popup>를 만들지만 이번에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> `ellipse1`로 설정 되었으므로 팝업이 <xref:System.Windows.Shapes.Ellipse> 아래에 나타납니다.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Shapes.Ellipse>를 기준으로 배치 됨을 보여 줍니다.  
  
 ![타원을 기준으로 배치되는 Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "PlacementTarget이 있는 Popup 컨트롤")    
  
> [!NOTE]
> @No__t_0의 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>입니다.  @No__t_0의 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>의 기본값은 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>입니다. 이러한 값은 나중에 "속성을 함께 사용하는 방법"에서 설명합니다.  
  
### <a name="target-area"></a>대상 영역  
 *대상 영역은* 화면에서 <xref:System.Windows.Controls.Primitives.Popup>의 기준이 되는 영역입니다. 앞의 예제에서 <xref:System.Windows.Controls.Primitives.Popup>은 대상 개체의 경계를 기준으로 정렬 되지만 일부 경우에는 <xref:System.Windows.Controls.Primitives.Popup>에 대상 개체가 있더라도 <xref:System.Windows.Controls.Primitives.Popup> 다른 범위에 정렬 됩니다.  @No__t_0 속성이 설정 된 경우 대상 영역이 대상 개체의 범위와 다릅니다.  
  
 다음 예제에서는 각각 <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Controls.Primitives.Popup>를 포함 하는 두 개의 <xref:System.Windows.Controls.Canvas> 개체를 만듭니다.  두 경우 모두 <xref:System.Windows.Controls.Primitives.Popup>의 대상 개체는 <xref:System.Windows.Controls.Canvas>입니다. 첫 번째 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Primitives.Popup>에는 각각 <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> 및 <xref:System.Windows.Rect.Height%2A> 속성이 50, 50, 50 및 100로 설정 된 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 되어 있습니다. 두 번째 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Primitives.Popup>에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 되지 않습니다.  따라서 첫 번째 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 아래에 배치 되 고 두 번째 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas> 아래에 배치 됩니다. 각 <xref:System.Windows.Controls.Canvas>에는 첫 번째 <xref:System.Windows.Controls.Primitives.Popup>에 대 한 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>와 동일한 범위가 있는 <xref:System.Windows.Shapes.Rectangle> 포함 됩니다.  @No__t_0는 응용 프로그램에 표시 되는 요소를 만들지 않습니다. 이 예에서는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>를 나타내는 <xref:System.Windows.Shapes.Rectangle>를 만듭니다.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![PlacementRectangle이 있을 때와 없을 때의 Popup](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "키가 없는 사각형의 Popup입니다.")  

### <a name="target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점  
 *대상 원점* 및 *Popup 맞춤 지점*은 각각 대상 영역 및 Popup에서 위치 지정에 사용되는 참조 지점입니다. @No__t_0 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 사용 하 여 대상 영역에서 popup을 오프셋할 수 있습니다.  @No__t_0 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>는 대상 원점과 팝업 맞춤 지점에 상대적입니다. @No__t_0 속성 값은 대상 원점 및 popup 맞춤 지점이 있는 위치를 결정 합니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Primitives.Popup>를 만들고 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성을 20으로 설정 합니다.  @No__t_0 속성이 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (기본값)로 설정 되어 있으므로 대상 원점이 대상 영역의 왼쪽 아래 모퉁이가 고 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이입니다.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![대상 원점 맞춤 지점을 사용한 Popup 배치](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "System.windows.controls.primitives.iscrollinfo.horizontaloffset 및 VerticalOffset를 사용 하는 Popup.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>속성을 함께 사용하는 방법  
 @No__t_0, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 값을 함께 고려 하 여 올바른 대상 영역, 대상 원점 및 팝업 맞춤 지점을 파악 해야 합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 값이 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> 되는 경우 대상 개체는 없으며, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>는 무시 되 고 대상 영역은 마우스 포인터의 범위입니다. 반면에 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 되는 경우에는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모가 대상 개체를 결정 하 고 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 영역을 결정 합니다.  
  
 다음 표에서는 대상 개체, 대상 영역, 대상 원점 및 팝업 맞춤 지점에 대해 설명 하 고 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 열거형 값에 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 사용 되는지 여부를 나타냅니다.  
  
|PlacementMode|대상 개체|대상 영역|대상 원점|Popup 맞춤 지점|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|해당 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|화면 또는 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 합니다.  @No__t_0는 화면을 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|해당 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|화면 또는 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 합니다.  @No__t_0는 화면을 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 아래 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 가운데.|@No__t_0의 중심입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|@No__t_0에서 정의 됩니다.|@No__t_0에서 정의 됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 오른쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|해당 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 됩니다.|대상 영역의 왼쪽 아래 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|해당 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 됩니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 오른쪽 위 모퉁이.|@No__t_0의 왼쪽 위 모퉁이입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 이거나, 설정 된 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>입니다.  @No__t_0 대상 개체를 기준으로 합니다.|대상 영역의 왼쪽 위 모퉁이.|@No__t_0의 왼쪽 아래 모퉁이입니다.|  
  
 다음 그림에서는 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대 한 <xref:System.Windows.Controls.Primitives.Popup>, 대상 영역, 대상 원점 및 팝업 맞춤 지점을 보여 줍니다. 각 그림에서 대상 영역은 노란색이 고 <xref:System.Windows.Controls.Primitives.Popup>는 파란색입니다.  
  
 ![Absolute 또는 AbsolutePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-absolute.png "배치가 Absolute 또는 AbsolutePoint입니다.")    
  
 ![Bottom 배치의 Popup](./media/popup-placement-behavior/popup-placement-bottom.png "배치가 아래쪽입니다.")   
  
 ![Center 배치의 Popup](./media/popup-placement-behavior/popup-placement-center.png "배치가 가운데 맞춤입니다.")    
  
 ![Left 배치의 Popup](./media/popup-placement-behavior/popup-placement-left.png "배치가 왼쪽입니다.")   
  
 ![Mouse 배치의 Popup](./media/popup-placement-behavior/popup-placement-mouse.png "배치가 마우스입니다.")  
  
 ![MousePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-mousepoint.png "배치가 MousePoint입니다.")  
  
 ![Relative 또는 RelativePoint 배치의 Popup](./media/popup-placement-behavior/popup-placement-relative.png "배치가 상대 또는 RelativePoint입니다.")    
  
 ![Right 배치의 Popup](./media/popup-placement-behavior/popup-placement-right.png "배치가 적합 합니다.")    
  
 ![Top 배치의 Popup](./media/popup-placement-behavior/popup-placement-top.png "배치가 위쪽입니다.")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Popup이 화면 가장자리와 만나는 경우  
 보안상의 이유로 화면 가장자리에 의해 <xref:System.Windows.Controls.Primitives.Popup>를 숨길 수 없습니다. 다음 세 가지 작업 중 하나는 <xref:System.Windows.Controls.Primitives.Popup> 화면에 가장자리가 나타날 때 발생 합니다.  
  
- 팝업은 <xref:System.Windows.Controls.Primitives.Popup>를 숨기는 화면 가장자리를 따라 자신을 realigns 합니다.  
  
- Popup에 다른 Popup 맞춤 지점이 사용됩니다.  
  
- Popup에 다른 대상 원점 및 Popup 맞춤 지점이 사용됩니다.  
  
 이러한 옵션은 이 섹션의 뒷부분에서 설명합니다.  
  
 화면 가장자리가 나타날 때 <xref:System.Windows.Controls.Primitives.Popup> 동작은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성의 값과 팝업이 발생 하는 화면 가장자리에 따라 다릅니다. 다음 표에서는 <xref:System.Windows.Controls.Primitives.Popup> 각 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 대 한 화면 가장자리가 나타날 때의 동작을 요약 합니다.  
  
|PlacementMode|위쪽 가장자리|아래쪽 가장자리|왼쪽 가장자리|오른쪽 가장자리|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경 됩니다.|왼쪽 가장자리에 맞춥니다.|팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이로 변경 됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경 됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 오른쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이로 변경 됩니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이 (마우스 포인터의 경계)로 변경 되 고 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경 됩니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경 됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|위쪽 가장자리에 맞춥니다.|팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이로 변경 됩니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이로 변경 됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|대상 원점이 대상 영역의 왼쪽 아래 모퉁이로 바뀌고 팝업 맞춤 지점은 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이로 변경 됩니다. 실제로이는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 되는 경우와 동일 합니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
  
### <a name="aligning-to-the-screen-edge"></a>화면 가장자리에 맞춤  
 전체 <xref:System.Windows.Controls.Primitives.Popup> 화면에 표시 되도록 자체적으로 위치를 조정 하 여 화면 가장자리에 <xref:System.Windows.Controls.Primitives.Popup>을 맞출 수 있습니다.  이 문제가 발생 하면 대상 원점과 팝업 맞춤 지점 간의 거리가 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 값과 다를 수 있습니다. @No__t_0 <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> 경우 <xref:System.Windows.Controls.Primitives.Popup> 모든 화면 가장자리에 자동으로 맞춰집니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>로 설정 되어 있고 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>가 100로 설정 되어 있다고 가정 합니다.  화면의 아래쪽 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 전체 또는 일부를 숨기면 <xref:System.Windows.Controls.Primitives.Popup> 화면 아래쪽 가장자리를 따라 자동으로 위치를 조정 하 고 대상 원점과 팝업 맞춤 지점 간의 세로 거리가 100 미만입니다. 다음 그림에서 이 경우를 보여 줍니다.  
  
 ![화면 가장자리에 맞춰진 Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup이 화면의 가장자리에 맞춰집니다.")    
  
### <a name="changing-the-popup-alignment-point"></a>Popup 맞춤 지점 변경  
 @No__t_0 <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint> 경우 팝업이 아래쪽 또는 오른쪽 화면 가장자리를 만나면 팝업 맞춤 지점이 변경 됩니다.  
  
 다음 그림에서는 아래쪽 화면 가장자리가 <xref:System.Windows.Controls.Primitives.Popup> 전체 또는 일부를 숨기는 경우 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이 임을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup이 화면의 아래쪽 가장자리를 만나면 팝업 맞춤 지점을 변경 합니다.")  

 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup> 오른쪽 화면 가장자리에 의해 숨겨지는 경우 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이 임을 보여 줍니다.  
  
 ![화면 가장자리로 인한 새로운 Popup 맞춤 지점](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup이 화면의 오른쪽 가장자리를 만나면 popup 맞춤 지점을 변경 합니다.")    
  
 @No__t_0 아래쪽 및 오른쪽 화면 가장자리를 만나면 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 아래 모퉁이입니다.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점 변경  
 @No__t_0 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Top> 이면 특정 화면 가장자리에 도달 하면 대상 원점 및 팝업 맞춤 지점이 변경 됩니다.  위치가 변경 되도록 하는 화면 가장자리는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값에 따라 달라 집니다.  
  
 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 되 고 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리를 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이가 고 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 아래 모퉁이 임을 보여 줍니다.  
  
 ![아래쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "배치가 아래쪽에 있고 popup이 화면의 아래쪽 가장자리에 도달 합니다.")    
  
 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Left> 되 고 <xref:System.Windows.Controls.Primitives.Popup> 왼쪽 화면 가장자리를 만나면 대상 원점이 대상 영역의 오른쪽 위 모퉁이가 고 팝업 맞춤 지점은 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이 임을 보여 줍니다.  
  
 ![왼쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "배치가 왼쪽에 있고 popup이 화면 왼쪽 가장자리에 도달 합니다.")  
  
 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 되 고 <xref:System.Windows.Controls.Primitives.Popup> 오른쪽 화면 가장자리를 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이가 고 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 오른쪽 위 모퉁이 임을 보여 줍니다.  
  
 ![오른쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "배치가 오른쪽에 있고 popup이 화면의 오른쪽 가장자리와 만나는 경우")  

 다음 그림은 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Top> 되 고 <xref:System.Windows.Controls.Primitives.Popup> 위쪽 화면 가장자리를 발견 하면 대상 원점이 대상 영역의 왼쪽 아래 모퉁이가 고 팝업 맞춤 지점이 <xref:System.Windows.Controls.Primitives.Popup>의 왼쪽 위 모퉁이 임을 보여 줍니다.  
  
 ![위쪽 화면 가장자리로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "배치가 위쪽이 고 popup이 화면의 위쪽 가장자리를 발견 합니다.")  
  
 다음 그림에서는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> 되 고 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리를 만나면 대상 원점이 대상 영역의 왼쪽 위 모퉁이 (마우스 포인터의 경계)와 popup 맞춤 지점이 왼쪽 아래에 있음을 보여 줍니다. <xref:System.Windows.Controls.Primitives.Popup>의 모퉁이입니다.  
  
 ![화면 가장자리 근처의 마우스로 인한 새로운 맞춤 지점](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "배치는 마우스이 고 popup은 화면의 아래쪽 가장자리가 발견 됩니다.")    
  
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 @No__t_0 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> 설정 하 여 대상 원점 및 popup 맞춤 지점을 사용자 지정할 수 있습니다. 그런 다음 <xref:System.Windows.Controls.Primitives.Popup>에 대 한 가능한 배치 지점과 기본 축 (기본 설정 순서 대로) 집합을 반환 하는 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 대리자를 정의 합니다. @No__t_0의 가장 큰 부분을 표시 하는 점이 선택 됩니다.  화면 가장자리에 의해 <xref:System.Windows.Controls.Primitives.Popup> 숨겨지는 경우 <xref:System.Windows.Controls.Primitives.Popup> 위치가 자동으로 조정 됩니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)(Popup 배치 샘플)
