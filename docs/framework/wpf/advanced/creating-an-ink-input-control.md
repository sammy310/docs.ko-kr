---
title: 잉크 입력 컨트롤 만들기
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 394318488b0afb8e043389e0abc3f51dce8604c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186291"
---
# <a name="creating-an-ink-input-control"></a>잉크 입력 컨트롤 만들기
잉크를 동적으로 정적으로 렌더링하는 사용자 지정 컨트롤을 만들 수 있습니다. 즉, 사용자가 스트로크를 그릴 때 렌더링 잉크는 태블릿 펜에서 잉크가 "흐르도록" 표시하고, 태블릿 펜을 통해 컨트롤에 추가된 후 잉크를 표시하거나, 클립보드에서 붙여넣거나, 파일에서 로드합니다. 잉크를 동적으로 렌더링하려면 컨트롤에서 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 사용해야 합니다. 잉크를 정적으로 렌더링하려면 스타일러스 이벤트<xref:System.Windows.UIElement.OnStylusDown%2A>메서드 (, <xref:System.Windows.UIElement.OnStylusMove%2A>및)를 <xref:System.Windows.UIElement.OnStylusUp%2A> <xref:System.Windows.Input.StylusPoint> 재정의하여 데이터를 수집하고, 획을 <xref:System.Windows.Controls.InkPresenter> 만들고, (컨트롤에서 잉크를 렌더링하는)에 추가해야 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [방법: 스타일러스 점 데이터 수집 및 잉크 획 작성](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [방법: 마우스에서 입력을 수락하도록 컨트롤을 사용하도록 설정합니다.](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [통합](#PuttingItTogether)  
  
- [추가 플러그인 및 DynamicRenderers 사용](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [결론](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>방법: 스타일러스 점 데이터 수집 및 잉크 획 작성  
 잉크 스트로크를 수집하고 관리하는 컨트롤을 만들려면 다음을 수행합니다.  
  
1. 에서 파생 <xref:System.Windows.Controls.Control> 된 클래스 또는 에서 <xref:System.Windows.Controls.Control>파생 된 <xref:System.Windows.Controls.Label>클래스 중 하나를 파생 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. 클래스에 <xref:System.Windows.Controls.InkPresenter> a를 추가하고 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 새 <xref:System.Windows.Controls.InkPresenter>로 설정합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.Controls.InkPresenter> <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <xref:System.Windows.UIElement.StylusPlugIns%2A> 메서드를 호출하여 에 의를 연결하고 컬렉션에 추가합니다. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 이렇게 하면 <xref:System.Windows.Controls.InkPresenter> 컨트롤에서 스타일러스 포인트 데이터가 수집될 때 잉크를 표시할 수 있습니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <xref:System.Windows.UIElement.OnStylusDown%2A> 메서드를 재정의합니다.  이 메서드에서는 에 대 한 호출으로 <xref:System.Windows.Input.Stylus.Capture%2A>스타일러스를 캡처합니다. 스타일러스를 캡처하면 스타일러스가 컨트롤의 <xref:System.Windows.UIElement.StylusMove> 경계를 <xref:System.Windows.UIElement.StylusUp> 벗어나더라도 컨트롤이 계속 수신되고 이벤트가 발생합니다. 이것은 엄격하게 필수는 아니지만 거의 항상 좋은 사용자 경험을 원합니다. 새 <xref:System.Windows.Input.StylusPointCollection> 데이터를 생성하여 데이터를 수집합니다. <xref:System.Windows.Input.StylusPoint> 마지막으로 <xref:System.Windows.Input.StylusPoint> <xref:System.Windows.Input.StylusPointCollection>의 초기 데이터 집합을 에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. 메서드를 <xref:System.Windows.UIElement.OnStylusMove%2A> 재정의하고 <xref:System.Windows.Input.StylusPoint> 이전에 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 데이터를 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. 메서드를 <xref:System.Windows.UIElement.OnStylusUp%2A> 재정의하고 <xref:System.Windows.Ink.Stroke> <xref:System.Windows.Input.StylusPointCollection> 데이터로 새 메서드를 만듭니다. 만든 새 <xref:System.Windows.Ink.Stroke> 스타일러스 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 캡처 및 <xref:System.Windows.Controls.InkPresenter> 릴리스 컬렉션에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>방법: 마우스에서 입력을 수락하도록 컨트롤을 사용하도록 설정합니다.  
 응용 프로그램에 이전 컨트롤을 추가하고 실행하고 마우스를 입력 장치로 사용하면 스트로크가 유지되지 않는 것을 알 수 있습니다. 마우스를 입력 장치로 사용할 때 스트로크를 유지하려면 다음을 수행합니다.  
  
1. 을 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 재정의하고 이벤트가 <xref:System.Windows.Input.StylusPointCollection> 발생했을 때 마우스의 위치를 가져옵니다 <xref:System.Windows.Input.StylusPoint> 및 포인트 데이터를 사용하여 <xref:System.Windows.Input.StylusPoint> 생성하고 에 <xref:System.Windows.Input.StylusPointCollection>추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의합니다. 이벤트가 발생했을 때 마우스의 위치를 얻고 <xref:System.Windows.Input.StylusPoint> 포인트 데이터를 사용하여 생성합니다.  이전에 <xref:System.Windows.Input.StylusPoint> 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 를 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드를 재정의합니다.  <xref:System.Windows.Input.StylusPointCollection> 데이터로 <xref:System.Windows.Ink.Stroke> 새 데이터를 만들고 만든 <xref:System.Windows.Ink.Stroke> 새 를 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> <xref:System.Windows.Controls.InkPresenter>을 의 컬렉션에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>
## <a name="putting-it-together"></a>통합  
 다음 예제는 사용자가 마우스 나 펜을 사용할 때 잉크를 수집 하는 사용자 지정 컨트롤입니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>추가 플러그인 및 DynamicRenderers 사용  
 InkCanvas와 마찬가지로 사용자 지정 컨트롤에는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 및 추가 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체가 있을 수 있습니다. 컬렉션에 추가합니다. <xref:System.Windows.UIElement.StylusPlugIns%2A> 순서는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 렌더링 될 때 적용 될 잉크의 모양을. 가정은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 라는 `dynamicRenderer` 및 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 라는 `translatePlugin` 태블릿 펜에서 잉크를 오프셋 하는. 경우 `translatePlugin` 첫 번째 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 및 `dynamicRenderer` , 두 번째는 사용자가 펜을 움직이면 "흐르는" 잉크가 오프셋 됩니다. 첫 `dynamicRenderer` 번째이고 `translatePlugin` 두 번째인 경우 사용자가 펜을 들어올릴 때까지 잉크가 오프셋되지 않습니다.  
  
<a name="AdvancedInkHandling_Conclusion"></a>
## <a name="conclusion"></a>결론  
 스타일러스 이벤트 메서드를 재정의하여 잉크를 수집하고 렌더링하는 컨트롤을 만들 수 있습니다. 사용자 고유의 컨트롤을 만들고, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 고유한 클래스를 파생시키고, <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>에 삽입하면 디지털 잉크로 상상할 수 있는 거의 모든 동작을 구현할 수 있습니다. 생성되는 <xref:System.Windows.Input.StylusPoint> 데이터에 액세스할 수 있으므로 <xref:System.Windows.Input.Stylus> 입력을 사용자 지정하고 응용 프로그램에 적합한 화면에 렌더링할 수 있습니다. <xref:System.Windows.Input.StylusPoint> 데이터에 대한 낮은 수준 액세스 권한이 있으므로 잉크 수집을 구현하고 응용 프로그램에 대한 최적의 성능으로 렌더링할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [고급 잉크 처리](advanced-ink-handling.md)
- [펜 입력 액세스 및 조작](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
