---
title: 비주얼 스튜디오 2019에서 첫 번째 WPF 응용 프로그램을 만들기 - .NET 프레임 워크
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 9381873faa8cca1accf95d823f5183a218d28813
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646425"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>자습서: Visual Studio 2019에서 첫 번째 WPF 응용 프로그램 만들기

이 문서에서는 대부분의 WPF 응용 프로그램에 공통적인 요소인 확장 가능한 응용 프로그램 태그 언어(XAML) 태그, 코드 숨김, 응용 프로그램 정의, 컨트롤, 레이아웃, 데이터 바인딩 및 스타일과 같은 요소를 포함하는 WPF(Windows 프레젠테이션 Foundation) 데스크톱 응용 프로그램을 개발하는 방법을 보여 주었습니다. 응용 프로그램을 개발하려면 Visual Studio를 사용합니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.
> [!div class="checklist"]
>
> - WPF 프로젝트를 만듭니다.
> - XAML을 사용하여 응용 프로그램의 사용자 인터페이스(UI)의 모양을 디자인합니다.
> - 코드를 작성하여 응용 프로그램의 동작을 빌드합니다.
> - 응용 프로그램을 관리하는 응용 프로그램 정의를 만듭니다.
> - 컨트롤을 추가하고 레이아웃을 만들어 응용 프로그램 UI를 작성합니다.
> - 응용 프로그램의 UI 전체에서 일관된 모양을 위한 스타일을 만듭니다.
> - UI를 데이터에 바인딩하여 데이터에서 UI를 채우고 데이터와 UI를 동기화된 상태로 유지합니다.

자습서가 끝나면 사용자가 선택한 사용자에 대한 비용 보고서를 볼 수 있는 독립 실행형 Windows 응용 프로그램을 빌드했습니다. 응용 프로그램은 브라우저 스타일 창에서 호스팅되는 여러 WPF 페이지로 구성됩니다.

> [!TIP]
> 이 자습서에서 사용되는 샘플 코드는 [자습서 WPF 앱 샘플 코드에서](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)시각적 기본 및 C#에 사용할 수 있습니다.
>
> 이 페이지 위에 있는 언어 선택기를 사용하여 샘플 코드의 코드 언어를 C#과 Visual Basic 간에 전환할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

