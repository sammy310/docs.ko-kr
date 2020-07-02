---
title: Visual Studio 디자인 타임 기능을 활용 하는 컨트롤 만들기
description: 디자인 타임 기능을 활용 하는 Windows Forms에서 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법에 대해 알아봅니다.
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 03c04578ecb01b689f58d41a46eef5793fb1182c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613912"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a><span data-ttu-id="4bf8b-103">연습: 디자인 타임 기능을 활용 하는 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-103">Walkthrough: Create a control that takes advantage of design-time features</span></span>

<span data-ttu-id="4bf8b-104">연결 된 사용자 지정 디자이너를 작성 하 여 사용자 지정 컨트롤에 대 한 디자인 타임 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-104">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="4bf8b-105">이 문서에서는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-105">This article illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="4bf8b-106">`MarqueeControl`이라는 형식과 연결 된 디자이너 클래스를 구현 `MarqueeControlRootDesigner` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-106">You'll implement a `MarqueeControl` type and an associated designer class called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="4bf8b-107">이 `MarqueeControl` 형식은 애니메이션 광원 및 깜박이는 텍스트를 포함 하는 극장 움직이는 텍스트와 비슷한 표시를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-107">The `MarqueeControl` type implements a display similar to a theater marquee with animated lights and flashing text.</span></span>

<span data-ttu-id="4bf8b-108">이 컨트롤의 디자이너는 디자인 환경과 상호 작용 하 여 사용자 지정 디자인 타임 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-108">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="4bf8b-109">사용자 지정 디자이너를 사용 하 여 `MarqueeControl` 애니메이션 조명 및 깜박이는 텍스트가 포함 된 사용자 지정 구현을 여러 조합으로 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-109">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="4bf8b-110">다른 Windows Forms 컨트롤과 마찬가지로 폼에서 어셈블된 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-110">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="4bf8b-111">이 연습을 완료 하면 사용자 지정 컨트롤은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-111">When you're finished with this walkthrough, your custom control will look something like the following:</span></span>

