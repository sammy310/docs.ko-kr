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
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="a69f7-103">연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용</span><span class="sxs-lookup"><span data-stu-id="a69f7-103">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="a69f7-104">이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송에 참가할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-104">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="a69f7-105">이 연습에서는 circle 셰이프를 나타내는 사용자 지정 WPF를 만듭니다 <xref:System.Windows.Controls.UserControl> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-105">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="a69f7-106">컨트롤에서 끌어서 놓기를 통해 데이터 전송을 활성화하는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-106">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="a69f7-107">예를 들어 한 원 컨트롤에서 다른 원 컨트롤로 끌면 채우기 색 데이터가 소스 원에서 대상 원으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-107">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="a69f7-108">원 컨트롤에서로 끌어 오면 <xref:System.Windows.Controls.TextBox> 채우기 색의 문자열 표현이에 복사 됩니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-108">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a69f7-109">또한 두 개의 패널 컨트롤과를 포함 하는 작은 응용 프로그램을 만들어 <xref:System.Windows.Controls.TextBox> 끌어서 놓기 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-109">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="a69f7-110">패널이 끌어 놓은 원 데이터를 처리하여 한 패널의 자식 컬렉션에서 다른 패널로 원을 이동하거나 복사할 수 있도록 하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-110">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="a69f7-111">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-111">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="a69f7-112">사용자 지정 사용자 정의 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="a69f7-112">Create a custom user control.</span></span>

- <span data-ttu-id="a69f7-113">사용자 정의 컨트롤을 끌기 소스로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a69f7-113">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="a69f7-114">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a69f7-114">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="a69f7-115">패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a69f7-115">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a69f7-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a69f7-116">Prerequisites</span></span>

<span data-ttu-id="a69f7-117">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-117">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="a69f7-118">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a69f7-118">Create the Application Project</span></span>
 <span data-ttu-id="a69f7-119">이 섹션에서는 두 개의 패널과를 사용 하는 기본 페이지를 포함 하는 응용 프로그램 인프라를 만듭니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="a69f7-120">Visual Basic 또는 Visual C#에서 `DragDropExample`이라는 새 WPF 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-120">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="a69f7-121">자세한 내용은 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a69f7-121">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="a69f7-122">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-122">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="a69f7-123">여는 태그와 닫는 태그 사이에 다음 태그를 추가 합니다 <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-123">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="a69f7-124">이 태그는 테스트 애플리케이션에 대한 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-124">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="a69f7-125">프로젝트에 새 사용자 정의 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a69f7-125">Add a New User Control to the Project</span></span>
 <span data-ttu-id="a69f7-126">이 섹션에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-126">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="a69f7-127">[프로젝트] 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-127">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="a69f7-128">**새 항목 추가** 대화 상자에서 이름을로 변경 하 `Circle.xaml` 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-128">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="a69f7-129">Circle.xaml과 해당 코드 숨김이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-129">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="a69f7-130">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-130">Open Circle.xaml.</span></span>

     <span data-ttu-id="a69f7-131">이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-131">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="a69f7-132">다음 태그를 루트에 추가 <xref:System.Windows.Controls.Grid> 하 여 파란색 원이 UI로 포함 된 간단한 사용자 정의 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-132">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="a69f7-133">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-133">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="a69f7-134">C #에서 매개 변수가 없는 생성자 뒤에 다음 코드를 추가 하 여 복사 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-134">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="a69f7-135">Visual Basic에서 다음 코드를 추가 하 여 매개 변수가 없는 생성자와 복사 생성자를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-135">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="a69f7-136">사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에서 복사 생성자 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-136">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="a69f7-137">간단한 원 사용자 정의 컨트롤에서 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-137">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="a69f7-138">주 창에 사용자 정의 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a69f7-138">Add the user control to the main window</span></span>

