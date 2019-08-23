---
title: '연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 8ac1ba6b8121aabea3c992ca5b943f231fc19ce2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950068"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="47b14-102">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="47b14-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="47b14-103">폼의 정확한 컨트롤 배치는 많은 애플리케이션에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="47b14-104">Windows Forms 디자이너는이를 위해 다양 한 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="47b14-105">가장 중요 <xref:System.Windows.Forms.Design.Behavior.SnapLine> 한 기능 중 하나는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>

 <span data-ttu-id="47b14-106">맞춤선은 컨트롤을 다른 컨트롤과 비교할 수 있는 정확한 위치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="47b14-107">또한 Windows 사용자 인터페이스 지침에 지정 된 대로 컨트롤 간의 여백에 권장 되는 거리가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="47b14-108">자세한 내용은 [사용자 인터페이스 디자인 및 개발](https://go.microsoft.com/FWLink/?LinkId=83878)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47b14-108">For details, see [User Interface Design and Development](https://go.microsoft.com/FWLink/?LinkId=83878).</span></span>

 <span data-ttu-id="47b14-109">맞춤선을 사용 하면 선명 하 고 전문적인 모양 및 동작 (모양 및 느낌)을 위해 컨트롤을 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>

 <span data-ttu-id="47b14-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="47b14-111">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="47b14-111">Creating a Windows Forms project</span></span>

- <span data-ttu-id="47b14-112">맞춤선을 사용 하 여 컨트롤 간격 조정 및 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-112">Spacing and Aligning Controls Using Snaplines</span></span>

- <span data-ttu-id="47b14-113">폼 및 컨테이너 여백에 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-113">Aligning to Form and Container Margins</span></span>

- <span data-ttu-id="47b14-114">그룹화 된 컨트롤에 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-114">Aligning to Grouped Controls</span></span>

- <span data-ttu-id="47b14-115">맞춤선을 사용 하 여 크기를 개요로 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="47b14-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>

- <span data-ttu-id="47b14-116">도구 상자에서 컨트롤을 끌 때 맞춤선 사용</span><span class="sxs-lookup"><span data-stu-id="47b14-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>

- <span data-ttu-id="47b14-117">맞춤선을 사용 하 여 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="47b14-117">Resizing Controls Using Snaplines</span></span>

- <span data-ttu-id="47b14-118">컨트롤의 텍스트에 레이블 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-118">Aligning a Label to a Control's Text</span></span>

- <span data-ttu-id="47b14-119">키보드 탐색에서 맞춤선 사용</span><span class="sxs-lookup"><span data-stu-id="47b14-119">Using Snaplines with Keyboard Navigation</span></span>

- <span data-ttu-id="47b14-120">맞춤선 및 레이아웃 패널</span><span class="sxs-lookup"><span data-stu-id="47b14-120">Snaplines and Layout Panels</span></span>

- <span data-ttu-id="47b14-121">맞춤선 해제</span><span class="sxs-lookup"><span data-stu-id="47b14-121">Disabling Snaplines</span></span>

 <span data-ttu-id="47b14-122">작업이 완료 되 면 맞춤선 기능에 의해 재생 된 레이아웃 역할을 이해 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="47b14-123">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="47b14-123">Creating the Project</span></span>
 <span data-ttu-id="47b14-124">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-124">The first step is to create the project and set up the form.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="47b14-125">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="47b14-125">To create the project</span></span>

1. <span data-ttu-id="47b14-126">"SnaplineExample" (**파일** > **새로 만들기** > **프로젝트** > **시각적 개체 C#**  또는VisualBasic > 클래식 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.데스크톱 > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="47b14-126">Create a Windows-based application project called "SnaplineExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="47b14-127">폼 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-127">Select the form in the Forms Designer.</span></span>

## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="47b14-128">맞춤선을 사용 하 여 컨트롤 간격 조정 및 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-128">Spacing and Aligning Controls Using Snaplines</span></span>
 <span data-ttu-id="47b14-129">맞춤선은 폼에서 컨트롤을 정확 하 고 직관적인 방식으로 정렬 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-129">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="47b14-130">이러한 컨트롤은 다른 컨트롤이 나 컨트롤 집합과 일치 하는 위치 근처에서 선택 된 컨트롤을 이동할 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-130">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="47b14-131">선택 항목은 다른 컨트롤을 지나서 이동할 때 제안 된 위치에 "스냅" 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-131">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>

### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="47b14-132">맞춤선을 사용 하 여 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-132">To arrange controls using snaplines</span></span>

1. <span data-ttu-id="47b14-133"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-133">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="47b14-134">컨트롤을 <xref:System.Windows.Forms.Button> 폼의 오른쪽 아래 모퉁이로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-134">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="47b14-135">컨트롤에 <xref:System.Windows.Forms.Button> 표시 되는 맞춤선은 폼의 아래쪽 및 오른쪽 테두리에 가까워집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-135">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="47b14-136">이러한 맞춤선은 컨트롤과 폼의 테두리 사이에 권장 되는 거리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-136">These snaplines display the recommended distance between the borders of the control and the form.</span></span>

3. <span data-ttu-id="47b14-137">폼의 <xref:System.Windows.Forms.Button> 테두리 주위에 컨트롤을 이동 하 고 맞춤선이 나타나는 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-137">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="47b14-138">완료 되 면 <xref:System.Windows.Forms.Button> 컨트롤을 폼의 가운데 근처로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-138">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>

4. <span data-ttu-id="47b14-139"><xref:System.Windows.Forms.Button> **도구 상자** 에서 다른 컨트롤을 폼으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-139">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="47b14-140">첫 번째 컨트롤 <xref:System.Windows.Forms.Button> 의 수준이 거의 될 때까지 두 번째 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-140">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="47b14-141">두 단추의 텍스트 기준선에 표시 되는 맞춤선을 확인 하 고 이동 하는 컨트롤이 다른 컨트롤과 정확히 같은 수준의 위치로 스냅 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-141">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

6. <span data-ttu-id="47b14-142">첫 번째 컨트롤 <xref:System.Windows.Forms.Button> 바로 위에 배치 될 때까지 두 번째 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-142">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="47b14-143">두 단추의 왼쪽 및 오른쪽 가장자리를 따라 표시 되는 맞춤선을 확인 하 고 이동 하는 컨트롤이 다른 컨트롤에 정확히 맞춰진 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-143">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>

7. <span data-ttu-id="47b14-144"><xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 거의 닿을 때까지 다른 컨트롤에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-144">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="47b14-145">두 요소 사이에 표시 되는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-145">Note the snapline that appears between them.</span></span> <span data-ttu-id="47b14-146">이 거리는 컨트롤의 테두리 사이에 권장 되는 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-146">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="47b14-147">또한 이동 하는 컨트롤이이 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-147">Also note that the control you are moving snaps to this position.</span></span>

8. <span data-ttu-id="47b14-148"><xref:System.Windows.Forms.Panel> **도구 상자** 에서 두 컨트롤을 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-148">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>

9. <span data-ttu-id="47b14-149">첫 번째와 거의 <xref:System.Windows.Forms.Panel> 같은 수준에 도달할 때까지 컨트롤 중 하나를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-149">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="47b14-150">두 컨트롤의 위쪽 및 아래쪽 가장자리에 표시 되는 맞춤선을 확인 하 고 이동 하는 컨트롤이 다른 컨트롤과 정확히 같은 수준의 위치로 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-150">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="47b14-151">폼 및 컨테이너 여백에 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-151">Aligning to Form and Container Margins</span></span>
 <span data-ttu-id="47b14-152">맞춤선을 통해 컨트롤을 일관 된 방식으로 폼과 컨테이너 여백에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-152">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>

### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="47b14-153">컨트롤을 폼 및 컨테이너 여백에 맞추려면</span><span class="sxs-lookup"><span data-stu-id="47b14-153">To align controls to form and container margins</span></span>

1. <span data-ttu-id="47b14-154"><xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 고 맞춤선이 나타날 때까지 폼의 오른쪽 테두리에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-154">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="47b14-155">오른쪽 테두리의 맞춤선 거리는 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성 및 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값의 합입니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-155">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>

> [!NOTE]
> <span data-ttu-id="47b14-156">폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성이 0, 0, 0, 0으로 설정 된 경우 Windows Forms 디자이너는 폼에 9, 9, 9 <xref:System.Windows.Forms.Control.Padding%2A> , 9의 그림자 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-156">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="47b14-157">이 동작을 재정의 하려면 0, 0, 0, 0이 아닌 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-157">To override this behavior, assign a value other than 0,0,0,0.</span></span>

1. <span data-ttu-id="47b14-158"><xref:System.Windows.Forms.Button> **속성** 창에서 <xref:System.Windows.Forms.Control.Margin%2A> 항목을<xref:System.Windows.Forms.Control.Margin%2A> 확장 하 고 속성을0으로설정하여컨트롤의속성값을변경합니다.<xref:System.Windows.Forms.Padding.All%2A></span><span class="sxs-lookup"><span data-stu-id="47b14-158">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="47b14-159">자세한 [내용은 연습: 안쪽 여백, 여백 및 AutoSize 속성](windows-forms-controls-padding-autosize.md)을 사용 하 여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="47b14-159">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>

2. <span data-ttu-id="47b14-160">맞춤선이 <xref:System.Windows.Forms.Button> 나타날 때까지 컨트롤을 폼의 오른쪽 테두리에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-160">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="47b14-161">이제이 거리가 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-161">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

3. <span data-ttu-id="47b14-162"><xref:System.Windows.Forms.GroupBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-162">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="47b14-163"><xref:System.Windows.Forms.GroupBox> **속성** 창에서 <xref:System.Windows.Forms.Control.Padding%2A> 항목을<xref:System.Windows.Forms.Control.Padding%2A> 확장 하 고 속성을10으로설정하여컨트롤의속성값을변경합니다.<xref:System.Windows.Forms.Padding.All%2A></span><span class="sxs-lookup"><span data-stu-id="47b14-163">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>

5. <span data-ttu-id="47b14-164">**도구 상자** <xref:System.Windows.Forms.Button> 에서컨트롤로컨트롤을끌어옵니다.<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="47b14-164">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

6. <span data-ttu-id="47b14-165">맞춤선이 나타날 때까지 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤의 오른쪽 테두리에 가깝게 이동 합니다. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="47b14-165">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="47b14-166"><xref:System.Windows.Forms.Button> 컨트롤<xref:System.Windows.Forms.GroupBox> 내에서 컨트롤을 이동 하 고 맞춤선이 나타나는 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-166">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>

## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="47b14-167">그룹화 된 컨트롤에 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-167">Aligning to Grouped Controls</span></span>
 <span data-ttu-id="47b14-168">맞춤선을 사용 하 여 컨트롤 내의 컨트롤 뿐만 아니라 그룹화 된 <xref:System.Windows.Forms.GroupBox> 컨트롤을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-168">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>

### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="47b14-169">그룹화 된 컨트롤에 맞추려면</span><span class="sxs-lookup"><span data-stu-id="47b14-169">To align to grouped controls</span></span>

1. <span data-ttu-id="47b14-170">폼에서 컨트롤을 두 개 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-170">Select two of the controls on your form.</span></span> <span data-ttu-id="47b14-171">선택 영역을 이동 하 고 선택 영역과 다른 컨트롤 사이에 나타나는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-171">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>

2. <span data-ttu-id="47b14-172"><xref:System.Windows.Forms.GroupBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-172">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="47b14-173">**도구 상자** <xref:System.Windows.Forms.Button> 에서컨트롤로컨트롤을끌어옵니다.<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="47b14-173">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

4. <span data-ttu-id="47b14-174"><xref:System.Windows.Forms.Button> 컨트롤 중 하나를 선택 하 여 <xref:System.Windows.Forms.GroupBox> 컨트롤 주위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-174">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="47b14-175"><xref:System.Windows.Forms.GroupBox> 컨트롤의 가장자리에 표시 되는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-175">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="47b14-176">컨트롤에 포함 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox> 된 컨트롤의 가장자리에 나타나는 맞춤선도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-176">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="47b14-177">컨테이너 컨트롤의 자식인 컨트롤은 맞춤선도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-177">Controls that are children of a container control also support snaplines.</span></span>

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="47b14-178">맞춤선을 사용 하 여 크기를 개요로 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="47b14-178">Using Snaplines to Place a Control by Outlining Its Size</span></span>
 <span data-ttu-id="47b14-179">맞춤선은 폼에 처음 배치할 때 컨트롤을 맞추는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-179">Snaplines help you align controls when you first place them on a form.</span></span>

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="47b14-180">맞춤선을 사용 하 여 컨트롤의 크기를 윤곽선으로 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-180">To use snaplines to place a control by outlining its size</span></span>

1. <span data-ttu-id="47b14-181">**도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-181">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="47b14-182">폼으로 끌어다 놓지 마세요.</span><span class="sxs-lookup"><span data-stu-id="47b14-182">Do not drag it onto the form.</span></span>

2. <span data-ttu-id="47b14-183">폼의 디자인 화면 위로 마우스 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-183">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="47b14-184">포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-184">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="47b14-185">또한 <xref:System.Windows.Forms.Button> 컨트롤의 맞춤 위치를 제안 하기 위해 표시 되는 맞춤선에 주목 하십시오.</span><span class="sxs-lookup"><span data-stu-id="47b14-185">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>

3. <span data-ttu-id="47b14-186">마우스 단추를 길게 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-186">Click and hold the mouse button.</span></span>

4. <span data-ttu-id="47b14-187">마우스 포인터를 폼 주위로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-187">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="47b14-188">컨트롤의 위치와 크기를 나타내는 윤곽선이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-188">Note that an outline is drawn, indicating the position and the size of the control.</span></span>

5. <span data-ttu-id="47b14-189">폼의 다른 컨트롤에 맞춰질 때까지 포인터를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-189">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="47b14-190">맞춤을 나타내는 맞춤선이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-190">Note that a snapline appears to indicate alignment.</span></span>

6. <span data-ttu-id="47b14-191">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-191">Release the mouse button.</span></span> <span data-ttu-id="47b14-192">컨트롤이 윤곽선에 표시 되는 위치와 크기에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-192">The control is created at the position and size indicated by the outline.</span></span>

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="47b14-193">도구 상자에서 컨트롤을 끌 때 맞춤선 사용</span><span class="sxs-lookup"><span data-stu-id="47b14-193">Using Snaplines When Dragging a Control from the Toolbox</span></span>
 <span data-ttu-id="47b14-194">맞춤선을 **도구 상자** 에서 폼으로 끌어올 때 컨트롤을 맞추는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-194">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="47b14-195">도구 상자에서 컨트롤을 끌 때 맞춤선을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-195">To use snaplines when dragging a control from the Toolbox</span></span>

1. <span data-ttu-id="47b14-196"><xref:System.Windows.Forms.Button> **도구 상자** 에서 컨트롤을 폼으로 끌어 온 다음 마우스 단추를 놓지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="47b14-196">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>

2. <span data-ttu-id="47b14-197">폼의 디자인 화면 위로 마우스 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-197">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="47b14-198">포인터가 새 <xref:System.Windows.Forms.Button> 컨트롤을 만들 위치를 나타내도록 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-198">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>

3. <span data-ttu-id="47b14-199">마우스 포인터를 폼 주위로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-199">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="47b14-200"><xref:System.Windows.Forms.Button> 컨트롤의 맞춤 위치를 제안 하기 위해 표시 되는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-200">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="47b14-201">다른 컨트롤과 정렬 된 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-201">Find a position that is aligned with other controls.</span></span>

4. <span data-ttu-id="47b14-202">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-202">Release the mouse button.</span></span> <span data-ttu-id="47b14-203">컨트롤이 맞춤선이 나타내는 위치에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-203">The control is created at the position indicated by the snaplines.</span></span>

## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="47b14-204">맞춤선을 사용 하 여 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="47b14-204">Resizing Controls Using Snaplines</span></span>
 <span data-ttu-id="47b14-205">맞춤선을 통해 컨트롤의 크기를 조정할 때 컨트롤을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-205">Snaplines help you align controls as you resize them.</span></span>

### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="47b14-206">맞춤선을 사용 하 여 컨트롤의 크기를 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-206">To resize a control using snaplines</span></span>

1. <span data-ttu-id="47b14-207"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-207">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="47b14-208">모퉁이 크기 <xref:System.Windows.Forms.Button> 조정 핸들 중 하나를 가져오고 끌어서 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-208">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="47b14-209">자세한 내용은 [방법: Windows Forms](how-to-resize-controls-on-windows-forms.md)에서 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-209">For details, see [How to: Resize Controls on Windows Forms](how-to-resize-controls-on-windows-forms.md).</span></span>

3. <span data-ttu-id="47b14-210"><xref:System.Windows.Forms.Button> 컨트롤의 테두리 중 하나가 다른 컨트롤에 맞춰질 때까지 크기 조정 핸들을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-210">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="47b14-211">맞춤선이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-211">Note that a snapline appears.</span></span> <span data-ttu-id="47b14-212">또한 크기 조정 핸들은 맞춤선이 나타내는 위치로 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-212">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>

4. <span data-ttu-id="47b14-213">여러 방향 <xref:System.Windows.Forms.Button> 으로 컨트롤의 크기를 조정 하 고 크기 조정 핸들을 다른 컨트롤에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-213">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="47b14-214">맞춤을 나타내기 위해 여러 방향에 맞춤선이 표시 되는 방식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-214">Note how the snaplines appear in various orientations to indicate alignment.</span></span>

## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="47b14-215">컨트롤의 텍스트에 레이블 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b14-215">Aligning a Label to a Control's Text</span></span>
 <span data-ttu-id="47b14-216">일부 컨트롤은 표시 된 텍스트에 다른 컨트롤을 맞추는 맞춤선을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-216">Some controls offer a snapline for aligning other controls to displayed text.</span></span>

### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="47b14-217">컨트롤의 텍스트에 레이블을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="47b14-217">To align a label to a control's text</span></span>

1. <span data-ttu-id="47b14-218"><xref:System.Windows.Forms.TextBox> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-218">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="47b14-219">컨트롤을 <xref:System.Windows.Forms.TextBox> 폼에 놓으면 스마트 태그 문자 모양을 클릭 하 고 **텍스트를 textBox1으로 설정** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-219">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="47b14-220">자세한 [내용은 연습: Windows Forms 컨트롤](performing-common-tasks-using-smart-tags-on-wf-controls.md)에서 스마트 태그를 사용 하 여 일반적인 작업 수행</span><span class="sxs-lookup"><span data-stu-id="47b14-220">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>

2. <span data-ttu-id="47b14-221"><xref:System.Windows.Forms.Label> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-221">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="47b14-222"><xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-222">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="47b14-223">컨트롤의 테두리는 표시 텍스트에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-223">Note that the control's borders are adjusted to fit the display text.</span></span>

4. <span data-ttu-id="47b14-224">컨트롤을 컨트롤의 왼쪽 <xref:System.Windows.Forms.TextBox> 으로 이동 하 여 컨트롤의 <xref:System.Windows.Forms.TextBox> 아래쪽 가장자리에 맞춥니다. <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="47b14-224">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="47b14-225">두 컨트롤의 아래쪽 가장자리를 따라 나타나는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-225">Note the snapline that appears along the bottom edges of the two controls.</span></span>

5. <span data-ttu-id="47b14-226"><xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Label> 텍스트 와<xref:System.Windows.Forms.TextBox> 텍스트가 맞춰질 때까지 컨트롤을 조금 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-226">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="47b14-227">두 컨트롤의 텍스트 필드가 정렬 되는 경우를 나타내는, 표시 되는 다른 스타일의 맞춤선에 유의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="47b14-227">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>

## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="47b14-228">키보드 탐색에서 맞춤선 사용</span><span class="sxs-lookup"><span data-stu-id="47b14-228">Using Snaplines with Keyboard Navigation</span></span>
 <span data-ttu-id="47b14-229">맞춤선을 사용 하면 키보드의 화살표 키를 사용 하 여 컨트롤을 정렬할 때 컨트롤을 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-229">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>

### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="47b14-230">키보드 탐색에서 맞춤선을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-230">To use snaplines with keyboard navigation</span></span>

1. <span data-ttu-id="47b14-231"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-231">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="47b14-232">폼의 왼쪽 위 모퉁이에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-232">Place it in the upper-left corner of the form.</span></span>

2. <span data-ttu-id="47b14-233">CTRL + 아래쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-233">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="47b14-234">컨트롤은 폼을 사용 가능한 첫 번째 가로 맞춤 위치로 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-234">Note that the control moves down the form to the first available horizontal alignment position.</span></span>

3. <span data-ttu-id="47b14-235">컨트롤이 폼의 아래쪽에 도달할 때까지 CTRL + 아래쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-235">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="47b14-236">폼을 아래로 이동할 때 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-236">Note the positions it occupies as it moves down the form.</span></span>

4. <span data-ttu-id="47b14-237">CTRL + 오른쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-237">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="47b14-238">컨트롤이 폼에서 사용 가능한 첫 번째 세로 맞춤 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-238">Note that the control moves across the form to the first available vertical alignment position.</span></span>

5. <span data-ttu-id="47b14-239">컨트롤이 폼의 양쪽에 도달할 때까지 CTRL + 오른쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-239">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="47b14-240">폼에서 이동할 때 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-240">Note the positions it occupies as it moves across the form.</span></span>

6. <span data-ttu-id="47b14-241">화살표 키의 조합을 사용 하 여 컨트롤을 폼 주위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-241">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="47b14-242">컨트롤이 있는 위치와 해당 컨트롤이 함께 나타나는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-242">Note the positions the control occupies and the snaplines that accompany them.</span></span>

7. <span data-ttu-id="47b14-243">SHIFT + any 화살표 키를 눌러 컨트롤의 <xref:System.Windows.Forms.Button> 크기를 한 픽셀씩 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-243">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>

8. <span data-ttu-id="47b14-244">Ctrl + SHIFT + 임의의 화살표 키를 눌러 맞춤선 단위로 <xref:System.Windows.Forms.Button> 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-244">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>

## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="47b14-245">맞춤선 및 레이아웃 패널</span><span class="sxs-lookup"><span data-stu-id="47b14-245">Snaplines and Layout Panels</span></span>
 <span data-ttu-id="47b14-246">맞춤선은 레이아웃 패널 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-246">Snaplines are disabled within layout panels.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="47b14-247">맞춤선을 선택적으로 사용 하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="47b14-247">To selectively disable snaplines</span></span>

1. <span data-ttu-id="47b14-248"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-248">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="47b14-249"><xref:System.Windows.Forms.Button> 도구 상자 **에서**컨트롤 아이콘을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-249">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="47b14-250">새 단추 컨트롤이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-250">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>

3. <span data-ttu-id="47b14-251">**도구 상자** 에서 두 <xref:System.Windows.Forms.Button> 번 클릭 하 여 컨트롤 아이콘을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-251">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="47b14-252">이렇게 하면 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 빈 셀이 하나 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-252">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="47b14-253"><xref:System.Windows.Forms.Button> **도구 상자** 에서 컨트롤의 <xref:System.Windows.Forms.TableLayoutPanel> 빈 셀로 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-253">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="47b14-254">맞춤선이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-254">Note that no snaplines appear.</span></span>

5. <span data-ttu-id="47b14-255">컨트롤을 컨트롤 외부로 <xref:System.Windows.Forms.TableLayoutPanel> 끌고 컨트롤 주위로 <xref:System.Windows.Forms.TableLayoutPanel> 이동 합니다. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="47b14-255">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="47b14-256">맞춤선이 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-256">Note that snaplines appear again.</span></span>

## <a name="disabling-snaplines"></a><span data-ttu-id="47b14-257">맞춤선 해제</span><span class="sxs-lookup"><span data-stu-id="47b14-257">Disabling Snaplines</span></span>
 <span data-ttu-id="47b14-258">맞춤선은 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-258">Snaplines are turned on by default.</span></span> <span data-ttu-id="47b14-259">맞춤선을 선택적으로 사용 하지 않도록 설정 하거나 디자인 환경에서 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-259">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="47b14-260">맞춤선을 선택적으로 사용 하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="47b14-260">To selectively disable snaplines</span></span>

- <span data-ttu-id="47b14-261">컨트롤을 폼 주위로 이동 하는 동안 ALT 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-261">Press the ALT key and while moving a control around the form.</span></span>

     <span data-ttu-id="47b14-262">맞춤선이 나타나지 않으며 컨트롤은 잠재적 맞춤 위치에 맞추지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-262">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>

### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="47b14-263">디자인 환경에서 맞춤선을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="47b14-263">To disable snaplines in the design environment</span></span>

1. <span data-ttu-id="47b14-264">**도구** 메뉴에서 **옵션** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-264">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="47b14-265">Windows Forms 디자이너 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-265">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="47b14-266">자세한 내용은 [옵션 대화 상자, Windows Forms 디자이너, 일반을](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47b14-266">For details, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span>

2. <span data-ttu-id="47b14-267">**일반** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-267">Select the **General** node.</span></span> <span data-ttu-id="47b14-268">**레이아웃 모드** 섹션에서 선택 영역을 **맞춤선** 에서 **SnapToGrid**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-268">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>

3. <span data-ttu-id="47b14-269">확인을 클릭 하 여 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-269">Click OK to apply the setting.</span></span>

4. <span data-ttu-id="47b14-270">폼에서 컨트롤을 선택 하 고 다른 컨트롤 주위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-270">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="47b14-271">맞춤선은 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-271">Note that snaplines do not appear.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47b14-272">다음 단계</span><span class="sxs-lookup"><span data-stu-id="47b14-272">Next Steps</span></span>
 <span data-ttu-id="47b14-273">맞춤선은 폼에서 컨트롤을 정렬 하는 직관적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-273">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="47b14-274">다음과 같은 사항을 더 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-274">Suggestions for more exploration include:</span></span>

- <span data-ttu-id="47b14-275"><xref:System.Windows.Forms.GroupBox> 다른<xref:System.Windows.Forms.GroupBox> 컨트롤 내에 컨트롤을 중첩 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="47b14-275">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="47b14-276">자식 <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Button> 컨트롤내에컨트롤을추가하고부모컨트롤내에다른컨트롤을추가합니다.<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="47b14-276">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="47b14-277">컨트롤을 <xref:System.Windows.Forms.Button> 이동 하 여 맞춤선이 컨테이너 경계를 교차 하는 방식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-277">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>

- <span data-ttu-id="47b14-278"><xref:System.Windows.Forms.TextBox> 컨트롤의 열과 컨트롤의 <xref:System.Windows.Forms.Label> 해당 열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-278">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="47b14-279"><xref:System.Windows.Forms.Label> `true`컨트롤의 속성값을로설정합니다.<xref:System.Windows.Forms.Control.AutoSize%2A></span><span class="sxs-lookup"><span data-stu-id="47b14-279">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="47b14-280">표시 된 텍스트를 <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.TextBox> 컨트롤의 텍스트와 맞추도록 맞춤선을 사용 하 여 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b14-280">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>

 <span data-ttu-id="47b14-281">Windows 사용자 인터페이스 디자인에 대 한 자세한 내용은 *Microsoft Windows 사용자 환경, 사용자 인터페이스 개발자 및 디자이너를 위한 공식 지침* , WA: Microsoft Press, 1999.</span><span class="sxs-lookup"><span data-stu-id="47b14-281">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="47b14-282">USBN 0-7356-0566-1).</span><span class="sxs-lookup"><span data-stu-id="47b14-282">(USBN: 0-7356-0566-1).</span></span>

## <a name="see-also"></a><span data-ttu-id="47b14-283">참고자료</span><span class="sxs-lookup"><span data-stu-id="47b14-283">See also</span></span>

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [<span data-ttu-id="47b14-284">연습: FlowLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="47b14-284">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="47b14-285">연습: TableLayoutPanel를 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="47b14-285">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="47b14-286">연습: 안쪽 여백, 여백 및 AutoSize 속성을 사용 하 여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="47b14-286">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
- [<span data-ttu-id="47b14-287">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="47b14-287">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
