---
title: Expander 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187120"
---
# <a name="expander-overview"></a>Expander 개요
컨트롤은 <xref:System.Windows.Controls.Expander> 창과 유사하고 헤더를 포함하는 확장 가능한 영역에 콘텐츠를 제공하는 방법을 제공합니다.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>단순 확장기 만들기  
 다음 예제에는 간단한을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.Expander> 제어 합니다. 이 예제는 <xref:System.Windows.Controls.Expander> 이전 그림과 같은 모양을 만듭니다.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> 및 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 의 <xref:System.Windows.Controls.Expander> 및 객체와 <xref:System.Windows.Controls.RadioButton> <xref:System.Windows.Controls.Image> 같은 복잡한 콘텐츠를 포함할 수도 있습니다.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>확장되는 콘텐츠 영역의 방향 설정  
 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up> <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right>속성을 사용하여 컨트롤의 콘텐츠 영역을 네 방향 중 하나로 확장하도록 설정할 수 있습니다. <xref:System.Windows.Controls.ExpandDirection> 콘텐츠 영역이 축소되면 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 해당 토글 버튼만 나타납니다. 방향 <xref:System.Windows.Controls.Button> 화살표를 표시하는 컨트롤은 콘텐츠 영역을 확장하거나 축소하는 토글 단추로 사용됩니다. 확장하면 창과 같은 영역에 모든 콘텐츠를 <xref:System.Windows.Controls.Expander> 표시하려고 시도합니다.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>패널에서 확장기의 크기 제어  
 <xref:System.Windows.Controls.Expander> 컨트롤이 <xref:System.Windows.Controls.Panel>에서 상속하는 레이아웃 컨트롤 내에 있는 <xref:System.Windows.Controls.StackPanel>경우 . <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.Expander.ExpandDirection%2A> <xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up> 마찬가지로 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 속성이 <xref:System.Windows.Controls.ExpandDirection.Left> 또는 <xref:System.Windows.Controls.ExpandDirection.Right>로 설정된 시기를 지정하지 마십시오.  
  
 확장된 콘텐츠가 표시되는 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.Expander> 방향으로 컨트롤에 크기 차원을 설정하면 콘텐츠에서 사용되는 영역을 제어하고 그 주위에 테두리를 표시합니다. 콘텐츠를 축소해도 테두리가 표시됩니다. 확장된 콘텐츠 영역의 크기를 설정하려면 <xref:System.Windows.Controls.Expander>의 콘텐츠에 크기 크기를 설정하거나 콘텐츠를 둘러싸는 <xref:System.Windows.Controls.ScrollViewer> 스크롤 기능을 원하는 경우 크기를 설정합니다.  
  
 컨트롤이 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.DockPanel>의 마지막 요소인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 경우 차원이 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.DockPanel>자동으로 의 나머지 영역과 같아지도록 설정합니다. 이 기본 동작을 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 방지하려면 <xref:System.Windows.Controls.DockPanel> 개체의 `false`속성을 로 설정하거나 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.DockPanel>의 마지막 요소가 아닌지 확인합니다.  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>스크롤 가능한 콘텐츠 만들기  
 콘텐츠가 콘텐츠 영역크기에 너무 큰 경우 스크롤 가능한 콘텐츠를 제공하기 <xref:System.Windows.Controls.Expander> 위해 <xref:System.Windows.Controls.ScrollViewer> a의 내용을 래핑할 수 있습니다. 컨트롤은 <xref:System.Windows.Controls.Expander> 스크롤 기능을 자동으로 제공하지 않습니다. 다음 그림에서는 <xref:System.Windows.Controls.Expander> 컨트롤이 포함된 <xref:System.Windows.Controls.ScrollViewer> 컨트롤을 보여 주며 있습니다.  
  
 **ScrollViewer의 확장기**  
  
 ![ScrollBar가 있는 확장기를 보여 주는 스크린샷입니다.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 에 <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ScrollViewer>컨트롤을 배치할 때 <xref:System.Windows.Controls.ScrollViewer> <xref:System.Windows.Controls.Expander> 콘텐츠가 열리는 방향에 해당하는 차원 속성을 <xref:System.Windows.Controls.Expander> 콘텐츠 영역의 크기로 설정합니다. <xref:System.Windows.Controls.Expander.ExpandDirection%2A> 예를 들어 속성을 <xref:System.Windows.Controls.Expander> 에 <xref:System.Windows.Controls.ExpandDirection.Down> 설정하면(콘텐츠 영역이 열리면) <xref:System.Windows.FrameworkElement.Height%2A> 컨트롤의 <xref:System.Windows.Controls.ScrollViewer> 속성을 콘텐츠 영역에 필요한 높이로 설정합니다. 대신 콘텐츠 자체에 높이 차원을 설정 <xref:System.Windows.Controls.ScrollViewer> 하는 경우이 설정을 인식 하지 않습니다 하 고 따라서 스크롤 가능한 콘텐츠를 제공 하지 않습니다.  
  
 다음 예제에서는 복잡한 콘텐츠가 있고 <xref:System.Windows.Controls.Expander> 컨트롤이 포함된 <xref:System.Windows.Controls.ScrollViewer> 컨트롤을 만드는 방법을 보여 주며, 컨트롤을 만드는 방법을 보여 주며, 컨트롤을 만드는 방법을 보여 주시고 있습니다. 이 예제에서는 <xref:System.Windows.Controls.Expander> 이 섹션의 시작 부분에 있는 그림과 같은 그림을 만듭니다.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>맞춤 속성 사용  
 컨트롤에 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성을 설정하여 콘텐츠를 <xref:System.Windows.Controls.Expander> 정렬할 수 있습니다. 이러한 속성을 설정하면 맞춤이 헤더뿐만 아니라 확장된 콘텐츠에도 적용됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [방법 주제](expander-how-to-topics.md)
