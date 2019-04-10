---
title: 레이아웃
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
ms.openlocfilehash: 7fc69ff0434a26dc196d24395bbd1e2f441008de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231125"
---
# <a name="layout"></a>레이아웃
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 레이아웃 시스템에 대해 설명합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용자 인터페이스를 만들려면 언제, 어떻게 레이아웃을 계산해야 하는지를 이해해야 합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [요소 경계 상자](#LayoutSystem_BoundingBox)  
  
-   [레이아웃 시스템](#LayoutSystem_Overview)  
  
-   [자식 측정 및 정렬](#LayoutSystem_Measure_Arrange)  
  
-   [패널 요소 및 사용자 지정 레이아웃 동작](#LayoutSystem_PanelsCustom)  
  
-   [레이아웃 성능 고려 사항](#LayoutSystem_Performance)  
  
-   [하위 픽셀 렌더링 및 레이아웃 반올림](#LayoutSystem_LayoutRounding)  
  
-   [새로운 기능](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>요소 경계 상자  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 레이아웃을 고려할 경우에는 모든 요소를 둘러싸고 있는 경계 상자를 이해해야 합니다. 각 <xref:System.Windows.FrameworkElement> 사용 하 여 레이아웃 시스템 생각할 수 있습니다 레이아웃에 배치 되는 사각형으로 합니다. <xref:System.Windows.Controls.Primitives.LayoutInformation> 클래스 요소의 레이아웃 할당 또는 슬롯의 경계를 반환 합니다. 사각형의 크기를 사용할 수 있는 화면 공간, 제약 조건, 레이아웃 관련 속성 (예: 여백 및 안쪽 여백) 및 부모 개별 동작의 크기를 계산 하 여 결정 <xref:System.Windows.Controls.Panel> 요소입니다. 이 데이터 처리, 레이아웃 시스템 특정의 모든 자식 항목 위치를 계산할 수 됩니다. <xref:System.Windows.Controls.Panel>합니다. 같은 부모 요소에는 크기 조정 특성 정의 고려해 야 것을 <xref:System.Windows.Controls.Border>, 자식에 영향을 줍니다.  
  
 다음 그림에서는 간단한 레이아웃을 보여 줍니다.  
  
 ![경계 상자가 없는 일반적인 grid를 보여주는 스크린샷.](./media/layout/grid-no-bounding-box-superimpose.png)  
  
 다음 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 이 레이아웃을 실현할 수 있습니다.  
  
 [!code-xaml[LayoutInformation#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 단일 <xref:System.Windows.Controls.TextBlock> 요소 내에 호스팅되는 <xref:System.Windows.Controls.Grid>합니다. 텍스트를 채우는 첫 번째 열에 할당된 된 공간 왼쪽 위 모퉁이 <xref:System.Windows.Controls.TextBlock> 실제로 훨씬 큽니다. 경계 상자 <xref:System.Windows.FrameworkElement> 를 사용 하 여 검색할 수는 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드. 다음 그림에서는 경계 상자는 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 ![이제 TextBlock 경계 상자는 표시를 보여 주는 스크린샷.](./media/layout/visible-textblock-bounding-box.png)  
  
 노란색 사각형에 할당된 된 공간에 표시 된 대로 <xref:System.Windows.Controls.TextBlock> 요소인 것 보다 실제로 훨씬 큽니다. 추가 요소에 추가 되는 <xref:System.Windows.Controls.Grid>,이 할당이 축소 정도 형식과 추가 되는 요소의 크기에 따라 확장 합니다.  
  
 레이아웃 슬롯을 <xref:System.Windows.Controls.TextBlock> 변환 됩니다를 <xref:System.Windows.Shapes.Path> 를 사용 하 여를 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드. 이 기술은 요소의 경계 상자를 표시하는 데 유용합니다.  
  
 [!code-csharp[LayoutInformation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>레이아웃 시스템  
 가장 간단한 레이아웃은 재귀 시스템이며 이를 통해 요소의 크기가 조정되고 요소가 배치되고 그려집니다. 레이아웃 측정 하 고 멤버를 정렬 하는 프로세스를 설명 하는 구체적으로 <xref:System.Windows.Controls.Panel> 요소의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션입니다. 레이아웃은 집약적인 프로세스입니다. 더 큰 숫자를 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션, 수가 클수록 수행 해야 하는 계산 합니다. 정의한 레이아웃 동작에 따라 복잡성 나타날 수도 있습니다는 <xref:System.Windows.Controls.Panel> 컬렉션을 소유 하는 요소입니다. 상대적으로 간단한 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Canvas>, 보다 복잡 한 보다 성능을 크게 향상을 가질 수 있습니다 <xref:System.Windows.Controls.Panel>, 같은 <xref:System.Windows.Controls.Grid>합니다.  
  
 때마다 자식 <xref:System.Windows.UIElement> 해당 위치를 변경할 레이아웃 시스템에 의해 새로운 단계가 트리거될 수에 합니다. 따라서 불필요한 호출로 인해 애플리케이션 성능이 저하될 수 있으므로 레이아웃 시스템을 호출할 수 있는 이벤트를 이해해야 합니다. 다음에서 레이아웃 시스템이 호출될 때 발생하는 프로세스에 대해 설명합니다.  
  
1.  자식 <xref:System.Windows.UIElement> 먼저 핵심 속성이 측정 되도록 하 여 레이아웃 프로세스를 시작 합니다.  
  
2.  에 정의 된 속성을 크기 조정 <xref:System.Windows.FrameworkElement> 와 같은 평가 됩니다 <xref:System.Windows.FrameworkElement.Width%2A>를 <xref:System.Windows.FrameworkElement.Height%2A>, 및 <xref:System.Windows.FrameworkElement.Margin%2A>합니다.  
  
3.  <xref:System.Windows.Controls.Panel>-같은 논리가 적용 됩니다 <xref:System.Windows.Controls.Dock> 방향 또는 누적 <xref:System.Windows.Controls.StackPanel.Orientation%2A>합니다.  
  
4.  모든 자식을 측정한 후에 콘텐츠가 정렬됩니다.  
  
5.  <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션이 화면에 그려집니다.  
  
6.  추가 하는 경우 프로세스가 다시 호출 됩니다 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 추가 됩니다을 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 적용 또는 <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드가 호출 됩니다.  
  
 이 프로세스와 해당 프로세스가 호출되는 방법은 다음 섹션에 자세히 정의되어 있습니다.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>자식 측정 및 정렬  
 레이아웃 시스템의 각 멤버에 대 한 두 개의 단계인는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션, 측정 단계 및 정렬 단계입니다. 각 자식 <xref:System.Windows.Controls.Panel> 자체 제공 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 고 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 고유한 특정 레이아웃 동작을 수행 하는 방법입니다.  
  
 측정 처리 단계에서의 각 멤버는 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 평가 됩니다. 프로세스에 대 한 호출으로 시작 된 <xref:System.Windows.UIElement.Measure%2A> 메서드. 부모의 구현 내에서이 메서드는 <xref:System.Windows.Controls.Panel> 요소인 레이아웃이 발생 하도록 명시적으로 호출할 필요가 없습니다.  
  
 첫 번째 기본 크기 속성을 <xref:System.Windows.UIElement> 와 같은 평가 됩니다 <xref:System.Windows.UIElement.Clip%2A> 및 <xref:System.Windows.UIElement.Visibility%2A>합니다. 명명 된 값이 생성 `constraintSize` 에 전달 된 <xref:System.Windows.FrameworkElement.MeasureCore%2A>합니다.  
  
 프레임 워크 속성에 정의 된 두 번째로, <xref:System.Windows.FrameworkElement> 처리 되는 값에 영향을 `constraintSize`입니다. 이러한 속성은 일반적으로 기본 크기 조정 특징을 설명 <xref:System.Windows.UIElement>와 같은 해당 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>합니다 <xref:System.Windows.FrameworkElement.Margin%2A>, 및 <xref:System.Windows.FrameworkElement.Style%2A>합니다. 이러한 각 속성은 요소를 표시하는 데 필요한 공간을 변경할 수 있습니다. <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 사용 하 여 이라고 `constraintSize` 매개 변수로 합니다.  
  
> [!NOTE]
>  속성 간에 차이가 <xref:System.Windows.FrameworkElement.Height%2A> 하 고 <xref:System.Windows.FrameworkElement.Width%2A> 하 고 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A>합니다. 예를 들어를 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성은 다른 높이 입력 및 레이아웃 시스템에 따라 계산된 된 값입니다. 값을 실제 렌더링 단계에 따라 레이아웃 시스템 자체적으로 설정 되 고 같은 속성의 설정 값 뒤에 약간 지연 될 수 있습니다 <xref:System.Windows.FrameworkElement.Height%2A>, 입력된 변경의 기준인 합니다.  
>   
>  때문에 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 은 계산된 된 값 수는 여러 개 있을 수 있습니다 또는 보고 변경 하 여 다양 한 작업의 결과로 레이아웃 시스템에서. 레이아웃 시스템은 자식 요소에 필요한 측정 공간, 부모 요소에 의한 제약 조건 등을 계산할 수도 있습니다.  
  
 측정 처리 단계의 궁극적인 목표를 확인 하려면 자식 항목이 해당 <xref:System.Windows.UIElement.DesiredSize%2A>, 중 발생 하는 <xref:System.Windows.FrameworkElement.MeasureCore%2A> 호출 합니다. 합니다 <xref:System.Windows.UIElement.DesiredSize%2A> 값으로 저장 됩니다 <xref:System.Windows.UIElement.Measure%2A> 콘텐츠 정렬 처리 단계 중에 사용 합니다.  
  
 정렬 처리 단계에 대 한 호출으로 시작 된 <xref:System.Windows.UIElement.Arrange%2A> 메서드. 정렬 처리 단계에서 부모 <xref:System.Windows.Controls.Panel> 요소 자식의 경계를 나타내는 사각형을 생성 합니다. 이 값이 전달 된 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 처리용 메서드.  
  
 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드를 평가 <xref:System.Windows.UIElement.DesiredSize%2A> 자식 요소의 렌더링 된 크기에 영향을 줄 수 있는 추가 여백을 평가 합니다. <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 생성을 `arrangeSize`, 전달 되는 합니다 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드의 <xref:System.Windows.Controls.Panel> 매개 변수로. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 생성 된 `finalSize` 자식입니다. 마지막으로 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드 여백 및 맞춤과 같은 오프셋된 속성에 대 한 최종 평가 않으며 자식을 레이아웃 슬롯 내에 놓습니다. 자식은 할당된 공간을 모두 채울 필요가 없으며 실제 모두 채우는 경우가 드뭅니다. 컨트롤의 부모에 반환 됩니다 <xref:System.Windows.Controls.Panel> 레이아웃 프로세스가 완료 됩니다.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>패널 요소 및 사용자 지정 레이아웃 동작  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 파생 되는 요소 그룹을 포함 <xref:System.Windows.Controls.Panel>합니다. 이러한 <xref:System.Windows.Controls.Panel> 요소 많은 복잡 한 레이아웃을 사용 하도록 설정 합니다. 예를 들어 요소 누적 손쉽게 달성할 수 있습니다 사용 하 여 합니다 <xref:System.Windows.Controls.StackPanel> 요소를 사용 하 여 더 복잡 한 고 흐름이 자유로운 레이아웃은 가능한 한 <xref:System.Windows.Controls.Canvas>합니다.  
  
 다음 표에서 사용 가능한 레이아웃 <xref:System.Windows.Controls.Panel> 요소입니다.  
  
|패널 이름|설명|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|명시적으로 좌표를 기준으로 자식 요소를 배치할 수 있는 영역을 정의 하는 <xref:System.Windows.Controls.Canvas> 영역입니다.|  
|<xref:System.Windows.Controls.DockPanel>|자식 요소를 서로 맞춰 가로 또는 세로로 정렬할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.Grid>|열 및 행으로 구성되는 유연한 모눈 영역을 정의합니다.|  
|<xref:System.Windows.Controls.StackPanel>|가로 또는 세로 방향으로 한 줄로 자식 요소를 정렬합니다.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|에 대 한 프레임 워크를 제공 <xref:System.Windows.Controls.Panel> 해당 자식 데이터 컬렉션을 가상화 하는 요소입니다. 이 클래스는 추상 클래스입니다.|  
|<xref:System.Windows.Controls.WrapPanel>|콘텐츠를 컨테이너의 가장자리에서 다음 줄로 나눠 왼쪽에서 오른쪽으로 자식 요소의 위치를 지정합니다. 위쪽에서에서 아래쪽으로 또는 오른쪽에서 왼쪽으로 값에 따라 순차적으로 발생 정렬 된 <xref:System.Windows.Controls.WrapPanel.Orientation%2A> 속성입니다.|  
  
 미리 정의 된 사용 가능 하지 않은 레이아웃이 필요한 응용 프로그램에 대 한 <xref:System.Windows.Controls.Panel> 에서 상속 하 여 요소를 사용자 지정 레이아웃 동작을 수행할 수 있습니다 <xref:System.Windows.Controls.Panel> 재정의 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 고 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드. 예제는 [Custom Radial Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159982)(사용자 지정 방사형 패널 샘플)을 참조하세요.  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>레이아웃 성능 고려 사항  
 레이아웃은 재귀적인 프로세스입니다. 각 자식 요소는 <xref:System.Windows.Controls.Panel.Children%2A> 레이아웃 시스템이 호출 될 때마다 컬렉션 처리를 가져옵니다. 따라서 필요하지 않을 때 레이아웃 시스템을 트리거하는 것을 피해야 합니다. 다음은 보다 뛰어난 성능을 얻는 데 도움이 되는 고려 사항입니다.  
  
-   레이아웃 시스템에서 재귀적으로 업데이트하도록 하는 속성 값 변경에 주의해야 합니다.  
  
     레이아웃 시스템을 초기화하는 값을 가진 종속성 속성은 공용 플래그로 표시됩니다. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> 및 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> 레이아웃 시스템에서 업데이트 값이 변경 되는 속성에 대 한 재귀를 강제로 유용한 단서를 제공 합니다. 요소의 경계 상자 크기에 영향을 줄 수 있는 모든 속성을 해야 일반적으로 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> 플래그가 true로 설정 합니다. 자세한 내용은 [종속성 속성 개요](dependency-properties-overview.md)를 참조하세요.  
  
-   사용 가능한 경우는 <xref:System.Windows.UIElement.RenderTransform%2A> of를 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>입니다.  
  
     A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 의 내용에 영향을 매우 유용한 방법일 수 있습니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. 그러나 변환 효과가 다른 요소의 위치에 영향을 줄에 없는 경우 것이 좋습니다 사용 하는 <xref:System.Windows.UIElement.RenderTransform%2A> 대신 있으므로 <xref:System.Windows.UIElement.RenderTransform%2A> 레이아웃 시스템을 호출 하지 않습니다. <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 해당 변환을 적용 하 고 영향을 받는 요소의 새 위치를 고려 하는 재귀적 레이아웃 업데이트를 수행 합니다.  
  
-   에 대 한 불필요 한 호출 방지 <xref:System.Windows.UIElement.UpdateLayout%2A>합니다.  
  
     <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드는 재귀적 레이아웃 업데이트를 강제 하 고 자주 필요 하지 않습니다. 전체 업데이트가 필요하다고 확신하는 경우를 제외하고는 레이아웃 시스템에서만 이 메서드를 호출합니다.  
  
-   큰 작업할 때 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션을 사용 하는 것이 좋습니다는 <xref:System.Windows.Controls.VirtualizingStackPanel> 일반 대신 <xref:System.Windows.Controls.StackPanel>합니다.  
  
     자식 컬렉션을 가상화 하 여는 <xref:System.Windows.Controls.VirtualizingStackPanel> 현재 부모의 뷰포트 내에 있는 메모리의 개체만 유지 합니다. 이를 통해 대부분의 시나리오에서 성능이 크게 향상됩니다.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>하위 픽셀 렌더링 및 레이아웃 반올림  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 시스템에서는 해상도와 장치의 영향을 받지 않기 위해 장치 독립적 단위를 사용합니다. 각 디바이스 독립적 픽셀은 시스템의 [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] 설정에 맞게 자동으로 크기가 조정됩니다. 이를 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션에서 다양한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 설정에 적합하게 크기를 조정할 수 있으며 자동으로 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]를 인식할 수 있도록 합니다.  
  
 그러나 이러한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 독립성은 앤티앨리어싱으로 인해 불규칙한 가장자리 렌더링을 만들 수 있습니다. 일반적으로 흐리거나 반투명한 가장자리로 표시되는 이러한 아티팩트는 가장자리의 위치가 디바이스 픽셀 사이가 아닌 디바이스 픽셀 가운데에 있을 때 발생할 수 있습니다. 레이아웃 시스템에서는 레이아웃 반올림을 사용하여 조정할 수 있는 방법을 제공합니다. 레이아웃 반올림에서 레이아웃 단계 동안 모든 비정수 픽셀 값을 레이아웃 시스템이 반올림합니다.  
  
 레이아웃 반올림은 기본적으로 사용되지 않습니다. 레이아웃 반올림을 사용 하도록 설정 하려면 설정 합니다 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 속성을 `true` 에서 <xref:System.Windows.FrameworkElement>합니다. 종속성 속성이므로 값이 시각적 트리의 모든 자식에 전파됩니다. 전체 UI에 대해 레이아웃 반올림을 사용 하려면 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 에 `true` 루트 컨테이너에서. 예제를 보려면 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>를 참조하십시오.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>새로운 기능  
 요소의 측정 방법과 정렬 방법을 이해하는 것이 레이아웃을 이해하기 위한 첫 단계입니다. 자세한 내용은 사용 가능한 <xref:System.Windows.Controls.Panel> 요소를 참조 하세요 [Panel 개요](../controls/panels-overview.md)합니다. 레이아웃에 영향을 줄 수 있는 다양한 배치 속성을 더 잘 이해하려면 [맞춤, 여백 및 안쪽 여백 개요](alignment-margins-and-padding-overview.md)를 참조하세요. 사용자 지정의 예 <xref:System.Windows.Controls.Panel> 요소를 참조 하세요 [사용자 지정 방사형 패널 샘플](https://go.microsoft.com/fwlink/?LinkID=159982)합니다. 간단한 응용 프로그램에서 모두 함께 배치할 준비가 되었을 때 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.UIElement>
- [Panel 개요](../controls/panels-overview.md)
- [맞춤, 여백 및 안쪽 여백 개요](alignment-margins-and-padding-overview.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
