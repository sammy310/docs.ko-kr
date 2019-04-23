---
title: InkCanvas Visual Studio에서 WPF 앱에서 만들기
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: 4309b1108b2ea96eb298ff3bb876a0f63b80dc32
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343599"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="6c575-102">Wpf에서 잉크 시작</span><span class="sxs-lookup"><span data-stu-id="6c575-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="6c575-103">Windows Presentation Foundation (WPF)에 쉽게 앱에 디지털 잉크를 통합 하는 잉크 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c575-104">전제 조건</span><span class="sxs-lookup"><span data-stu-id="6c575-104">Prerequisites</span></span>

<span data-ttu-id="6c575-105">다음 예제를 사용 하려면 먼저 설치 [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-105">To use the following examples, first install [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="6c575-106">또한 기본 WPF 앱을 작성 하는 방법을 알면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="6c575-107">WPF 시작 도움말을 참조 하세요. [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="6c575-108">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="6c575-108">Quick Start</span></span>

<span data-ttu-id="6c575-109">이 섹션에서는 잉크를 수집 하는 간단한 WPF 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="6c575-110">잉크 사용</span><span class="sxs-lookup"><span data-stu-id="6c575-110">Got Ink?</span></span>

<span data-ttu-id="6c575-111">잉크를 지 원하는 WPF 앱을 만들려면:</span><span class="sxs-lookup"><span data-stu-id="6c575-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="6c575-112">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="6c575-113">새 **WPF 앱**합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="6c575-114">에 **새 프로젝트** 대화 상자에서 확장 된 **설치 됨** > **Visual C#** 또는 **Visual Basic**  >   **Windows 데스크톱** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="6c575-115">다음을 선택 합니다 **WPF 앱 (.NET Framework)** 앱 템플릿.</span><span class="sxs-lookup"><span data-stu-id="6c575-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="6c575-116">이름을 입력 하 고 선택한 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="6c575-117">Visual Studio는 프로젝트를 만듭니다. 및 *MainWindow.xaml* 디자이너에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="6c575-118">형식 `<InkCanvas/>` 간에 `<Grid>` 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![InkCanvas 태그를 사용 하 여 XAML 디자이너](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="6c575-120">키를 눌러 **F5** 디버거에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="6c575-121">스타일러스 또는 마우스를 사용 하 여, 작성할 **hello world** 창의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="6c575-122">잉크에 해당 하는 12 키 입력을 사용 하 여 "hello world" 응용 프로그램을 작성 했습니다!</span><span class="sxs-lookup"><span data-stu-id="6c575-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="6c575-123">앱 꾸미기</span><span class="sxs-lookup"><span data-stu-id="6c575-123">Spice Up Your App</span></span>

<span data-ttu-id="6c575-124">WPF의 일부 기능을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="6c575-125">열기 및 닫기 간의 대체 \<창 > 태그에 다음 태그를 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="6c575-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="6c575-126">이 XAML에 잉크 입력 기능 화면에서 배경이 그라데이션 브러시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF 앱에서 화면 잉크 입력에서 그라데이션 색](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="6c575-128">뒤에 XAML 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="6c575-129">XAML을 사용 하면 매우 쉽게 사용자 인터페이스를 디자인, 실제 응용 프로그램 이벤트를 처리 하는 코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="6c575-130">마우스의 응답을 마우스 오른쪽 단추로 클릭 하 여 잉크를 확대 하는 간단한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="6c575-131">설정 된 `MouseRightButtonUp` 처리기에 XAML에서:</span><span class="sxs-lookup"><span data-stu-id="6c575-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="6c575-132">**솔루션 탐색기**, MainWindow.xaml을 확장 하 고 (MainWindow.xaml.vb 또는 MainWindow.xaml.cs) 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="6c575-133">다음 이벤트 처리기 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="6c575-134">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-134">Run the application.</span></span> <span data-ttu-id="6c575-135">에 잉크를 일부 추가 마우스 오른쪽 단추로 클릭 또는 스타일러스를 사용 하 여 해당 하는 키를 눌러-대기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="6c575-136">마우스 오른쪽 단추로 클릭할 때마다 디스플레이 확대 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="6c575-137">XAML 대신 프로시저 코드 사용</span><span class="sxs-lookup"><span data-stu-id="6c575-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="6c575-138">프로시저 코드에서 모든 WPF 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="6c575-139">모든 XAML을 전혀 사용 하지 않는 WPF에 대 한 "Hello 잉크 World" 응용 프로그램을 만들려면 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="6c575-140">Visual Studio에서 새 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="6c575-141">에 **새 프로젝트** 대화 상자에서 확장 된 **설치 됨** > **Visual C#** 또는 **Visual Basic**  >   **Windows 데스크톱** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="6c575-142">다음을 선택 합니다 **콘솔 앱 (.NET Framework)** 앱 템플릿.</span><span class="sxs-lookup"><span data-stu-id="6c575-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="6c575-143">이름을 입력 하 고 선택한 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="6c575-144">Program.cs 또는 Program.vb 파일에 다음 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="6c575-145">마우스 오른쪽 단추로 클릭 하 여 PresentationCore, PresentationFramework, 및 WindowsBase 어셈블리에 대 한 참조를 추가 **참조가** 에 **솔루션 탐색기** 선택 하 고 **참조추가**.</span><span class="sxs-lookup"><span data-stu-id="6c575-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![참조 관리자 PresentationCore 및 PresentationFramework 표시](./media/getting-started-with-ink/references.png)

1. <span data-ttu-id="6c575-147">키를 눌러 응용 프로그램을 빌드합니다 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="6c575-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c575-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c575-148">See also</span></span>

- [<span data-ttu-id="6c575-149">디지털 잉크</span><span class="sxs-lookup"><span data-stu-id="6c575-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="6c575-150">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="6c575-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="6c575-151">필기 인식</span><span class="sxs-lookup"><span data-stu-id="6c575-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="6c575-152">잉크 저장</span><span class="sxs-lookup"><span data-stu-id="6c575-152">Storing Ink</span></span>](storing-ink.md)