1. <span data-ttu-id="a69f7-139">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-139">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="a69f7-140">다음 XAML을 여는 태그에 추가 하 여 <xref:System.Windows.Window> 현재 응용 프로그램에 대 한 XML 네임 스페이스 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-140">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="a69f7-141">첫 번째에서 <xref:System.Windows.Controls.StackPanel> 다음 XAML을 추가 하 여 첫 번째 패널에서 Circle 사용자 정의 컨트롤의 두 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-141">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="a69f7-142">패널에 대한 전체 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-142">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="a69f7-143">사용자 정의 컨트롤에서 끌기 소스 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="a69f7-143">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="a69f7-144">이 섹션에서는 메서드를 재정의 <xref:System.Windows.UIElement.OnMouseMove%2A> 하 고 끌어서 놓기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-144">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="a69f7-145">마우스 단추를 누른 상태에서 마우스 단추를 누르면로 전송할 데이터를 패키지할 수 있습니다 <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-145">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a69f7-146">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-146">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="a69f7-147">끌어서 놓기 작업을 시작하려면</span><span class="sxs-lookup"><span data-stu-id="a69f7-147">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="a69f7-148">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-148">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a69f7-149">다음 재정의를 추가 <xref:System.Windows.UIElement.OnMouseMove%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.MouseMove> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-149">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="a69f7-150">이 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-150">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-151">마우스를 이동하는 동안 마우스 왼쪽 단추를 눌렀는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-151">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="a69f7-152">원 데이터를에 패키지 <xref:System.Windows.DataObject> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-152">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a69f7-153">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-153">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="a69f7-154">정적 메서드를 호출 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> 하 여 끌어서 놓기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-154">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="a69f7-155">메서드에 다음 세 개의 매개 변수를 전달 합니다 <xref:System.Windows.DragDrop.DoDragDrop%2A> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-155">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="a69f7-156">`dragSource` – 이 컨트롤에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-156">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="a69f7-157">`data`– <xref:System.Windows.DataObject> 이전 코드에서 만든입니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-157">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="a69f7-158">`allowedEffects`– 허용 된 끌어서 놓기 작업 ( <xref:System.Windows.DragDropEffects.Copy> 또는) <xref:System.Windows.DragDropEffects.Move> 입니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-158">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="a69f7-159">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-159">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a69f7-160">원 컨트롤 중 하나를 클릭 하 고 패널, 다른 원 및로 끕니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-160">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a69f7-161">위로 끌면 <xref:System.Windows.Controls.TextBox> 커서는 이동을 나타내기 위해 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-161">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="a69f7-162">위로 원을 끌어 오면 <xref:System.Windows.Controls.TextBox> **ctrl** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-162">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="a69f7-163">복사를 나타내기 위해 커서가 어떻게 변경되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-163">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="a69f7-164">원을로 끌어 놓습니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-164">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a69f7-165">원 채우기 색의 문자열 표현이에 추가 됩니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-165">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="a69f7-166">![원의 채우기 색에 대한 문자열 표현](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="a69f7-166">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="a69f7-167">기본적으로 커서는 끌어서 놓기 작업 중 데이터 놓기의 결과를 나타내도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-167">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="a69f7-168">이벤트를 처리 <xref:System.Windows.UIElement.GiveFeedback> 하 고 다른 커서를 설정 하 여 사용자에 게 제공 되는 피드백을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-168">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="a69f7-169">사용자에 게 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="a69f7-169">Give feedback to the user</span></span>

1. <span data-ttu-id="a69f7-170">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-170">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a69f7-171">다음 재정의를 추가 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.GiveFeedback> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-171">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="a69f7-172">이 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-172">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-173"><xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>놓기 대상의 이벤트 처리기에 설정 된 값을 확인 합니다 <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-173">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="a69f7-174">값을 기준으로 사용자 지정 커서를 설정 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-174">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="a69f7-175">커서는 데이터 놓기의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-175">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="a69f7-176">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-176">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a69f7-177">패널, 다른 원 및에서 원 컨트롤 중 하나를 끕니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-177">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a69f7-178">이제 커서는 재정의에서 지정한 사용자 지정 커서입니다 <xref:System.Windows.UIElement.OnGiveFeedback%2A> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-178">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="a69f7-179">![사용자 지정 커서로 끌어서 놓기](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="a69f7-179">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="a69f7-180">에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-180">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="a69f7-181">`green` 텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-181">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="a69f7-182">기본 커서가 끌어서 놓기 작업의 결과를 나타내도록 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-182">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="a69f7-183">피드백 커서는 항상 끌기 소스에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-183">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="a69f7-184">사용자 정의 컨트롤에서 놓기 대상 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="a69f7-184">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="a69f7-185">이 섹션에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하는 메서드를 재정의하며, 대상에 끌어 놓은 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-185">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="a69f7-186">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a69f7-186">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="a69f7-187">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-187">Open Circle.xaml.</span></span>

2. <span data-ttu-id="a69f7-188">여는 <xref:System.Windows.Controls.UserControl> 태그에서 속성을 추가 하 <xref:System.Windows.UIElement.AllowDrop%2A> 고로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-188">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="a69f7-189"><xref:System.Windows.UIElement.OnDrop%2A>메서드는 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이로 설정 되 `true` 고 끌기 소스의 데이터가 Circle 사용자 정의 컨트롤에 삭제 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-189">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="a69f7-190">이 메서드에서는 끌어 놓은 데이터를 처리하고 해당 데이터를 원에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-190">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="a69f7-191">끌어 놓은 데이터를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="a69f7-191">To process the dropped data</span></span>

1. <span data-ttu-id="a69f7-192">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-192">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a69f7-193">다음 재정의를 추가 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.Drop> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-193">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="a69f7-194">이 <xref:System.Windows.UIElement.OnDrop%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-194">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-195">메서드를 사용 하 여 <xref:System.Windows.DataObject.GetDataPresent%2A> 끌어 온 데이터에 문자열 개체가 포함 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-195">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="a69f7-196"><xref:System.Windows.DataObject.GetData%2A>문자열 데이터가 있는 경우 메서드를 사용 하 여 문자열 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-196">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="a69f7-197">는를 사용 하 여 문자열을로 <xref:System.Windows.Media.BrushConverter> 변환 <xref:System.Windows.Media.Brush> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-197">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="a69f7-198">변환이 성공 하면는 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> Circle 컨트롤의 UI를 제공 하는의에 브러시를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-198">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="a69f7-199">이벤트를 <xref:System.Windows.UIElement.Drop> 처리 된 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-199">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="a69f7-200">이 이벤트를 수신하는 다른 요소가 원 사용자 정의 컨트롤에서 해당 이벤트를 처리했음을 알 수 있도록 놓기 이벤트를 처리된 것으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-200">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="a69f7-201">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-201">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a69f7-202">에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-202">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="a69f7-203">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-203">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="a69f7-204">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-204">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="a69f7-205">![브러시로 문자열 변환](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="a69f7-205">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="a69f7-206">에 텍스트를 입력 합니다 `green` <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-206">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="a69f7-207">에서 텍스트를 선택 `gre` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-207">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="a69f7-208">이 텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-208">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="a69f7-209">놓기가 허용됨을 나타내도록 커서가 변경되지만 `gre`가 유효한 색이 아니기 때문에 원의 색은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-209">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="a69f7-210">녹색 원 컨트롤에서 끌어서 파란색 원 컨트롤에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-210">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="a69f7-211">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-211">The Circle changes from blue to green.</span></span> <span data-ttu-id="a69f7-212">표시 되는 커서는 <xref:System.Windows.Controls.TextBox> 또는 원이 끌기 소스 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-212">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="a69f7-213">속성을 <xref:System.Windows.UIElement.AllowDrop%2A> 로 설정 하 `true` 고 끌어 놓은 데이터를 처리 하는 것은 요소를 놓기 대상으로 설정 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-213">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="a69f7-214">그러나 더 나은 사용자 환경을 제공 하기 위해 <xref:System.Windows.UIElement.DragEnter> , 및 이벤트도 처리 해야 합니다 <xref:System.Windows.UIElement.DragLeave> <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-214">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="a69f7-215">이러한 이벤트에서 데이터를 놓기 전에 검사를 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-215">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="a69f7-216">데이터를 원 사용자 정의 컨트롤로 끌면 컨트롤에서 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-216">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="a69f7-217">컨트롤에서 데이터 처리 방법을 알지 못하는 경우 놓기를 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-217">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="a69f7-218">이렇게 하려면 이벤트를 처리 하 <xref:System.Windows.UIElement.DragOver> 고 속성을 설정 <xref:System.Windows.DragEventArgs.Effects%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-218">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="a69f7-219">데이터 놓기가 허용되는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a69f7-219">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="a69f7-220">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-220">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a69f7-221">다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragOver%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragOver> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-221">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="a69f7-222">이 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-222">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-223"><xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.None>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-223">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="a69f7-224">메서드에서 수행 하는 것과 동일한 검사를 수행 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 Circle 사용자 정의 컨트롤이 끌어 온 데이터를 처리할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-224">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="a69f7-225">사용자 정의 컨트롤에서 데이터를 처리할 수 있는 경우에는 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 또는로 설정 합니다 <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-225">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="a69f7-226">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-226">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a69f7-227">에서 텍스트를 선택 `gre` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-227">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="a69f7-228">텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-228">Drag the text to a Circle control.</span></span> <span data-ttu-id="a69f7-229">`gre`가 유효한 색이 아니므로 놓기가 허용되지 않음을 나타내도록 커서가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-229">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="a69f7-230">놓기 작업의 미리 보기를 적용하여 사용자 환경을 더욱 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-230">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="a69f7-231">Circle 사용자 정의 컨트롤의 경우 및 메서드를 재정의 <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-231">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="a69f7-232">컨트롤 위로 데이터를 끌면 현재 배경이 <xref:System.Windows.Shapes.Shape.Fill%2A> 자리 표시자 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-232">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="a69f7-233">그러면 문자열이 브러시로 변환 되 고 <xref:System.Windows.Shapes.Ellipse> 원의 UI를 제공 하는에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-233">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="a69f7-234">데이터를 삭제 하지 않고 원 밖으로 끌면 원래 <xref:System.Windows.Shapes.Shape.Fill%2A> 값이 원에 다시 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-234">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="a69f7-235">끌어서 놓기 작업의 결과를 미리 보려면</span><span class="sxs-lookup"><span data-stu-id="a69f7-235">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="a69f7-236">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-236">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a69f7-237">Circle 클래스에서 라는 private 변수를 선언 하 <xref:System.Windows.Media.Brush> `_previousFill` 고로 초기화 `null` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-237">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="a69f7-238">다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragEnter%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragEnter> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-238">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="a69f7-239">이 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-239">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-240"><xref:System.Windows.Shapes.Shape.Fill%2A>의 속성을 변수에 저장 합니다 <xref:System.Windows.Shapes.Ellipse> `_previousFill` .</span><span class="sxs-lookup"><span data-stu-id="a69f7-240">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="a69f7-241">메서드에서 수행 하는 것과 동일한 검사를 수행 <xref:System.Windows.UIElement.OnDrop%2A> 하 여 데이터를로 변환할 수 있는지 여부를 확인 합니다 <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-241">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="a69f7-242">데이터가 유효한으로 변환 되 면 <xref:System.Windows.Media.Brush> 이를의에 적용 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-242">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="a69f7-243">다음 재정의를 추가 <xref:System.Windows.UIElement.OnDragLeave%2A> 하 여 이벤트에 대 한 클래스 처리를 제공 <xref:System.Windows.UIElement.DragLeave> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-243">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="a69f7-244">이 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-244">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-245"><xref:System.Windows.Media.Brush> `_previousFill` <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> Circle 사용자 정의 컨트롤의 UI를 제공 하는의에 변수에 저장 된를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-245">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="a69f7-246">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-246">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="a69f7-247">에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-247">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="a69f7-248">텍스트를 놓지 않고 원 컨트롤 위로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-248">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="a69f7-249">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-249">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="a69f7-250">![&#45;&#45;끌어서 놓기 작업의 효과 미리 보기](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="a69f7-250">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="a69f7-251">원 컨트롤에서 멀리 텍스트를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-251">Drag the text away from the Circle control.</span></span> <span data-ttu-id="a69f7-252">원이 녹색에서 다시 파란색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-252">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="a69f7-253">패널에서 삭제 된 데이터를 받을 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a69f7-253">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="a69f7-254">이 섹션에서는 Circle 사용자 정의 컨트롤을 호스팅하는 패널을 끌어 끌어온 원 데이터의 놓기 대상 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-254">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="a69f7-255">한 패널에서 다른 패널로 원을 이동 하거나, **Ctrl** 키를 누른 채 원를 끌어서 놓는 방법으로 원 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-255">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="a69f7-256">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-256">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="a69f7-257">다음 XAML에 표시 된 것 처럼 각 <xref:System.Windows.Controls.StackPanel> 컨트롤에서 및 이벤트에 대 한 처리기를 <xref:System.Windows.UIElement.DragOver> 추가 <xref:System.Windows.UIElement.Drop> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-257">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="a69f7-258"><xref:System.Windows.UIElement.DragOver>이벤트 처리기의 이름을, `panel_DragOver` 및로 이벤트 처리기의 이름을로 <xref:System.Windows.UIElement.Drop> `panel_Drop` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-258">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="a69f7-259">MainWindows.xaml.cs 또는 MainWindow.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-259">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="a69f7-260">이벤트 처리기에 대 한 다음 코드를 추가 합니다 <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-260">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="a69f7-261">이 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-261">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-262"><xref:System.Windows.DataObject>원 사용자 정의 컨트롤에 의해 패키지 되 고에 대 한 호출에 전달 된 "개체" 데이터가 끌어온 데이터에 포함 되어 있는지 확인 <xref:System.Windows.DragDrop.DoDragDrop%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-262">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="a69f7-263">"Object" 데이터가 있는 경우 **Ctrl** 키를 눌렀는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-263">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="a69f7-264">**Ctrl** 키를 누르면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성이로 설정 <xref:System.Windows.DragDropEffects.Copy> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-264">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="a69f7-265">그렇지 않은 경우 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을로 설정 <xref:System.Windows.DragDropEffects.Move> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-265">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="a69f7-266">이벤트 처리기에 대 한 다음 코드를 추가 합니다 <xref:System.Windows.UIElement.Drop> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-266">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="a69f7-267">이 <xref:System.Windows.UIElement.Drop> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-267">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="a69f7-268">이벤트가 이미 처리 되었는지 여부를 확인 <xref:System.Windows.UIElement.Drop> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-268">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="a69f7-269">예를 들어, 이벤트를 처리 하는 다른 원에 원을 놓는 경우 <xref:System.Windows.UIElement.Drop> 원이 포함 된 패널에서 해당 원을 처리 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-269">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="a69f7-270"><xref:System.Windows.UIElement.Drop>이벤트가 처리 되지 않은 경우 **Ctrl** 키를 눌렀는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-270">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="a69f7-271">이 발생할 때 **Ctrl** 키를 누르면 <xref:System.Windows.UIElement.Drop> 에서 Circle 컨트롤의 복사본을 만들어의 컬렉션에 추가 합니다 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="a69f7-271">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="a69f7-272">**Ctrl** 키를 누르지 않으면 <xref:System.Windows.Controls.Panel.Children%2A> 부모 패널의 컬렉션에서 원을 <xref:System.Windows.Controls.Panel.Children%2A> 끌어 놓은 패널의 컬렉션으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-272">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="a69f7-273"><xref:System.Windows.DragEventArgs.Effects%2A> <xref:System.Windows.DragDrop.DoDragDrop%2A> 이동 또는 복사 작업의 수행 여부를 메서드에 알리도록 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-273">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="a69f7-274">**F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-274">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="a69f7-275">에서 텍스트를 선택 `green` <xref:System.Windows.Controls.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-275">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="a69f7-276">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-276">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="a69f7-277">왼쪽 패널에서 오른쪽 패널로 원 컨트롤을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-277">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="a69f7-278">왼쪽 패널의 컬렉션에서 원이 제거 되 <xref:System.Windows.Controls.Panel.Children%2A> 고 오른쪽 패널의 자식 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-278">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="a69f7-279">Circle 컨트롤을 패널에서 다른 패널로 끌고 **Ctrl** 키를 누른 상태에서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-279">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="a69f7-280">원이 복사 되 고 복사본이 <xref:System.Windows.Controls.Panel.Children%2A> 수신 패널의 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a69f7-280">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="a69f7-281">![Ctrl 키를 누른 채 원 끌기](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="a69f7-281">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="a69f7-282">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a69f7-282">See also</span></span>

- [<span data-ttu-id="a69f7-283">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="a69f7-283">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
