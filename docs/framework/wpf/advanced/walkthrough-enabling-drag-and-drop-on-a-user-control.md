---
title: '연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991803"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="eb2ed-102">연습: 사용자 정의 컨트롤에서 끌어서 놓기 사용</span><span class="sxs-lookup"><span data-stu-id="eb2ed-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="eb2ed-103">이 연습에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 끌어서 놓기 데이터 전송에 참가할 수 있는 사용자 지정 사용자 정의 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="eb2ed-104">이 연습에서는 circle 셰이프를 나타내는 사용자 지정 WPF <xref:System.Windows.Controls.UserControl> 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="eb2ed-105">컨트롤에서 끌어서 놓기를 통해 데이터 전송을 활성화하는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="eb2ed-106">예를 들어 한 원 컨트롤에서 다른 원 컨트롤로 끌면 채우기 색 데이터가 소스 원에서 대상 원으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="eb2ed-107">원 컨트롤에서로 <xref:System.Windows.Controls.TextBox>끌어 오면 채우기 색의 문자열 표현이에 복사 <xref:System.Windows.Controls.TextBox>됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="eb2ed-108">또한 두 개의 패널 컨트롤과를 <xref:System.Windows.Controls.TextBox> 포함 하는 작은 응용 프로그램을 만들어 끌어서 놓기 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="eb2ed-109">패널이 끌어 놓은 원 데이터를 처리하여 한 패널의 자식 컬렉션에서 다른 패널로 원을 이동하거나 복사할 수 있도록 하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="eb2ed-110">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="eb2ed-111">사용자 지정 사용자 정의 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="eb2ed-111">Create a custom user control.</span></span>

- <span data-ttu-id="eb2ed-112">사용자 정의 컨트롤을 끌기 소스로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="eb2ed-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="eb2ed-113">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="eb2ed-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="eb2ed-114">패널이 사용자 정의 컨트롤에서 놓은 데이터를 받을 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="eb2ed-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb2ed-115">전제 조건</span><span class="sxs-lookup"><span data-stu-id="eb2ed-115">Prerequisites</span></span>

