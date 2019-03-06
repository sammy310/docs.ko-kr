---
title: Popup 배치 동작
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 0f02fcef5c905e81808d76b71b45e0d010084268
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360560"
---
# <a name="popup-placement-behavior"></a>Popup 배치 동작
<xref:System.Windows.Controls.Primitives.Popup> 컨트롤 응용 프로그램 위에 떠 있는 별도 창에서 콘텐츠를 표시 합니다. 위치를 지정할 수 있습니다는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤, 마우스를 또는 사용 하 여 화면을 기준으로 합니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성입니다.  이러한 속성의 위치를 지정 하는 유연성을 제공 하기 위해 함께 작동 합니다 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Controls.ToolTip> 고 <xref:System.Windows.Controls.ContextMenu> 클래스 또한 이러한 5 개의 속성을 정의 하 고 유사 하 게 동작 합니다.  
  

  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Popup 위치 지정  
 배치를 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 수는 <xref:System.Windows.UIElement> 또는 전체 화면.  다음 예제에서는 네 개를 만듭니다 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 하는 컨트롤을 <xref:System.Windows.UIElement>-이 경우 이미지에서. 모든는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤을 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성이로 설정 `image1`, 하지만 각 <xref:System.Windows.Controls.Primitives.Popup> 배치 속성에 대 한 다른 값.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 다음 그림에서는 이미지를 보여 줍니다. 및 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤  
  
 ![네 개의 팝업 컨트롤이 있는 이미지](./media/popupplacementintro.png "PopupPlacementIntro")  
네 개의 Popup이 있는 이미지  
  
 이 간단한 예제에는 설정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 사용 하 여는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 속성 위치 보다 더 많은 제어할 수는 <xref:System.Windows.Controls.Primitives.Popup> 배치 됩니다.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>용어 정의: Popup 분석  
 다음 용어 이해에서 유용 하는 방법을 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>를 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 서로 관련 속성 및 <xref:System.Windows.Controls.Primitives.Popup>:  
  
-   대상 개체  
  
-   대상 영역  
  
-   대상 원점  
  
-   Popup 맞춤 지점  
  
 이러한 용어의 다양 한 측면을 참조 하는 편리한 방법을 제공 합니다 <xref:System.Windows.Controls.Primitives.Popup> 와 연관 된 컨트롤입니다.  
  
### <a name="target-object"></a>대상 개체  
 합니다 *대상 개체* 요소는 <xref:System.Windows.Controls.Primitives.Popup> 연관 된 합니다. 경우는 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성을 설정 하면 대상 개체를 지정 합니다.  하는 경우 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 을 설정 하지 않으면 및 <xref:System.Windows.Controls.Primitives.Popup> 부모가 부모는 대상 개체입니다.  없는 경우 없습니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 값 및 부모가 대상 개체가 및 <xref:System.Windows.Controls.Primitives.Popup> 화면을 기준으로 배치 됩니다.  
  
 다음 예제는 <xref:System.Windows.Controls.Primitives.Popup> 의 자식인은 <xref:System.Windows.Controls.Canvas>합니다.  예제 설정 하지 않습니다 합니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 속성에는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 에 대 한 기본값 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>이므로 <xref:System.Windows.Controls.Primitives.Popup> 아래에 표시 됩니다는 <xref:System.Windows.Controls.Canvas>합니다.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 다음 그림에서는 합니다 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 배치 된는 <xref:System.Windows.Controls.Canvas>합니다.  
  
 ![Placementtarget이 없는 popup 컨트롤](./media/popupplacementnoplacementtarget.PNG "PopupPlacementNoPlacementTarget")  
PlacementTarget이 없는 Popup 컨트롤  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> 의 자식인을 <xref:System.Windows.Controls.Canvas>, 이번 합니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 로 설정 되어 `ellipse1`이므로 아래 팝업이 표시 되는 <xref:System.Windows.Shapes.Ellipse>합니다.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 다음 그림에서는 합니다 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 배치 된는 <xref:System.Windows.Shapes.Ellipse>합니다.  
  
 ![타원에 상대적으로 배치 되는 팝업](./media/popupplacementwithplacementtarget.PNG "PopupPlacementWithPlacementTarget")  
