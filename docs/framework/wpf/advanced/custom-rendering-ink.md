---
title: 잉크 렌더링 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111831"
---
# <a name="custom-rendering-ink"></a>잉크 렌더링 사용자 지정
스트로크의 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 속성을 사용하면 크기, 색상 및 모양과 같은 획모양을 지정할 수 있지만 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 허용한 것 이상으로 모양을 사용자 지정하려는 경우가 있을 수 있습니다. 에어브러시, 오일 페인트 및 다른 많은 효과가 있는 모양을 렌더링하여 잉크 모양을 사용자 지정하려는 경우도 있을 수 있습니다. WPF(Windows 프레젠테이션 재단)를 사용하면 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 및 <xref:System.Windows.Ink.Stroke> 개체를 구현하여 렌더링 잉크를 사용자 지정할 수 있습니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [아키텍처](#Architecture)  
  
- [동적 렌더러 구현](#ImplementingADynamicRenderer)  
  
- [사용자 지정 스트로크 구현](#ImplementingCustomStrokes)  
  
- [사용자 지정 InkCanvas 구현](#ImplementingACustomInkCanvas)  
  
- [결론](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>Architecture  
 잉크 렌더링은 두 번 발생합니다. 사용자가 잉크 입력 표면에 잉크를 쓸 때 한 번 발생하고 잉크 지원 표면에 스트로크가 추가된 후에 다시 한 번 발생합니다. 사용자가 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 디지타이저에서 태블릿 펜을 이동할 때 잉크를 <xref:System.Windows.Ink.Stroke> 렌더링하고 요소에 추가되면 렌더링됩니다.  
  
 동적으로 잉크를 렌더링하는 경우 세 가지 클래스를 구현해야 합니다.  
  
1. **DynamicRenderer**: <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>에서 파생되는 클래스를 구현합니다. 이 클래스는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 그려질 때 스트로크를 렌더링하는 특수화된 클래스입니다. 은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 별도의 스레드에서 렌더링을 수행하므로 응용 프로그램 사용자 인터페이스(UI) 스레드가 차단된 경우에도 잉크를 수집하는 잉크가 나타납니다. 스레딩 모델에 대한 자세한 내용은 [잉크 스레딩 모델](the-ink-threading-model.md)을 참조하세요. 획을 동적으로 렌더링하도록 사용자 지정하려면 메서드를 재정의합니다. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>  
  
2. **스트로크**: <xref:System.Windows.Ink.Stroke>에서 파생되는 클래스를 구현합니다. 이 클래스는 <xref:System.Windows.Input.StylusPoint> 개체로 변환된 후 데이터의 정적 렌더링을 담당합니다. <xref:System.Windows.Ink.Stroke> 스트로크의 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 정적 렌더링이 동적 렌더링과 일치하는지 확인하기 위해 메서드를 재정의합니다.  
  
3. **잉크 캔버스:** <xref:System.Windows.Controls.InkCanvas>에서 파생되는 클래스를 구현합니다. 속성에 사용자 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 지정을 할당합니다. <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 메서드를 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 재정의하고 속성에 사용자 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 지정 스트로크를 추가합니다. 이를 통해 잉크 모양이 일관되게 유지됩니다.  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>동적 렌더러 구현  
 클래스는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]보다 특수화된 렌더링을 수행하려면 의 표준 부분이지만 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 메서드에서 파생되고 메서드를 재정의하는 사용자 지정된 동적 렌더러를 만들어야 합니다.  
  
 다음 예제에서는 선형 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 그라데이션 브러시 효과로 잉크를 그리는 사용자 지정을 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>사용자 지정 스트로크 구현  
 <xref:System.Windows.Ink.Stroke>에서 파생되는 클래스를 구현합니다. 이 클래스는 개체로 변환된 후 데이터를 <xref:System.Windows.Input.StylusPoint> <xref:System.Windows.Ink.Stroke> 렌더링합니다. 실제 도면을 수행하려면 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 클래스를 재정의합니다.  
  
 Stroke 클래스는 메서드를 <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> 사용하여 사용자 지정 데이터를 저장할 수도 있습니다. 이 데이터는 스트로크 데이터와 함께 저장되어 유지됩니다.  
  
 클래스는 <xref:System.Windows.Ink.Stroke> 적중 테스트를 수행할 수도 있습니다. 현재 클래스의 메서드를 재정의하여 사용자 <xref:System.Windows.Ink.Stroke.HitTest%2A> 고유의 적중 테스트 알고리즘을 구현할 수도 있습니다.  
  
 다음 C# 코드는 데이터를 <xref:System.Windows.Ink.Stroke> 3D <xref:System.Windows.Input.StylusPoint> 스트로크로 렌더링하는 사용자 지정 클래스를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>사용자 지정 InkCanvas 구현  
 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 및 스트로크를 사용하는 가장 쉬운 방법은 이러한 <xref:System.Windows.Controls.InkCanvas> 클래스에서 파생되고 사용하는 클래스를 구현하는 것입니다. 사용자에게 <xref:System.Windows.Controls.InkCanvas> 선을 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 그릴 때 스트로크가 렌더링되는 방법을 지정하는 속성이 있습니다.  
  
 에 렌더링 스트로크를 <xref:System.Windows.Controls.InkCanvas> 사용자 지정하려면 다음을 수행합니다.  
  
- 에서 파생되는 클래스를 <xref:System.Windows.Controls.InkCanvas>만듭니다.  
  
- 속성에 사용자 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 지정을 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> 할당합니다.  
  
- <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 메서드를 재정의합니다. 이 메서드에서 InkCanvas에 추가된 원래 스트로크를 제거합니다. 그런 다음 사용자 지정 스트로크를 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 만들고 속성에 추가하고 사용자 <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> 지정 스트로크가 포함된 새 클래스를 사용하여 기본 클래스를 호출합니다.  
  
 다음 C# 코드는 사용자 <xref:System.Windows.Controls.InkCanvas> 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 스트로크를 사용하고 사용자 지정 스트로크를 수집하는 사용자 지정 클래스를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 A는 <xref:System.Windows.Controls.InkCanvas> 하나 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>이상의 것을 가질 수 있습니다. 속성에 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkCanvas> 추가하여 여러 객체를 추가할 수 있습니다. <xref:System.Windows.UIElement.StylusPlugIns%2A>  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>결론  
 고유한 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>및 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Controls.InkCanvas> 클래스를 파생하여 잉크 모양을 사용자 지정할 수 있습니다. 이와 함께 이러한 클래스는 사용자가 스트로크를 그릴 때와 스트로크가 수집된 후의 모양이 일관되도록 합니다.  
  
## <a name="see-also"></a>참고 항목

- [고급 잉크 처리](advanced-ink-handling.md)