<span data-ttu-id="eb2ed-116">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="eb2ed-117">응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="eb2ed-117">Create the Application Project</span></span>
 <span data-ttu-id="eb2ed-118">이 섹션에서는 두 개의 패널과를 <xref:System.Windows.Controls.TextBox>사용 하는 기본 페이지를 포함 하는 응용 프로그램 인프라를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="eb2ed-119">Visual Basic 또는 Visual C#에서 `DragDropExample`이라는 새 WPF 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="eb2ed-120">자세한 내용은 [연습: 내 첫 번째 WPF 데스크톱](../getting-started/walkthrough-my-first-wpf-desktop-application.md)응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="eb2ed-121">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="eb2ed-122">여는 태그와 닫는 <xref:System.Windows.Controls.Grid> 태그 사이에 다음 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="eb2ed-123">이 태그는 테스트 애플리케이션에 대한 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="eb2ed-124">프로젝트에 새 사용자 정의 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="eb2ed-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="eb2ed-125">이 섹션에서는 프로젝트에 새 사용자 정의 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="eb2ed-126">[프로젝트] 메뉴에서 **사용자 정의 컨트롤 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="eb2ed-127">**새 항목 추가** 대화 상자에서 이름을로 `Circle.xaml`변경 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="eb2ed-128">Circle.xaml과 해당 코드 숨김이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="eb2ed-129">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="eb2ed-130">이 파일에는 사용자 정의 컨트롤의 사용자 인터페이스 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="eb2ed-131">다음 태그를 루트 <xref:System.Windows.Controls.Grid> 에 추가 하 여 파란색 원이 UI로 포함 된 간단한 사용자 정의 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="eb2ed-132">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="eb2ed-133">에서 C#매개 변수가 없는 생성자 뒤에 다음 코드를 추가 하 여 복사 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="eb2ed-134">Visual Basic에서 다음 코드를 추가 하 여 매개 변수가 없는 생성자와 복사 생성자를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="eb2ed-135">사용자 정의 컨트롤을 복사할 수 있도록 하려면 코드 숨김 파일에서 복사 생성자 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="eb2ed-136">간단한 원 사용자 정의 컨트롤에서 사용자 정의 컨트롤의 채우기와 크기만 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="eb2ed-137">주 창에 사용자 정의 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="eb2ed-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="eb2ed-138">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="eb2ed-139">다음 XAML을 여 <xref:System.Windows.Window> 는 태그에 추가 하 여 현재 응용 프로그램에 대 한 XML 네임 스페이스 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="eb2ed-140">첫 <xref:System.Windows.Controls.StackPanel>번째에서 다음 XAML을 추가 하 여 첫 번째 패널에서 Circle 사용자 정의 컨트롤의 두 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="eb2ed-141">패널에 대한 전체 XAML은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="eb2ed-142">사용자 정의 컨트롤에서 끌기 소스 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="eb2ed-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="eb2ed-143">이 섹션에서는 메서드를 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의 하 고 끌어서 놓기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="eb2ed-144">마우스 단추를 누른 상태에서 마우스 단추를 누르면로 <xref:System.Windows.DataObject>전송할 데이터를 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="eb2ed-145">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="eb2ed-146">끌어서 놓기 작업을 시작하려면</span><span class="sxs-lookup"><span data-stu-id="eb2ed-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="eb2ed-147">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="eb2ed-148">다음 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.MouseMove> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="eb2ed-149">이 <xref:System.Windows.UIElement.OnMouseMove%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-150">마우스를 이동하는 동안 마우스 왼쪽 단추를 눌렀는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="eb2ed-151">원 데이터를에 <xref:System.Windows.DataObject>패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="eb2ed-152">이 경우 원 컨트롤은 채우기 색의 문자열 표현, 높이의 double 표현과 자신의 복사본이라는 세 개의 데이터 항목을 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="eb2ed-153">정적 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> 메서드를 호출 하 여 끌어서 놓기 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="eb2ed-154"><xref:System.Windows.DragDrop.DoDragDrop%2A> 메서드에 다음 세 개의 매개 변수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="eb2ed-155">`dragSource` – 이 컨트롤에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="eb2ed-156">`data`– 이전 코드에서 만든입니다.<xref:System.Windows.DataObject></span><span class="sxs-lookup"><span data-stu-id="eb2ed-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="eb2ed-157">`allowedEffects`– 허용 된 끌어서 놓기 작업 ( <xref:System.Windows.DragDropEffects.Copy> 또는 <xref:System.Windows.DragDropEffects.Move>)입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="eb2ed-158">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="eb2ed-159">원 컨트롤 중 하나를 클릭 하 고 패널, 다른 원 및 <xref:System.Windows.Controls.TextBox>로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="eb2ed-160">위로 <xref:System.Windows.Controls.TextBox>끌면 커서는 이동을 나타내기 위해 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="eb2ed-161">위로 <xref:System.Windows.Controls.TextBox>원을 끌어 오면 **ctrl** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="eb2ed-162">복사를 나타내기 위해 커서가 어떻게 변경되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="eb2ed-163">원을로 <xref:System.Windows.Controls.TextBox>끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="eb2ed-164">원 채우기 색의 문자열 표현이에 추가 <xref:System.Windows.Controls.TextBox>됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="eb2ed-165">![원 채우기 색의 문자열 표현](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="eb2ed-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="eb2ed-166">기본적으로 커서는 끌어서 놓기 작업 중 데이터 놓기의 결과를 나타내도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="eb2ed-167">이벤트를 <xref:System.Windows.UIElement.GiveFeedback> 처리 하 고 다른 커서를 설정 하 여 사용자에 게 제공 되는 피드백을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="eb2ed-168">사용자에 게 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="eb2ed-168">Give feedback to the user</span></span>