![텍스트 및 시작 및 중지 단추를 표시 하는 앱입니다.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="4bf8b-113">전체 코드 목록은 [방법: 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-113">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bf8b-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="4bf8b-114">Prerequisites</span></span>

<span data-ttu-id="4bf8b-115">이 연습을 완료 하려면 Visual Studio가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-115">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="4bf8b-116">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-116">Create the project</span></span>

<span data-ttu-id="4bf8b-117">첫 번째 단계에서는 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-117">The first step is to create the application project.</span></span> <span data-ttu-id="4bf8b-118">이 프로젝트를 사용 하 여 사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="4bf8b-119">Visual Studio에서 새 Windows Forms 응용 프로그램 프로젝트를 만들고 이름을 **MarqueeControlTest**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-119">In Visual Studio, create a new Windows Forms Application project, and name it **MarqueeControlTest**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="4bf8b-120">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-120">Create the control library project</span></span>

1. <span data-ttu-id="4bf8b-121">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-121">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="4bf8b-122">프로젝트 이름을 **MarqueeControlLibrary**로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-122">Name the project **MarqueeControlLibrary**.</span></span>

2. <span data-ttu-id="4bf8b-123">**솔루션 탐색기**를 사용 하 여 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1" 인 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-123">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

3. <span data-ttu-id="4bf8b-124"><xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-124">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-125">새 소스 파일에 **MarqueeControl**의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-125">Give the new source file a base name of **MarqueeControl**.</span></span>

4. <span data-ttu-id="4bf8b-126">**솔루션 탐색기**를 사용 하 여 프로젝트에 새 폴더를 만듭니다 `MarqueeControlLibrary` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-126">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span>

5. <span data-ttu-id="4bf8b-127">**디자인** 폴더를 마우스 오른쪽 단추로 클릭 하 고 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-127">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="4bf8b-128">이름을 **MarqueeControlRootDesigner**로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-128">Name it **MarqueeControlRootDesigner**.</span></span>

6. <span data-ttu-id="4bf8b-129">이 참조를 프로젝트에 추가 하려면 System.web 어셈블리의 형식을 사용 해야 합니다. `MarqueeControlLibrary`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-129">You'll need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

## <a name="reference-the-custom-control-project"></a><span data-ttu-id="4bf8b-130">사용자 지정 컨트롤 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="4bf8b-130">Reference the Custom Control Project</span></span>

<span data-ttu-id="4bf8b-131">프로젝트를 사용 하 여 `MarqueeControlTest` 사용자 지정 컨트롤을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-131">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="4bf8b-132">프로젝트에 프로젝트 참조를 추가할 때 테스트 프로젝트가 사용자 지정 컨트롤을 인식 합니다 `MarqueeControlLibrary` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-132">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

<span data-ttu-id="4bf8b-133">프로젝트에서 `MarqueeControlTest` 어셈블리에 대 한 프로젝트 참조를 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-133">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="4bf8b-134">어셈블리를 직접 참조 하는 대신 **참조 추가** 대화 상자의 **프로젝트** 탭을 사용 해야 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-134">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="4bf8b-135">사용자 지정 컨트롤 및 사용자 지정 디자이너 정의</span><span class="sxs-lookup"><span data-stu-id="4bf8b-135">Define a Custom Control and Its Custom Designer</span></span>

<span data-ttu-id="4bf8b-136">사용자 지정 컨트롤은 클래스에서 파생 됩니다 <xref:System.Windows.Forms.UserControl> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-136">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="4bf8b-137">이를 통해 컨트롤에 다른 컨트롤을 포함 하 고 컨트롤에 많은 기본 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-137">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

<span data-ttu-id="4bf8b-138">사용자 지정 컨트롤에는 연결 된 사용자 지정 디자이너가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-138">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="4bf8b-139">이렇게 하면 사용자 지정 컨트롤에 맞게 특별히 조정 된 고유한 디자인 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-139">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

<span data-ttu-id="4bf8b-140">클래스를 사용 하 여 컨트롤을 해당 디자이너와 연결 합니다 <xref:System.ComponentModel.DesignerAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-140">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="4bf8b-141">사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발 하는 중 이므로 사용자 지정 디자이너는 인터페이스를 구현 합니다 <xref:System.ComponentModel.Design.IRootDesigner> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-141">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="4bf8b-142">사용자 지정 컨트롤 및 사용자 지정 디자이너를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-142">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="4bf8b-143">`MarqueeControl` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-143">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-144">파일의 맨 위에 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-144">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="4bf8b-145"><xref:System.ComponentModel.DesignerAttribute>클래스 선언에를 추가 합니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-145">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="4bf8b-146">이렇게 하면 사용자 지정 컨트롤이 해당 디자이너에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-146">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="4bf8b-147">`MarqueeControlRootDesigner` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-147">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-148">파일의 맨 위에 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-148">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="4bf8b-149">`MarqueeControlRootDesigner`클래스에서 상속 하도록의 선언을 변경 합니다 <xref:System.Windows.Forms.Design.DocumentDesigner> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-149">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="4bf8b-150"><xref:System.ComponentModel.ToolboxItemFilterAttribute> **도구 상자**를 사용 하 여 디자이너 상호 작용을 지정 하려면를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-150">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4bf8b-151">클래스에 대 한 정의가 `MarqueeControlRootDesigner` MarqueeControlLibrary 라는 네임 스페이스에 포함 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-151">The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called MarqueeControlLibrary.Design.</span></span> <span data-ttu-id="4bf8b-152">이 선언은 디자인 관련 형식에 대해 예약 된 특수 네임 스페이스에 디자이너를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-152">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="4bf8b-153">클래스에 대 한 생성자를 정의 `MarqueeControlRootDesigner` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-153">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="4bf8b-154"><xref:System.Diagnostics.Trace.WriteLine%2A>생성자 본문에 문을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-154">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="4bf8b-155">이는 디버깅에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-155">This will be useful for debugging.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a><span data-ttu-id="4bf8b-156">사용자 지정 컨트롤의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-156">Create an instance of your custom control</span></span>

1. <span data-ttu-id="4bf8b-157"><xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlTest` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-157">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="4bf8b-158">새 소스 파일에 **DemoMarqueeControl**의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-158">Give the new source file a base name of **DemoMarqueeControl**.</span></span>

2. <span data-ttu-id="4bf8b-159">`DemoMarqueeControl` **코드 편집기**에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-159">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-160">파일 맨 위에서 `MarqueeControlLibrary` 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-160">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. <span data-ttu-id="4bf8b-161">`DemoMarqueeControl`클래스에서 상속 하도록의 선언을 변경 합니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-161">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

4. <span data-ttu-id="4bf8b-162">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-162">Build the project.</span></span>

5. <span data-ttu-id="4bf8b-163">Windows Forms 디자이너에서 Form1을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-163">Open Form1 in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="4bf8b-164">**도구 상자** 에서 **MarqueeControlTest 구성 요소** 탭을 찾아 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-164">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="4bf8b-165">를 `DemoMarqueeControl` **도구 상자** 에서 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-165">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

7. <span data-ttu-id="4bf8b-166">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-166">Build the project.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="4bf8b-167">디자인 타임 디버깅을 위한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="4bf8b-167">Set Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="4bf8b-168">사용자 지정 디자인 타임 환경을 개발 하는 경우에는 컨트롤과 구성 요소를 디버깅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-168">When you're developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="4bf8b-169">디자인 타임에 디버깅을 허용 하도록 프로젝트를 설정 하는 간단한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-169">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="4bf8b-170">자세한 내용은 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버그](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-170">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

1. <span data-ttu-id="4bf8b-171">프로젝트를 마우스 오른쪽 단추로 클릭 `MarqueeControlLibrary` 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-171">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="4bf8b-172">**MarqueeControlLibrary 속성 페이지** 대화 상자에서 **디버그** 페이지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-172">In the **MarqueeControlLibrary Property Pages** dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="4bf8b-173">**시작 작업** 섹션에서 **시작 외부 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-173">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="4bf8b-174">Visual studio의 개별 인스턴스를 디버깅 하 게 되므로 visual studio IDE를 찾아보려면 줄임표 ( ![ Visual studio 속성 창의 줄임표 단추 (...)) 단추를 클릭 합니다 ](./media/visual-studio-ellipsis-button.png) .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-174">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="4bf8b-175">실행 파일의 이름은 devenv.exe 이며,를 기본 위치에 설치한 경우 해당 경로는 *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition>\Common7\IDE\devenv.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-175">The name of the executable file is devenv.exe, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE\devenv.exe*.</span></span>

4. <span data-ttu-id="4bf8b-176">**확인**을 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-176">Select **OK** to close the dialog box.</span></span>

5. <span data-ttu-id="4bf8b-177">MarqueeControlLibrary 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택 하 여이 디버깅 구성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-177">Right-click the MarqueeControlLibrary project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="4bf8b-178">검사점</span><span class="sxs-lookup"><span data-stu-id="4bf8b-178">Checkpoint</span></span>

<span data-ttu-id="4bf8b-179">이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버그할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-179">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="4bf8b-180">디버깅 환경이 올바르게 설정 된 것으로 확인 되 면 사용자 지정 컨트롤과 사용자 지정 디자이너 간의 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-180">Once you've determined that the debugging environment is set up correctly, you'll test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="4bf8b-181">디버깅 환경 및 디자이너 연결을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-181">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="4bf8b-182">**코드 편집기** 에서 MarqueeControlRootDesigner 소스 파일을 열고 문에 중단점을 설정 <xref:System.Diagnostics.Trace.WriteLine%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-182">Open the MarqueeControlRootDesigner source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="4bf8b-183">**F5** 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-183">Press **F5** to start the debugging session.</span></span>

   <span data-ttu-id="4bf8b-184">Visual Studio의 새 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-184">A new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="4bf8b-185">Visual Studio의 새 인스턴스에서 MarqueeControlTest 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-185">In the new instance of Visual Studio, open the MarqueeControlTest solution.</span></span> <span data-ttu-id="4bf8b-186">**파일** 메뉴에서 **최근 프로젝트** 를 선택 하 여 솔루션을 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-186">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="4bf8b-187">MarqueeControlTest 솔루션 파일이 가장 최근에 사용 된 파일로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-187">The MarqueeControlTest.sln solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="4bf8b-188">`DemoMarqueeControl`디자이너에서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-188">Open the `DemoMarqueeControl` in the designer.</span></span>

   <span data-ttu-id="4bf8b-189">Visual Studio의 디버깅 인스턴스는 중단점에서 포커스를 가져오고 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-189">The debugging instance of Visual Studio obtains focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="4bf8b-190">**F5** 키를 눌러 디버깅 세션을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-190">Press **F5** to continue the debugging session.</span></span>

<span data-ttu-id="4bf8b-191">이 시점에서 모든 항목은 사용자 지정 컨트롤 및 이와 관련 된 사용자 지정 디자이너를 개발 하 고 디버그할 수 있도록 준비 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-191">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="4bf8b-192">이 문서의 나머지 부분에서는 컨트롤 및 디자이너의 기능 구현에 대 한 세부 정보를 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-192">The remainder of this article concentrates on the details of implementing features of the control and the designer.</span></span>

## <a name="implement-the-custom-control"></a><span data-ttu-id="4bf8b-193">사용자 지정 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="4bf8b-193">Implement the Custom Control</span></span>

<span data-ttu-id="4bf8b-194">는 `MarqueeControl` <xref:System.Windows.Forms.UserControl> 약간의 사용자 지정을 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-194">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="4bf8b-195">이는 `Start` 움직이는 텍스트 애니메이션을 시작 하는와 애니메이션을 중지 하는 라는 두 개의 메서드를 노출 합니다. `Stop`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-195">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="4bf8b-196">는 `MarqueeControl` 인터페이스를 구현 하는 자식 컨트롤을 포함 하므로를 `IMarqueeWidget` `Start` `Stop` `StartMarquee` `StopMarquee` 구현 하는 각 자식 컨트롤에서 각 자식 컨트롤을 열거 하 고 및 메서드를 각각 호출 `IMarqueeWidget` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-196">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="4bf8b-197">및 컨트롤의 모양은 `MarqueeBorder` `MarqueeText` 레이아웃에 따라 달라 지므로 메서드를 재정의 하 `MarqueeControl` <xref:System.Windows.Forms.Control.OnLayout%2A> 고 <xref:System.Windows.Forms.Control.PerformLayout%2A> 이 형식의 자식 컨트롤에 대해를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-197">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="4bf8b-198">사용자 지정의 범위입니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-198">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="4bf8b-199">런타임 기능은 및 컨트롤에서 구현 되며 `MarqueeBorder` `MarqueeText` 디자인 타임 기능은 및 클래스에 의해 구현 됩니다 `MarqueeBorderDesigner` `MarqueeControlRootDesigner` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-199">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="4bf8b-200">사용자 지정 컨트롤을 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-200">To implement your custom control</span></span>

1. <span data-ttu-id="4bf8b-201">`MarqueeControl` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-201">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-202">`Start`및 메서드를 구현 `Stop` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-202">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="4bf8b-203"><xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-203">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a><span data-ttu-id="4bf8b-204">사용자 지정 컨트롤에 대 한 자식 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-204">Create a Child Control for Your Custom Control</span></span>

<span data-ttu-id="4bf8b-205">는 `MarqueeControl` 컨트롤 및 컨트롤과 같은 두 가지 종류의 자식 컨트롤을 호스팅합니다 `MarqueeBorder` `MarqueeText` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-205">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="4bf8b-206">`MarqueeBorder`:이 컨트롤은 가장자리 주위에 "광원" 테두리를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-206">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="4bf8b-207">광원은 순서 대로 깜박이 므로 테두리를 중심으로 이동 하는 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-207">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="4bf8b-208">광원의 속도는 라는 속성에 의해 제어 됩니다 `UpdatePeriod` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-208">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="4bf8b-209">다른 여러 사용자 지정 속성은 컨트롤의 모양에 대 한 다른 측면을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-209">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="4bf8b-210">및 라는 두 메서드 `StartMarquee` `StopMarquee` 는 애니메이션이 시작 되 고 중지 되는 시기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-210">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="4bf8b-211">`MarqueeText`:이 컨트롤은 깜박이는 문자열을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-211">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="4bf8b-212">컨트롤과 마찬가지로 `MarqueeBorder` 텍스트가 깜박이는 속도는 속성에 의해 제어 됩니다 `UpdatePeriod` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-212">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="4bf8b-213">컨트롤에는 컨트롤과 `MarqueeText` `StartMarquee` 공통적인 및 `StopMarquee` 메서드도 있습니다 `MarqueeBorder` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-213">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="4bf8b-214">디자인 타임에를 `MarqueeControlRootDesigner` 사용 하면 이러한 두 컨트롤 형식을 모든 조합으로에 추가할 수 있습니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-214">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="4bf8b-215">두 컨트롤의 공통 기능은 이라는 인터페이스로 팩터링 됩니다 `IMarqueeWidget` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-215">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="4bf8b-216">이렇게 하면에서 `MarqueeControl` 움직이는 텍스트와 관련 된 자식 컨트롤을 검색 하 고 특수 한 처리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-216">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="4bf8b-217">정기 애니메이션 기능을 구현 하려면 <xref:System.ComponentModel.BackgroundWorker> 네임 스페이스의 개체를 사용 합니다 <xref:System.ComponentModel?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-217">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4bf8b-218"><xref:System.Windows.Forms.Timer>개체를 사용할 수 있지만 많은 개체가 있을 경우 `IMarqueeWidget` 단일 UI 스레드가 애니메이션을 유지 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-218">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="4bf8b-219">사용자 지정 컨트롤에 대 한 자식 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-219">To create a child control for your custom control</span></span>

1. <span data-ttu-id="4bf8b-220">프로젝트에 새 클래스 항목을 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-220">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-221">새 소스 파일에 "IMarqueeWidget"의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-221">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="4bf8b-222">`IMarqueeWidget` **코드 편집기** 에서 소스 파일을 열고 선언을에서로 변경 합니다 `class` `interface` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-222">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="4bf8b-223">다음 코드를 인터페이스에 추가 `IMarqueeWidget` 하 여 두 개의 메서드와 marquee 애니메이션을 조작 하는 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-223">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="4bf8b-224">프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-224">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-225">새 소스 파일에 "MarqueeText"의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-225">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="4bf8b-226"><xref:System.ComponentModel.BackgroundWorker>구성 요소를 **도구 상자** 에서 컨트롤로 끌어 옵니다 `MarqueeText` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-226">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="4bf8b-227">이 구성 요소는 `MarqueeText` 컨트롤을 비동기적으로 업데이트 하는 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-227">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="4bf8b-228">**속성** 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 **true**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-228">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="4bf8b-229">이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 정기적으로 이벤트를 발생 시키고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 비동기 업데이트를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-229">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span>

   <span data-ttu-id="4bf8b-230">자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-230">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="4bf8b-231">`MarqueeText` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-231">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-232">파일의 맨 위에 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-232">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="4bf8b-233">인터페이스를 구현 하기 위해 `MarqueeText` 및에서 상속 하도록의 선언을 변경 합니다 <xref:System.Windows.Forms.Label> `IMarqueeWidget` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-233">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="4bf8b-234">노출 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-234">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="4bf8b-235">`isLit`필드는 속성에 지정 된 색으로 텍스트를 그릴지 여부를 결정 `LightColor` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-235">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="4bf8b-236">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-236">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="4bf8b-237">`StartMarquee`및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 메서드를 호출 하 여 애니메이션을 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-237">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="4bf8b-238"><xref:System.ComponentModel.CategoryAttribute.Category%2A>및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 속성에 적용 `UpdatePeriod` 되므로 "움직이는 텍스트" 라는 속성 창의 사용자 지정 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-238">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="4bf8b-239">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-239">Implement the property accessors.</span></span> <span data-ttu-id="4bf8b-240">클라이언트에 및 라는 두 가지 속성을 `LightColor` 노출 `DarkColor` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-240">You'll expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="4bf8b-241"><xref:System.ComponentModel.CategoryAttribute.Category%2A>및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 이러한 속성에 적용 되므로 "움직이는 텍스트" 라는 속성 창의 사용자 지정 섹션에 속성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-241">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="4bf8b-242">구성 요소의 및 이벤트에 대 한 처리기를 구현 <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-242">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="4bf8b-243"><xref:System.ComponentModel.BackgroundWorker.DoWork>가를 `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 호출 하 여 코드에서 애니메이션을 중지할 때까지 이벤트 처리기는에서 지정 된 시간 (밀리초) 동안 대기 하 고 이벤트를 발생 시킵니다 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-243">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="4bf8b-244"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>이벤트 처리기는 밝은 상태와 어두운 상태 사이에서 텍스트를 전환 하 여 깜빡이는 모양을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-244">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="4bf8b-245">애니메이션을 <xref:System.Windows.Forms.Control.OnPaint%2A> 사용 하도록 설정 하려면 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-245">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="4bf8b-246">**F6** 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-246">Press **F6** to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="4bf8b-247">MarqueeBorder 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-247">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="4bf8b-248">컨트롤은 `MarqueeBorder` 컨트롤 보다 약간 더 정교 합니다 `MarqueeText` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-248">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="4bf8b-249">이 클래스에는 더 많은 속성이 있으며 메서드의 애니메이션은 <xref:System.Windows.Forms.Control.OnPaint%2A> 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-249">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="4bf8b-250">원칙적으로는 컨트롤과 매우 유사 `MarqueeText` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-250">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="4bf8b-251">컨트롤은 `MarqueeBorder` 자식 컨트롤을 가질 수 있으므로 이벤트를 인식 해야 <xref:System.Windows.Forms.Control.Layout> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-251">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="4bf8b-252">MarqueeBorder 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-252">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="4bf8b-253">프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-253">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-254">새 소스 파일에 "MarqueeBorder"의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-254">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="4bf8b-255"><xref:System.ComponentModel.BackgroundWorker>구성 요소를 **도구 상자** 에서 컨트롤로 끌어 옵니다 `MarqueeBorder` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-255">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="4bf8b-256">이 구성 요소는 `MarqueeBorder` 컨트롤을 비동기적으로 업데이트 하는 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-256">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="4bf8b-257">**속성** 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgress` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 **true**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-257">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="4bf8b-258">이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소가 정기적으로 이벤트를 발생 시키고 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 비동기 업데이트를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-258">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="4bf8b-259">자세한 내용은 [BackgroundWorker 구성 요소](backgroundworker-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-259">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="4bf8b-260">**속성** 창에서 **이벤트** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-260">In the **Properties** window, select the **Events** button.</span></span> <span data-ttu-id="4bf8b-261">및 이벤트에 대 한 처리기를 연결 <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-261">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="4bf8b-262">`MarqueeBorder` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-262">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-263">파일의 맨 위에 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-263">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="4bf8b-264">를 `MarqueeBorder` 상속 하 고 인터페이스를 구현 하려면의 선언을 변경 합니다 <xref:System.Windows.Forms.Panel> `IMarqueeWidget` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-264">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="4bf8b-265">컨트롤의 상태를 관리 하는 두 개의 열거형을 선언 합니다 `MarqueeBorder` . `MarqueeSpinDirection` 즉, 조명이 테두리 주위에 "회전" 하는 방향을 결정 하 고는 `MarqueeLightShape` 광원의 모양 (사각형 또는 원형)을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-265">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="4bf8b-266">이러한 선언을 클래스 선언 앞에 추가 `MarqueeBorder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-266">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="4bf8b-267">노출 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-267">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="4bf8b-268">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-268">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="4bf8b-269">`StartMarquee`및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 메서드를 호출 하 여 애니메이션을 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 시작 및 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-269">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="4bf8b-270">컨트롤은 `MarqueeBorder` 자식 컨트롤을 포함할 수 있기 때문에 `StartMarquee` 메서드는 모든 자식 컨트롤을 열거 하 고를 `StartMarquee` 구현 하는 컨트롤에 대해를 호출 합니다 `IMarqueeWidget` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-270">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="4bf8b-271">`StopMarquee`메서드에는 비슷한 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-271">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="4bf8b-272">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-272">Implement the property accessors.</span></span> <span data-ttu-id="4bf8b-273">컨트롤에는 `MarqueeBorder` 모양을 제어 하는 여러 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-273">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="4bf8b-274">구성 요소의 및 이벤트에 대 한 처리기를 구현 <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-274">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="4bf8b-275"><xref:System.ComponentModel.BackgroundWorker.DoWork>가를 `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 호출 하 여 코드에서 애니메이션을 중지할 때까지 이벤트 처리기는에서 지정 된 시간 (밀리초) 동안 대기 하 고 이벤트를 발생 시킵니다 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-275">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="4bf8b-276"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>이벤트 처리기는 다른 조명의 밝은/어둡게 상태를 결정 하는 "기본" 조명의 위치를 증가 시키고 메서드를 호출 하 여 컨트롤이 자신을 다시 <xref:System.Windows.Forms.Control.Refresh%2A> 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-276">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="4bf8b-277">도우미 메서드인 및를 구현 `IsLit` `DrawLight` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-277">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="4bf8b-278">`IsLit`메서드는 지정 된 위치의 광원 색을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-278">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="4bf8b-279">"Lit" 인 광원은 속성에 지정 된 색으로 그려지고 `LightColor` , "짙은" 광원은 속성에 지정 된 색으로 그려집니다 `DarkColor` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-279">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="4bf8b-280">`DrawLight`메서드는 적절 한 색, 모양 및 위치를 사용 하 여 조명을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-280">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="4bf8b-281"><xref:System.Windows.Forms.Control.OnLayout%2A> 및 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-281">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="4bf8b-282"><xref:System.Windows.Forms.Control.OnPaint%2A>메서드는 컨트롤의 가장자리를 따라 조명을 그립니다 `MarqueeBorder` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-282">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="4bf8b-283">메서드는 <xref:System.Windows.Forms.Control.OnPaint%2A> 컨트롤의 크기에 따라 달라 지므로 `MarqueeBorder` 레이아웃이 변경 될 때마다이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-283">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="4bf8b-284">이를 위해서는를 재정의 하 <xref:System.Windows.Forms.Control.OnLayout%2A> 고를 호출 <xref:System.Windows.Forms.Control.Refresh%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-284">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="4bf8b-285">사용자 지정 디자이너를 만들어 속성을 숨기 고 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-285">Create a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="4bf8b-286">`MarqueeControlRootDesigner`클래스는 루트 디자이너에 대 한 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-286">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="4bf8b-287">에서 작동 하는이 디자이너 외에도 `MarqueeControl` 컨트롤에 특별히 연결 된 사용자 지정 디자이너가 필요 `MarqueeBorder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-287">In addition to this designer, which operates on the `MarqueeControl`, you'll need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="4bf8b-288">이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에 적합 한 사용자 지정 동작을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-288">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="4bf8b-289">특히은 `MarqueeBorderDesigner` `MarqueeBorder` 디자인 환경과의 상호 작용을 변경 하 여 컨트롤의 특정 속성을 "숨기" 고 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-289">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="4bf8b-290">구성 요소의 속성 접근자에 대 한 호출을 가로채는 "숨김" 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-290">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="4bf8b-291">이를 통해 디자이너는 사용자가 설정한 값을 추적 하 고 필요에 따라 디자인 되는 구성 요소에 해당 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-291">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="4bf8b-292">이 예제에서 <xref:System.Windows.Forms.Control.Visible%2A> 및 속성은 <xref:System.Windows.Forms.Control.Enabled%2A> 에 의해 숨겨집니다 `MarqueeBorderDesigner` . 그러면 사용자가 `MarqueeBorder` 디자인 타임에 컨트롤을 숨기 거 나 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-292">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="4bf8b-293">디자이너는 속성을 추가 하 고 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-293">Designers can also add and remove properties.</span></span> <span data-ttu-id="4bf8b-294">이 예제에서는 <xref:System.Windows.Forms.Control.Padding%2A> `MarqueeBorder` 컨트롤에서 속성에 지정 된 조명의 크기에 따라 프로그래밍 방식으로 안쪽 여백을 설정 하므로 디자인 타임에 속성이 제거 됩니다 `LightSize` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-294">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="4bf8b-295">의 기본 클래스는 `MarqueeBorderDesigner` <xref:System.ComponentModel.Design.ComponentDesigner> 디자인 타임에 컨트롤에 의해 노출 되는 특성, 속성 및 이벤트를 변경할 수 있는 메서드를 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-295">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="4bf8b-296">이러한 메서드를 사용 하 여 구성 요소의 공용 인터페이스를 변경 하는 경우 다음 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-296">When changing the public interface of a component using these methods, follow these rules:</span></span>

- <span data-ttu-id="4bf8b-297">메서드에만 항목 추가 또는 제거 `PreFilter`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-297">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="4bf8b-298">메서드의 기존 항목만 수정 `PostFilter`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-298">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="4bf8b-299">항상 메서드에서 기본 구현을 먼저 호출 합니다. `PreFilter`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-299">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="4bf8b-300">메서드의 마지막 기본 구현을 항상 호출 합니다. `PostFilter`</span><span class="sxs-lookup"><span data-stu-id="4bf8b-300">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="4bf8b-301">이러한 규칙을 준수 하면 디자인 타임 환경의 모든 디자이너에서 디자인 중인 모든 구성 요소를 일관 되 게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-301">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="4bf8b-302"><xref:System.ComponentModel.Design.ComponentDesigner>클래스는 숨겨진 속성의 값을 관리 하기 위한 사전을 제공 하므로 특정 인스턴스 변수를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-302">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="4bf8b-303">속성을 숨기고 필터링 하기 위한 사용자 지정 디자이너를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-303">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="4bf8b-304">**디자인** 폴더를 마우스 오른쪽 단추로 클릭 하 고 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-304">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="4bf8b-305">원본 파일에 **MarqueeBorderDesigner**의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-305">Give the source file a base name of **MarqueeBorderDesigner**.</span></span>

2. <span data-ttu-id="4bf8b-306">**코드 편집기**에서 MarqueeBorderDesigner 원본 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-306">Open the MarqueeBorderDesigner source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-307">파일의 맨 위에 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-307">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="4bf8b-308">의 선언을 `MarqueeBorderDesigner` 에서 상속 하도록 변경 <xref:System.Windows.Forms.Design.ParentControlDesigner> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-308">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="4bf8b-309">컨트롤은 `MarqueeBorder` 자식 컨트롤을 포함할 수 있으므로는 `MarqueeBorderDesigner` <xref:System.Windows.Forms.Design.ParentControlDesigner> 부모-자식 상호 작용을 처리 하는에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-309">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="4bf8b-310">의 기본 구현을 재정의 <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-310">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="4bf8b-311"><xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-311">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="4bf8b-312">이러한 구현은 컨트롤의 속성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-312">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a><span data-ttu-id="4bf8b-313">구성 요소 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="4bf8b-313">Handle Component Changes</span></span>

<span data-ttu-id="4bf8b-314">`MarqueeControlRootDesigner`클래스는 인스턴스에 대 한 사용자 지정 디자인 타임 환경을 제공 합니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-314">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="4bf8b-315">대부분의 디자인 타임 기능은 클래스에서 상속 됩니다 <xref:System.Windows.Forms.Design.DocumentDesigner> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-315">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="4bf8b-316">코드는 구성 요소 변경 내용 처리 및 디자이너 동사 추가와 같은 두 가지 특정 사용자 지정을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-316">Your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

<span data-ttu-id="4bf8b-317">사용자가 `MarqueeControl` 인스턴스를 디자인할 때 루트 디자이너는 `MarqueeControl` 및 해당 자식 컨트롤에 대 한 변경 내용을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-317">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="4bf8b-318">디자인 타임 환경은 <xref:System.ComponentModel.Design.IComponentChangeService> 구성 요소 상태에 대 한 변경 내용을 추적 하는 데 편리한 서비스인를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-318">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

<span data-ttu-id="4bf8b-319">메서드를 사용 하 여 환경을 쿼리하여이 서비스에 대 한 참조를 가져옵니다 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-319">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="4bf8b-320">쿼리가 성공 하면 디자이너는 이벤트에 대 한 처리기를 연결 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 하 고 디자인 타임에 일관 된 상태를 유지 하는 데 필요한 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-320">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

<span data-ttu-id="4bf8b-321">클래스의 경우에 `MarqueeControlRootDesigner` <xref:System.Windows.Forms.Control.Refresh%2A> 포함 된 각 개체에 대해 메서드를 호출 합니다 `IMarqueeWidget` `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-321">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="4bf8b-322">이렇게 하면 `IMarqueeWidget` 해당 부모와 같은 속성이 변경 될 때 개체 자체가 적절히 다시 그려집니다 <xref:System.Windows.Forms.Control.Size%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-322">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="4bf8b-323">구성 요소 변경을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-323">To handle component changes</span></span>

1. <span data-ttu-id="4bf8b-324">`MarqueeControlRootDesigner` **코드 편집기** 에서 소스 파일을 열고 메서드를 재정의 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-324">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="4bf8b-325">의 기본 구현을 호출 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 하 고를 쿼리 <xref:System.ComponentModel.Design.IComponentChangeService> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-325">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="4bf8b-326"><xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>이벤트 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-326">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="4bf8b-327">전송 구성 요소의 형식을 테스트 하 고, 인 경우 `IMarqueeWidget` 해당 메서드를 호출 <xref:System.Windows.Forms.Control.Refresh%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-327">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="4bf8b-328">사용자 지정 디자이너에 디자이너 동사 추가</span><span class="sxs-lookup"><span data-stu-id="4bf8b-328">Add Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="4bf8b-329">디자이너 동사는 이벤트 처리기에 연결된 메뉴 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-329">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="4bf8b-330">디자인 타임에 디자이너 동사가 구성 요소의 바로 가기 메뉴에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-330">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="4bf8b-331">자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-331">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="4bf8b-332">디자이너에는 **테스트 실행** 및 **테스트 중지**라는 두 개의 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-332">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="4bf8b-333">이러한 동사를 사용 하 여 디자인 타임에의 런타임 동작을 볼 수 있습니다 `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-333">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="4bf8b-334">이러한 동사는에 추가 됩니다 `MarqueeControlRootDesigner` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-334">These verbs will be added to `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="4bf8b-335">**테스트 실행** 이 호출 되 면 동사 이벤트 처리기가에서 메서드를 호출 합니다 `StartMarquee` `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-335">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="4bf8b-336">**테스트 중지** 가 호출 되 면 동사 이벤트 처리기가에서 메서드를 호출 합니다 `StopMarquee` `MarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-336">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="4bf8b-337">`StartMarquee`및 `StopMarquee` 메서드는를 구현 하는 포함 된 컨트롤에서 이러한 메서드를 호출 하 여 `IMarqueeWidget` 포함 된 `IMarqueeWidget` 컨트롤도 테스트에 참여 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-337">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="4bf8b-338">사용자 지정 디자이너에 디자이너 동사를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-338">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="4bf8b-339">클래스에서 `MarqueeControlRootDesigner` 및 라는 이벤트 처리기를 추가 `OnVerbRunTest` `OnVerbStopTest` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-339">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="4bf8b-340">이러한 이벤트 처리기를 해당 디자이너 동사에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-340">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="4bf8b-341">`MarqueeControlRootDesigner`<xref:System.ComponentModel.Design.DesignerVerbCollection>기본 클래스에서를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-341">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="4bf8b-342">새 개체 두 개를 만들고 <xref:System.ComponentModel.Design.DesignerVerb> 메서드에서이 컬렉션에 추가 합니다 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-342">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a><span data-ttu-id="4bf8b-343">사용자 지정 UITypeEditor 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-343">Create a Custom UITypeEditor</span></span>

<span data-ttu-id="4bf8b-344">사용자에 대 한 사용자 지정 디자인 타임 환경을 만들 때 속성 창와 사용자 지정 상호 작용을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-344">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="4bf8b-345">를 만들어이를 수행할 수 있습니다 <xref:System.Drawing.Design.UITypeEditor> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-345">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

<span data-ttu-id="4bf8b-346">`MarqueeBorder`컨트롤은 속성 창의 여러 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-346">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="4bf8b-347">이러한 속성 중 두 개 `MarqueeSpinDirection` `MarqueeLightShape` 는 열거형으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-347">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="4bf8b-348">UI 형식 편집기를 사용 하는 방법을 보여 주기 위해 `MarqueeLightShape` 속성에는 연결 된 <xref:System.Drawing.Design.UITypeEditor> 클래스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-348">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="4bf8b-349">사용자 지정 UI 형식 편집기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-349">To create a custom UI type editor</span></span>

1. <span data-ttu-id="4bf8b-350">`MarqueeBorder` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-350">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="4bf8b-351">클래스의 정의에서 `MarqueeBorder` `LightShapeEditor` 에서 파생 되는 이라는 클래스를 선언 합니다 <xref:System.Drawing.Design.UITypeEditor> .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-351">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="4bf8b-352"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService>라는 인스턴스 변수를 선언 `editorService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-352">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="4bf8b-353"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-353">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="4bf8b-354">이 구현에서는 <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> 을 표시 하는 방법을 디자인 환경에 알려 주는를 반환 합니다 `LightShapeEditor` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-354">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="4bf8b-355"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-355">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="4bf8b-356">이 구현은 디자인 환경에서 개체를 쿼리 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-356">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="4bf8b-357">성공 하면이 생성 `LightShapeSelectionControl` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-357">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="4bf8b-358"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>메서드를 호출 하 여를 시작 `LightShapeEditor` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-358">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="4bf8b-359">이 호출의 반환 값은 디자인 환경으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-359">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="4bf8b-360">사용자 지정 UITypeEditor에 대 한 뷰 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="4bf8b-360">Create a View Control for your Custom UITypeEditor</span></span>

<span data-ttu-id="4bf8b-361">`MarqueeLightShape`속성은 두 가지 유형의 조명 모양 `Square` 및를 지원 `Circle` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-361">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="4bf8b-362">속성 창에서 이러한 값을 그래픽으로 표시 하는 용도로만 사용 되는 사용자 지정 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-362">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="4bf8b-363">에서이 사용자 지정 컨트롤을 사용 <xref:System.Drawing.Design.UITypeEditor> 하 여 속성 창와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-363">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="4bf8b-364">사용자 지정 UI 형식 편집기에 대 한 뷰 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-364">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="4bf8b-365"><xref:System.Windows.Forms.UserControl>프로젝트에 새 항목을 추가 `MarqueeControlLibrary` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-365">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-366">새 소스 파일에 **LightShapeSelectionControl**의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-366">Give the new source file a base name of **LightShapeSelectionControl**.</span></span>

2. <span data-ttu-id="4bf8b-367"><xref:System.Windows.Forms.Panel> **도구 상자** 에서 두 컨트롤을로 끌어 옵니다 `LightShapeSelectionControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-367">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="4bf8b-368">및로 이름을로 `squarePanel` `circlePanel` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-368">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="4bf8b-369">나란히 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-369">Arrange them side by side.</span></span> <span data-ttu-id="4bf8b-370"><xref:System.Windows.Forms.Control.Size%2A>두 컨트롤의 속성을 <xref:System.Windows.Forms.Panel> **(60, 60)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-370">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to **(60, 60)**.</span></span> <span data-ttu-id="4bf8b-371"><xref:System.Windows.Forms.Control.Location%2A>컨트롤의 속성을 `squarePanel` **(8, 10)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-371">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to **(8, 10)**.</span></span> <span data-ttu-id="4bf8b-372"><xref:System.Windows.Forms.Control.Location%2A>컨트롤의 속성을 `circlePanel` **(80, 10)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-372">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to **(80, 10)**.</span></span> <span data-ttu-id="4bf8b-373">마지막으로 <xref:System.Windows.Forms.Control.Size%2A> 의 속성을 `LightShapeSelectionControl` **(150, 80)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-373">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to **(150, 80)**.</span></span>

3. <span data-ttu-id="4bf8b-374">`LightShapeSelectionControl` **코드 편집기**에서 소스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-374">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="4bf8b-375">파일 맨 위에서 <xref:System.Windows.Forms.Design?displayProperty=nameWithType> 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-375">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. <span data-ttu-id="4bf8b-376"><xref:System.Windows.Forms.Control.Click>및 컨트롤에 대 한 이벤트 처리기를 구현 `squarePanel` `circlePanel` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-376">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="4bf8b-377">이러한 메서드 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> 는를 호출 하 여 사용자 지정 <xref:System.Drawing.Design.UITypeEditor> 편집 세션을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-377">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. <span data-ttu-id="4bf8b-378"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService>라는 인스턴스 변수를 선언 `editorService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-378">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. <span data-ttu-id="4bf8b-379">`MarqueeLightShape`라는 인스턴스 변수를 선언 `lightShapeValue` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-379">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. <span data-ttu-id="4bf8b-380">생성자에서 `LightShapeSelectionControl` <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 `squarePanel` 및 컨트롤의 이벤트에 연결 `circlePanel` <xref:System.Windows.Forms.Control.Click> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-380">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="4bf8b-381">또한 `MarqueeLightShape` 디자인 환경에서 필드에 값을 할당 하는 생성자 오버 로드를 정의 합니다 `lightShapeValue` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-381">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. <span data-ttu-id="4bf8b-382"><xref:System.ComponentModel.Component.Dispose%2A>메서드에서 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-382">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. <span data-ttu-id="4bf8b-383">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-383">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="4bf8b-384">LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl 파일을 열고 메서드의 기본 정의를 제거 합니다. <xref:System.ComponentModel.Component.Dispose%2A></span><span class="sxs-lookup"><span data-stu-id="4bf8b-384">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

10. <span data-ttu-id="4bf8b-385">`LightShape` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-385">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. <span data-ttu-id="4bf8b-386"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-386">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="4bf8b-387">이 구현에서는 채워진 사각형 및 원을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-387">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="4bf8b-388">또한 한 도형 둘레에 테두리를 그리면 선택한 값이 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-388">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a><span data-ttu-id="4bf8b-389">디자이너에서 사용자 지정 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="4bf8b-389">Test your Custom Control in the Designer</span></span>

<span data-ttu-id="4bf8b-390">이제 프로젝트를 빌드할 수 있습니다 `MarqueeControlLibrary` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-390">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="4bf8b-391">클래스에서 상속 하 `MarqueeControl` 고 폼에서 사용 하는 컨트롤을 만들어 구현을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-391">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="4bf8b-392">사용자 지정 MarqueeControl 구현을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bf8b-392">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="4bf8b-393">Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-393">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="4bf8b-394">그러면 형식의 인스턴스가 만들어지고 `DemoMarqueeControl` 형식의 인스턴스에 표시 됩니다 `MarqueeControlRootDesigner` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-394">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="4bf8b-395">**도구 상자**에서 **MarqueeControlLibrary 구성 요소** 탭을 엽니다. `MarqueeBorder`및 `MarqueeText` 컨트롤을 선택할 수 있는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-395">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="4bf8b-396">컨트롤의 인스턴스를 디자인 화면으로 끌어 옵니다 `MarqueeBorder` `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-396">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="4bf8b-397">이 `MarqueeBorder` 컨트롤을 부모 컨트롤에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-397">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="4bf8b-398">컨트롤의 인스턴스를 디자인 화면으로 끌어 옵니다 `MarqueeText` `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-398">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="4bf8b-399">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-399">Build the solution.</span></span>

6. <span data-ttu-id="4bf8b-400">를 마우스 오른쪽 단추로 클릭 하 `DemoMarqueeControl` 고 바로 가기 메뉴에서 **테스트 실행** 옵션을 선택 하 여 애니메이션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-400">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="4bf8b-401">**테스트 중지** 를 클릭 하 여 애니메이션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-401">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="4bf8b-402">디자인 뷰에서 **Form1**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-402">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="4bf8b-403">폼에 컨트롤 두 개를 추가 <xref:System.Windows.Forms.Button> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-403">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="4bf8b-404">및의 이름을로 `startButton` `stopButton` 변경 하 고 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 **시작** 및 **중지**로 각각 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-404">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="4bf8b-405"><xref:System.Windows.Forms.Control.Click>두 컨트롤에 대 한 이벤트 처리기를 구현 <xref:System.Windows.Forms.Button> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-405">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="4bf8b-406">**도구 상자**에서 **MarqueeControlTest 구성 요소** 탭을 엽니다. 선택할 수 있는이 표시 됩니다 `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-406">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="4bf8b-407">인스턴스를 `DemoMarqueeControl` **Form1** 디자인 화면으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-407">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="4bf8b-408"><xref:System.Windows.Forms.Control.Click>이벤트 처리기에서의 및 메서드를 호출 합니다 `Start` `Stop` `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-408">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

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

13. <span data-ttu-id="4bf8b-409">프로젝트를 `MarqueeControlTest` 시작 프로젝트로 설정 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-409">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="4bf8b-410">를 표시 하는 양식이 표시 됩니다 `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-410">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="4bf8b-411">**시작** 단추를 선택 하 여 애니메이션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-411">Select the **Start** button to start the animation.</span></span> <span data-ttu-id="4bf8b-412">깜박이는 텍스트가 표시 되 고 테두리 주위에서 조명이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-412">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4bf8b-413">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4bf8b-413">Next steps</span></span>

<span data-ttu-id="4bf8b-414">에서는 `MarqueeControlLibrary` 사용자 지정 컨트롤 및 관련 디자이너의 간단한 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-414">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="4bf8b-415">이 샘플은 여러 가지 방법으로 더 정교 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-415">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="4bf8b-416">디자이너에서의 속성 값을 변경 합니다 `DemoMarqueeControl` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-416">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="4bf8b-417">컨트롤을 추가 하 `MarqueBorder` 고 부모 인스턴스 내에 도킹 하 여 중첩 된 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-417">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="4bf8b-418">및 광원 관련 속성에 대해 다양 한 설정을 사용 하 여 실험 합니다 `UpdatePeriod` .</span><span class="sxs-lookup"><span data-stu-id="4bf8b-418">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="4bf8b-419">의 고유한 구현을 작성 `IMarqueeWidget` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-419">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="4bf8b-420">예를 들어, 여러 이미지를 사용 하 여 깜박이는 "neon sign" 또는 애니메이션 기호를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-420">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="4bf8b-421">디자인 타임 환경을 추가로 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-421">Further customize the design-time experience.</span></span> <span data-ttu-id="4bf8b-422">및 보다 더 많은 속성을 숨길 <xref:System.Windows.Forms.Control.Enabled%2A> 수 <xref:System.Windows.Forms.Control.Visible%2A> 있으며 새 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-422">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="4bf8b-423">자식 컨트롤 도킹과 같은 일반적인 작업을 단순화 하기 위해 새 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-423">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="4bf8b-424">라이선스를 사용 `MarqueeControl` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-424">License the `MarqueeControl`.</span></span>

- <span data-ttu-id="4bf8b-425">컨트롤이 serialize 되는 방법 및 컨트롤이 생성 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-425">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="4bf8b-426">자세한 내용은 [동적 소스 코드 생성 및 컴파일](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bf8b-426">For more information, see [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4bf8b-427">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4bf8b-427">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
