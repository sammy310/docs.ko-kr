---
title: 표시기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111181"
---
# <a name="adorners-overview"></a>표시기 개요

장식하는 것은 사용자에게 <xref:System.Windows.FrameworkElement>시각적 신호를 제공하는 데 사용되는 특수 유형의 입니다. 표시기는 다른 용도로 요소에 기능 핸들을 추가하거나 컨트롤에 대한 상태 정보를 제공하는 데 사용할 수 있습니다.

## <a name="about-adorners"></a>표시기 정보

A는 <xref:System.Windows.Documents.Adorner> <xref:System.Windows.UIElement>에 <xref:System.Windows.FrameworkElement> 바인딩된 사용자 지정입니다. Adornor는 <xref:System.Windows.Documents.AdornerLayer>항상 장식된 요소 또는 장식된 요소의 컬렉션 위에 있는 렌더링 서피스인 에서 렌더링됩니다. 표시기의 렌더링은 표시기가 <xref:System.Windows.UIElement> 바인딩된 렌더링과 독립적입니다. 장식기는 일반적으로 지정된 요소의 왼쪽 상단에 있는 표준 2D 좌표 원소를 사용하여 바인딩된 요소를 기준으로 배치됩니다.

표시기에 대한 일반 애플리케이션은 다음과 같습니다.

- 사용자가 어떤 식으로든 <xref:System.Windows.UIElement> 요소를 조작할 수 있도록 하는 기능 핸들을 추가합니다(크기 조정, 회전, 위치 변경 등).
- 다양한 상태를 나타내거나 다양한 이벤트에 대한 응답으로 시각적 피드백을 제공합니다.
- 에 시각적 장식을 <xref:System.Windows.UIElement>오버레이합니다.
- 의 일부 또는 전부를 시각적으로 <xref:System.Windows.UIElement>마스킹하거나 재정의합니다.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 시각적 요소를 표시하는 기본 프레임워크를 제공합니다. 다음 표에 개체 및 해당 용도를 표시할 때 사용되는 기본 유형이 나와 있습니다. 몇 가지 사용 예는 다음과 같습니다.

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|모든 구체적인 표시기 구현이 상속받는 추상 기본 클래스입니다.|
|<xref:System.Windows.Documents.AdornerLayer>|하나 이상의 표시한 요소의 표시기에 대한 렌더링 계층을 나타내는 클래스입니다.|
|<xref:System.Windows.Documents.AdornerDecorator>|표시기 계층이 요소 컬렉션에 연결될 수 있도록 하는 클래스입니다.|

## <a name="implementing-a-custom-adorner"></a>사용자 지정 표시기 구현

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 표시기 프레임워크는 기본적으로 사용자 지정 표시기의 생성을 지원하는 데 사용됩니다. 사용자 지정 표시기는 추상 <xref:System.Windows.Documents.Adorner> 클래스에서 상속하는 클래스를 구현하여 만들어집니다.

> [!NOTE]
> 부모는 <xref:System.Windows.Documents.Adorner> 은 합니다 <xref:System.Windows.Documents.AdornerLayer> 렌더링 하는 <xref:System.Windows.Documents.Adorner>, 표시 되는 요소가 없습니다.

다음 예제에서는 간단한 표시기를 구현하는 클래스를 보여 줍니다. 예제 표시기는 단순히 원의 모서리를 <xref:System.Windows.UIElement> 원으로 장식합니다.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
다음 이미지는 다음에 적용된 심플서클어데너를 <xref:System.Windows.Controls.TextBox>보여 주며, 다음 이미지는 다음과 같은

![장식된 텍스트 상자를 보여 주는 스크린샷입니다.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>표시기에 대한 렌더링 동작

표시기에는 고유 렌더링 동작이 포함되어 있지 않음에 유의해야 합니다. 표시기를 렌더링하는 것은 표시기 구현자의 책임입니다. 렌더링 동작을 구현하는 일반적인 방법은 메서드를 <xref:System.Windows.UIElement.OnRender%2A> 재정의하고 <xref:System.Windows.Media.DrawingContext> 하나 이상의 개체를 사용하여 필요에 따라 표시자의 시각적 개체를 렌더링하는 것입니다(위의 예와 같이).

> [!NOTE]
> 표시기 계층에 배치된 모든 개체는 설정한 스타일의 나머지 부분 맨 위에 렌더링됩니다. 즉, 표시기는 시각적으로 항상 맨 위에 있으며 z-순서를 사용하여 재정의할 수 없습니다.

## <a name="events-and-hit-testing"></a>이벤트 및 적중 횟수 테스트

Adorna는 다른 <xref:System.Windows.FrameworkElement>것과 마찬가지로 입력 이벤트를 수신합니다.  표시기는 항상 장식하는 요소보다 z 순서가 높기 때문에 표시기는 기본 <xref:System.Windows.UIElement.Drop> 장식 <xref:System.Windows.UIElement.MouseMove>요소에 대한 의도일 수 있는 입력 이벤트(예: 또는)를 수신합니다.  표시기는 특정 입력 이벤트를 수신하고 이벤트를 다시 발생시켜 표시한 기본 요소에 전달할 수 있습니다.

표시기 에서 요소의 통과 적중 테스트를 사용 하려면 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 표시기에서 **false** false 히트 테스트 속성을 설정 합니다.  적중 도수 테스트에 대한 자세한 내용은 [시각적 계층의 적중 테스트 를](../graphics-multimedia/hit-testing-in-the-visual-layer.md)참조하십시오.

## <a name="adorning-a-single-uielement"></a>단일 UIElement 표시

표시기를 특정에 <xref:System.Windows.UIElement>바인딩하려면 다음 단계를 따르십시오.

1. 정적 메서드를 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 호출하여 <xref:System.Windows.Documents.AdornerLayer> 표시할 <xref:System.Windows.UIElement> 개체를 가져옵니다. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>지정된 <xref:System.Windows.UIElement>에서 시작하여 시각적 트리를 위로 걷고 찾은 첫 번째 표시레이어를 반환합니다. (표시기 계층이 없으면 메서드가 null을 반환합니다.)

2. 메서드를 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 호출하여 표시기를 대상에 <xref:System.Windows.UIElement>바인딩합니다.

 다음 예제에서는 SimpleCircleAdorn (위에 표시 됨)을 명명 된 <xref:System.Windows.Controls.TextBox> *myTextBox에*바인딩합니다.

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.

## <a name="adorning-the-children-of-a-panel"></a>패널의 자식 표시

의 자식에 <xref:System.Windows.Controls.Panel>표시기를 바인딩하려면 다음 단계를 따르십시오.

1. 메서드를 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 호출하여 자식을 표시할 요소에 대한 표시레이어를 찾습니다.

2. 부모 요소의 자식을 통해 탐색 하고 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 각 자식 요소에 표시기를 바인딩하는 메서드를 호출합니다.

다음 예제에서는 simpleCircleAdorn (위에 표시 됨)을 명명 <xref:System.Windows.Controls.StackPanel> 된 *myStackPanel의*자식에 바인딩합니다.

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.AdornerHitTestResult>
- [WPF에서 Shape 및 기본 그리기 개요](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Drawing 개체 개요](../graphics-multimedia/drawing-objects-overview.md)
- [방법 주제](adorners-how-to-topics.md)
