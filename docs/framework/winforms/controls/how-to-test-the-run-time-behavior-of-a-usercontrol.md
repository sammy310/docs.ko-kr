---
title: '방법: UserControl의 런타임 동작 테스트'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180202"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="c9990-102">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="c9990-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="c9990-103">@No__t-0을 개발 하는 경우 런타임 동작을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="c9990-104">별도의 Windows 기반 응용 프로그램 프로젝트를 만들고 테스트 폼에 컨트롤을 저장할 수 있지만이 절차는 불편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="c9990-105">빠르고 쉬운 방법은 Visual Studio에서 제공 하는 **UserControl 테스트 컨테이너** 를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="c9990-106">이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9990-107">테스트 컨테이너가 @no__t를 로드 하려면-0 컨트롤에 하나 이상의 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="c9990-108">C++ **UserControl 테스트 컨테이너**를 사용 하 여 시각적 컨트롤을 테스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="c9990-109">UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="c9990-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="c9990-110">Visual Studio에서 Windows 컨트롤 라이브러리 프로젝트를 만들고 이름을 **TestContainerExample**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="c9990-111">**Windows Forms 디자이너**에서 <xref:System.Windows.Forms.Label> 컨트롤을 **도구 상자** 에서 컨트롤의 디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="c9990-112"><kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="c9990-113">테스트 컨테이너는 **미리 보기** 창에서 <xref:System.Windows.Forms.UserControl>과 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="c9990-114">**미리 보기** 창 오른쪽의 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 표시 되는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="c9990-115">해당 값을 **Controldark**값으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="c9990-116">컨트롤이 짙은 색으로 변경 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="c9990-117">다른 속성 값을 변경 하 고 컨트롤에 미치는 영향을 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="c9990-118">**미리 보기** 창 아래에서 **사용자 정의 컨트롤 채우기** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="c9990-119">창에 맞게 컨트롤의 크기가 조정 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="c9990-120">테스트 컨테이너의 크기를 조정 하 고 창을 사용 하 여 컨트롤의 크기가 조정 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="c9990-121">테스트 컨테이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-121">Close the test container.</span></span>

7. <span data-ttu-id="c9990-122">**TestContainerExample** 프로젝트에 다른 사용자 정의 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="c9990-123">**Windows Forms 디자이너**에서 <xref:System.Windows.Forms.Button> 컨트롤을 **도구 상자** 에서 컨트롤의 디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="c9990-124"><kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="c9990-125">**사용자 컨트롤 선택** <xref:System.Windows.Forms.ComboBox>을 클릭 하 여 두 사용자 정의 컨트롤 사이를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="c9990-126">다른 프로젝트에서 사용자 정의 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="c9990-126">Test user controls from another project</span></span>

<span data-ttu-id="c9990-127">현재 프로젝트의 테스트 컨테이너에 있는 다른 프로젝트에서 사용자 정의 컨트롤을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="c9990-128">Visual Studio에서 Windows 컨트롤 라이브러리 프로젝트를 만들고 이름을 **TestContainerExample2**로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="c9990-129">**Windows Forms 디자이너**에서 <xref:System.Windows.Forms.RadioButton> 컨트롤을 **도구 상자** 에서 컨트롤의 디자인 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="c9990-130"><kbd>F5</kbd> 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="c9990-131">테스트 컨테이너는 **미리 보기** 창에서 <xref:System.Windows.Forms.UserControl>과 함께 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="c9990-132">**로드** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="c9990-133">**열기** 대화 상자에서 이전 절차에서 빌드한 *TestContainerExample*로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="c9990-134">*TestContainerExample* 를 선택 하 고 **열기** 단추를 클릭 하 여 사용자 정의 컨트롤을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="c9990-135">**사용자 컨트롤 선택** <xref:System.Windows.Forms.ComboBox>을 사용 하 여 **TestContainerExample** 프로젝트에서 두 사용자 정의 컨트롤 사이를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9990-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9990-136">참조</span><span class="sxs-lookup"><span data-stu-id="c9990-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <span data-ttu-id="c9990-137">[방법: 복합 컨트롤 작성 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="c9990-137">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>
- <span data-ttu-id="c9990-138">[연습: 복합 컨트롤 작성 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="c9990-138">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>
- <span data-ttu-id="c9990-139">[사용자 정의 컨트롤 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c9990-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
