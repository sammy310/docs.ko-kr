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
ms.openlocfilehash: 98b2abf813a232e36b80683254174b12b97659bb
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095218"
---
# <a name="creating-an-ink-input-control"></a>잉크 입력 컨트롤 만들기
동적 및 정적으로 잉크를 렌더링 하는 사용자 지정 컨트롤을 만들 수 있습니다. 즉, 사용자가 스트로크를 그릴 때 잉크를 렌더링 하 여 태블릿 펜에서 잉크를 "flow"로 표시 하 고, 태블릿 펜을 통하거나 클립보드에 붙여넣거나 파일에서 로드 한 후 잉크를 표시 합니다. 동적으로 잉크를 렌더링 하려면 컨트롤에서 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 사용 해야 합니다. 정적으로 잉크를 렌더링 하려면 스타일러스 이벤트 메서드 (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>및 <xref:System.Windows.UIElement.OnStylusUp%2A>)를 재정의 하 여 <xref:System.Windows.Input.StylusPoint> 데이터를 수집 하 고, 스트로크를 만든 후 컨트롤에서 잉크를 렌더링 하는 <xref:System.Windows.Controls.InkPresenter>에 추가 해야 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- [방법: 스타일러스 지점 데이터 수집 및 잉크 스트로크 만들기](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [방법: 컨트롤에서 마우스 입력을 허용 하도록 설정](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [함께 배치](#PuttingItTogether)  
  
- [추가 플러그 인 및 DynamicRenderers 사용](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [결론](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>방법: 스타일러스 지점 데이터 수집 및 잉크 스트로크 만들기  
 잉크 스트로크를 수집 하 고 관리 하는 컨트롤을 만들려면 다음을 수행 합니다.  
  
1. <xref:System.Windows.Controls.Control> 또는 <xref:System.Windows.Controls.Control>에서 파생 된 클래스 중 하나 (예: <xref:System.Windows.Controls.Label>)에서 클래스를 파생 시킵니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. 클래스에 <xref:System.Windows.Controls.InkPresenter>를 추가 하 고 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 새 <xref:System.Windows.Controls.InkPresenter>로 설정 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 메서드를 호출 하 여 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>를 <xref:System.Windows.Controls.InkPresenter>에 연결 하 고 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 컬렉션에 <xref:System.Windows.UIElement.StylusPlugIns%2A>을 추가 합니다. 이렇게 하면 컨트롤이 스타일러스 지점 데이터를 수집할 때 잉크를 표시할 <xref:System.Windows.Controls.InkPresenter> 수 있습니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <xref:System.Windows.UIElement.OnStylusDown%2A> 메서드를 재정의합니다.  이 메서드에서 <xref:System.Windows.Input.Stylus.Capture%2A>에 대 한 호출을 사용 하 여 스타일러스를 캡처합니다. 스타일러스를 캡처하면 컨트롤이 컨트롤의 경계를 벗어나면 컨트롤이 계속 <xref:System.Windows.UIElement.StylusMove> 및 <xref:System.Windows.UIElement.StylusUp> 이벤트를 수신 합니다. 이는 반드시 필요한 것은 아니지만 좋은 사용자 환경을 위해 거의 항상 필요 합니다. <xref:System.Windows.Input.StylusPoint> 데이터를 수집 하는 새 <xref:System.Windows.Input.StylusPointCollection>를 만듭니다. 마지막으로 <xref:System.Windows.Input.StylusPoint> 데이터의 초기 집합을 <xref:System.Windows.Input.StylusPointCollection>에 추가 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. <xref:System.Windows.UIElement.OnStylusMove%2A> 메서드를 재정의 하 고 앞에서 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 <xref:System.Windows.Input.StylusPoint> 데이터를 추가 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. <xref:System.Windows.UIElement.OnStylusUp%2A> 메서드를 재정의 하 고 <xref:System.Windows.Input.StylusPointCollection> 데이터를 사용 하 여 새 <xref:System.Windows.Ink.Stroke>을 만듭니다. 만든 새 <xref:System.Windows.Ink.Stroke>를 <xref:System.Windows.Controls.InkPresenter>의 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 컬렉션에 추가 하 고 스타일러스 캡처를 해제 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>방법: 컨트롤에서 마우스 입력을 허용 하도록 설정  
 응용 프로그램에 이전 컨트롤을 추가 하 고 실행 한 다음 마우스를 입력 장치로 사용 하면 스트로크가 지속 되지 않는다는 것을 알 수 있습니다. 마우스가 입력 장치로 사용 될 때 스트로크를 유지 하려면 다음을 수행 합니다.  
  
1. <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>를 재정의 하 고 새 <xref:System.Windows.Input.StylusPointCollection> 만든 다음 이벤트가 발생 했을 때 마우스의 위치를 가져오고 point 데이터를 사용 하 여 <xref:System.Windows.Input.StylusPoint>를 만든 다음 <xref:System.Windows.Input.StylusPointCollection>에 <xref:System.Windows.Input.StylusPoint>를 추가 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의합니다. 이벤트가 발생 했을 때 마우스의 위치를 가져오고 점 데이터를 사용 하 여 <xref:System.Windows.Input.StylusPoint>를 만듭니다.  이전에 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 <xref:System.Windows.Input.StylusPoint>를 추가 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드를 재정의합니다.  <xref:System.Windows.Input.StylusPointCollection> 데이터를 사용 하 여 새 <xref:System.Windows.Ink.Stroke>을 만들고 만든 새 <xref:System.Windows.Ink.Stroke>을 <xref:System.Windows.Controls.InkPresenter>의 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 컬렉션에 추가 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>함께 배치  
 다음 예제는 사용자가 마우스나 펜 중 하나를 사용할 때 잉크를 수집 하는 사용자 지정 컨트롤입니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>추가 플러그 인 및 DynamicRenderers 사용  
 InkCanvas와 마찬가지로 사용자 지정 컨트롤에는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 및 추가 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체가 있을 수 있습니다. <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가 합니다. 순서는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 렌더링 될 때 적용 될 잉크의 모양을. 가정은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 라는 `dynamicRenderer` 및 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 라는 `translatePlugin` 태블릿 펜에서 잉크를 오프셋 하는. 경우 `translatePlugin` 첫 번째 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 및 `dynamicRenderer` , 두 번째는 사용자가 펜을 움직이면 "흐르는" 잉크가 오프셋 됩니다. `dynamicRenderer` 처음이 고 `translatePlugin` 두 번째 이면 사용자가 펜을 뗄 때까지 잉크가 오프셋 되지 않습니다.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>결론  
 스타일러스 이벤트 메서드를 재정의 하 여 잉크를 수집 하 고 렌더링 하는 컨트롤을 만들 수 있습니다. 사용자 고유의 컨트롤을 만들고 사용자 고유의 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 파생 시킨 다음 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>에 삽입 하 여 디지털 잉크로 에서도 모든 동작을 구현할 수 있습니다. 생성 되는 <xref:System.Windows.Input.StylusPoint> 데이터에 대 한 액세스를 제공 하 여 응용 프로그램에 맞게 입력 <xref:System.Windows.Input.Stylus> 사용자 지정 하 고 화면에 렌더링 하는 기회를 제공 합니다. <xref:System.Windows.Input.StylusPoint> 데이터에 대 한 하위 수준 액세스 권한이 있으므로 응용 프로그램에 대 한 최적의 성능으로 잉크 수집을 구현 하 고 렌더링할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [고급 잉크 처리](advanced-ink-handling.md)
- [펜 입력 액세스 및 조작](https://docs.microsoft.com/previous-versions/ms818317(v=msdn.10))
