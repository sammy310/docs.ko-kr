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
ms.openlocfilehash: 7629843730a82584e94448ceac1ea574906876c9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095140"
---
# <a name="intercepting-input-from-the-stylus"></a>스타일러스에서 입력 가로채기
<xref:System.Windows.Input.StylusPlugIns> 아키텍처는 <xref:System.Windows.Input.Stylus> 입력 및 디지털 잉크 <xref:System.Windows.Ink.Stroke> 개체 만들기에 대 한 하위 수준 제어를 구현 하는 메커니즘을 제공 합니다. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스는 사용자 지정 동작을 구현 하 고 최적의 성능을 위해 스타일러스 장치에서 들어오는 데이터 스트림에 적용 하는 메커니즘을 제공 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [아키텍처](#Architecture)  
  
- [스타일러스 플러그 인 구현](#ImplementingStylusPlugins)  
  
- [InkCanvas에 플러그 인 추가](#AddingYourPluginToAnInkCanvas)  
  
- [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>아키텍처  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>은 [펜 입력 액세스 및 조작](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))에 설명 된 [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) api의 진화입니다.  
  
 각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>. 요소의 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>을 추가 하 여 생성 될 때 <xref:System.Windows.Input.StylusPoint> 데이터를 조작할 수 있습니다. <xref:System.Windows.Input.StylusPoint> 데이터는 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 지점 데이터 뿐만 아니라 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 데이터를 포함 하 여 시스템 디지타이저에서 지 원하는 모든 속성으로 구성 됩니다.  
  
 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>를 추가 하면 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체가 <xref:System.Windows.Input.Stylus> 장치에서 들어오는 데이터 스트림에 직접 삽입 됩니다. <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 플러그 인을 추가 하는 순서는 <xref:System.Windows.Input.StylusPoint> 데이터를 받는 순서를 결정 합니다. 예를 들어 특정 영역으로 입력을 제한 하는 필터 플러그 인을 추가 하 고 쓸 때 제스처를 인식 하는 플러그 인을 추가 하는 경우 제스처를 인식 하는 플러그 인이 필터링 된 <xref:System.Windows.Input.StylusPoint> 데이터를 수신 합니다.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>스타일러스 플러그 인 구현  
 플러그 인을 구현 하려면 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>에서 클래스를 파생 시킵니다. 이 클래스는 <xref:System.Windows.Input.Stylus>에서 들어오는 데이터 스트림에 적용 됩니다. 이 클래스에서 <xref:System.Windows.Input.StylusPoint> 데이터의 값을 수정할 수 있습니다.  
  
> [!CAUTION]
> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throw 하거나 예외를 발생 시키는 경우 응용 프로그램이 종료 됩니다. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>를 사용 하는 컨트롤을 철저 하 게 테스트 하 고 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 예외를 throw 하지 않는 특정 한 경우에만 컨트롤을 사용 해야 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Stylus> 장치에서 제공 되는 <xref:System.Windows.Input.StylusPoint> 데이터의 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 값을 수정 하 여 스타일러스 입력을 제한 하는 플러그 인을 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>InkCanvas에 플러그 인 추가  
 사용자 지정 플러그 인을 사용 하는 가장 쉬운 방법은 InkCanvas에서 파생 되는 클래스를 구현 하 고이를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 추가 하는 것입니다.  
  
 다음 예제에서는 잉크를 필터링 하는 사용자 지정 <xref:System.Windows.Controls.InkCanvas>를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 응용 프로그램에 `FilterInkCanvas`를 추가 하 고 실행 하면 사용자가 스트로크를 완료할 때까지 잉크가 지역으로 제한 되지 않습니다. 이는 <xref:System.Windows.Controls.InkCanvas>에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 이며 이미 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션의 멤버인 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성이 있기 때문입니다. <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가한 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 데이터를 받은 후 <xref:System.Windows.Input.StylusPoint> 데이터를 받습니다. 따라서 사용자가 펜을 뗄 때 까지는 스트로크를 종료할 때까지 <xref:System.Windows.Input.StylusPoint> 데이터가 필터링 되지 않습니다. 사용자가 그릴 때 잉크를 필터링 하려면 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>앞에 `FilterPlugin`을 삽입 해야 합니다.  
  
 다음 C# 코드에서는 잉크를 그릴 때 필터링 하는 사용자 지정 <xref:System.Windows.Controls.InkCanvas>를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>결론  
 사용자 고유의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 파생 하 여 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 컬렉션에 삽입 하면 디지털 잉크의 동작을 크게 향상 시킬 수 있습니다. 생성 된 <xref:System.Windows.Input.StylusPoint> 데이터에 액세스할 수 있으므로 <xref:System.Windows.Input.Stylus> 입력을 사용자 지정할 수 있습니다. <xref:System.Windows.Input.StylusPoint> 데이터에 대 한 하위 수준 액세스 권한이 있으므로 응용 프로그램의 성능을 최적화 하 고 잉크 수집 및 렌더링을 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [고급 잉크 처리](advanced-ink-handling.md)
- [펜 입력 액세스 및 조작](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))
