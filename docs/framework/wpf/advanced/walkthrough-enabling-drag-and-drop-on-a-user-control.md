---
title: '연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용'
description: Windows Presentation Foundation에서 끌어서 놓기 데이터 전송에 참여할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168274"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용

이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송에 참가할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.

이 연습에서는 circle 셰이프를 나타내는 사용자 지정 WPF를 만듭니다 <xref:System.Windows.Controls.UserControl> . 컨트롤에서 끌어서 놓기를 통해 데이터 전송을 활성화하는 기능을 구현합니다. 예를 들어 한 원 컨트롤에서 다른 원 컨트롤로 끌면 채우기 색 데이터가 소스 원에서 대상 원으로 복사됩니다. 원 컨트롤에서로 끌어 오면 <xref:System.Windows.Controls.TextBox> 채우기 색의 문자열 표현이에 복사 됩니다 <xref:System.Windows.Controls.TextBox> . 또한 두 개의 패널 컨트롤과를 포함 하는 작은 응용 프로그램을 만들어 <xref:System.Windows.Controls.TextBox> 끌어서 놓기 기능을 테스트 합니다. 패널이 끌어 놓은 원 데이터를 처리하여 한 패널의 자식 컬렉션에서 다른 패널로 원을 이동하거나 복사할 수 있도록 하는 코드를 작성합니다.

이 연습에서는 다음 작업을 수행합니다.

- 사용자 지정 사용자 정의 컨트롤 만들기

- 사용자 정의 컨트롤을 끌기 소스로 사용할 수 있도록 설정

- 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정

- 패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정

## <a name="prerequisites"></a>필수 구성 요소

이 연습을 완료하려면 Visual Studio가 필요합니다.

## <a name="create-the-application-project"></a>응용 프로그램 프로젝트 만들기
 이 섹션에서는 두 개의 패널과를 사용 하는 기본 페이지를 포함 하는 응용 프로그램 인프라를 만듭니다 <xref:System.Windows.Controls.TextBox> .

1. Visual Basic 또는 Visual C#에서 `DragDropExample`이라는 새 WPF 애플리케이션 프로젝트를 만듭니다. 자세한 내용은 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.

2. MainWindow.xaml을 엽니다.

3. 여는 태그와 닫는 태그 사이에 다음 태그를 추가 합니다 <xref:System.Windows.Controls.Grid> .

     이 태그는 테스트 애플리케이션에 대한 사용자 인터페이스를 만듭니다.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>프로젝트에 새 사용자 정의 컨트롤 추가
 이 섹션에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.

1. [프로젝트] 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.

2. **새 항목 추가** 대화 상자에서 이름을로 변경 하 `Circle.xaml` 고 **추가**를 클릭 합니다.

     Circle.xaml과 해당 코드 숨김이 프로젝트에 추가됩니다.

3. Circle.xaml을 엽니다.

     이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.

4. 다음 태그를 루트에 추가 <xref:System.Windows.Controls.Grid> 하 여 파란색 원이 UI로 포함 된 간단한 사용자 정의 컨트롤을 만듭니다.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

6. C #에서 매개 변수가 없는 생성자 뒤에 다음 코드를 추가 하 여 복사 생성자를 만듭니다. Visual Basic에서 다음 코드를 추가 하 여 매개 변수가 없는 생성자와 복사 생성자를 모두 만듭니다.

     사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에서 복사 생성자 메서드를 추가합니다. 간단한 원 사용자 정의 컨트롤에서 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>주 창에 사용자 정의 컨트롤 추가

1. MainWindow.xaml을 엽니다.

