---
title: '연습: 사용자 지정 구성 요소로 도구 상자 자동 채우기'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211150"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="6bd1e-102">연습: 사용자 지정 구성 요소로 도구 상자 자동 채우기</span><span class="sxs-lookup"><span data-stu-id="6bd1e-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="6bd1e-103">구성 요소는 현재 열려 있는 솔루션의 프로젝트에서 정의 된 경우는 자동으로 나타나는 합니다 **도구 상자**, 작업이 사용자가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="6bd1e-104">채울 수도 있습니다는 **도구 상자** 사용 하 여 사용자 지정 구성 요소를 사용 하 여 합니다 [선택 도구 상자 항목 대화 상자 (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), 하지만 **도구 상자** 고려 솔루션에 있는 항목의 다음 특성을 모두 사용 하 여 출력을 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="6bd1e-105">구현 <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="6bd1e-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="6bd1e-106">없는 <xref:System.ComponentModel.ToolboxItemAttribute> 로 `false`;</span><span class="sxs-lookup"><span data-stu-id="6bd1e-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="6bd1e-107">없는 <xref:System.ComponentModel.DesignTimeVisibleAttribute> 로 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="6bd1e-108">합니다 **도구 상자** 솔루션의 프로젝트에서 빌드되지 않은 항목이 표시 되지 않도록 참조 체인을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="6bd1e-109">이 연습에서는 사용자 지정 구성 요소에 자동으로 표시 하는 방법을 보여 줍니다.는 **도구 상자** 빌드될 때 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="6bd1e-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6bd1e-111">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="6bd1e-112">사용자 지정 구성 요소를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-112">Creating a custom component.</span></span>

- <span data-ttu-id="6bd1e-113">사용자 지정 구성 요소의 인스턴스를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="6bd1e-114">언로드 및 사용자 지정 구성 요소를 다시 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="6bd1e-115">완료 했으면 확인 하 게 합니다 **도구 상자** 사용자가 만든 구성 요소를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="6bd1e-116">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-116">Create the project</span></span>

1. <span data-ttu-id="6bd1e-117">Visual Studio에서 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다 `ToolboxExample` (**파일** > **New** > **프로젝트**  >  **시각적 C#**  하거나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="6bd1e-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="6bd1e-118">프로젝트에 새 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-118">Add a new component to the project.</span></span> <span data-ttu-id="6bd1e-119">이를 `DemoComponent`라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="6bd1e-120">자세한 내용은 [방법: 새 프로젝트 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="6bd1e-121">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-121">Build the project.</span></span>

4. <span data-ttu-id="6bd1e-122">**도구** 메뉴를 클릭 합니다 **옵션** 항목.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="6bd1e-123">클릭 **일반** 아래에서 **Windows Forms 디자이너** 항목을 확인 합니다 **AutoToolboxPopulate** 옵션을 설정 **True**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="6bd1e-124">사용자 지정 구성 요소의 인스턴스를 만듭니다</span><span class="sxs-lookup"><span data-stu-id="6bd1e-124">Create an instance of a custom component</span></span>

<span data-ttu-id="6bd1e-125">다음 단계는 양식의 사용자 지정 구성 요소의 인스턴스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="6bd1e-126">때문에 합니다 **도구 상자** 자동으로 새 구성 요소에 대 한 계정,이 다른 구성 요소나 컨트롤을 만드는 것 만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="6bd1e-127">프로젝트의 폼을 엽니다는 **Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="6bd1e-128">에 **도구 상자**, 이라는 새 탭을 클릭 **ToolboxExample 구성 요소**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="6bd1e-129">탭을 클릭 하면 표시 됩니다 **DemoComponent**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bd1e-130">성능상의 이유로, 자동으로 채워진 영역의 구성 요소를 **도구 상자** 사용자 지정 비트맵을 표시 하지 않습니다 및 <xref:System.Drawing.ToolboxBitmapAttribute> 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="6bd1e-131">사용자 지정 구성 요소에 대 한 아이콘을 표시 하는 **도구 상자**를 사용 하 여를 **도구 상자 항목 선택** 대화 상자 요소를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="6bd1e-132">구성 요소를 양식에 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="6bd1e-133">구성 요소 인스턴스의 생성 되어에 추가 합니다 **구성 요소 트레이에**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="6bd1e-134">사용자 지정 구성 요소를 다시 로드 및 언로드</span><span class="sxs-lookup"><span data-stu-id="6bd1e-134">Unload and reload a custom component</span></span>

<span data-ttu-id="6bd1e-135">합니다 **도구 상자** 의 각 구성 요소는 계정 프로젝트를 로드 하 고 프로젝트를 로드할 프로젝트의 구성 요소에 대 한 참조를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="6bd1e-136">솔루션에서 프로젝트를 언로드하십시오.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="6bd1e-137">언로드 프로젝트에 대 한 자세한 내용은 참조 하세요. [방법: 프로젝트 다시 로드 및 언로드](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="6bd1e-138">저장 하 라는 메시지가 나타나면 선택할 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="6bd1e-139">새 **Windows 응용 프로그램** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="6bd1e-140">폼을 엽니다는 **디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="6bd1e-141">합니다 **ToolboxExample 구성 요소** 탭에서 이전 프로젝트는 이제 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="6bd1e-142">다시 로드를 `ToolboxExample` 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="6bd1e-143">합니다 **ToolboxExample 구성 요소** 탭 이제 다시 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6bd1e-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6bd1e-144">Next steps</span></span>

<span data-ttu-id="6bd1e-145">이 연습을 보여 줍니다 합니다 **도구 상자** 프로젝트의 구성 요소를 고려 되지만 **도구 상자** 컨트롤 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="6bd1e-146">추가 하 고 솔루션에서 제어 프로젝트를 제거 하 여 사용자 고유의 사용자 지정 컨트롤을 사용 하 여 실험 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bd1e-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bd1e-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="6bd1e-147">See also</span></span>

- <span data-ttu-id="6bd1e-148">[일반적으로 Windows Forms 디자이너, 옵션 대화 상자](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bd1e-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="6bd1e-149">[방법: 도구 상자 탭 조작](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bd1e-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="6bd1e-150">[도구 상자 항목 선택 대화 상자(Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bd1e-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="6bd1e-151">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="6bd1e-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