1. <span data-ttu-id="eb2ed-169">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="eb2ed-170">다음 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.GiveFeedback> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="eb2ed-171">이 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-172">놓기 대상 <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 의 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기에 설정 된 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="eb2ed-173"><xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 값을 기준으로 사용자 지정 커서를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="eb2ed-174">커서는 데이터 놓기의 결과에 대한 시각적 피드백을 사용자에게 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="eb2ed-175">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="eb2ed-176">패널, 다른 원 및에서 <xref:System.Windows.Controls.TextBox>원 컨트롤 중 하나를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="eb2ed-177">이제 커서는 <xref:System.Windows.UIElement.OnGiveFeedback%2A> 재정의에서 지정한 사용자 지정 커서입니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="eb2ed-178">![사용자 지정 커서로 끌어서 놓기](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="eb2ed-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="eb2ed-179">에서 텍스트 `green` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="eb2ed-180">`green` 텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="eb2ed-181">기본 커서가 끌어서 놓기 작업의 결과를 나타내도록 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="eb2ed-182">피드백 커서는 항상 끌기 소스에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="eb2ed-183">사용자 정의 컨트롤에서 놓기 대상 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="eb2ed-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="eb2ed-184">이 섹션에서는 사용자 정의 컨트롤이 놓기 대상이 되도록 지정하고, 사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하는 메서드를 재정의하며, 대상에 끌어 놓은 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="eb2ed-185">사용자 정의 컨트롤을 놓기 대상으로 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="eb2ed-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="eb2ed-186">Circle.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="eb2ed-187">여 <xref:System.Windows.Controls.UserControl> 는 태그에서 <xref:System.Windows.UIElement.AllowDrop%2A> 속성을 추가 하 고로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="eb2ed-188">메서드 <xref:System.Windows.UIElement.OnDrop%2A> 는 <xref:System.Windows.UIElement.AllowDrop%2A> 속성이로 `true` 설정 되 고 끌기 소스의 데이터가 Circle 사용자 정의 컨트롤에 삭제 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="eb2ed-189">이 메서드에서는 끌어 놓은 데이터를 처리하고 해당 데이터를 원에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="eb2ed-190">끌어 놓은 데이터를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="eb2ed-190">To process the dropped data</span></span>

