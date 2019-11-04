---
title: '연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 76c880c208355b01d0fbaf46cf58091ad147846b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460604"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="9bf50-102">연습: 패딩, 여백 및 AutoSize 속성을 사용 하 여 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="9bf50-102">Walkthrough: Lay out controls with padding, margins, and the AutoSize property</span></span>

<span data-ttu-id="9bf50-103">폼의 정확한 컨트롤 배치는 많은 애플리케이션에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="9bf50-104">Visual Studio의 **Windows Forms 디자이너** 는이를 위해 다양 한 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="9bf50-105">가장 중요 한 세 가지는 모든 Windows Forms 컨트롤에 있는 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>및 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

<span data-ttu-id="9bf50-106"><xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

<span data-ttu-id="9bf50-107"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

<span data-ttu-id="9bf50-108">다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

![Windows Forms 컨트롤의 여백 및 안쪽 여백](./media/vs-winformpadmargin.gif)

<span data-ttu-id="9bf50-110"><xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 컨트롤이 내용에 맞게 자동으로 크기를 조정 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="9bf50-111">원래 <xref:System.Windows.Forms.Control.Size%2A> 속성 값 보다 작은 크기로 크기를 조정 하지 않으며 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 값을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bf50-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="9bf50-112">Prerequisites</span></span>

<span data-ttu-id="9bf50-113">이 연습을 완료 하려면 Visual Studio가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-113">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="9bf50-114">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-114">Create the project</span></span>

1. <span data-ttu-id="9bf50-115">Visual Studio에서 `LayoutExample`라는 **Windows 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-115">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span>

2. <span data-ttu-id="9bf50-116">**Windows Forms 디자이너**에서 양식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-116">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="set-margins-for-controls"></a><span data-ttu-id="9bf50-117">컨트롤의 여백 설정</span><span class="sxs-lookup"><span data-stu-id="9bf50-117">Set margins for controls</span></span>

<span data-ttu-id="9bf50-118"><xref:System.Windows.Forms.Control.Margin%2A> 속성을 사용 하 여 컨트롤 간의 기본 거리를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-118">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="9bf50-119">컨트롤을 다른 컨트롤에 가까이 이동할 때 두 컨트롤의 여백을 보여 주는 맞춤선이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-119">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="9bf50-120">이동 하는 컨트롤은 여백으로 정의 된 거리에도 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-120">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="9bf50-121">Margin 속성을 사용 하 여 폼에 컨트롤을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-121">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="9bf50-122">두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 **도구 상자** 에서 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-122">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="9bf50-123"><xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 거의 닿을 때까지 다른 컨트롤 가까이로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-123">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

   <span data-ttu-id="9bf50-124">두 항목 사이에 나타나는 맞춤선을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-124">Observe the snapline that appears between them.</span></span> <span data-ttu-id="9bf50-125">이 거리는 두 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 값 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-125">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="9bf50-126">이동 하는 컨트롤이이 거리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-126">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="9bf50-127">자세한 내용은 [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bf50-127">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="9bf50-128">**속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **20**으로 설정 하 여 컨트롤 중 하나의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-128">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

4. <span data-ttu-id="9bf50-129"><xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 다른 컨트롤 가까이로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-129">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

   <span data-ttu-id="9bf50-130">여백 값의 합을 정의 하는 맞춤선이 더 길고 컨트롤이 다른 컨트롤에서 더 큰 거리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-130">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="9bf50-131">**속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.Top%2A> 속성을 **5**로 설정 하 여 선택한 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-131">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to **5**.</span></span>