2. 다음 XAML을 여는 태그에 추가 하 여 <xref:System.Windows.Window> 현재 응용 프로그램에 대 한 XML 네임 스페이스 참조를 만듭니다.

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. 첫 번째에서 <xref:System.Windows.Controls.StackPanel> 다음 XAML을 추가 하 여 첫 번째 패널에서 Circle 사용자 정의 컨트롤의 두 인스턴스를 만듭니다.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     패널에 대한 전체 XAML은 다음과 같습니다.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>사용자 정의 컨트롤에서 끌기 소스 이벤트 구현
 이 섹션에서는 메서드를 재정의 <xref:System.Windows.UIElement.OnMouseMove%2A> 하 고 끌어서 놓기 작업을 시작 합니다.

 마우스 단추를 누른 상태에서 마우스 단추를 누르면로 전송할 데이터를 패키지할 수 있습니다 <xref:System.Windows.DataObject> . 이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.

### <a name="to-initiate-a-drag-and-drop-operation"></a>끌어서 놓기 작업을 시작하려면

1. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

2. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnMouseMove%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.MouseMove> 합니다.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     이 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의는 다음 작업을 수행 합니다.

    - 마우스를 이동하는 동안 마우스 왼쪽 단추를 눌렀는지 여부를 확인합니다.

    - 원 데이터를에 패키지 <xref:System.Windows.DataObject> 합니다. 이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.

    - 정적 메서드를 호출 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> 하 여 끌어서 놓기 작업을 시작 합니다. 메서드에 다음 세 개의 매개 변수를 전달 합니다 <xref:System.Windows.DragDrop.DoDragDrop%2A> .

        - `dragSource` – 이 컨트롤에 대한 참조입니다.

        - `data`– <xref:System.Windows.DataObject> 이전 코드에서 만든입니다.

        - `allowedEffects`– 허용 된 끌어서 놓기 작업 ( <xref:System.Windows.DragDropEffects.Copy> 또는) <xref:System.Windows.DragDropEffects.Move> 입니다.

3. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

4. 원 컨트롤 중 하나를 클릭 하 고 패널, 다른 원 및로 끕니다 <xref:System.Windows.Controls.TextBox> . 위로 끌면 <xref:System.Windows.Controls.TextBox> 커서는 이동을 나타내기 위해 변경 됩니다.

5. 위로 원을 끌어 오면 <xref:System.Windows.Controls.TextBox> **ctrl** 키를 누릅니다. 복사를 나타내기 위해 커서가 어떻게 변경되는지 확인합니다.

6. 원을로 끌어 놓습니다 <xref:System.Windows.Controls.TextBox> . 원 채우기 색의 문자열 표현이에 추가 됩니다 <xref:System.Windows.Controls.TextBox> .

     ![원의 채우기 색에 대한 문자열 표현](./media/dragdrop-colorstring.png "DragDrop_ColorString")

기본적으로 커서는 끌어서 놓기 작업 중 데이터 놓기의 결과를 나타내도록 변경됩니다. 이벤트를 처리 <xref:System.Windows.UIElement.GiveFeedback> 하 고 다른 커서를 설정 하 여 사용자에 게 제공 되는 피드백을 사용자 지정할 수 있습니다.

## <a name="give-feedback-to-the-user"></a>사용자에 게 피드백 제공

1. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

2. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.GiveFeedback> 합니다.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     이 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의는 다음 작업을 수행 합니다.

    - <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>놓기 대상의 이벤트 처리기에 설정 된 값을 확인 합니다 <xref:System.Windows.UIElement.DragOver> .

    - 값을 기준으로 사용자 지정 커서를 설정 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 합니다. 커서는 데이터 놓기의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.

3. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

