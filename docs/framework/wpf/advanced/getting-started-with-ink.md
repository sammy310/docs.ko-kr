---
title: Visual Studio에서 WPF 앱에 InkCanvas 만들기
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: ebbf25037921e7802b2bfcb6ffa562d16a849ffa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920246"
---
# <a name="get-started-with-ink-in-wpf"></a>WPF에서 잉크 시작

WPF (Windows Presentation Foundation)에는 디지털 잉크를 앱에 쉽게 통합 하는 데 사용 되는 잉크 기능이 있습니다.

## <a name="prerequisites"></a>Prerequisites

다음 예제를 사용 하려면 먼저 [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)를 설치 합니다. 또한 기본적인 WPF 앱을 작성 하는 방법을 알고 있습니다. WPF 시작에 대 한 도움말은 [연습: 내 첫 wpf 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.

## <a name="quick-start"></a>빠른 시작

이 섹션은 잉크를 수집 하는 간단한 WPF 응용 프로그램을 작성 하는 데 도움이 됩니다.

### <a name="got-ink"></a>잉크가 있나요?

잉크를 지 원하는 WPF 앱을 만들려면 다음을 수행 합니다.

1. Visual Studio를 엽니다.

2. 새 **WPF 앱**을 만듭니다.

   **새 프로젝트** 대화 상자에서 **설치** > **시각적 개체 C#**  또는 **Visual Basic** > **Windows Desktop** 범주를 확장 합니다. 그런 다음 **WPF 앱 (.NET Framework)** 앱 템플릿을 선택 합니다. 이름을 입력 하 고 **확인**을 선택 합니다.

   Visual Studio에서 프로젝트가 만들어지고 디자이너에서 *mainwindow.xaml* 이 열립니다.

3. `<Grid>` 태그 사이에 `<InkCanvas/>`을 입력 합니다.

   ![InkCanvas 태그를 사용 하는 XAML 디자이너](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. 디버거에서 응용 프로그램을 시작 하려면 **f5** 키를 누릅니다.

5. 스타일러스 또는 마우스를 사용 하 여 창에서 **hello 세계** 를 작성 합니다.

12 개의 키 입력만 있는 "hello 세계" 응용 프로그램에 해당 하는 잉크를 작성 했습니다.

### <a name="spice-up-your-app"></a>앱 꾸며보세요

WPF의 일부 기능을 활용 하겠습니다. 열기 및 닫기 \<> 창 사이의 모든 항목을 다음 태그로 바꿉니다.

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

이 XAML은 잉크 화면에 그라데이션 브러시 배경을 만듭니다.

![WPF 앱의 잉크 화면 그라데이션 색](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>XAML 뒤에 코드를 추가 합니다.

XAML을 사용 하면 사용자 인터페이스를 매우 쉽게 디자인할 수 있지만 실제 응용 프로그램은 이벤트를 처리 하는 코드를 추가 해야 합니다. 마우스 오른쪽 단추 클릭에 대 한 응답으로 잉크를 확대 하는 간단한 예제는 다음과 같습니다.

1. XAML에서 `MouseRightButtonUp` 처리기를 설정 합니다.

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. **솔루션 탐색기**에서 mainwindow.xaml를 확장 하 고 코드 파일 (MainWindow.xaml.cs 또는 mainwindow.xaml)을 엽니다. 다음 이벤트 처리기 코드를 추가 합니다.

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. 애플리케이션을 실행합니다. 일부 잉크를 추가 하 고 마우스 오른쪽 단추를 클릭 하거나 스타일러스를 사용 하 여 선택 및 유지를 수행 합니다.

   마우스 오른쪽 단추로 클릭할 때마다 디스플레이가 확대 됩니다.

### <a name="use-procedural-code-instead-of-xaml"></a>XAML 대신 절차적 코드 사용

절차적 코드에서 모든 WPF 기능에 액세스할 수 있습니다. XAML을 전혀 사용 하지 않는 WPF 용 "Hello Ink 세계" 응용 프로그램을 만들려면 다음 단계를 수행 합니다.

1. Visual Studio에서 새 콘솔 응용 프로그램 프로젝트를 만듭니다.

   **새 프로젝트** 대화 상자에서 **설치** > **시각적 개체 C#**  또는 **Visual Basic** > **Windows Desktop** 범주를 확장 합니다. 그런 다음 **콘솔 앱 (.NET Framework)** 앱 템플릿을 선택 합니다. 이름을 입력 하 고 **확인**을 선택 합니다.

1. Program.cs 또는 Program .vb 파일에 다음 코드를 붙여 넣습니다.

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. **솔루션 탐색기** 에서 **참조** 를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 하 여 PresentationCore, PresentationFramework 및 windowsbase 어셈블리에 대 한 참조를 추가 합니다.

   ![PresentationCore 및 PresentationFramework를 보여 주는 참조 관리자](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. **F5**키를 눌러 응용 프로그램을 빌드합니다.

## <a name="see-also"></a>참조

- [디지털 잉크](digital-ink.md)
- [잉크 수집](collecting-ink.md)
- [필기 인식](handwriting-recognition.md)
- [잉크 저장](storing-ink.md)
