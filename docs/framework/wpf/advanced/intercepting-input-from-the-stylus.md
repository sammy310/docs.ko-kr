---
title: 스타일러스에서 입력 가로채기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181924"
---
# <a name="intercepting-input-from-the-stylus"></a>스타일러스에서 입력 가로채기
아키텍처는 <xref:System.Windows.Input.StylusPlugIns> <xref:System.Windows.Input.Stylus> 입력 및 디지털 잉크 <xref:System.Windows.Ink.Stroke> 개체 생성에 대한 낮은 수준의 제어를 구현하기 위한 메커니즘을 제공합니다. 클래스는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 사용자 지정 동작을 구현하고 최적의 성능을 위해 스타일러스 장치에서 오는 데이터 스트림에 적용하는 메커니즘을 제공합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [아키텍처](#Architecture)  
  
- [스타일러스 플러그인 구현](#ImplementingStylusPlugins)  
  
- [잉크 캔버스에 플러그인 추가](#AddingYourPluginToAnInkCanvas)  
  
- [결론](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 은 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> [펜 입력 에 액세스 및 조작에](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))설명된 [스타일러스Input](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) API의 진화입니다.  
  
 각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. 요소의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 a를 추가하여 생성될 <xref:System.Windows.Input.StylusPoint> 때 데이터를 조작할 수 있습니다. <xref:System.Windows.Input.StylusPoint>데이터는 <xref:System.Windows.Input.StylusPoint.X%2A> 데이터뿐만 <xref:System.Windows.Input.StylusPoint.Y%2A> <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 아니라 및 포인트 데이터를 포함하여 시스템 디지타이저에서 지원하는 모든 속성으로 구성됩니다.  
  
 객체는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 추가할 때 <xref:System.Windows.Input.Stylus> 장치에서 오는 데이터 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 스트림에 직접 삽입됩니다. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 플러그인이 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가되는 순서는 데이터를 수신하는 <xref:System.Windows.Input.StylusPoint> 순서를 지정합니다. 예를 들어 특정 영역에 대한 입력을 제한하는 필터 플러그인을 추가한 다음 제스처가 기록될 때 제스처를 인식하는 플러그인을 추가하면 제스처를 인식하는 플러그인이 필터링된 <xref:System.Windows.Input.StylusPoint> 데이터를 받게 됩니다.  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a>스타일러스 플러그인 구현  
 플러그인을 구현하려면 에서 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>클래스를 파생합니다. 이 클래스는 <xref:System.Windows.Input.Stylus>에서 들어오는 데이터 스트림o에 적용됩니다. 이 클래스에서 데이터의 값을 수정할 <xref:System.Windows.Input.StylusPoint> 수 있습니다.  
  
> [!CAUTION]
> 발생하거나 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 예외가 발생하면 응용 프로그램이 닫힙됩니다. a를 사용하는 컨트롤을 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 철저히 테스트하고 예외를 throw하지 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 않을 것이 확실한 경우에만 컨트롤을 사용해야 합니다.  
  
 다음 <xref:System.Windows.Input.StylusPoint.X%2A> 예제에서는 <xref:System.Windows.Input.StylusPoint.Y%2A> <xref:System.Windows.Input.StylusPoint> 장치에서 들어오는 데이터의 값과 스타일러스 입력을 제한하는 플러그인을 <xref:System.Windows.Input.Stylus> 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>잉크 캔버스에 플러그인 추가  
 사용자 지정 플러그인을 사용하는 가장 쉬운 방법은 InkCanvas에서 파생된 클래스를 구현하고 속성에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 추가하는 것입니다.  
  
 다음 예제에서는 잉크를 <xref:System.Windows.Controls.InkCanvas> 필터링하는 사용자 지정을 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 응용 프로그램에 `FilterInkCanvas` a를 추가하고 실행하면 사용자가 스트로크를 완료할 때까지 잉크가 영역으로 제한되지 않는다는 것을 알 수 있습니다. 이는 컬렉션의 <xref:System.Windows.Controls.InkCanvas> <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 구성원인 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성이 있기 때문입니다. 컬렉션에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> 추가한 사용자 지정은 데이터를 수신한 <xref:System.Windows.Input.StylusPoint> 후 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 데이터를 수신합니다. 따라서 사용자가 펜을 <xref:System.Windows.Input.StylusPoint> 들어 올려 스트로크를 종료할 때까지 데이터가 필터링되지 않습니다. 사용자가 잉크를 그릴 때 잉크를 필터링하려면 `FilterPlugin` 를 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>앞에 삽입해야 합니다.  
  
 다음 C# 코드는 잉크가 그려질 때 잉크를 필터링하는 사용자 지정을 <xref:System.Windows.Controls.InkCanvas> 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>결론  
 자신의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 파생하고 컬렉션에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 삽입하면 디지털 잉크의 동작을 크게 향상시킬 수 있습니다. 생성되는 <xref:System.Windows.Input.StylusPoint> 데이터에 액세스할 수 있으므로 <xref:System.Windows.Input.Stylus> 입력을 사용자 지정할 수 있습니다. <xref:System.Windows.Input.StylusPoint> 데이터에 대한 낮은 수준의 액세스 권한을 가지므로 응용 프로그램에 가장 적합한 성능으로 잉크 수집 및 렌더링을 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [고급 잉크 처리](advanced-ink-handling.md)
- [펜 입력 액세스 및 조작](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