PlacementTarget이 있는 Popup 컨트롤  
  
> [!NOTE]
>  에 대 한 <xref:System.Windows.Controls.ToolTip>을 기본값인 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 는 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>합니다.  에 대 한 <xref:System.Windows.Controls.ContextMenu>을 기본값인 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>합니다. 이러한 값은 나중에 "속성을 함께 사용하는 방법"에서 설명합니다.  
  
### <a name="target-area"></a>대상 영역  
 합니다 *대상 영역* 화면의 영역는 <xref:System.Windows.Controls.Primitives.Popup> 기준으로 합니다. 이전 예제에서를 <xref:System.Windows.Controls.Primitives.Popup> 경우도 있지만 대상 개체의 경계에 맞춰집니다 합니다 <xref:System.Windows.Controls.Primitives.Popup> 다른 경계에 맞춥니다 경우에는 <xref:System.Windows.Controls.Primitives.Popup> 대상 개체에 합니다.  경우는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 속성을 설정 하면 대상 영역은 대상 개체의 범위와 다릅니다.  
  
 다음 예제에서는 두 개의 <xref:System.Windows.Controls.Canvas> 개의 개체를 <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Controls.Primitives.Popup>합니다.  두 경우 모두에 대 한 대상 개체를 <xref:System.Windows.Controls.Primitives.Popup> 되는 <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Controls.Primitives.Popup> 첫 번째에서 <xref:System.Windows.Controls.Canvas> 에 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 사용 하 여 설정 해당 <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>를 <xref:System.Windows.Rect.Width%2A>, 및 <xref:System.Windows.Rect.Height%2A> 속성이 각각 50, 50, 50 및 100으로 설정 합니다. 합니다 <xref:System.Windows.Controls.Primitives.Popup> 두 번째에서 <xref:System.Windows.Controls.Canvas> 없는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 합니다.  결과적으로, 첫 번째 <xref:System.Windows.Controls.Primitives.Popup> 아래에 배치 됩니다 합니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 하 고 두 번째 <xref:System.Windows.Controls.Primitives.Popup> 아래에 배치 됩니다는 <xref:System.Windows.Controls.Canvas>합니다. 각 <xref:System.Windows.Controls.Canvas> 도 포함 되어 있습니다를 <xref:System.Windows.Shapes.Rectangle> 동일한 범위의 있는 합니다 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 첫 번째 <xref:System.Windows.Controls.Primitives.Popup>입니다.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 응용 프로그램에서 시각적 요소를 만들지 않습니다 만듭니다는 <xref:System.Windows.Shapes.Rectangle> 나타내는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>합니다.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![팝업 및 placementrectangle](./media/popupplacementplacementrectangle.PNG "PopupPlacementPlacementRectangle")  
PlacementRectangle이 있을 때와 없을 때의 팝업  
  