4. 패널, 다른 원 및에서 원 컨트롤 중 하나를 끕니다 <xref:System.Windows.Controls.TextBox> . 이제 커서는 재정의에서 지정한 사용자 지정 커서입니다 <xref:System.Windows.UIElement.OnGiveFeedback%2A> .

     ![사용자 지정 커서로 끌어서 놓기](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5. 에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.

6. `green` 텍스트를 원 컨트롤로 끕니다. 기본 커서가 끌어서 놓기 작업의 결과를 나타내도록 표시되는지 확인합니다. 피드백 커서는 항상 끌기 소스에 의해 설정됩니다.

## <a name="implement-drop-target-events-in-the-user-control"></a>사용자 정의 컨트롤에서 놓기 대상 이벤트 구현
 이 섹션에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하는 메서드를 재정의하며, 대상에 끌어 놓은 데이터를 처리합니다.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하려면

1. Circle.xaml을 엽니다.

2. 여는 <xref:System.Windows.Controls.UserControl> 태그에서 속성을 추가 하 <xref:System.Windows.UIElement.AllowDrop%2A> 고로 설정 `true` 합니다.

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<xref:System.Windows.UIElement.OnDrop%2A>메서드는 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이로 설정 되 `true` 고 끌기 소스의 데이터가 Circle 사용자 정의 컨트롤에 삭제 될 때 호출 됩니다. 이 메서드에서는 끌어 놓은 데이터를 처리하고 해당 데이터를 원에 적용합니다.

### <a name="to-process-the-dropped-data"></a>끌어 놓은 데이터를 처리하려면

1. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

2. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.Drop> 합니다.

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     이 <xref:System.Windows.UIElement.OnDrop%2A> 재정의는 다음 작업을 수행 합니다.

    - 메서드를 사용 하 여 <xref:System.Windows.DataObject.GetDataPresent%2A> 끌어 온 데이터에 문자열 개체가 포함 되어 있는지 여부를 확인 합니다.

    - <xref:System.Windows.DataObject.GetData%2A>문자열 데이터가 있는 경우 메서드를 사용 하 여 문자열 데이터를 추출 합니다.

    - 는를 사용 하 여 문자열을로 <xref:System.Windows.Media.BrushConverter> 변환 <xref:System.Windows.Media.Brush> 합니다.

    - 변환이 성공 하면는 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> Circle 컨트롤의 UI를 제공 하는의에 브러시를 적용 합니다.

    - 이벤트를 <xref:System.Windows.UIElement.Drop> 처리 된 것으로 표시 합니다. 이 이벤트를 수신하는 다른 요소가 원 사용자 정의 컨트롤에서 해당 이벤트를 처리했음을 알 수 있도록 놓기 이벤트를 처리된 것으로 표시해야 합니다.

3. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

4. 에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.

5. 텍스트를 원 컨트롤로 끌어서 놓습니다. 원이 파란색에서 녹색으로 바뀝니다.

     ![브러시로 문자열 변환](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6. 에 텍스트를 입력 합니다 `green` <xref:System.Windows.Controls.TextBox> .

7. 에서 텍스트를 선택 `gre` <xref:System.Windows.Controls.TextBox> 합니다.

8. 이 텍스트를 원 컨트롤로 끌어서 놓습니다. 놓기가 허용됨을 나타내도록 커서가 변경되지만 `gre`가 유효한 색이 아니기 때문에 원의 색은 변경되지 않습니다.

9. 녹색 원 컨트롤에서 끌어서 파란색 원 컨트롤에 놓습니다. 원이 파란색에서 녹색으로 바뀝니다. 표시 되는 커서는 <xref:System.Windows.Controls.TextBox> 또는 원이 끌기 소스 인지에 따라 달라 집니다.

속성을 <xref:System.Windows.UIElement.AllowDrop%2A> 로 설정 하 `true` 고 끌어 놓은 데이터를 처리 하는 것은 요소를 놓기 대상으로 설정 하는 데 필요 합니다. 그러나 더 나은 사용자 환경을 제공 하기 위해 <xref:System.Windows.UIElement.DragEnter> , 및 이벤트도 처리 해야 합니다 <xref:System.Windows.UIElement.DragLeave> <xref:System.Windows.UIElement.DragOver> . 이러한 이벤트에서 데이터를 놓기 전에 검사를 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.

데이터를 원 사용자 정의 컨트롤로 끌면 컨트롤에서 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다. 컨트롤에서 데이터 처리 방법을 알지 못하는 경우 놓기를 거부해야 합니다. 이렇게 하려면 이벤트를 처리 하 <xref:System.Windows.UIElement.DragOver> 고 속성을 설정 <xref:System.Windows.DragEventArgs.Effects%2A> 합니다.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>데이터 놓기가 허용되는지 확인하려면

1. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

2. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragOver%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragOver> 합니다.

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     이 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의는 다음 작업을 수행 합니다.

    - <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.None>로 설정합니다.

    - 메서드에서 수행 하는 것과 동일한 검사를 수행 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 Circle 사용자 정의 컨트롤이 끌어 온 데이터를 처리할 수 있는지 여부를 확인 합니다.

    - 사용자 정의 컨트롤에서 데이터를 처리할 수 있는 경우에는 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 또는로 설정 합니다 <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move> .

3. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

4. 에서 텍스트를 선택 `gre` <xref:System.Windows.Controls.TextBox> 합니다.

5. 텍스트를 원 컨트롤로 끕니다. `gre`가 유효한 색이 아니므로 놓기가 허용되지 않음을 나타내도록 커서가 변경됩니다.

 놓기 작업의 미리 보기를 적용하여 사용자 환경을 더욱 향상시킬 수 있습니다. Circle 사용자 정의 컨트롤의 경우 및 메서드를 재정의 <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> 합니다. 컨트롤 위로 데이터를 끌면 현재 배경이 <xref:System.Windows.Shapes.Shape.Fill%2A> 자리 표시자 변수에 저장 됩니다. 그러면 문자열이 브러시로 변환 되 고 <xref:System.Windows.Shapes.Ellipse> 원의 UI를 제공 하는에 적용 됩니다. 데이터를 삭제 하지 않고 원 밖으로 끌면 원래 <xref:System.Windows.Shapes.Shape.Fill%2A> 값이 원에 다시 적용 됩니다.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>끌어서 놓기 작업의 결과를 미리 보려면

1. Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.

2. Circle 클래스에서 라는 private 변수를 선언 하 <xref:System.Windows.Media.Brush> `_previousFill` 고로 초기화 `null` 합니다.

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragEnter%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragEnter> 합니다.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     이 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의는 다음 작업을 수행 합니다.

    - <xref:System.Windows.Shapes.Shape.Fill%2A>의 속성을 변수에 저장 합니다 <xref:System.Windows.Shapes.Ellipse> `_previousFill` .

    - 메서드에서 수행 하는 것과 동일한 검사를 수행 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 데이터를로 변환할 수 있는지 여부를 확인 합니다 <xref:System.Windows.Media.Brush> .

    - 데이터가 유효한으로 변환 되 면 <xref:System.Windows.Media.Brush> 이를의에 적용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> .

4. 다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragLeave%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragLeave> 합니다.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     이 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의는 다음 작업을 수행 합니다.

    - <xref:System.Windows.Media.Brush> `_previousFill` <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> Circle 사용자 정의 컨트롤의 UI를 제공 하는의에 변수에 저장 된를 적용 합니다.

5. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

6. 에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.

7. 텍스트를 놓지 않고 원 컨트롤 위로 끕니다. 원이 파란색에서 녹색으로 바뀝니다.

     ![&#45;&#45;끌어서 놓기 작업의 효과 미리 보기](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8. 원 컨트롤에서 멀리 텍스트를 끕니다. 원이 녹색에서 다시 파란색으로 바뀝니다.

## <a name="enable-a-panel-to-receive-dropped-data"></a>패널에서 삭제 된 데이터를 받을 수 있도록 설정

이 섹션에서는 Circle 사용자 정의 컨트롤을 호스팅하는 패널을 끌어 끌어온 원 데이터의 놓기 대상 역할을 할 수 있습니다. 한 패널에서 다른 패널로 원을 이동 하거나, **Ctrl** 키를 누른 채 원를 끌어서 놓는 방법으로 원 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현 합니다.

1. MainWindow.xaml을 엽니다.

2. 다음 XAML에 표시 된 것 처럼 각 <xref:System.Windows.Controls.StackPanel> 컨트롤에서 및 이벤트에 대 한 처리기를 <xref:System.Windows.UIElement.DragOver> 추가 <xref:System.Windows.UIElement.Drop> 합니다. <xref:System.Windows.UIElement.DragOver>이벤트 처리기의 이름을, `panel_DragOver` 및로 이벤트 처리기의 이름을로 <xref:System.Windows.UIElement.Drop> `panel_Drop` 합니다.

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. MainWindows.xaml.cs 또는 MainWindow.xaml.vb를 엽니다.

4. 이벤트 처리기에 대 한 다음 코드를 추가 합니다 <xref:System.Windows.UIElement.DragOver> .

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     이 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기는 다음 작업을 수행 합니다.

    - <xref:System.Windows.DataObject>원 사용자 정의 컨트롤에 의해 패키지 되 고에 대 한 호출에 전달 된 "개체" 데이터가 끌어온 데이터에 포함 되어 있는지 확인 <xref:System.Windows.DragDrop.DoDragDrop%2A> 합니다.

    - "Object" 데이터가 있는 경우 **Ctrl** 키를 눌렀는지 여부를 확인 합니다.

    - **Ctrl** 키를 누르면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성이로 설정 <xref:System.Windows.DragDropEffects.Copy> 됩니다. 그렇지 않은 경우 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을로 설정 <xref:System.Windows.DragDropEffects.Move> 합니다.

5. 이벤트 처리기에 대 한 다음 코드를 추가 합니다 <xref:System.Windows.UIElement.Drop> .

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     이 <xref:System.Windows.UIElement.Drop> 이벤트 처리기는 다음 작업을 수행 합니다.

    - 이벤트가 이미 처리 되었는지 여부를 확인 <xref:System.Windows.UIElement.Drop> 합니다. 예를 들어, 이벤트를 처리 하는 다른 원에 원을 놓는 경우 <xref:System.Windows.UIElement.Drop> 원이 포함 된 패널에서 해당 원을 처리 하지 않도록 합니다.

    - <xref:System.Windows.UIElement.Drop>이벤트가 처리 되지 않은 경우 **Ctrl** 키를 눌렀는지 여부를 확인 합니다.

    - 이 발생할 때 **Ctrl** 키를 누르면 <xref:System.Windows.UIElement.Drop> 에서 Circle 컨트롤의 복사본을 만들어의 컬렉션에 추가 합니다 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.StackPanel> .

    - **Ctrl** 키를 누르지 않으면 <xref:System.Windows.Controls.Panel.Children%2A> 부모 패널의 컬렉션에서 원을 <xref:System.Windows.Controls.Panel.Children%2A> 끌어 놓은 패널의 컬렉션으로 이동 합니다.

    - <xref:System.Windows.DragEventArgs.Effects%2A> <xref:System.Windows.DragDrop.DoDragDrop%2A> 이동 또는 복사 작업의 수행 여부를 메서드에 알리도록 속성을 설정 합니다.

6. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

7. 에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.

8. 텍스트를 원 컨트롤로 끌어서 놓습니다.

9. 왼쪽 패널에서 오른쪽 패널로 원 컨트롤을 끌어서 놓습니다. 왼쪽 패널의 컬렉션에서 원이 제거 되 <xref:System.Windows.Controls.Panel.Children%2A> 고 오른쪽 패널의 자식 컬렉션에 추가 됩니다.

10. Circle 컨트롤을 패널에서 다른 패널로 끌고 **Ctrl** 키를 누른 상태에서 놓습니다. 원이 복사 되 고 복사본이 <xref:System.Windows.Controls.Panel.Children%2A> 수신 패널의 컬렉션에 추가 됩니다.

     ![Ctrl 키를 누른 채 원 끌기](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>참고 항목

- [끌어서 놓기 개요](drag-and-drop-overview.md)
