---
title: '연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: 70cd08a9d7d03cec4e946d2acb806dbecfe774f7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724629"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="e6a4b-102">연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>

<span data-ttu-id="e6a4b-103">연결 된 사용자 지정 디자이너를 작성 하 여 사용자 지정 컨트롤에 대 한 디자인 타임 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="e6a4b-104">이 연습에서는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="e6a4b-105">구현 합니다는 `MarqueeControl` 형식 및 호출 하는 연결 된 디자이너 클래스는 `MarqueeControlRootDesigner`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="e6a4b-106">`MarqueeControl` 형식이 애니메이션된 조명 및 깜박이 텍스트를 사용 하 여 극장식 움직이는 텍스트와 유사한 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>

<span data-ttu-id="e6a4b-107">이 컨트롤에 대 한 디자이너는 디자인 환경 사용자 지정 디자인 타임 환경을 제공 하기 위해 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="e6a4b-108">사용자 지정 디자이너를 사용 하 여 사용자 지정을 조합할 수 `MarqueeControl` 애니메이션된 조명 및 다양 한 조합 깜박이 텍스트를 사용 하 여 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="e6a4b-109">다른 Windows Forms 컨트롤과 마찬가지로 폼에서 어셈블된 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="e6a4b-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="e6a4b-111">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-111">Creating the Project</span></span>

- <span data-ttu-id="e6a4b-112">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-112">Creating a Control Library Project</span></span>

- <span data-ttu-id="e6a4b-113">사용자 지정 컨트롤 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="e6a4b-113">Referencing the Custom Control Project</span></span>

- <span data-ttu-id="e6a4b-114">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너 정의</span><span class="sxs-lookup"><span data-stu-id="e6a4b-114">Defining a Custom Control and Its Custom Designer</span></span>

- <span data-ttu-id="e6a4b-115">사용자 지정 컨트롤의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-115">Creating an Instance of Your Custom Control</span></span>

- <span data-ttu-id="e6a4b-116">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-116">Setting Up the Project for Design-Time Debugging</span></span>

- <span data-ttu-id="e6a4b-117">사용자 지정 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="e6a4b-117">Implementing Your Custom Control</span></span>

- <span data-ttu-id="e6a4b-118">사용자 지정 컨트롤의 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-118">Creating a Child Control for Your Custom Control</span></span>

- <span data-ttu-id="e6a4b-119">통해 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-119">Create the MarqueeBorder Child Control</span></span>

- <span data-ttu-id="e6a4b-120">섀도 필터 속성을 사용자 지정 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>

- <span data-ttu-id="e6a4b-121">구성 요소 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="e6a4b-121">Handling Component Changes</span></span>

- <span data-ttu-id="e6a4b-122">사용자 지정 디자이너에 추가할 디자이너 동사</span><span class="sxs-lookup"><span data-stu-id="e6a4b-122">Adding Designer Verbs to your Custom Designer</span></span>

- <span data-ttu-id="e6a4b-123">사용자 지정 UITypeEditor 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-123">Creating a Custom UITypeEditor</span></span>

- <span data-ttu-id="e6a4b-124">디자이너에서 사용자 지정 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="e6a4b-124">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="e6a4b-125">완료 되 면 다음과 같이 사용자 지정 컨트롤 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-125">When you are finished, your custom control will look something like the following:</span></span>

<span data-ttu-id="e6a4b-126">![가능한 MarqueeControl 배치](./media/demomarqueecontrol.gif "항목")</span><span class="sxs-lookup"><span data-stu-id="e6a4b-126">![A possible MarqueeControl arrangement](./media/demomarqueecontrol.gif "DemoMarqueeControl")</span></span>

