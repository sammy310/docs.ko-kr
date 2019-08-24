---
title: '연습: 첫 번째 터치 애플리케이션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: a915b8e238550eb3d9c1bcbe72d0d05a83a8312c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605802"
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="01a47-102">연습: 첫 번째 터치 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="01a47-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="01a47-103">응용 프로그램이 터치에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-103">enables applications to respond to touch.</span></span> <span data-ttu-id="01a47-104">예를 들어, 하나를 사용 하 여 응용 프로그램을 조작할 수 있습니다 또는이 연습에서는 사용자가 이동할 수 있는 응용 프로그램을 만듭니다 원하는 터치 스크린과 같은 터치 감지 장치에서 손가락을 크기를 조정 하거나 터치를 사용 하 여 단일 개체를 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01a47-105">전제 조건</span><span class="sxs-lookup"><span data-stu-id="01a47-105">Prerequisites</span></span>  
 <span data-ttu-id="01a47-106">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-106">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="01a47-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="01a47-107">Visual Studio.</span></span>  
  
- <span data-ttu-id="01a47-108">Windows Touch를 지 원하는 터치 스크린과 같은 터치식 입력을 허용 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-108">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="01a47-109">또한 응용 프로그램을 만드는 방법의 기본적인 이해를 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 특히 구독 하 고 이벤트를 처리 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-109">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="01a47-110">자세한 내용은 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-110">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="01a47-111">애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="01a47-111">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="01a47-112">애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="01a47-112">To create the application</span></span>  
  
1. <span data-ttu-id="01a47-113">Visual Basic 또는 Visual C#에서 `BasicManipulation`이라는 새 WPF 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-113">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="01a47-114">자세한 내용은 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-114">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
2. <span data-ttu-id="01a47-115">MainWindow.xaml의 내용을 다음 XAML을 사용 하 여 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-115">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="01a47-116">이 태그는 빨간색을 포함 하는 간단한 응용 프로그램을 만듭니다 <xref:System.Windows.Shapes.Rectangle> 에 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-116">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="01a47-117">합니다 <xref:System.Windows.UIElement.IsManipulationEnabled%2A> 의 속성을 <xref:System.Windows.Shapes.Rectangle> 조작 이벤트를 받을 수 있도록 true로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-117">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="01a47-118">응용 프로그램을 등록 합니다 <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, 및 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-118">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="01a47-119">이동 논리를 포함 하는 이러한 이벤트는 <xref:System.Windows.Shapes.Rectangle> 사용자 조작 경우.</span><span class="sxs-lookup"><span data-stu-id="01a47-119">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3. <span data-ttu-id="01a47-120">Visual Basic의 경우 MainWindow.xaml의 첫 번째 줄을 사용 하는 경우 대체 `x:Class="BasicManipulation.MainWindow"` 사용 하 여 `x:Class="MainWindow"`입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-120">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4. <span data-ttu-id="01a47-121">에 `MainWindow` 클래스를 다음 추가 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-121">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="01a47-122">합니다 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트가 발생할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 터치 감지 입력 개체를 조작 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-122">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="01a47-123">코드는 조작의 위치를 기준으로 하도록 지정 합니다 <xref:System.Windows.Window> 설정 하 여는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-123">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5. <span data-ttu-id="01a47-124">에 `MainWindow` 클래스를 다음 추가 <xref:System.Windows.Input.ManipulationDelta> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-124">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>

     <span data-ttu-id="01a47-125"><xref:System.Windows.Input.ManipulationDelta> 이벤트 발생 터치 입력 위치를 변경 하 고 조작 하는 동안 여러 번 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-125">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="01a47-126">이벤트는 손가락 발생 한 후에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-126">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="01a47-127">예를 들어, 사용자가 화면에서 손가락을 끌 경우는 <xref:System.Windows.Input.ManipulationDelta> 이벤트 손가락 이동으로 여러 번 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-127">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="01a47-128">화면에서 손가락을 움직일 때의 <xref:System.Windows.Input.ManipulationDelta> 관성을 시뮬레이션 하기 위해 이벤트가 계속 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-128">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>

     <span data-ttu-id="01a47-129">적용 되는 코드를 <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 의 <xref:System.Windows.Shapes.Rectangle> 는 사용자가 터치 이동 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-129">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="01a47-130">또한 확인 여부를 <xref:System.Windows.Shapes.Rectangle> 의 범위를 벗어납니다를 <xref:System.Windows.Window> 관성 도중 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-130">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="01a47-131">따라서 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> 조작을 종료 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-131">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>

     [!code-csharp[BasicManipulation#ManipulationDelta](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6. <span data-ttu-id="01a47-132">에 `MainWindow` 클래스를 다음 추가 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-132">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>

     <span data-ttu-id="01a47-133"><xref:System.Windows.UIElement.ManipulationInertiaStarting> 사용자 화면에서 손가락을 모두 발생 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-133">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="01a47-134">코드에는 초기 속도 및 이동, 확장 및 회전 사각형의 감속을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-134">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7. <span data-ttu-id="01a47-135">프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-135">Build and run the project.</span></span>

     <span data-ttu-id="01a47-136">창에 나타나는 빨간색 사각형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-136">You should see a red square appear in the window.</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="01a47-137">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="01a47-137">Testing the Application</span></span>
 <span data-ttu-id="01a47-138">응용 프로그램을 테스트 하려면 다음 조작을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-138">To test the application, try the following manipulations.</span></span> <span data-ttu-id="01a47-139">동시에 다음 중 하나 이상 수행할 수 있습니다 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-139">Note that you can do more than one of the following at the same time.</span></span>

- <span data-ttu-id="01a47-140">이동 하는 <xref:System.Windows.Shapes.Rectangle>, 위에 손가락을 놓고는 <xref:System.Windows.Shapes.Rectangle> 화면에서 손가락을 이동 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-140">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>

- <span data-ttu-id="01a47-141">크기를 조정 하려면 합니다 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치를 <xref:System.Windows.Shapes.Rectangle> 더 가깝게 또는 멀리 움직여 다른 손가락 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-141">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>

- <span data-ttu-id="01a47-142">회전 하는 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치 합니다 <xref:System.Windows.Shapes.Rectangle> 손가락을 서로 회전 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-142">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>

 <span data-ttu-id="01a47-143">관성 시킬 이전 조작을 수행 하면 화면에서 손가락을 발생 신속 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-143">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="01a47-144"><xref:System.Windows.Shapes.Rectangle> 이동, 크기 조정 또는 중지 하기 전에 몇 초간 회전 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a47-144">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>

## <a name="see-also"></a><span data-ttu-id="01a47-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="01a47-145">See also</span></span>

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>