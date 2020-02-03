---
title: Visual Studio에서 InkCanvas 만들기
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737893"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="2495c-102">WPF에서 잉크 시작</span><span class="sxs-lookup"><span data-stu-id="2495c-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="2495c-103">WPF (Windows Presentation Foundation)에는 디지털 잉크를 앱에 쉽게 통합 하는 데 사용 되는 잉크 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2495c-104">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2495c-104">Prerequisites</span></span>

<span data-ttu-id="2495c-105">다음 예제를 사용 하려면 먼저 [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="2495c-106">또한 기본적인 WPF 앱을 작성 하는 방법을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="2495c-107">WPF 시작에 대 한 도움말은 [연습: 내 첫 wpf 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2495c-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="2495c-108">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="2495c-108">Quick Start</span></span>

<span data-ttu-id="2495c-109">이 섹션은 잉크를 수집 하는 간단한 WPF 응용 프로그램을 작성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="2495c-110">잉크가 있나요?</span><span class="sxs-lookup"><span data-stu-id="2495c-110">Got Ink?</span></span>

<span data-ttu-id="2495c-111">잉크를 지 원하는 WPF 앱을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="2495c-112">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="2495c-113">새 **WPF 앱**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="2495c-114">**새 프로젝트** 대화 상자에서 **설치** > **시각적 개체 C#**  또는 **Visual Basic** > **Windows Desktop** 범주를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="2495c-115">그런 다음 **WPF 앱 (.NET Framework)** 앱 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="2495c-116">이름을 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="2495c-117">Visual Studio에서 프로젝트가 만들어지고 디자이너에서 *mainwindow.xaml* 이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="2495c-118">`<Grid>` 태그 사이에 `<InkCanvas/>`을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![InkCanvas 태그를 사용 하는 XAML 디자이너](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="2495c-120">디버거에서 응용 프로그램을 시작 하려면 **f5** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="2495c-121">스타일러스 또는 마우스를 사용 하 여 창에서 **hello 세계** 를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="2495c-122">12 개의 키 입력만 있는 "hello 세계" 응용 프로그램에 해당 하는 잉크를 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="2495c-123">앱 꾸며보세요</span><span class="sxs-lookup"><span data-stu-id="2495c-123">Spice Up Your App</span></span>

<span data-ttu-id="2495c-124">WPF의 일부 기능을 활용 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="2495c-125">열기 및 닫기 \<> 창 사이의 모든 항목을 다음 태그로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="2495c-126">이 XAML은 잉크 화면에 그라데이션 브러시 배경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF 앱의 잉크 화면 그라데이션 색](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="2495c-128">XAML 뒤에 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="2495c-129">XAML을 사용 하면 사용자 인터페이스를 매우 쉽게 디자인할 수 있지만 실제 응용 프로그램은 이벤트를 처리 하는 코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="2495c-130">마우스 오른쪽 단추 클릭에 대 한 응답으로 잉크를 확대 하는 간단한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="2495c-131">XAML에서 `MouseRightButtonUp` 처리기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="2495c-132">**솔루션 탐색기**에서 mainwindow.xaml를 확장 하 고 코드 파일 (MainWindow.xaml.cs 또는 mainwindow.xaml)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="2495c-133">다음 이벤트 처리기 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="2495c-134">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-134">Run the application.</span></span> <span data-ttu-id="2495c-135">일부 잉크를 추가 하 고 마우스 오른쪽 단추를 클릭 하거나 스타일러스를 사용 하 여 선택 및 유지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="2495c-136">마우스 오른쪽 단추로 클릭할 때마다 디스플레이가 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="2495c-137">XAML 대신 절차적 코드 사용</span><span class="sxs-lookup"><span data-stu-id="2495c-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="2495c-138">절차적 코드에서 모든 WPF 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="2495c-139">XAML을 전혀 사용 하지 않는 WPF 용 "Hello Ink 세계" 응용 프로그램을 만들려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="2495c-140">Visual Studio에서 새 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="2495c-141">**새 프로젝트** 대화 상자에서 **설치** > **시각적 개체 C#**  또는 **Visual Basic** > **Windows Desktop** 범주를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="2495c-142">그런 다음 **콘솔 앱 (.NET Framework)** 앱 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="2495c-143">이름을 입력 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="2495c-144">Program.cs 또는 Program .vb 파일에 다음 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="2495c-145">**솔루션 탐색기** 에서 **참조** 를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 하 여 PresentationCore, PresentationFramework 및 windowsbase 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![PresentationCore 및 PresentationFramework를 보여 주는 참조 관리자](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="2495c-147">**F5**키를 눌러 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2495c-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2495c-148">See also</span></span>

- [<span data-ttu-id="2495c-149">디지털 잉크</span><span class="sxs-lookup"><span data-stu-id="2495c-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="2495c-150">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="2495c-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="2495c-151">필기 인식</span><span class="sxs-lookup"><span data-stu-id="2495c-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="2495c-152">잉크 저장</span><span class="sxs-lookup"><span data-stu-id="2495c-152">Storing Ink</span></span>](storing-ink.md)