1. <span data-ttu-id="eb2ed-191">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="eb2ed-192">다음 <xref:System.Windows.UIElement.OnDrop%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.Drop> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="eb2ed-193">이 <xref:System.Windows.UIElement.OnDrop%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-194">메서드를 <xref:System.Windows.DataObject.GetDataPresent%2A> 사용 하 여 끌어 온 데이터에 문자열 개체가 포함 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="eb2ed-195">문자열 데이터가 <xref:System.Windows.DataObject.GetData%2A> 있는 경우 메서드를 사용 하 여 문자열 데이터를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="eb2ed-196">는 <xref:System.Windows.Media.BrushConverter> 를 사용 하 여 문자열 <xref:System.Windows.Media.Brush>을로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="eb2ed-197">변환이 성공 하면는 Circle 컨트롤의 UI를 제공 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> 하는의에 브러시를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="eb2ed-198">이벤트를 <xref:System.Windows.UIElement.Drop> 처리 된 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="eb2ed-199">이 이벤트를 수신하는 다른 요소가 원 사용자 정의 컨트롤에서 해당 이벤트를 처리했음을 알 수 있도록 놓기 이벤트를 처리된 것으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="eb2ed-200">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="eb2ed-201">에서 텍스트 `green` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="eb2ed-202">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="eb2ed-203">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="eb2ed-204">![문자열을 브러시로 변환](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="eb2ed-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="eb2ed-205">에 텍스트 `green` 를 입력 합니다. <xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="eb2ed-206">에서 텍스트 `gre` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="eb2ed-207">이 텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="eb2ed-208">놓기가 허용됨을 나타내도록 커서가 변경되지만 `gre`가 유효한 색이 아니기 때문에 원의 색은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="eb2ed-209">녹색 원 컨트롤에서 끌어서 파란색 원 컨트롤에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="eb2ed-210">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="eb2ed-211">표시 되는 커서는 <xref:System.Windows.Controls.TextBox> 또는 원이 끌기 소스 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="eb2ed-212">속성을로 `true` 설정 하 고 끌어 놓은 데이터를 처리 하는 것은 요소를 놓기 대상으로 설정 하는 데 필요 합니다. <xref:System.Windows.UIElement.AllowDrop%2A></span><span class="sxs-lookup"><span data-stu-id="eb2ed-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="eb2ed-213">그러나 더 나은 사용자 환경을 제공 하기 위해 <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>및 <xref:System.Windows.UIElement.DragOver> 이벤트도 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="eb2ed-214">이러한 이벤트에서 데이터를 놓기 전에 검사를 수행하고 사용자에게 추가 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="eb2ed-215">데이터를 원 사용자 정의 컨트롤로 끌면 컨트롤에서 끌고 있는 데이터를 처리할 수 있는지 여부를 끌기 소스에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="eb2ed-216">컨트롤에서 데이터 처리 방법을 알지 못하는 경우 놓기를 거부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="eb2ed-217">이렇게 하려면 <xref:System.Windows.UIElement.DragOver> 이벤트를 처리 하 고 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="eb2ed-218">데이터 놓기가 허용되는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="eb2ed-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="eb2ed-219">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="eb2ed-220">다음 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.DragOver> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="eb2ed-221">이 <xref:System.Windows.UIElement.OnDragOver%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-222"><xref:System.Windows.DragEventArgs.Effects%2A> 속성을 <xref:System.Windows.DragDropEffects.None>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="eb2ed-223"><xref:System.Windows.UIElement.OnDrop%2A> 메서드에서 수행 하는 것과 동일한 검사를 수행 하 여 Circle 사용자 정의 컨트롤이 끌어 온 데이터를 처리할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="eb2ed-224">사용자 정의 컨트롤에서 데이터를 처리할 수 있는 경우에 <xref:System.Windows.DragEventArgs.Effects%2A> 는 속성 <xref:System.Windows.DragDropEffects.Copy> 을 <xref:System.Windows.DragDropEffects.Move>또는로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="eb2ed-225">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="eb2ed-226">에서 텍스트 `gre` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="eb2ed-227">텍스트를 원 컨트롤로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="eb2ed-228">`gre`가 유효한 색이 아니므로 놓기가 허용되지 않음을 나타내도록 커서가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="eb2ed-229">놓기 작업의 미리 보기를 적용하여 사용자 환경을 더욱 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="eb2ed-230">Circle 사용자 정의 컨트롤의 경우 <xref:System.Windows.UIElement.OnDragEnter%2A> 및 <xref:System.Windows.UIElement.OnDragLeave%2A> 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="eb2ed-231">컨트롤 위로 데이터를 끌면 현재 배경이 <xref:System.Windows.Shapes.Shape.Fill%2A> 자리 표시자 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="eb2ed-232">그러면 문자열이 브러시로 변환 되 고 원의 UI를 제공 <xref:System.Windows.Shapes.Ellipse> 하는에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="eb2ed-233">데이터를 삭제 하지 않고 원 밖으로 끌면 원래 <xref:System.Windows.Shapes.Shape.Fill%2A> 값이 원에 다시 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="eb2ed-234">끌어서 놓기 작업의 결과를 미리 보려면</span><span class="sxs-lookup"><span data-stu-id="eb2ed-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="eb2ed-235">Circle.xaml.cs 또는 Circle.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="eb2ed-236">Circle 클래스에서 라는 <xref:System.Windows.Media.Brush> `_previousFill` private 변수를 선언 하 고로 `null`초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="eb2ed-237">다음 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.DragEnter> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="eb2ed-238">이 <xref:System.Windows.UIElement.OnDragEnter%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-239"><xref:System.Windows.Shapes.Shape.Fill%2A> 의<xref:System.Windows.Shapes.Ellipse> 속성을`_previousFill` 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="eb2ed-240"><xref:System.Windows.UIElement.OnDrop%2A> 메서드에서 수행 하는 것과 동일한 검사를 수행 하 여 데이터를 <xref:System.Windows.Media.Brush>로 변환할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="eb2ed-241">데이터가 유효한 <xref:System.Windows.Media.Brush>으로 변환 되 면이 <xref:System.Windows.Shapes.Shape.Fill%2A> 를 <xref:System.Windows.Shapes.Ellipse>의에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="eb2ed-242">다음 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의를 추가 하 여 <xref:System.Windows.UIElement.DragLeave> 이벤트에 대 한 클래스 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="eb2ed-243">이 <xref:System.Windows.UIElement.OnDragLeave%2A> 재정의는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-244">Circle 사용자 <xref:System.Windows.Media.Brush> 정의 컨트롤의 `_previousFill` UI를 제공 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> 하는의에 변수에 저장 된를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="eb2ed-245">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="eb2ed-246">에서 텍스트 `green` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="eb2ed-247">텍스트를 놓지 않고 원 컨트롤 위로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="eb2ed-248">원이 파란색에서 녹색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="eb2ed-249">![끌어서 놓기 작업의 결과 미리 보기](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="eb2ed-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="eb2ed-250">원 컨트롤에서 멀리 텍스트를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="eb2ed-251">원이 녹색에서 다시 파란색으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="eb2ed-252">패널에서 삭제 된 데이터를 받을 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="eb2ed-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="eb2ed-253">이 섹션에서는 Circle 사용자 정의 컨트롤을 호스팅하는 패널을 끌어 끌어온 원 데이터의 놓기 대상 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="eb2ed-254">한 패널에서 다른 패널로 원을 이동 하거나, **Ctrl** 키를 누른 채 원를 끌어서 놓는 방법으로 원 컨트롤의 복사본을 만들 수 있도록 하는 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="eb2ed-255">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="eb2ed-256">다음 XAML에 표시 된 것 처럼 각 <xref:System.Windows.Controls.StackPanel> 컨트롤에서 <xref:System.Windows.UIElement.DragOver> 및 <xref:System.Windows.UIElement.Drop> 이벤트에 대 한 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="eb2ed-257">이벤트 <xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop> 처리기의 이름을, 및로 이벤트 처리기 `panel_Drop`의 이름을로 합니다. `panel_DragOver`</span><span class="sxs-lookup"><span data-stu-id="eb2ed-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="eb2ed-258">MainWindows.xaml.cs 또는 MainWindow.xaml.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="eb2ed-259"><xref:System.Windows.UIElement.DragOver> 이벤트 처리기에 대 한 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="eb2ed-260">이 <xref:System.Windows.UIElement.DragOver> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-261">원 사용자 정의 컨트롤에 <xref:System.Windows.DataObject> 의해 패키지 되 고에 대 <xref:System.Windows.DragDrop.DoDragDrop%2A>한 호출에 전달 된 "개체" 데이터가 끌어온 데이터에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="eb2ed-262">"Object" 데이터가 있는 경우 **Ctrl** 키를 눌렀는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="eb2ed-263">**Ctrl** 키를 누르면 <xref:System.Windows.DragEventArgs.Effects%2A> 속성이로 <xref:System.Windows.DragDropEffects.Copy>설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="eb2ed-264">그렇지 않은 경우 <xref:System.Windows.DragEventArgs.Effects%2A> 속성을로 <xref:System.Windows.DragDropEffects.Move>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="eb2ed-265"><xref:System.Windows.UIElement.Drop> 이벤트 처리기에 대 한 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="eb2ed-266">이 <xref:System.Windows.UIElement.Drop> 이벤트 처리기는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="eb2ed-267"><xref:System.Windows.UIElement.Drop> 이벤트가 이미 처리 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="eb2ed-268">예를 들어, <xref:System.Windows.UIElement.Drop> 이벤트를 처리 하는 다른 원에 원을 놓는 경우 원이 포함 된 패널에서 해당 원을 처리 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="eb2ed-269">이벤트가 처리 되지 않은 경우 Ctrl 키를 눌렀는지 여부를 확인 합니다. <xref:System.Windows.UIElement.Drop></span><span class="sxs-lookup"><span data-stu-id="eb2ed-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="eb2ed-270">이 <xref:System.Windows.UIElement.Drop> 발생할 때 **Ctrl** 키를 누르면에서 Circle 컨트롤의 복사본을 만들어의 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.StackPanel>컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="eb2ed-271">**Ctrl** 키를 누르지 않으면 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.Panel.Children%2A> 부모 패널의 컬렉션에서 원을 끌어 놓은 패널의 컬렉션으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="eb2ed-272">이동 또는 복사 작업의 수행 <xref:System.Windows.DragDrop.DoDragDrop%2A> 여부를 메서드에 알리도록 속성을설정합니다.<xref:System.Windows.DragEventArgs.Effects%2A></span><span class="sxs-lookup"><span data-stu-id="eb2ed-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="eb2ed-273">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="eb2ed-274">에서 텍스트 `green` 를 선택 합니다.<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="eb2ed-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="eb2ed-275">텍스트를 원 컨트롤로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="eb2ed-276">왼쪽 패널에서 오른쪽 패널로 원 컨트롤을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="eb2ed-277">왼쪽 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에서 원이 제거 되 고 오른쪽 패널의 자식 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="eb2ed-278">Circle 컨트롤을 패널에서 다른 패널로 끌고 **Ctrl** 키를 누른 상태에서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="eb2ed-279">원이 복사 되 고 복사본이 수신 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb2ed-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="eb2ed-280">![Ctrl 키를 누른 채 원 끌기](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="eb2ed-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="eb2ed-281">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb2ed-281">See also</span></span>

- [<span data-ttu-id="eb2ed-282">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="eb2ed-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
