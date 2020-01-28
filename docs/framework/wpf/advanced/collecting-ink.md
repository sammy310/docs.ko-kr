---
title: 디지털 잉크 수집
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747031"
---
# <a name="collect-ink"></a>잉크 수집

[Windows Presentation Foundation](../index.md) 플랫폼은 기능의 핵심 요소로서 디지털 잉크를 수집합니다. 이 항목에서는 Windows Presentation Foundation (WPF)에서 잉크를 수집 하는 방법에 대해 설명 합니다.

## <a name="prerequisites"></a>전제 조건

다음 예제를 사용 하려면 먼저 Visual Studio 및 Windows SDK를 설치 해야 합니다. WPF 용 응용 프로그램을 작성 하는 방법에 대해서도 이해 해야 합니다. WPF를 시작 하는 방법에 대 한 자세한 내용은 [연습: 내 첫 wpf 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.

## <a name="use-the-inkcanvas-element"></a>InkCanvas 요소 사용

<xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> 요소는 WPF에서 잉크를 수집 하는 가장 쉬운 방법을 제공 합니다. <xref:System.Windows.Controls.InkCanvas> 요소를 사용 하 여 잉크 입력을 받고 표시 합니다. 일반적으로 스타일러스를 사용하여 잉크를 입력합니다.이 스타일러스는 디지타이저와 상호 작용하여 잉크 스트로크를 생성합니다. 또한 스타일러스 대신 마우스를 사용할 수도 있습니다. 생성 된 스트로크는 <xref:System.Windows.Ink.Stroke> 개체로 표시 되 고 프로그래밍 방식으로 및 사용자 입력에 의해 조작 될 수 있습니다. 사용자는 <xref:System.Windows.Controls.InkCanvas>를 사용 하 여 기존 <xref:System.Windows.Ink.Stroke>를 선택, 수정 또는 삭제할 수 있습니다.

XAML을 사용 하 여 **InkCanvas** 요소를 트리에 추가 하는 것 처럼 잉크 컬렉션을 쉽게 설정할 수 있습니다. 다음 예제에서는 Visual Studio에서 만든 기본 WPF 프로젝트에 <xref:System.Windows.Controls.InkCanvas>를 추가 합니다.

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

**InkCanvas** 요소는 자식 요소를 포함할 수도 있으므로 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있습니다. 예를 들어 텍스트 요소에 잉크 기능을 추가 하려면 단순히 <xref:System.Windows.Controls.InkCanvas>의 자식으로 만듭니다.

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

잉크를 사용 하 여 이미지를 표시 하기 위한 지원을 추가 하는 것은 간단 합니다.

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>InkCollection 모드

<xref:System.Windows.Controls.InkCanvas>은 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성을 통해 다양 한 입력 모드를 지원 합니다.

### <a name="manipulate-ink"></a>잉크 조작

<xref:System.Windows.Controls.InkCanvas>에서는 많은 잉크 편집 작업을 지원 합니다. 예를 들어 <xref:System.Windows.Controls.InkCanvas>는 펜 후면 지우기를 지원 하 고 요소에 기능을 추가 하는 데 필요한 추가 코드는 없습니다.

#### <a name="selection"></a>선택 항목

선택 모드를 설정 하는 것은 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **Select**로 설정 하는 것 만큼 간단 합니다.

다음 코드는 <xref:System.Windows.Forms.CheckBox>값에 따라 편집 모드를 설정 합니다.

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 속성을 사용 하 여 잉크 스트로크의 모양을 변경 합니다. 예를 들어 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> <xref:System.Windows.Ink.DrawingAttributes>의 멤버는 렌더링 된 <xref:System.Windows.Ink.Stroke>의 색을 설정 합니다.

다음 예제에서는 선택 된 스트로크의 색을 빨강으로 변경 합니다.

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성은 <xref:System.Windows.Controls.InkCanvas>에서 만들 스트로크의 높이, 너비 및 색과 같은 속성에 대 한 액세스를 제공 합니다. <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 변경한 후에는 <xref:System.Windows.Controls.InkCanvas>에 입력 된 모든 이후 스트로크가 새 속성 값으로 렌더링 됩니다.

코드 숨김이 파일의 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 수정 하는 것 외에도 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 지정 하는 데 XAML 구문을 사용할 수 있습니다.

다음 예제에서는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성을 설정 하는 방법을 보여 줍니다. 이 코드를 사용 하려면 Visual Studio에서 "HelloInkCanvas" 이라는 새 WPF 프로젝트를 만듭니다. *Mainwindow.xaml* 파일의 코드를 다음 코드로 바꿉니다.

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

다음으로, Mainwindow.xaml 클래스 내의 코드 뒤에 다음 단추 이벤트 처리기를 추가 합니다.

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

이 코드를 복사한 후 Visual Studio에서 **f5** 키를 눌러 디버거에서 프로그램을 실행 합니다.

<xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.InkCanvas>위에 단추를 배치 하는 방법을 확인 합니다. 단추 위쪽에서 잉크를 시도 하는 경우 <xref:System.Windows.Controls.InkCanvas>은 단추 뒤에 잉크를 수집 하 고 렌더링 합니다. 이는 단추가 자식이 아닌 <xref:System.Windows.Controls.InkCanvas>의 형제 이기 때문입니다. 또한 단추가 z 순서에서 더 앞서기 때문에 잉크가 단추 뒤에서 렌더링됩니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