6. <span data-ttu-id="9bf50-132">선택한 컨트롤을 다른 컨트롤 아래로 이동 하 여 맞춤선이 더 짧아 지는 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-132">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="9bf50-133">선택한 컨트롤을 다른 컨트롤의 왼쪽으로 이동 하 고 4 단계에서 관찰 된 값이 맞춤선에 유지 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-133">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="9bf50-134"><xref:System.Windows.Forms.Control.Margin%2A> 속성의 각 측면 (<xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>을 다른 값으로 설정 하거나 <xref:System.Windows.Forms.Padding.All%2A> 속성을 사용 하 여 모두 동일한 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-134">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="set-padding-for-controls"></a><span data-ttu-id="9bf50-135">컨트롤의 안쪽 여백 설정</span><span class="sxs-lookup"><span data-stu-id="9bf50-135">Set padding for controls</span></span>

<span data-ttu-id="9bf50-136">응용 프로그램에 필요한 정확한 레이아웃을 얻기 위해 컨트롤에는 종종 자식 컨트롤이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-136">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="9bf50-137">자식 컨트롤의 테두리를 부모 컨트롤의 테두리에 근접 하 게 지정 하려는 경우 부모 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-137">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="9bf50-138"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 콘텐츠 (예: <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성)가 해당 테두리에 근접 하는 것을 제어 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-138">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="9bf50-139">안쪽 여백을 사용 하 여 폼에 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9bf50-139">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="9bf50-140"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-140">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="9bf50-141"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="9bf50-142">**속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **5**로 설정 하 여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-142">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="9bf50-143">컨트롤이 확장 되어 새 안쪽 여백을 위한 공간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-143">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="9bf50-144"><xref:System.Windows.Forms.GroupBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-144">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="9bf50-145">**도구 상자** 의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-145">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="9bf50-146"><xref:System.Windows.Forms.GroupBox> 컨트롤의 오른쪽 아래 모퉁이에 <xref:System.Windows.Forms.Button> 컨트롤의 위치를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-146">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

   <span data-ttu-id="9bf50-147"><xref:System.Windows.Forms.Button> 컨트롤이 <xref:System.Windows.Forms.GroupBox> 컨트롤의 아래쪽 및 오른쪽 테두리에 도달할 때 나타나는 맞춤선을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-147">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="9bf50-148">이러한 맞춤선은 <xref:System.Windows.Forms.Button>의 <xref:System.Windows.Forms.Control.Margin%2A> 속성에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-148">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="9bf50-149">**속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **20**으로 설정 하 여 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-149">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

6. <span data-ttu-id="9bf50-150"><xref:System.Windows.Forms.GroupBox> 컨트롤 내에서 <xref:System.Windows.Forms.Button> 컨트롤을 선택 하 고 <xref:System.Windows.Forms.GroupBox>의 가운데로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-150">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

   <span data-ttu-id="9bf50-151">맞춤선은 <xref:System.Windows.Forms.GroupBox> 컨트롤의 테두리에서 더 큰 거리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-151">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="9bf50-152">이 거리는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성의 합입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-152">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="size-controls-automatically"></a><span data-ttu-id="9bf50-153">컨트롤 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="9bf50-153">Size controls automatically</span></span>

<span data-ttu-id="9bf50-154">일부 응용 프로그램에서는 컨트롤의 크기가 디자인 타임에와 동일 하 게 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-154">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="9bf50-155">예를 들어 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트는 데이터베이스에서 가져올 수 있으며 해당 길이는 미리 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-155">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length are not known in advance.</span></span>

<span data-ttu-id="9bf50-156"><xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `true`으로 설정 되 면 컨트롤은 해당 내용에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-156">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="9bf50-157">자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bf50-157">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="9bf50-158">AutoSize 속성을 사용 하 여 폼에 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9bf50-158">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="9bf50-159"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-159">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="9bf50-160"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-160">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="9bf50-161"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **이 단추로 텍스트 속성에 대 한 긴 문자열로**변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-161">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to **This button has a long string for its Text property**.</span></span>

   <span data-ttu-id="9bf50-162">변경 내용을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤의 크기가 새 텍스트에 맞게 자동으로 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-162">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="9bf50-163">다른 <xref:System.Windows.Forms.Button> 컨트롤을 **도구 상자** 에서 폼으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-163">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="9bf50-164"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에는 텍스트 속성에 대 한 긴 문자열이 있습니다.** "로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-164">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="9bf50-165">변경을 커밋하면 <xref:System.Windows.Forms.Button> 컨트롤의 크기가 자동으로 조정 되지 않으며 텍스트가 컨트롤의 오른쪽 가장자리에 의해 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-165">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="9bf50-166">**속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을 확장 하 고 <xref:System.Windows.Forms.Padding.All%2A> 속성을 **5**로 설정 하 여 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-166">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="9bf50-167">컨트롤의 내부에 있는 텍스트는 네 면 모두 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-167">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="9bf50-168"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 **true**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

   <span data-ttu-id="9bf50-169"><xref:System.Windows.Forms.Button> 컨트롤은 전체 문자열을 포함 하도록 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-169">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="9bf50-170">또한 텍스트 주위에 안쪽 여백이 추가 되어 <xref:System.Windows.Forms.Button> 컨트롤이 4 방향으로 모두 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-170">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="9bf50-171"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-171">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="9bf50-172">폼의 오른쪽 아래 모퉁이 근처에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-172">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="9bf50-173"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

10. <span data-ttu-id="9bf50-174"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-174">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="9bf50-175"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에는 텍스트 속성에 대 한 긴 문자열이 있습니다.** "로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="9bf50-176">변경 내용을 커밋하는 경우 <xref:System.Windows.Forms.Button> 컨트롤은 왼쪽 방향으로 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-176">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="9bf50-177">일반적으로 자동 크기 조정은 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 설정과 반대 방향으로 컨트롤의 크기를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-177">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="9bf50-178">AutoSize 및 AutoSizeMode 속성</span><span class="sxs-lookup"><span data-stu-id="9bf50-178">AutoSize and AutoSizeMode properties</span></span>

 <span data-ttu-id="9bf50-179">일부 컨트롤은 컨트롤의 자동 크기 조정 동작에 대 한 보다 세분화 된 제어를 제공 하는 `AutoSizeMode` 속성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-179">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="9bf50-180">AutoSizeMode 속성 사용</span><span class="sxs-lookup"><span data-stu-id="9bf50-180">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="9bf50-181"><xref:System.Windows.Forms.Panel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-181">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="9bf50-182"><xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 **true**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-182">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="9bf50-183">**도구 상자** 의 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="9bf50-184"><xref:System.Windows.Forms.Panel> 컨트롤의 오른쪽 아래 모퉁이 근처에 <xref:System.Windows.Forms.Button> 컨트롤을 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-184">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="9bf50-185"><xref:System.Windows.Forms.Panel> 컨트롤을 선택 하 고 오른쪽 아래 크기 조정 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-185">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="9bf50-186"><xref:System.Windows.Forms.Panel> 컨트롤의 크기를 더 크거나 작게 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-186">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9bf50-187"><xref:System.Windows.Forms.Panel> 컨트롤의 크기를 자유롭게 조정할 수 있지만 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모퉁이의 위치 보다 작게 크기를 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-187">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="9bf50-188">이 동작은 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>되는 `AutoSizeMode` 속성의 기본값으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-188">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="9bf50-189"><xref:System.Windows.Forms.Panel> 컨트롤의 `AutoSizeMode` 속성 값을 <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-189">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

   <span data-ttu-id="9bf50-190"><xref:System.Windows.Forms.Panel> 컨트롤의 크기는 <xref:System.Windows.Forms.Button> 컨트롤을 둘러쌉니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-190">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="9bf50-191"><xref:System.Windows.Forms.Panel> 컨트롤의 크기를 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-191">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="9bf50-192"><xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤의 왼쪽 위 모퉁이를 향해 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-192">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

   <span data-ttu-id="9bf50-193"><xref:System.Windows.Forms.Panel> 컨트롤은 <xref:System.Windows.Forms.Button> 컨트롤의 새 위치로 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-193">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bf50-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9bf50-194">Next steps</span></span>

<span data-ttu-id="9bf50-195">Windows Forms 응용 프로그램에서 컨트롤을 정렬 하는 다양 한 레이아웃 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-195">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="9bf50-196">다음은 시도해 볼 수 있는 몇 가지 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-196">Here are some combinations you might try:</span></span>

- <span data-ttu-id="9bf50-197"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용 하 여 양식을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-197">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="9bf50-198">자세한 내용은 [연습: TableLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bf50-198">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="9bf50-199"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값 뿐만 아니라 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 변경해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-199">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="9bf50-200"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤을 사용 하 여 동일한 실험을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-200">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="9bf50-201">자세한 내용은 [연습: FlowLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bf50-201">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="9bf50-202"><xref:System.Windows.Forms.Panel> 컨트롤의 도킹 자식 컨트롤을 사용 하 여 실험 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-202">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="9bf50-203"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 속성을 보다 일반적으로 인식 하며, 자식 컨트롤을 <xref:System.Windows.Forms.Panel> 컨트롤에 배치 하 고 자식 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정 하 여이를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-203">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="9bf50-204"><xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 다양 한 값으로 설정 하 고 효과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf50-204">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf50-205">참조</span><span class="sxs-lookup"><span data-stu-id="9bf50-205">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="9bf50-206">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="9bf50-206">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="9bf50-207">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9bf50-207">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="9bf50-208">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9bf50-208">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="9bf50-209">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9bf50-209">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