- **.NET 데스크톱 개발** 워크로드가 설치된 [Visual Studio 2019입니다.](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

   최신 버전의 Visual Studio 설치에 대한 자세한 내용은 [Visual Studio 설치를](/visualstudio/install/install-visual-studio)참조하십시오.

## <a name="create-the-application-project"></a>응용 프로그램 프로젝트 만들기

첫 번째 단계는 응용 프로그램 정의, 두 페이지 및 이미지를 포함하는 응용 프로그램 인프라를 만드는 것입니다.

1. 시각적 기본 또는 시각적 C #라는 이름의 **`ExpenseIt`** 새 WPF 응용 프로그램 프로젝트를 만듭니다.

   1. 비주얼 스튜디오를 열고 **시작** 메뉴에서 **새 프로젝트 만들기를** 선택합니다.

      **새 프로젝트 만들기** 대화 상자가 열립니다.

   2. **언어** 드롭다운에서 **C#** 또는 **시각적 기본**을 선택합니다.

   3. **WPF 앱(.NET 프레임워크)** 템플릿을 선택한 다음 을 **선택합니다.**

      ![새 프로젝트 만들기 대화 상자](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      **새 프로젝트 구성** 대화 상자가 열립니다.

   4. 프로젝트 이름을 **`ExpenseIt`** 입력한 다음 **만들기를**선택합니다.

      ![새 프로젝트 대화 상자 구성](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio에서 프로젝트를 만들고 **MainWindow.xaml**이라는 기본 응용 프로그램 창에 대 한 디자이너를 엽니다.

2. *응용 프로그램.xaml* (시각적 기본) 또는 *App.xaml* (C #)를 엽니 다.

    이 XAML 파일은 WPF 응용 프로그램 및 모든 응용 프로그램 리소스를 정의합니다. 또한 이 파일을 사용하여 응용 프로그램이 시작될 때 자동으로 표시되는 이 경우 *MainWindow.xaml을*지정합니다.

    XAML은 시각적 기본에서 다음과 같이 되어야 합니다.

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    그리고 C #의 다음과 같습니다.

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. *오픈 메인윈도우.xaml*.

    이 XAML 파일은 응용 프로그램의 기본 창이며 페이지에서 만든 콘텐츠를 표시합니다. 클래스는 <xref:System.Windows.Window> 제목, 크기 또는 아이콘과 같은 창의 속성을 정의하고 닫거나 숨기는 등의 이벤트를 처리합니다.

4. 다음 <xref:System.Windows.Window> XAML에 표시된 대로 요소를 <xref:System.Windows.Navigation.NavigationWindow>로 변경합니다.

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   이 응용 프로그램은 사용자 입력에 따라 다른 콘텐츠로 이동합니다. 이것이 주 <xref:System.Windows.Window> 를 로 변경해야 <xref:System.Windows.Navigation.NavigationWindow>하는 이유입니다. <xref:System.Windows.Navigation.NavigationWindow>의 <xref:System.Windows.Window>모든 속성을 상속합니다. XAML 파일의 <xref:System.Windows.Navigation.NavigationWindow> 요소는 클래스의 인스턴스를 <xref:System.Windows.Navigation.NavigationWindow> 만듭니다. 자세한 내용은 [탐색 개요를](../app-development/navigation-overview.md)참조하십시오.

5. <xref:System.Windows.Navigation.NavigationWindow> 태그 사이에서 <xref:System.Windows.Controls.Grid> 요소를 제거합니다.

6. 요소에 대한 XAML 코드의 다음 <xref:System.Windows.Navigation.NavigationWindow> 속성을 변경합니다.

    - <xref:System.Windows.Window.Title%2A> 속성을 "로`ExpenseIt`설정합니다.

    - <xref:System.Windows.FrameworkElement.Height%2A> 속성을 350픽셀로 설정합니다.

    - <xref:System.Windows.FrameworkElement.Width%2A> 속성을 500픽셀로 설정합니다.

    XAML은 시각적 기본에 대해 다음과 같이 만들어야 합니다.

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    그리고 C #에 대한 다음처럼 :

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. *메인윈도우.xaml.vb* 또는 *MainWindow.xaml.cs.*

    이 파일은 *MainWindow.xaml*에서 선언 된 이벤트를 처리하는 코드를 포함하는 코드 숨은 파일입니다. 이 파일에는 XAML에 정의된 창의 부분 클래스가 포함되어 있습니다.

8. C#을 사용하는 경우 `MainWindow` 에서 파생되는 클래스를 변경합니다. <xref:System.Windows.Navigation.NavigationWindow> 시각적 기본에서 XAML에서 창을 변경할 때 자동으로 발생 합니다. 이제 C# 코드는 다음과 같이 표시됩니다.

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>응용 프로그램에 파일 추가

이 섹션에서는 애플리케이션에 두 페이지와 이미지를 추가합니다.

1. 프로젝트에 새 페이지를 추가하고 이름을 지정합니다. *`ExpenseItHome.xaml`*

   1. **솔루션 탐색기에서**프로젝트 노드를 **`ExpenseIt`** 마우스 오른쪽 단추로 클릭하고**페이지** **추가를** > 선택합니다.

   1. 새 **항목 추가** 대화 상자에서 **페이지(WPF)** 템플릿이 이미 선택되었습니다. 이름을 **`ExpenseItHome`** 입력한 다음 **에 추가를**선택합니다.

    이 페이지는 응용 프로그램을 시작할 때 표시되는 첫 번째 페이지입니다. 비용 보고서를 표시하기 위해 선택할 수 있는 사용자 목록이 표시됩니다.

1. 을 *`ExpenseItHome.xaml`* 엽니다.

1. <xref:System.Windows.Controls.Page.Title%2A> "를`ExpenseIt - Home`"로 설정합니다.

1. `DesignHeight` 350픽셀과 `DesignWidth` 500픽셀로 설정합니다.

    이제 XAML이 시각적 기본에 대해 다음과 같이 표시됩니다.

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    그리고 C #에 대한 다음처럼 :

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. *오픈 메인윈도우.xaml*.

1. 요소에 속성을 추가하고 ""로`ExpenseItHome.xaml`설정합니다. <xref:System.Windows.Navigation.NavigationWindow.Source%2A> <xref:System.Windows.Navigation.NavigationWindow>

    이 *`ExpenseItHome.xaml`* 설정은 응용 프로그램이 시작될 때 열리는 첫 번째 페이지로 설정됩니다.

    시각적 기본의 예제 XAML:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    그리고 C #에서 :

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > 속성 **창의** **기타** 범주에서 **소스** 속성을 설정할 수도 있습니다.
   >
   > ![속성 창의 소스 속성](./media/properties-source.png)

1. 프로젝트에 다른 새 WPF 페이지를 추가하고 *ExpenseReportPage.xaml의*이름을 지정합니다.

   1. **솔루션 탐색기에서**프로젝트 노드를 **`ExpenseIt`** 마우스 오른쪽 단추로 클릭하고**페이지** **추가를** > 선택합니다.

   1. 새 **항목 추가** 대화 상자에서 **페이지(WPF)** 템플릿을 선택합니다. **비용 보고서 페이지**라는 이름을 입력한 다음 에 **추가를**선택합니다.

    이 페이지에는 **`ExpenseItHome`** 페이지에서 선택한 사람의 지출 보고서가 표시됩니다.

1. *ExpenseReportPage.xaml*을 엽니다.

1. <xref:System.Windows.Controls.Page.Title%2A> "를`ExpenseIt - View Expense`"로 설정합니다.

1. `DesignHeight` 350픽셀과 `DesignWidth` 500픽셀로 설정합니다.

    *이제 지출 보고서Page.xaml은* 시각적 기본에서 다음과 같이 표시됩니다.

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    그리고 C #의 다음과 같습니다.

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. 오픈 *ExpenseItHome.xaml.vb* 및 *비용 보고서Page.xaml.vb,* 또는 *ExpenseItHome.xaml.cs* *및 ExpenseReportPage.xaml.cs*.

    새 페이지 파일을 만들 면 Visual Studio에서 *자동으로 코드 숨 파일이* 만들어집니다. 이러한 코드 숨김 파일은 사용자 입력에 응답하기 위한 논리를 처리합니다.

    코드는 **`ExpenseItHome`** 다음과 같아야 합니다.

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    그리고 **비용 보고서 페이지에**대한 다음과 같은 :

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. 프로젝트에 *watermark.png라는* 이미지를 추가합니다. 사용자 고유의 이미지를 만들거나 샘플 코드에서 파일을 복사하거나 [microsoft/WPF-샘플](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub 리포지토리에서 다운로드할 수 있습니다.

    1. 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고**기존 항목** **추가를** > 선택하거나 **Shift**+**Alt**+**A를**누릅니다.

    2. 기존 **항목 추가** 대화 상자에서 파일 필터를 **모든 파일** 또는 **이미지 파일로**설정하고 사용할 이미지 파일로 찾아이동한 다음 **추가를**선택합니다.

## <a name="build-and-run-the-application"></a>애플리케이션 빌드 및 실행

1. 응용 프로그램을 빌드하고 실행하려면 **F5를** 누르거나 **디버그** 메뉴에서 **디버깅 시작을** 선택합니다.

    다음 그림에서는 <xref:System.Windows.Navigation.NavigationWindow> 단추를 가진 응용 프로그램을 보여 주며 있습니다.

    ![빌드하고 실행한 후 응용 프로그램.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. 응용 프로그램을 닫아 Visual Studio로 돌아갑니다.

## <a name="create-the-layout"></a>레이아웃 만들기

레이아웃은 UI 요소를 배치하는 순서가 정해된 방법을 제공하며 UI의 크기를 조정할 때 해당 요소의 크기와 위치도 관리합니다. 일반적으로 다음 레이아웃 컨트롤 중 하나를 사용하여 레이아웃을 만듭니다.

- <xref:System.Windows.Controls.Canvas>- 캔버스 영역을 기준으로 한 좌표를 사용하여 자식 요소를 명시적으로 배치할 수 있는 영역을 정의합니다.
- <xref:System.Windows.Controls.DockPanel>- 서로 에 대해 가로 또는 세로로 자식 요소를 정렬 할 수있는 영역을 정의합니다.
- <xref:System.Windows.Controls.Grid>- 열과 행으로 구성된 유연한 그리드 영역을 정의합니다.
- <xref:System.Windows.Controls.StackPanel>- 자식 요소를 가로 또는 세로로 향할 수 있는 한 줄로 정렬합니다.
- <xref:System.Windows.Controls.VirtualizingStackPanel>- 수평 또는 수직 방향의 한 줄에 콘텐츠를 정렬하고 가상화합니다.
- <xref:System.Windows.Controls.WrapPanel>- 하위 요소를 왼쪽에서 오른쪽으로 순차적으로 배치하여 포함된 상자의 가장자리에 있는 다음 줄로 콘텐츠를 분리합니다. 후속 순서는 방향 속성의 값에 따라 위에서 아래로 또는 오른쪽에서 왼쪽으로 순차적으로 수행됩니다.

이러한 각 레이아웃 컨트롤은 자식 요소에 대한 특정 유형의 레이아웃을 지원합니다. `ExpenseIt`페이지의 크기를 조정할 수 있으며 각 페이지에는 다른 요소와 함께 가로 및 세로로 정렬된 요소가 있습니다. 이 예제에서는 <xref:System.Windows.Controls.Grid> 응용 프로그램의 레이아웃 요소로 사용됩니다.

> [!TIP]
> 요소에 대한 <xref:System.Windows.Controls.Panel> 자세한 내용은 [패널 개요를](../controls/panels-overview.md)참조하십시오. 레이아웃에 대한 자세한 내용은 [레이아웃](../advanced/layout.md)을 참조하십시오.

이 섹션에서는 <xref:System.Windows.Controls.Grid> 에서 *`ExpenseItHome.xaml`* 열 및 행 정의를 추가하여 세 개의 행과 10픽셀 여백이 있는 단일 열 테이블을 만듭니다.

1. 에서 *`ExpenseItHome.xaml`* 요소의 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Grid> 속성을 왼쪽, 위쪽, 오른쪽 및 아래쪽 여백에 해당하는 "10,0,10,10"으로 설정합니다.

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > **레이아웃** 범주에서 **속성** 창에서 **여백** 값을 설정할 수도 있습니다.
   >
   > ![속성 창의 여백 값](./media/properties-margin.png)

2. 태그 사이에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가하여 행 및 열 정의를 만듭니다.

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    두 <xref:System.Windows.Controls.RowDefinition.Height%2A> 행 중 의 <xref:System.Windows.GridLength.Auto%2A>집합은 행의 내용에 따라 행의 크기가 조정됩니다. <xref:System.Windows.Controls.RowDefinition.Height%2A> 기본값은 <xref:System.Windows.GridUnitType.Star> 크기 조정이며, 이는 행 높이가 사용 가능한 공간의 가중치 비율임을 의미합니다. 예를 들어 두 행에 <xref:System.Windows.Controls.RowDefinition.Height%2A> 각각 "*"가 있는 경우 각각 사용 가능한 공간의 절반인 높이가 있습니다.

    이제 <xref:System.Windows.Controls.Grid> 다음 XAML이 포함되어야 합니다.

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>컨트롤 추가

이 섹션에서는 홈 페이지 UI를 업데이트하여 지출 보고서를 표시할 사람을 한 사람을 선택하는 사람 목록을 표시합니다. 컨트롤은 사용자가 애플리케이션과 상호 작용할 수 있게 하는 UI 개체입니다. 자세한 내용은 [컨트롤](../controls/index.md)을 참조하십시오.

이 UI를 만들려면 다음 요소를 추가합니다. *`ExpenseItHome.xaml`*

- A(사람 <xref:System.Windows.Controls.ListBox> 목록)입니다.
- A(목록 <xref:System.Windows.Controls.Label> 헤더용)입니다.
- A(목록에서 <xref:System.Windows.Controls.Button> 선택한 사람의 지출 보고서를 보려면 클릭합니다).

각 컨트롤은 연결된 속성을 <xref:System.Windows.Controls.Grid> 설정하여 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 의 행에 배치됩니다. 연결된 속성에 대한 자세한 내용은 [연결된 속성 개요를](../advanced/attached-properties-overview.md)참조하십시오.

1. 에서 *`ExpenseItHome.xaml`* 태그 사이의 어딘가에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가합니다.

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > **도구 상자** 창에서 디자인 창으로 드래그한 다음 **속성** 창에서 해당 속성을 설정하여 컨트롤을 만들 수도 있습니다.

2. 애플리케이션을 빌드 및 실행합니다.

    다음 그림에서는 만든 컨트롤을 보여 주며,

![비용그것은 이름 목록을 표시하는 샘플 스크린 샷](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>이미지 및 제목 추가

이 섹션에서는 이미지와 페이지 제목으로 홈 페이지 UI를 업데이트합니다.

1. 에서 *`ExpenseItHome.xaml`* 230픽셀로 <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> 고정된 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 다른 열을 추가합니다.

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <xref:System.Windows.Controls.Grid.RowDefinitions%2A>에 다른 행을 추가하여 총 4개의 행을 추가합니다.

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. 세 가지 컨트롤(테두리, ListBox 및 단추)에서 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성을 1로 설정하여 컨트롤을 두 번째 열로 이동합니다.

4. 세 컨트롤(테두리, ListBox 및 <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> Button) 및 테두리 요소에 대해 각 컨트롤의 값을 1씩 증가시켜 각 컨트롤을 행 아래로 이동합니다.

   이제 세 컨트롤에 대한 XAML은 다음과 같습니다.

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. 다음 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> XAML을 태그와 `</Grid>` 태그 사이에 추가하여 다음 XAML을 `<Grid>` 추가하여 *filemark.png* 이미지 파일로 속성을 설정합니다.

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. 요소 <xref:System.Windows.Controls.Border> 앞에 "비용 <xref:System.Windows.Controls.Label> 보고서 보기"라는 내용과 함께 a를 추가합니다. 이 레이블은 페이지의 제목입니다.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. 애플리케이션을 빌드 및 실행합니다.

다음 그림에서는 방금 추가한 내용의 결과를 보여 주며,

![ExpenseIt 샘플 스크린샷으로 새 이미지 배경 및 페이지 제목 표시](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>이벤트를 처리하는 코드 추가

1. 에서 *`ExpenseItHome.xaml`* 요소에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 추가합니다. <xref:System.Windows.Controls.Button> 자세한 내용은 [방법: 간단한 이벤트 처리기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))를 참조하십시오.

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. 열기 *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* 또는 .

3. `ExpenseItHome` 클래스에 다음 코드를 추가하여 단추 클릭 이벤트 처리기를 추가합니다. 이벤트 처리기가 **비용 보고서 페이지** 페이지를 엽니다.

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>비용 보고서 페이지에 대한 UI 만들기

*비용 보고서Page.xaml* **`ExpenseItHome`** 페이지에서 선택한 사람에 대 한 비용 보고서를 표시 합니다. 이 섹션에서는 **비용 보고서 페이지에**대한 UI를 만듭니다. 또한 다양한 UI 요소에 배경 및 채우기 색상을 추가합니다.

1. *ExpenseReportPage.xaml*을 엽니다.

2. 태그 사이에 다음 XAML을 <xref:System.Windows.Controls.Grid> 추가합니다.

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    이 UI는 *`ExpenseItHome.xaml`* 에 표시된 보고서 데이터를 제외하면 와 <xref:System.Windows.Controls.DataGrid>유사합니다.

3. 애플리케이션을 빌드 및 실행합니다.

4. 보기 단추를 **선택합니다.**

    경비 보고서 페이지가 나타납니다. 또한 뒤로 탐색 버튼이 활성화되어 있습니다.

다음 그림에서는 *ExpenseReportPage.xaml에*추가된 UI 요소를 보여 주어집니다.

![ExpenseIt 방금 비용 보고서 페이지에 대해 만든 UI를 보여주는 샘플 스크린샷입니다.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>스타일 컨트롤

다양한 요소의 모양은 UI에서 동일한 형식의 모든 요소에 대해 동일합니다. UI는 [스타일을](../../../desktop-wpf/fundamentals/styles-templates-overview.md) 사용하여 여러 요소에서 모양을 재사용할 수 있도록 합니다. 스타일 재사용성은 XAML 생성 및 관리를 단순화하는 데 도움이 됩니다. 이 섹션에서는 이전 단계에서 정의된 요소별 특성을 스타일로 바꿉니다.

1. *응용 프로그램.xaml* 또는 *App.xaml을*엽니 다.

2. 태그 사이에 다음 XAML을 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 추가합니다.

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    이 XAML은 다음 스타일을 추가합니다.

    - `headerTextStyle`: 페이지 제목 <xref:System.Windows.Controls.Label>의 형식을 지정합니다.

    - `labelStyle`: <xref:System.Windows.Controls.Label> 컨트롤의 형식을 지정합니다.

    - `columnHeaderStyle`: <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>의 형식을 지정합니다.

    - `listHeaderStyle`: 목록 헤더 <xref:System.Windows.Controls.Border> 컨트롤의 형식을 지정합니다.

    - `listHeaderTextStyle`: 목록 헤더의 <xref:System.Windows.Controls.Label>서식을 지정하려면 .

    - `buttonStyle`: 에 `ExpenseItHome.xaml` <xref:System.Windows.Controls.Button> 서식을 지정하려면 .

    스타일은 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 속성 요소의 리소스 및 자식입니다. 이 위치에서 스타일은 애플리케이션의 모든 요소에 적용됩니다. .NET 앱에서 리소스를 사용하는 예는 [응용 프로그램 리소스 사용을](../advanced/how-to-use-application-resources.md)참조하십시오.

3. 에서 *`ExpenseItHome.xaml`* <xref:System.Windows.Controls.Grid> 요소 간의 모든 것을 다음 XAML로 바꿉꿉입니다.

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    스타일을 적용하면 각 컨트롤의 모양을 정의하는 <xref:System.Windows.VerticalAlignment> 및 <xref:System.Windows.Media.FontFamily> 와 같은 속성이 제거되고 바뀝니다. 예를 들어"비용 `headerTextStyle` 보고서 보기"에 <xref:System.Windows.Controls.Label>적용됩니다.

4. *ExpenseReportPage.xaml*을 엽니다.

5. <xref:System.Windows.Controls.Grid> 요소 간의 모든 것을 다음 XAML로 바꿉꿉입니다.

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    이 XAML은 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.Border> 요소에 스타일을 추가합니다.

6. 애플리케이션을 빌드 및 실행합니다. 창 모양은 이전과 동일합니다.

    ![ExpenseIt 샘플 스크린샷은 마지막 섹션과 동일한 모양을 가지고 있습니다.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. 응용 프로그램을 닫아 Visual Studio로 돌아갑니다.

## <a name="bind-data-to-a-control"></a>데이터를 컨트롤에 바인딩합니다.

이 섹션에서는 다양한 컨트롤에 바인딩된 XML 데이터를 만듭니다.

1. 에서 *`ExpenseItHome.xaml`* 열기 <xref:System.Windows.Controls.Grid> 요소 후 다음 XAML을 추가하여 <xref:System.Windows.Data.XmlDataProvider> 각 사용자의 데이터를 포함하는 을 만듭니다.

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    데이터는 리소스로 <xref:System.Windows.Controls.Grid> 만들어집니다. 일반적으로 이 데이터는 파일로 로드되지만 간단히 하기 위해 데이터가 인라인으로 추가됩니다.

2. `<Grid.Resources>` 요소 내에서 다음 `<xref:System.Windows.DataTemplate>` 요소를 추가하여 요소 다음에 데이터를 <xref:System.Windows.Controls.ListBox>표시하는 방법을 정의합니다. `<XmlDataProvider>`

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요를](../data/data-templating-overview.md)참조하십시오.

3. 기존 <xref:System.Windows.Controls.ListBox> XAML을 다음 XAML로 바꿉꿉입니다.

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    이 XAML은 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 <xref:System.Windows.Controls.ListBox> 데이터 원본에 바인딩하고 데이터 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>템플릿을 으로 적용합니다.

## <a name="connect-data-to-controls"></a>데이터를 컨트롤에 연결

다음으로 페이지에서 선택한 **`ExpenseItHome`** 이름을 검색하고 **ExpenseReportPage의**생성자에게 전달하는 코드를 추가합니다. **ExpenseReportPage는** *ExpenseReportPage.xaml에* 바인딩하는 컨트롤인 전달된 항목으로 데이터 컨텍스트를 설정합니다.

1. 비용 *보고서 열기페이지.xaml.vb* 또는 *ExpenseReportPage.xaml.cs*.

2. 선택한 사람의 비용 보고서 데이터를 전달할 수 있도록 개체를 사용하는 생성자를 추가합니다.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. 열기 *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* 또는 .

4. <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 변경하여 선택한 사람의 비용 보고서 데이터를 전달하는 새 생성자를 호출합니다.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>데이터 템플릿으로 데이터 스타일

이 섹션에서는 데이터 템플릿을 사용하여 데이터 바인딩 된 목록의 각 항목에 대한 UI를 업데이트합니다.

1. *ExpenseReportPage.xaml*을 엽니다.

2. "이름" 및 "Department" <xref:System.Windows.Controls.Label> 요소의 내용을 적절한 데이터 원본 속성에 바인딩합니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. 열기 <xref:System.Windows.Controls.Grid> 요소 후 비용 보고서 데이터를 표시 하는 방법을 정의 하는 다음 데이터 템플릿을 추가 합니다.

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <xref:System.Windows.Controls.DataGridTextColumn> 요소를 <xref:System.Windows.Controls.DataGrid> 요소 아래에 있는 요소로 <xref:System.Windows.Controls.DataGridTemplateColumn> 바꾸고 템플릿을 적용합니다.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. 애플리케이션을 빌드 및 실행합니다.

6. 사람을 선택한 다음 **보기** 단추를 선택합니다.

다음 그림에서는 컨트롤, `ExpenseIt` 레이아웃, 스타일, 데이터 바인딩 및 데이터 템플릿이 적용된 응용 프로그램의 두 페이지를 보여 주었습니다.

![이름 목록과 비용 보고서를 표시하는 앱의 두 페이지.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> 이 샘플에서는 WPF의 특정 기능을 보여 주며 보안, 지역화 및 접근성과 같은 모든 모범 사례를 따르지 않습니다. WPF 및 .NET 앱 개발 모범 사례에 대한 포괄적인 내용은 다음 항목을 참조하십시오.
>
> - [액세스 가능성](../../ui-automation/accessibility-best-practices.md)
> - [보안](../security-wpf.md)
> - [WPF 전역화 및 지역화](../advanced/wpf-globalization-and-localization-overview.md)
> - [WPF 성능](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>다음 단계

이 연습에서는 WPF(Windows 프레젠테이션 파운데이션)를 사용하여 UI를 만드는 여러 가지 기술을 배웠습니다. 이제 데이터 바인딩 .NET 앱의 구성 요소를 기본적으로 이해해야 합니다. WPF 아키텍처 및 프로그래밍 모델에 대한 자세한 내용은 다음 항목을 참조하세요.

- [WPF 아키텍처](../advanced/wpf-architecture.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [종속성 속성 개요](../advanced/dependency-properties-overview.md)
- [레이아웃](../advanced/layout.md)

애플리케이션을 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

- [애플리케이션 개발](../app-development/index.md)
- [컨트롤](../controls/index.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [그래픽 및 멀티미디어](../graphics-multimedia/index.md)
- [WPF의 문서](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>참고 항목

- [패널 개요](../controls/panels-overview.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [WPF 응용 프로그램 빌드](../app-development/building-a-wpf-application-wpf.md)
- [스타일 및 템플릿](../controls/styles-and-templates.md)