<span data-ttu-id="e6a4b-127">전체 코드 목록은 참조 하세요. [방법: 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

> [!NOTE]
> <span data-ttu-id="e6a4b-128">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-128">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e6a4b-129">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-129">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e6a4b-130">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-130">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6a4b-131">전제 조건</span><span class="sxs-lookup"><span data-stu-id="e6a4b-131">Prerequisites</span></span>

<span data-ttu-id="e6a4b-132">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-132">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="e6a4b-133">만들고 Visual Studio를 설치한 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행 하는 일을 할 수 있는 충분 한 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-133">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="e6a4b-134">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-134">Creating the Project</span></span>

<span data-ttu-id="e6a4b-135">첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-135">The first step is to create the application project.</span></span> <span data-ttu-id="e6a4b-136">사용자 지정 컨트롤을 호스팅하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-136">You will use this project to build the application that hosts the custom control.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="e6a4b-137">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-137">To create the project</span></span>

- <span data-ttu-id="e6a4b-138">"MarqueeControlTest" 라는 Windows Forms 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >   **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-138">Create a Windows Forms Application project called "MarqueeControlTest" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="creating-a-control-library-project"></a><span data-ttu-id="e6a4b-139">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-139">Creating a Control Library Project</span></span>

<span data-ttu-id="e6a4b-140">다음 단계에서는 컨트롤 라이브러리 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-140">The next step is to create the control library project.</span></span> <span data-ttu-id="e6a4b-141">새 사용자 지정 컨트롤 및 해당 사용자 지정 디자이너 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-141">You will create a new custom control and its corresponding custom designer.</span></span>

### <a name="to-create-the-control-library-project"></a><span data-ttu-id="e6a4b-142">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-142">To create the control library project</span></span>

1. <span data-ttu-id="e6a4b-143">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-143">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="e6a4b-144">"MarqueeControlLibrary." 프로젝트 이름을</span><span class="sxs-lookup"><span data-stu-id="e6a4b-144">Name the project "MarqueeControlLibrary."</span></span>

2. <span data-ttu-id="e6a4b-145">사용 하 여 **솔루션 탐색기**, 선택한 언어에 따라 "UserControl1.cs" 또는 "UserControl1.vb" 라는 소스 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-145">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="e6a4b-146">자세한 내용은 [방법: 제거, 삭제 및 항목을 제외](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-146">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="e6a4b-147">새 <xref:System.Windows.Forms.UserControl> 항목을 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-147">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-148">새 소스 파일 "MarqueeControl."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-148">Give the new source file a base name of "MarqueeControl."</span></span>

4. <span data-ttu-id="e6a4b-149">사용 하 여 **솔루션 탐색기**에서 새 폴더 만들기를 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-149">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-150">자세한 내용은 [방법: 새 프로젝트 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-150">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="e6a4b-151">새 폴더의 이름을 "디자인"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-151">Name the new folder "Design."</span></span>

5. <span data-ttu-id="e6a4b-152">마우스 오른쪽 단추로 클릭 합니다 **디자인** 폴더 및 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-152">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="e6a4b-153">소스 파일 "MarqueeControlRootDesigner."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-153">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>

6. <span data-ttu-id="e6a4b-154">System.Design 어셈블리의 형식을 사용 하 여,이 참조를 추가 해야 합니다는 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-154">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6a4b-155">System.Design 어셈블리를 사용 하려면 프로젝트가 정식 버전의.NET Framework,.NET Framework 4 클라이언트 프로필 아님를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-155">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="e6a4b-156">대상 프레임 워크를 변경 하려면 참조 [방법: 한 버전의 .NET Framework를 대상으로 지정](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-156">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="e6a4b-157">사용자 지정 컨트롤 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="e6a4b-157">Referencing the Custom Control Project</span></span>

<span data-ttu-id="e6a4b-158">사용 하 여는 `MarqueeControlTest` 프로젝트를 사용자 지정 컨트롤을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-158">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="e6a4b-159">에 대 한 프로젝트 참조를 추가 하면 테스트 프로젝트 사용자 지정 컨트롤을 인식 될는 `MarqueeControlLibrary` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-159">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="e6a4b-160">사용자 지정 컨트롤 프로젝트를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-160">To reference the custom control project</span></span>

- <span data-ttu-id="e6a4b-161">에 `MarqueeControlTest` 프로젝트를 프로젝트 참조를 추가 합니다 `MarqueeControlLibrary` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-161">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="e6a4b-162">사용 해야 합니다 **프로젝트** 탭에 **참조 추가** 참조 하는 대신 대화 상자를 `MarqueeControlLibrary` 어셈블리를 직접.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-162">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="e6a4b-163">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너 정의</span><span class="sxs-lookup"><span data-stu-id="e6a4b-163">Defining a Custom Control and Its Custom Designer</span></span>
 <span data-ttu-id="e6a4b-164">사용자 지정 컨트롤에서 파생 됩니다는 <xref:System.Windows.Forms.UserControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-164">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="e6a4b-165">이렇게 하면 컨트롤이 다른 컨트롤을 포함 하 고 컨트롤 많은 기본 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-165">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

 <span data-ttu-id="e6a4b-166">사용자 지정 컨트롤을 사용자 지정 디자이너를 연결된 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-166">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="e6a4b-167">이 옵션을 사용 하면 사용자 지정 컨트롤을 위해 특별히 고안 된 고유한 디자인 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-167">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

 <span data-ttu-id="e6a4b-168">사용 하 여 해당 디자이너를 사용 하 여 컨트롤을 연결 합니다 <xref:System.ComponentModel.DesignerAttribute> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-168">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="e6a4b-169">사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발 하는 사용자 지정 디자이너를 구현 합니다 <xref:System.ComponentModel.Design.IRootDesigner> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-169">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="e6a4b-170">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-170">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="e6a4b-171">열기는 `MarqueeControl` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-171">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-172">파일의 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-172">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="e6a4b-173">추가 합니다 <xref:System.ComponentModel.DesignerAttribute> 에 `MarqueeControl` 클래스 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-173">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="e6a4b-174">이 디자이너를 사용 하 여 사용자 지정 컨트롤을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-174">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="e6a4b-175">열기는 `MarqueeControlRootDesigner` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-175">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-176">파일의 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-176">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="e6a4b-177">선언을 변경 `MarqueeControlRootDesigner` 에서 상속 하는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-177">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="e6a4b-178">적용 된 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 디자이너와 상호 작용을 지정 하는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-178">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

     <span data-ttu-id="e6a4b-179">**참고** 에 대 한 정의 `MarqueeControlRootDesigner` "MarqueeControlLibrary.Design." 라는 네임 스페이스의 클래스에 묶여</span><span class="sxs-lookup"><span data-stu-id="e6a4b-179">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="e6a4b-180">이 선언은 배치 디자이너 특수 네임 스페이스의 디자인 관련 형식에 대 한 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-180">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="e6a4b-181">에 대 한 생성자를 정의 합니다 `MarqueeControlRootDesigner` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-181">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="e6a4b-182">삽입을 <xref:System.Diagnostics.Trace.WriteLine%2A> 생성자 본문에는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-182">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="e6a4b-183">이 디버깅 목적으로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-183">This will be useful for debugging purposes.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="e6a4b-184">사용자 지정 컨트롤의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-184">Creating an Instance of Your Custom Control</span></span>
 <span data-ttu-id="e6a4b-185">양식에서 컨트롤의 인스턴스를 컨트롤의 사용자 지정 디자인 타임 동작을 관찰 배치 `MarqueeControlTest` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-185">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>

### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="e6a4b-186">사용자 지정 컨트롤의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-186">To create an instance of your custom control</span></span>

1. <span data-ttu-id="e6a4b-187">새 <xref:System.Windows.Forms.UserControl> 항목을 `MarqueeControlTest` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-187">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="e6a4b-188">새 소스 파일 "항목입니다."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-188">Give the new source file a base name of "DemoMarqueeControl."</span></span>

2. <span data-ttu-id="e6a4b-189">엽니다는 `DemoMarqueeControl` 파일을 **코드 편집기**.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-189">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-190">파일의 맨 위에 있는 가져오기는 `MarqueeControlLibrary` 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-190">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. <span data-ttu-id="e6a4b-191">선언을 변경 `DemoMarqueeControl` 에서 상속 하는 `MarqueeControl` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-191">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

2. <span data-ttu-id="e6a4b-192">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-192">Build the project.</span></span>

3. <span data-ttu-id="e6a4b-193">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-193">Open `Form1` in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="e6a4b-194">찾을 **MarqueeControlTest 구성 요소** 탭에 **도구 상자** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-194">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="e6a4b-195">끌어서를 `DemoMarqueeControl` 에서 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-195">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="e6a4b-196">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-196">Build the project.</span></span>

## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="e6a4b-197">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-197">Setting Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="e6a4b-198">사용자 지정 디자인 타임 환경을 개발 하는 경우 디버그 하 여 컨트롤 및 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-198">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="e6a4b-199">디자인 타임에 디버깅을 허용 하도록 프로젝트를 설정 하는 간단한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-199">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="e6a4b-200">자세한 내용은 [연습: 디자인 타임에 디버깅 사용자 지정 Windows Forms 컨트롤](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-200">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="e6a4b-201">디자인 타임 디버깅을 위해 프로젝트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-201">To set up the project for design-time debugging</span></span>

1. <span data-ttu-id="e6a4b-202">마우스 오른쪽 단추로 클릭 합니다 `MarqueeControlLibrary` 프로젝트를 마우스 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-202">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="e6a4b-203">"MarqueeControlLibrary 속성 페이지" 대화 상자에서 선택 합니다 **디버그** 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-203">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="e6a4b-204">에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-204">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="e6a4b-205">해야 줄임표 하므로 별도 인스턴스, Visual Studio의 디버깅 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 클릭 하 여 Visual Studio IDE에 대 한 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-205">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="e6a4b-206">실행 파일의 이름을 devenv.exe가 이며 기본 위치에 설치한 경우 해당 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-206">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

4. <span data-ttu-id="e6a4b-207">대화 상자를 닫으려면 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-207">Click OK to close the dialog box.</span></span>

5. <span data-ttu-id="e6a4b-208">마우스 오른쪽 단추로 클릭는 `MarqueeControlLibrary` 프로젝트 및 "시작 프로젝트로 설정"이 디버깅 구성을 사용 하도록 설정 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-208">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="e6a4b-209">검사점</span><span class="sxs-lookup"><span data-stu-id="e6a4b-209">Checkpoint</span></span>

<span data-ttu-id="e6a4b-210">이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버그 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-210">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="e6a4b-211">디버깅 환경을 올바르게 설정 되어 있는지를 확인 한 후에 사용자 지정 컨트롤 및 사용자 지정 디자이너 간의 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-211">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="e6a4b-212">디버깅 환경 및 디자이너 연결을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-212">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="e6a4b-213">열기를 `MarqueeControlRootDesigner` 소스 파일을 **코드 편집기** 중단점을 설정 하 고를 <xref:System.Diagnostics.Trace.WriteLine%2A> 문.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-213">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="e6a4b-214">F5 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-214">Press F5 to start the debugging session.</span></span> <span data-ttu-id="e6a4b-215">Visual Studio의 새 인스턴스를 만들어짐을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-215">Note that a new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="e6a4b-216">Visual Studio의 새 인스턴스를 "MarqueeControlTest" 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-216">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="e6a4b-217">선택 하 여 솔루션을 쉽게 찾을 수 있습니다 **최근에 사용한 프로젝트** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-217">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="e6a4b-218">"MarqueeControlTest.sln" 솔루션 파일을 최근에 사용 된 파일으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-218">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="e6a4b-219">열기는 `DemoMarqueeControl` 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-219">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="e6a4b-220">Visual Studio의 디버깅 인스턴스 포커스를 획득 하 고 실행이 중단점에서 중지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-220">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="e6a4b-221">F5 키를 눌러 디버깅 세션을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-221">Press F5 to continue the debugging session.</span></span>

<span data-ttu-id="e6a4b-222">이 시점에서 모든 항목의 개발 및 사용자 지정 컨트롤 및 연결 된 해당 사용자 지정 디자이너를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-222">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="e6a4b-223">이 연습의 나머지 부분을 컨트롤 디자이너의 기능을 구현 하는 세부 정보를 중점적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-223">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>

## <a name="implementing-your-custom-control"></a><span data-ttu-id="e6a4b-224">사용자 지정 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="e6a4b-224">Implementing Your Custom Control</span></span>

<span data-ttu-id="e6a4b-225">`MarqueeControl` 되는 <xref:System.Windows.Forms.UserControl> 약간의 사용자 지정을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-225">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="e6a4b-226">두 메서드를 노출 합니다. `Start`, 움직이는 텍스트 애니메이션을 시작 하는 및 `Stop`, 애니메이션을 중지 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-226">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="e6a4b-227">때문에 `MarqueeControl` 구현 하는 자식 컨트롤을 포함 합니다 `IMarqueeWidget` 인터페이스 `Start` 및 `Stop` 각 자식 컨트롤 및 호출 열거를 `StartMarquee` 및 `StopMarquee` 메서드를 각 자식 컨트롤에 각각 구현 하는 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-227">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="e6a4b-228">모양의 합니다 `MarqueeBorder` 및 `MarqueeText` 컨트롤의 레이아웃에 따라 다릅니다. 하므로 `MarqueeControl` 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드 및 호출 <xref:System.Windows.Forms.Control.PerformLayout%2A> 이 형식의 자식 컨트롤에.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-228">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="e6a4b-229">이 범위는 `MarqueeControl` 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-229">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="e6a4b-230">런타임 기능에서 구현 되는 `MarqueeBorder` 및 `MarqueeText` 컨트롤 및 디자인 타임 기능에서 구현 되는 `MarqueeBorderDesigner` 및 `MarqueeControlRootDesigner` 클래스.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-230">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="e6a4b-231">사용자 지정 컨트롤을 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-231">To implement your custom control</span></span>

1. <span data-ttu-id="e6a4b-232">열기는 `MarqueeControl` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-232">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-233">구현 된 `Start` 고 `Stop` 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-233">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="e6a4b-234"><xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-234">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="e6a4b-235">사용자 지정 컨트롤의 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-235">Creating a Child Control for Your Custom Control</span></span>

<span data-ttu-id="e6a4b-236">`MarqueeControl` 두 가지 유형의 자식 컨트롤을 호스트 하는: 합니다 `MarqueeBorder` 컨트롤 및 `MarqueeText` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-236">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="e6a4b-237">`MarqueeBorder`: 이 컨트롤에는 가장자리 주위 "lights"의 테두리를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-237">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="e6a4b-238">표시등 순서 대로 나타나도록 테두리 이동할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-238">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="e6a4b-239">표시등는 속도 라는 속성에 의해 제어 됩니다 `UpdatePeriod`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-239">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="e6a4b-240">다른 사용자 지정 속성을 여러 컨트롤의 모양의 다른 측면을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-240">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="e6a4b-241">두 가지 메서드를 호출 `StartMarquee` 고 `StopMarquee`, 애니메이션의 시작 및 중지 시기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-241">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="e6a4b-242">`MarqueeText`: 이 컨트롤은 깜박이 문자열을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-242">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="e6a4b-243">같은 합니다 `MarqueeBorder` 컨트롤에 텍스트를 깜박이 속도 의해 제어 됩니다는 `UpdatePeriod` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-243">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="e6a4b-244">`MarqueeText` 컨트롤을 `StartMarquee` 및 `StopMarquee` 공통 된 메서드는 `MarqueeBorder` 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-244">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="e6a4b-245">디자인 타임에 `MarqueeControlRootDesigner` 이러한 두 가지 컨트롤 형식에 추가할 수 있습니다는 `MarqueeControl` 의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-245">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="e6a4b-246">두 컨트롤의 일반적인 기능은 라는 인터페이스를 팩터링 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-246">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="e6a4b-247">따라서는 `MarqueeControl` 를 움직이는 텍스트와 관련 된 자식 컨트롤을 검색 하 여 특별 한 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-247">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="e6a4b-248">정기적인 애니메이션 기능을 구현 하려면 사용할지 <xref:System.ComponentModel.BackgroundWorker> 에서 개체를 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-248">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e6a4b-249">사용할 수 있습니다 <xref:System.Windows.Forms.Timer> 있지만 개체를 여러 `IMarqueeWidget` 개체를 사용할 수 있는, 단일 UI 스레드를 애니메이션으로 유지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-249">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="e6a4b-250">사용자 지정 컨트롤의 자식 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-250">To create a child control for your custom control</span></span>

1. <span data-ttu-id="e6a4b-251">새 클래스 항목을 추가 합니다 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-251">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-252">새 소스 파일 "IMarqueeWidget."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-252">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="e6a4b-253">열기는 `IMarqueeWidget` 소스 파일을 **코드 편집기** 에서 선언을 변경 하 고 `class` 에 `interface`:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-253">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="e6a4b-254">다음 코드를 추가 합니다 `IMarqueeWidget` 움직이는 텍스트 애니메이션을 조작 하는 속성과 두 메서드를 노출 하는 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-254">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="e6a4b-255">새 **사용자 지정 컨트롤** 항목을 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-255">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-256">새 소스 파일 "통해."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-256">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="e6a4b-257">끌어서를 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소를 **도구 상자** 에 프로그램 `MarqueeText` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-257">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="e6a4b-258">이 구성 된 `MarqueeText` 자체를 비동기적으로 업데이트 하도록 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-258">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="e6a4b-259">속성 창에서 설정 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 하 고 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-259">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="e6a4b-260">이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 주기적으로 발생를 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 및 비동기 업데이트를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-260">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="e6a4b-261">자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-261">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="e6a4b-262">열기는 `MarqueeText` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-262">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-263">파일의 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-263">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="e6a4b-264">선언을 변경 `MarqueeText` 상속할 <xref:System.Windows.Forms.Label> 하 고 구현 하는 `IMarqueeWidget` 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-264">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="e6a4b-265">노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-265">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="e6a4b-266">합니다 `isLit` 필드에 지정 된 색에 그릴 텍스트 인지 여부를 확인 합니다 `LightColor` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-266">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="e6a4b-267">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-267">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="e6a4b-268">`StartMarquee` 및 `StopMarquee` 메서드를 호출 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 애니메이션을 중지 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-268">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="e6a4b-269">합니다 <xref:System.ComponentModel.CategoryAttribute.Category%2A> 하 고 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성에 적용 되는 `UpdatePeriod` "움직이는 텍스트입니다." 라는 속성 창의 사용자 지정 섹션을 나타나는 속성</span><span class="sxs-lookup"><span data-stu-id="e6a4b-269">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="e6a4b-270">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-270">Implement the property accessors.</span></span> <span data-ttu-id="e6a4b-271">클라이언트에 두 속성을 노출 됩니다. `LightColor` 및 `DarkColor`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-271">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="e6a4b-272">합니다 <xref:System.ComponentModel.CategoryAttribute.Category%2A> 고 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성 속성을 "움직이는 텍스트입니다." 라는 속성 창의 사용자 지정 섹션에 표시 되므로 이러한 속성에 적용 됩니다</span><span class="sxs-lookup"><span data-stu-id="e6a4b-272">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="e6a4b-273">에 대 한 처리기를 구현 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-273">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="e6a4b-274">합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기로 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 이벤트가 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션을 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-274">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="e6a4b-275"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기 깜박임 모양을에 밝은 영역과 어두운 상태 텍스트를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-275">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="e6a4b-276">재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 애니메이션을 사용 하도록 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-276">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="e6a4b-277">F6 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-277">Press F6 to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="e6a4b-278">통해 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-278">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="e6a4b-279">합니다 `MarqueeBorder` 컨트롤은 보다 약간 더 복잡 합니다 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-279">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="e6a4b-280">더 많은 속성이 있고에 애니메이션을 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-280">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="e6a4b-281">원칙적으로 상당히 비슷하다는 것을 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-281">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="e6a4b-282">때문에 합니다 `MarqueeBorder` 컨트롤에 자식 컨트롤이 있을 수 있습니다에 유의 해야 <xref:System.Windows.Forms.Control.Layout> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-282">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="e6a4b-283">통해 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-283">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="e6a4b-284">새 **사용자 지정 컨트롤** 항목을 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-284">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-285">새 소스 파일 "통해."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-285">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="e6a4b-286">끌어서를 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소를 **도구 상자** 에 프로그램 `MarqueeBorder` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-286">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="e6a4b-287">이 구성 된 `MarqueeBorder` 자체를 비동기적으로 업데이트 하도록 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-287">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="e6a4b-288">속성 창에서 설정 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 하 고 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-288">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="e6a4b-289">이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 주기적으로 발생를 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 및 비동기 업데이트를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-289">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="e6a4b-290">자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-290">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="e6a4b-291">속성 창에서 이벤트 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-291">In the Properties window, click the Events button.</span></span> <span data-ttu-id="e6a4b-292">에 대 한 처리기를 연결 합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-292">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="e6a4b-293">열기는 `MarqueeBorder` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-293">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-294">파일의 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-294">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="e6a4b-295">선언을 변경 `MarqueeBorder` 상속할 <xref:System.Windows.Forms.Panel> 및 구현 하는 `IMarqueeWidget` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-295">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="e6a4b-296">관리에 대 한 두 개의 열거형을 선언 합니다 `MarqueeBorder` 컨트롤의 상태: `MarqueeSpinDirection`는 전등 "회전" 테두리 방향을 결정 하는 및 `MarqueeLightShape`, (사각형 또는 순환) 광원의 모양을 결정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-296">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="e6a4b-297">이러한 선언을 `MarqueeBorder` 클래스 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-297">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="e6a4b-298">노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-298">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="e6a4b-299">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-299">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="e6a4b-300">`StartMarquee` 및 `StopMarquee` 메서드를 호출 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 애니메이션을 중지 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-300">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="e6a4b-301">때문에 합니다 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수는 `StartMarquee` 메서드 열거 모든 자식 컨트롤을 호출 `StartMarquee` 에서 구현 하는 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-301">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="e6a4b-302">`StopMarquee` 메서드가 구현 방법이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-302">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="e6a4b-303">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-303">Implement the property accessors.</span></span> <span data-ttu-id="e6a4b-304">`MarqueeBorder` 컨트롤의 모양을 제어 하는 것에 대 한 여러 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-304">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="e6a4b-305">에 대 한 처리기를 구현 합니다 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-305">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="e6a4b-306">합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기로 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 이벤트가 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션을 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-306">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="e6a4b-307">합니다 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기를 다른 광원의 밝기 상태 결정은 "기본" 밝은 테마와 호출의 위치를 증가 시킵니다.는 <xref:System.Windows.Forms.Control.Refresh%2A> 그려집니다 컨트롤이 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-307">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="e6a4b-308">도우미 메서드를 구현 `IsLit` 고 `DrawLight`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-308">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="e6a4b-309">`IsLit` 메서드는 지정 된 위치의 광원의 색을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-309">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="e6a4b-310">에 지정 된 색에는 "활성화"를 그려집니다 합니다 `LightColor` 에 지정 된 색에서 속성 및 "어두운" 되는 것이 그려지는 `DarkColor` 속성.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-310">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="e6a4b-311">`DrawLight` 메서드는 적절 한 색, 모양 및 위치를 사용 하 여 광원을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-311">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="e6a4b-312">재정의 된 <xref:System.Windows.Forms.Control.OnLayout%2A> 고 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-312">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="e6a4b-313">합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 의 가장자리를 따라 조명을 메서드는 `MarqueeBorder` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-313">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="e6a4b-314">때문에 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 크기에 따라 달라 집니다는 `MarqueeBorder` 레이아웃 변경 될 때마다 호출 해야 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-314">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="e6a4b-315">이 위해 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 호출 <xref:System.Windows.Forms.Control.Refresh%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-315">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="e6a4b-316">섀도 필터 속성을 사용자 지정 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-316">Creating a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="e6a4b-317">`MarqueeControlRootDesigner` 클래스 루트 디자이너에 대 한 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-317">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="e6a4b-318">작동 하는이 디자이너 외에도 합니다 `MarqueeControl`, 특히 연결 된 사용자 지정 디자이너를 해야 합니다는 `MarqueeBorder` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-318">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="e6a4b-319">이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에서 적절 한 사용자 지정 동작을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-319">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="e6a4b-320">특히를 `MarqueeBorderDesigner` "섀도"를 기준으로 특정 속성을 필터링 합니다 `MarqueeBorder` 컨트롤의 디자인 환경 상호 작용을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-320">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="e6a4b-321">"숨김" 이라고 구성 요소의 속성 접근자에 대 한 호출을 가로채기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-321">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="e6a4b-322">통해 디자이너는 사용자가 설정한 값을 추적 하 고 필요에 따라 디자인 하 고 구성 요소에 해당 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-322">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="e6a4b-323">예를 들어 합니다 <xref:System.Windows.Forms.Control.Visible%2A> 및 <xref:System.Windows.Forms.Control.Enabled%2A> 속성에 의해 숨겨질 수는 `MarqueeBorderDesigner`에서 만들기를 방지 하는 `MarqueeBorder` 컨트롤이 보이지 않거나 디자인 타임 동안 사용 안 함.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-323">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="e6a4b-324">또한 디자이너 추가 하 고 속성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-324">Designers can also add and remove properties.</span></span> <span data-ttu-id="e6a4b-325">예를 들어 합니다 <xref:System.Windows.Forms.Control.Padding%2A> 디자인 타임에 속성을 제거할 수는 `MarqueeBorder` 컨트롤은 프로그래밍 방식으로 지정 된 광원의 크기에 따라 안쪽 여백을 설정는 `LightSize` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-325">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="e6a4b-326">에 대 한 기본 클래스 `MarqueeBorderDesigner` 는 <xref:System.ComponentModel.Design.ComponentDesigner>, 특성, 속성 및 디자인 타임에 컨트롤을 통해 노출 되는 이벤트를 변경할 수 있는 메서드가 있는:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-326">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="e6a4b-327">이러한 메서드를 사용 하 여 구성 요소의 공용 인터페이스를 변경할 때에 이러한 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-327">When changing the public interface of a component using these methods, you must follow these rules:</span></span>

- <span data-ttu-id="e6a4b-328">항목 추가 또는 제거를 `PreFilter` 만 메서드</span><span class="sxs-lookup"><span data-stu-id="e6a4b-328">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="e6a4b-329">기존 항목의 수정 된 `PostFilter` 메서드만</span><span class="sxs-lookup"><span data-stu-id="e6a4b-329">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="e6a4b-330">항상 기본 구현을 처음는 `PreFilter` 메서드</span><span class="sxs-lookup"><span data-stu-id="e6a4b-330">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="e6a4b-331">항상 기본 구현에서 마지막으로 호출 된 `PostFilter` 메서드</span><span class="sxs-lookup"><span data-stu-id="e6a4b-331">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="e6a4b-332">이러한 규칙을 준수 하면 모든 디자이너는 디자인 타임 환경에서 일관 된 뷰를 디자인 하 고 모든 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-332">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="e6a4b-333"><xref:System.ComponentModel.Design.ComponentDesigner> 클래스를 특정 인스턴스 변수를 만들 필요는 숨겨진된 속성의 값을 관리 하는 것에 대 한 사전을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-333">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="e6a4b-334">섀도 및 필터 속성에 사용자 지정 디자이너를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-334">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="e6a4b-335">마우스 오른쪽 단추로 클릭 합니다 **디자인** 폴더 및 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-335">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="e6a4b-336">소스 파일 "MarqueeBorderDesigner."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-336">Give the source file a base name of "MarqueeBorderDesigner."</span></span>

2. <span data-ttu-id="e6a4b-337">열기는 `MarqueeBorderDesigner` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-337">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-338">파일의 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-338">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="e6a4b-339">선언을 변경 `MarqueeBorderDesigner` 상속할 <xref:System.Windows.Forms.Design.ParentControlDesigner>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-339">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="e6a4b-340">때문에 합니다 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수 있습니다 `MarqueeBorderDesigner` 에서 상속 <xref:System.Windows.Forms.Design.ParentControlDesigner>, 부모-자식 상호 작용을 처리 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-340">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="e6a4b-341">기본 구현을 재정의 <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-341">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="e6a4b-342">
  <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-342">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="e6a4b-343">이러한 구현은 컨트롤의 속성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-343">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a><span data-ttu-id="e6a4b-344">구성 요소 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="e6a4b-344">Handling Component Changes</span></span>
 <span data-ttu-id="e6a4b-345">합니다 `MarqueeControlRootDesigner` 클래스에 대 한 사용자 지정 디자인 타임 환경을 제공 하 `MarqueeControl` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-345">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="e6a4b-346">대부분의 디자인 타임 기능에서 상속 됩니다는 <xref:System.Windows.Forms.Design.DocumentDesigner> 두 개의 특정 사용자 지정을 구현 하면 코드는 클래스: 구성 요소 변경 내용 처리 및 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-346">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

 <span data-ttu-id="e6a4b-347">사용자가 디자인으로 해당 `MarqueeControl` 인스턴스, 루트 디자이너에 변경 내용을 추적 합니다는 `MarqueeControl` 컨트롤과 해당 자식 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-347">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="e6a4b-348">편리 하 게 서비스를 제공 하는 디자인 타임 환경 <xref:System.ComponentModel.Design.IComponentChangeService>, 구성 요소 상태 변경 내용을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-348">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

 <span data-ttu-id="e6a4b-349">환경에 쿼리하여이 서비스에 대 한 참조를 획득 하는 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-349">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="e6a4b-350">쿼리가 성공 하는, 하는 경우 디자이너에 대 한 처리기를 연결할 수는 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 이벤트 및 디자인 타임에 일관 된 상태로 유지 하는 데 필요한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-350">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

 <span data-ttu-id="e6a4b-351">경우는 `MarqueeControlRootDesigner` 클래스를 호출 합니다 <xref:System.Windows.Forms.Control.Refresh%2A> 각 메서드 `IMarqueeWidget` 에 포함 된 개체는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-351">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="e6a4b-352">그러면 합니다 `IMarqueeWidget` 속성 같은 부모 항목의 경우 자체 적절 하 게 다시 표시할 개체 <xref:System.Windows.Forms.Control.Size%2A> 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-352">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="e6a4b-353">구성 요소 변경을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-353">To handle component changes</span></span>

1. <span data-ttu-id="e6a4b-354">열기를 `MarqueeControlRootDesigner` 소스 파일을 **코드 편집기** 재정의 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-354">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="e6a4b-355">기본 구현을 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 용 하 고 쿼리를 <xref:System.ComponentModel.Design.IComponentChangeService>입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-355">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="e6a4b-356">구현 된 <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-356">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="e6a4b-357">보내는 구성 요소의 형식을 테스트 하 고는 `IMarqueeWidget`, 호출 해당 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-357">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="e6a4b-358">사용자 지정 디자이너에 추가할 디자이너 동사</span><span class="sxs-lookup"><span data-stu-id="e6a4b-358">Adding Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="e6a4b-359">디자이너 동사는 이벤트 처리기에 연결 된 메뉴 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-359">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="e6a4b-360">디자이너 동사는 디자인 타임 구성 요소의 바로 가기 메뉴에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-360">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="e6a4b-361">자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-361">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="e6a4b-362">디자이너에 두 개의 디자이너 동사를 추가 합니다. **테스트 실행** 하 고 **테스트 중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-362">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="e6a4b-363">런타임 동작을 볼 수 있습니다 이러한 동사는 `MarqueeControl` 디자인 타임.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-363">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="e6a4b-364">에 추가할 이러한 동사는 `MarqueeControlRootDesigner`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-364">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="e6a4b-365">때 **테스트 실행** 는 호출 동사 이벤트 처리기를 호출 합니다 `StartMarquee` 메서드를는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-365">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="e6a4b-366">때 **테스트 중지** 는 호출 동사 이벤트 처리기를 호출 합니다 `StopMarquee` 메서드를는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-366">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="e6a4b-367">구현의 합니다 `StartMarquee` 및 `StopMarquee` 메서드를 구현 하는 포함 된 컨트롤에서 이러한 메서드를 호출할 `IMarqueeWidget`하므로 포함 된 모든, `IMarqueeWidget` 컨트롤은 테스트에도 참여.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-367">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="e6a4b-368">디자이너 동사 사용자 지정 디자이너를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-368">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="e6a4b-369">에 `MarqueeControlRootDesigner` 클래스 라는 이벤트 처리기를 추가 합니다 `OnVerbRunTest` 고 `OnVerbStopTest`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-369">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="e6a4b-370">해당 디자이너 동사에 이러한 이벤트 처리기를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-370">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="e6a4b-371">`MarqueeControlRootDesigner` 상속을 <xref:System.ComponentModel.Design.DesignerVerbCollection> 해당 기본 클래스에서입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-371">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="e6a4b-372">만든 두 개의 새 <xref:System.ComponentModel.Design.DesignerVerb> 개체에서이 컬렉션에 추가 하 여 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-372">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="e6a4b-373">사용자 지정 UITypeEditor 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-373">Creating a Custom UITypeEditor</span></span>

<span data-ttu-id="e6a4b-374">사용자에 대 한 사용자 지정 디자인 타임 환경을 만들 때 속성 창 사용 하 여 사용자 지정 상호 작용을 만드는 것이 좋은 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-374">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="e6a4b-375">만들어이 수행할 수 있습니다는 <xref:System.Drawing.Design.UITypeEditor>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-375">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="e6a4b-376">자세한 내용은 [방법: UI 형식 편집기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120))합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-376">For more information, see [How to: Create a UI Type Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).</span></span>

<span data-ttu-id="e6a4b-377">`MarqueeBorder` 컨트롤 속성 창의 여러 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-377">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="e6a4b-378">이러한 속성 중 두 가지 `MarqueeSpinDirection` 고 `MarqueeLightShape` 열거형으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-378">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="e6a4b-379">UI 형식 편집기를 사용에 설명 하는 `MarqueeLightShape` 속성을 연결 해야 합니다. <xref:System.Drawing.Design.UITypeEditor> 클래스.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-379">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="e6a4b-380">사용자 지정 UI 형식 편집기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-380">To create a custom UI type editor</span></span>

1. <span data-ttu-id="e6a4b-381">열기는 `MarqueeBorder` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-381">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="e6a4b-382">정의에 `MarqueeBorder` 클래스를 호출 하는 클래스를 선언 `LightShapeEditor` 에서 파생 되는 <xref:System.Drawing.Design.UITypeEditor>합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-382">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="e6a4b-383">선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 이라는 인스턴스 변수 `editorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-383">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="e6a4b-384"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-384">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="e6a4b-385">이 구현은 <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, 디자인 환경에서 표시 하는 방법을 알려는 `LightShapeEditor`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-385">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="e6a4b-386"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-386">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="e6a4b-387">이 구현은 디자인 환경에 대 한 쿼리는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-387">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="e6a4b-388">성공 하면 만듭니다는 `LightShapeSelectionControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-388">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="e6a4b-389">합니다 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> 메서드를 호출을 시작 하는 `LightShapeEditor`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-389">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="e6a4b-390">이 호출의 반환 값은 디자인 환경에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-390">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="e6a4b-391">사용자 지정 UITypeEditor 프로그램에 대 한 뷰 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-391">Creating a View Control for your Custom UITypeEditor</span></span>

1. <span data-ttu-id="e6a4b-392">`MarqueeLightShape` 속성은 두 가지 유형의 밝은 셰이프를 지원 합니다. `Square` 및 `Circle`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-392">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="e6a4b-393">속성 창에서 이러한 값을 그래픽으로 표시 하기 위한 용도로 사용 되는 사용자 지정 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-393">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="e6a4b-394">이 사용자 지정 컨트롤에서 사용할 프로그램 <xref:System.Drawing.Design.UITypeEditor> 속성 창을 사용 하 여 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-394">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="e6a4b-395">뷰 컨트롤에 대해 만들려는 사용자 지정 UI 형식 편집기</span><span class="sxs-lookup"><span data-stu-id="e6a4b-395">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="e6a4b-396">새 <xref:System.Windows.Forms.UserControl> 항목을 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-396">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-397">새 소스 파일 "쿼리에 성공 합니다."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="e6a4b-397">Give the new source file a base name of "LightShapeSelectionControl."</span></span>

2. <span data-ttu-id="e6a4b-398">두 개 <xref:System.Windows.Forms.Panel> 에서 제어 합니다 **도구 상자** 에 `LightShapeSelectionControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-398">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="e6a4b-399">해당 이름을 `squarePanel` 고 `circlePanel`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-399">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="e6a4b-400">나란히 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-400">Arrange them side by side.</span></span> <span data-ttu-id="e6a4b-401">설정 합니다 <xref:System.Windows.Forms.Control.Size%2A> 속성은 <xref:System.Windows.Forms.Panel> 컨트롤 (60, 60).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-401">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="e6a4b-402">설정 합니다 <xref:System.Windows.Forms.Control.Location%2A> 속성의는 `squarePanel` 컨트롤 (8, 10).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-402">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="e6a4b-403">설정 합니다 <xref:System.Windows.Forms.Control.Location%2A> 속성의는 `circlePanel` 컨트롤 (80, 10).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-403">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="e6a4b-404">마지막으로 설정 합니다 <xref:System.Windows.Forms.Control.Size%2A> 속성의는 `LightShapeSelectionControl` 를 (150, 80).</span><span class="sxs-lookup"><span data-stu-id="e6a4b-404">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>

3. <span data-ttu-id="e6a4b-405">열기는 `LightShapeSelectionControl` 소스 파일을 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-405">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="e6a4b-406">파일의 맨 위에 있는 가져오기는 <xref:System.Windows.Forms.Design?displayProperty=nameWithType> 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="e6a4b-406">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. <span data-ttu-id="e6a4b-407">구현 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기는 `squarePanel` 고 `circlePanel` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-407">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="e6a4b-408">이러한 메서드 호출 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> 사용자 지정 종료 <xref:System.Drawing.Design.UITypeEditor> 세션을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-408">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. <span data-ttu-id="e6a4b-409">선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 이라는 인스턴스 변수 `editorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-409">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. <span data-ttu-id="e6a4b-410">선언 된 `MarqueeLightShape` 이라는 인스턴스 변수 `lightShapeValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-410">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. <span data-ttu-id="e6a4b-411">에 `LightShapeSelectionControl` 생성자 연결 합니다 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를를 `squarePanel` 및 `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-411">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="e6a4b-412">또한 할당 하는 생성자 오버 로드를 정의 합니다 `MarqueeLightShape` 디자인 환경에서 값을 `lightShapeValue` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-412">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. <span data-ttu-id="e6a4b-413">에 <xref:System.ComponentModel.Component.Dispose%2A> 메서드를 분리 합니다 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-413">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. <span data-ttu-id="e6a4b-414">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-414">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="e6a4b-415">LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl.Designer.vb 파일을 열고 조건의 기본 정의 제거 합니다 <xref:System.ComponentModel.Component.Dispose%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-415">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

5. <span data-ttu-id="e6a4b-416">
  `LightShape\` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-416">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. <span data-ttu-id="e6a4b-417"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-417">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="e6a4b-418">이 구현은 속이 찬된 사각형 및 원을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-418">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="e6a4b-419">또한 선택한 값 주위의 테두리 모양을 또는 다른 그려 강조 표시 됩니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-419">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="e6a4b-420">디자이너에서 사용자 지정 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="e6a4b-420">Testing your Custom Control in the Designer</span></span>

<span data-ttu-id="e6a4b-421">이 시점에서 빌드할 수 있습니다는 `MarqueeControlLibrary` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-421">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="e6a4b-422">구현에서 상속 되는 컨트롤을 만들어 테스트를 `MarqueeControl` 클래스 및 폼에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-422">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="e6a4b-423">사용자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e6a4b-423">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="e6a4b-424">Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-424">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="e6a4b-425">인스턴스를 만들고이 `DemoMarqueeControl` 입력 하 고 인스턴스의 표시는 `MarqueeControlRootDesigner` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-425">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="e6a4b-426">에 **도구 상자**오픈 합니다 **MarqueeControlLibrary 구성 요소** 탭. 표시 됩니다는 `MarqueeBorder` 및 `MarqueeText` 컨트롤을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-426">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="e6a4b-427">인스턴스를 드래그 합니다 `MarqueeBorder` 컨트롤을 `DemoMarqueeControl` 디자인 화면.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-427">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="e6a4b-428">이 도킹 `MarqueeBorder` 컨트롤을 부모 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-428">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="e6a4b-429">인스턴스를 드래그 합니다 `MarqueeText` 컨트롤을 `DemoMarqueeControl` 디자인 화면.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-429">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="e6a4b-430">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-430">Build the solution.</span></span>

6. <span data-ttu-id="e6a4b-431">마우스 오른쪽 단추로 클릭 합니다 `DemoMarqueeControl` 와 바로 가기 메뉴에서에서를 **테스트 실행** 애니메이션을 시작 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-431">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="e6a4b-432">클릭 **테스트 중지** 여 애니메이션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-432">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="e6a4b-433">디자인 뷰에서 **Form1**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-433">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="e6a4b-434">두 개의 배치 <xref:System.Windows.Forms.Button> 폼의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-434">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="e6a4b-435">이름을 지정 하 여 `startButton` 및 `stopButton`를 변경 합니다 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 **시작** 및 **중지**, 각각.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-435">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="e6a4b-436">구현 <xref:System.Windows.Forms.Control.Click> 둘 다에 대 한 이벤트 처리기 <xref:System.Windows.Forms.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-436">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="e6a4b-437">에 **도구 상자**오픈 합니다 **MarqueeControlTest 구성 요소** 탭. 표시 됩니다는 `DemoMarqueeControl` 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-437">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="e6a4b-438">인스턴스를 끌어 `DemoMarqueeControl` 에 **Form1** 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-438">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="e6a4b-439">에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 호출 합니다 `Start` 및 `Stop` 메서드를 `DemoMarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-439">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

```vb
Private Sub startButton_Click(sender As Object, e As System.EventArgs)
    Me.demoMarqueeControl1.Start()
End Sub 'startButton_Click

Private Sub stopButton_Click(sender As Object, e As System.EventArgs)
Me.demoMarqueeControl1.Stop()
End Sub 'stopButton_Click
```

```csharp
private void startButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Start();
}

private void stopButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Stop();
}
```

1. <span data-ttu-id="e6a4b-440">설정 된 `MarqueeControlTest` 시작 프로젝트와 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-440">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="e6a4b-441">표시 하는 폼을 보면 프로그램 `DemoMarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-441">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="e6a4b-442">클릭 합니다 **시작** 애니메이션을 시작 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-442">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="e6a4b-443">깜박이 텍스트와 테두리 이동 광원 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-443">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6a4b-444">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e6a4b-444">Next Steps</span></span>

<span data-ttu-id="e6a4b-445">`MarqueeControlLibrary` 사용자 지정 컨트롤과 연결 된 디자이너의 간단한 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-445">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="e6a4b-446">여러 가지 방법으로이 샘플을 더 복잡 한 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-446">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="e6a4b-447">에 대 한 속성 값을 변경 합니다 `DemoMarqueeControl` 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-447">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="e6a4b-448">추가 `MarqueBorder` 컨트롤과 중첩된 효과를 만들려면 해당 부모 인스턴스 내에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-448">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="e6a4b-449">에 대 한 다른 설정 사용 하 여 실험을 `UpdatePeriod` 및 조명 관련 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-449">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="e6a4b-450">고유한 구현을 작성 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-450">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="e6a4b-451">예를 들어, 깜박이 "neon 로그인" 또는 애니메이션된 사인 여러 이미지를 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-451">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="e6a4b-452">추가 디자인 타임 환경을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-452">Further customize the design-time experience.</span></span> <span data-ttu-id="e6a4b-453">보다 더 많은 속성을 숨기기를 시도할 수 있습니다 <xref:System.Windows.Forms.Control.Enabled%2A> 고 <xref:System.Windows.Forms.Control.Visible%2A>, 및 새 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-453">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="e6a4b-454">자식 컨트롤을 도킹 등의 일반적인 작업을 간소화 하기 위해 새 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-454">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="e6a4b-455">라이선스는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-455">License the `MarqueeControl`.</span></span> <span data-ttu-id="e6a4b-456">자세한 내용은 [방법: 구성 요소 및 컨트롤 라이선스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-456">For more information, see [How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).</span></span>

- <span data-ttu-id="e6a4b-457">컨트롤은 직렬화 하는 방법 및 코드에 생성 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-457">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="e6a4b-458">자세한 내용은 [동적 소스 코드 생성 및 컴파일](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a4b-458">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6a4b-459">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6a4b-459">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- <span data-ttu-id="e6a4b-460">[방법: 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e6a4b-460">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>
- <span data-ttu-id="e6a4b-461">[디자인 타임 지원 확장](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e6a4b-461">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- <span data-ttu-id="e6a4b-462">[사용자 지정 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e6a4b-462">[Custom Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))</span></span>