### <a name="target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점  
 *대상 원점* 및 *Popup 맞춤 지점*은 각각 대상 영역 및 Popup에서 위치 지정에 사용되는 참조 지점입니다. 사용할 수는 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 고 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 대상 영역에서 popup을 오프셋할 속성입니다.  합니다 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 고 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 대상 원점 및 popup 맞춤 지점을 기준으로 합니다. 값을 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성 대상 원점 및 popup 맞춤 지점이 있는 위치를 결정 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> 가져오거나 설정 합니다 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 20 속성.  합니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성이로 설정 되어 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (기본값), 되므로 대상 원점은 대상 영역의 왼쪽 아래 모서리 이며 팝업 맞춤 지점의 왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 다음 그림에서는 이전 예제의 결과를 보여 줍니다.  
  
 ![대상 원점 맞춤 지점 사용한 popup 배치](./media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
HorizontalOffset 및 VerticalOffset을 사용한 Popup  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>속성을 함께 사용하는 방법  
 값 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, 및 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 정확한 대상 영역, 대상 원점 및 popup 맞춤 지점을 파악 하려면 함께 고려해 야 합니다.  예를 들어 경우 값 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, 대상 개체가 없습니다를 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 됩니다 대상 영역이 마우스 포인터의 경계 및 합니다. 반면에 하는 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>의 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 대상 개체를 결정 하는 부모 또는 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 영역을 결정 합니다.  
  
 다음 표에서 대상 개체, 대상 영역, 대상 원점 및 popup 맞춤 지점 및 나타냅니다 여부 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 및 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 각각에 사용 되 <xref:System.Windows.Controls.Primitives.PlacementMode> 열거형 값입니다.  
  
|PlacementMode|대상 개체|대상 영역|대상 원점|Popup 맞춤 지점|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|화면 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 화면에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 아래 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 가운데.|가운데를 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|정의 된 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>합니다.|정의 된 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|오른쪽 위 모서리의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 됩니다.|대상 영역의 왼쪽 아래 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|해당 사항 없음. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 무시 됩니다.|마우스 포인터의 경계. <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 무시 됩니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 오른쪽 위 모퉁이.|왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 또는 부모입니다.|대상 개체 또는 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 설정 된 경우.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 대상 개체에 상대적입니다.|대상 영역의 왼쪽 위 모퉁이.|왼쪽 아래 모서리를 <xref:System.Windows.Controls.Primitives.Popup>입니다.|  
  
 다음 그림에 나온 합니다 <xref:System.Windows.Controls.Primitives.Popup>, 각각에 대 한 대상 영역, 대상 원점 및 popup 맞춤 지점 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다. 각 그림에서 대상 영역은 노란색이 고 <xref:System.Windows.Controls.Primitives.Popup> 파란색입니다.  
  
 ![Absolute 또는 AbsolutePoint 배치의 popup](./media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Placement가 Absolute 또는 AbsolutePoint임  
  
 ![Bottom 배치의 popup](./media/popupplacementbottom.png "PopupPlacementBottom")  
Placement가 Bottom임  
  
 ![Center 배치의 popup](./media/popupplacementcenter.png "PopupPlacementCenter")  
Placement가 Center임  
  
 ![Left 배치의 popup](./media/popupplacementleft.png "PopupPlacementLeft")  
Placement가 Left임  
  
 ![Mouse 배치의 popup](./media/popupplacementmouse.png "PopupPlacementMouse")  
Placement가 Mouse임  
  
 ![MousePoint 배치의 popup](./media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Placement가 MousePoint임  
  
 ![Relative 또는 RelativePoint 배치의 popup](./media/popupplacementrelative.png "PopupPlacementRelative")  
Placement가 Relative 또는 RelativePoint임  
  
 ![Right 배치의 popup](./media/popupplacementright.png "PopupPlacementRight")  
Placement가 Right임  
  
 ![Top 배치의 popup](./media/popupplacementtop.png "PopupPlacementTop")  
Placement가 Top임  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Popup이 화면 가장자리와 만나는 경우  
 보안상의 이유로 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리가 숨길 수 없습니다. 다음 세 가지 중 하나가 발생 하면는 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리와 만나면:  
  
-   팝업을 가리는 모호 하 게 화면 가장자리는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
-   Popup에 다른 Popup 맞춤 지점이 사용됩니다.  
  
-   Popup에 다른 대상 원점 및 Popup 맞춤 지점이 사용됩니다.  
  
 이러한 옵션은 이 섹션의 뒷부분에서 설명합니다.  
  
 동작을 <xref:System.Windows.Controls.Primitives.Popup> 화면 가장자리의 값에 따라 발생 하는 경우는 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성과 popup 가장자리를 화면. 다음 표에서 동작 때 합니다 <xref:System.Windows.Controls.Primitives.Popup> 각각에 대해 화면 가장자리와 만나면 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다.  
  
|PlacementMode|위쪽 가장자리|아래쪽 가장자리|왼쪽 가장자리|오른쪽 가장자리|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점의 왼쪽 아래 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점 변경의 오른쪽 위 모서리의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점의 왼쪽 아래 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 오른쪽 위 모퉁이에 변경 되 고 popup 맞춤 지점의 왼쪽 위 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|위쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역 (마우스 포인터의 경계)의 왼쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점의 왼쪽 아래 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점의 왼쪽 아래 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|위쪽 가장자리에 맞춥니다.|Popup 맞춤 지점의 왼쪽 아래 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다.|왼쪽 가장자리에 맞춥니다.|Popup 맞춤 지점이 Popup의 오른쪽 위 모퉁이로 변경됩니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|위쪽 가장자리에 맞춥니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|대상 원점이 대상 영역의 왼쪽 위 모퉁이로 변경 되 고 popup 맞춤 지점 변경의 오른쪽 위 모서리의 <xref:System.Windows.Controls.Primitives.Popup>합니다.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|대상 원점이 대상 영역의 왼쪽 아래 모퉁이로 변경 되 고 popup 맞춤 지점의 왼쪽 위 모퉁이로 변경 되는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 와 동일 이것이 사실 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 는 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>합니다.|아래쪽 가장자리에 맞춥니다.|왼쪽 가장자리에 맞춥니다.|오른쪽 가장자리에 맞춥니다.|  
  
### <a name="aligning-to-the-screen-edge"></a>화면 가장자리에 맞춤  
 A <xref:System.Windows.Controls.Primitives.Popup> 맞출 수 화면 가장자리에 따라서 자체 위치에서 전체 <xref:System.Windows.Controls.Primitives.Popup> 화면에 표시 됩니다.  대상 원점 및 popup 맞춤 지점 간의 거리 값에서 다를 수 있습니다이 문제가 발생 하면 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 고 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>입니다. 때 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>는 <xref:System.Windows.Controls.Primitives.Popup> 모든 화면 가장자리에 맞춰 정렬 합니다.  예를 들어, 가정를 <xref:System.Windows.Controls.Primitives.Popup> 했습니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 로 설정 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> 및 <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> 100으로 설정 합니다.  화면의 아래쪽 가장자리의 일부나 전부를 숨긴 경우 합니다 <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> 자체적 화면과 대상 원점 및 popup 사이의 세로 거리의 아래쪽 가장자리 맞춤 지점이 100 미만입니다. 다음 그림에서 이 경우를 보여 줍니다.  
  
 ![화면 가장자리에 맞춰진 popup](./media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
화면 가장자리에 맞춰진 Popup  
  
### <a name="changing-the-popup-alignment-point"></a>Popup 맞춤 지점 변경  
 경우 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 은 <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, 아래쪽 또는 오른쪽 화면 가장자리 popup 때 popup 맞춤 지점을 변경 합니다.  
  
 다음 그림에서는 아래쪽 화면 가장자리의 일부나 전부를 숨기는 경우는 <xref:System.Windows.Controls.Primitives.Popup>, 팝업 맞춤 지점은의 왼쪽 아래 모서리를 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 ![아래쪽 화면 가장자리로 인 한 새로운 맞춤 지점](./media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Popup이 화면의 아래쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함  
  
 다음 그림에서는 때 합니다 <xref:System.Windows.Controls.Primitives.Popup> 숨겨져 오른쪽 화면 가장자리와 만나고 popup 맞춤 지점을의 오른쪽 위 모서리를 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 ![화면 가장자리로 인 한 새로운 팝업 맞춤 지점](./media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Popup이 화면의 오른쪽 가장자리와 만나고 Popup 맞춤 지점을 변경함  
  
 경우는 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽과 오른쪽 화면 가장자리를 발견 하면 팝업 맞춤 지점은 오른쪽 아래 모퉁이의 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>대상 원점 및 Popup 맞춤 지점 변경  
 때 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>를 <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, 또는 <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, 특정 화면 가장자리 발견 되 면 대상 원점 및 popup 맞춤 지점이 변경 합니다.  위치 변경을 일으키는 화면 가장자리에 따라 달라 집니다는 <xref:System.Windows.Controls.Primitives.PlacementMode> 값입니다.  
  
 다음 그림을 보여 줍니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> 및 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리와 만나는 대상 원점은 대상 영역의 왼쪽 위 모퉁이 이며 팝업 맞춤 지점의 왼쪽 아래 모서리를 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![아래쪽 화면 가장자리로 인 한 새로운 맞춤 지점](./media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Placement가 Bottom이고 Popup이 화면의 아래쪽 가장자리와 만남  
  
 다음 그림을 보여 줍니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Left> 하며 <xref:System.Windows.Controls.Primitives.Popup> 왼쪽된 화면 가장자리와 만나는 대상 원점은 대상 영역의 오른쪽 위 모서리 및 popup 맞춤 지점은 합니다 의왼쪽위모퉁이<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![왼쪽된 화면 가장자리로 인 한 새로운 맞춤 지점](./media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Placement가 Left이고 Popup이 화면의 왼쪽 가장자리와 만남  
  
 다음 그림을 보여 줍니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Right> 및 <xref:System.Windows.Controls.Primitives.Popup> 오른쪽 화면 가장자리와 만나는 대상 원점은 대상 영역의 왼쪽 위 모퉁이 이며 팝업 맞춤 지점의 오른쪽 위 모서리를 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![오른쪽 화면 가장자리로 인 한 새로운 맞춤 지점](./media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Placement가 Right이고 Popup이 화면의 오른쪽 가장자리와 만남  
  
 다음 그림을 보여 줍니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Top> 및 <xref:System.Windows.Controls.Primitives.Popup> 위쪽 화면 가장자리와 만나는 대상 원점은 대상 영역의 왼쪽 아래 모서리 이며 팝업 맞춤 지점의 왼쪽 위 모퉁이 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![위쪽 화면 가장자리로 인 한 새로운 맞춤 지점](./media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Placement가 Top이고 Popup이 화면의 위쪽 가장자리와 만남  
  
 다음 그림을 보여 줍니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 됩니다 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> 고 <xref:System.Windows.Controls.Primitives.Popup> 아래쪽 화면 가장자리와 만나는 대상 원점은 대상 영역 (마우스 포인터의 경계) 및 popup 맞춤의 왼쪽 위 모퉁이 점은의 왼쪽 아래 모서리를 <xref:System.Windows.Controls.Primitives.Popup>입니다.  
  
 ![화면 가장자리 근처의 마우스로 인 한 새로운 맞춤 지점](./media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Placement가 Mouse이고 Popup이 화면의 아래쪽 가장자리와 만남  
  
### <a name="customizing-popup-placement"></a>Popup 배치 사용자 지정  
 대상 원점 및 popup 맞춤 지점을 설정 하 여 사용자 지정할 수 있습니다 합니다 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> 속성을 <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>입니다. 그런 다음 정의 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> 에 대 한 가능한 배치 지점 및 기본 축을 (기본 설정의 순서로)의 집합을 반환 하는 대리자는 <xref:System.Windows.Controls.Primitives.Popup>합니다. 가장 큰 부분을 표시 하는 지점이 <xref:System.Windows.Controls.Primitives.Popup> 을 선택 합니다.  위치를 <xref:System.Windows.Controls.Primitives.Popup> 하는 경우 자동으로 조정 됩니다는 <xref:System.Windows.Controls.Primitives.Popup> 화면의 가장자리에 의해 숨겨집니다. 예제를 보려면 [사용자 지정 팝업 위치 지정](how-to-specify-a-custom-popup-position.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [Popup Placement Sample](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)(Popup 배치 샘플)
