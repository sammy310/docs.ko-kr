---
title: '방법: 컨트롤 제작'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 169104f51898f9bda08efa08685207e50406a7ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746712"
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="c4557-102">방법: Windows Forms 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="c4557-102">How to: Author controls for Windows Forms</span></span>

<span data-ttu-id="c4557-103">컨트롤은 사용자와 프로그램 간의 그래픽 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="c4557-104">컨트롤은 데이터를 제공하거나 처리하고, 사용자 입력을 허용하고, 사용자 및 애플리케이션을 연결하는 다른 함수의 구성원을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="c4557-105">컨트롤이 기본적으로 그래픽 인터페이스를 사용하는 구성 요소이기 때문에 사용자 상호 작용을 제공할 뿐만 아니라 구성 요소가 수행하는 모든 함수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="c4557-106">컨트롤은 특정 목적을 수행하기 위해 만들어지며 컨트롤 작성은 다른 프로그래밍 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="c4557-107">이 점을 염두하면서 다음 단계는 컨트롤 작성 프로세스의 개요를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="c4557-108">링크는 각 단계에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-108">Links provide additional information on the individual steps.</span></span>

## <a name="to-author-a-control"></a><span data-ttu-id="c4557-109">컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="c4557-109">To author a control</span></span>

1. <span data-ttu-id="c4557-110">컨트롤이 수행하려는 항목 또는 애플리케이션에서 컨트롤이 맡은 역할을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-110">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="c4557-111">고려해야 하는 요인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-111">Factors to consider are:</span></span>

    - <span data-ttu-id="c4557-112">어떤 종류의 그래픽 인터페이스가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="c4557-112">What kind of graphical interface do you need?</span></span>

    - <span data-ttu-id="c4557-113">이 컨트롤이 다룰 특정 사용자 인터페이스는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c4557-113">What specific user interactions will this control handle?</span></span>

    - <span data-ttu-id="c4557-114">기존 컨트롤에서 필요한 기능을 제공하나요?</span><span class="sxs-lookup"><span data-stu-id="c4557-114">Is the functionality you need provided by any existing controls?</span></span>

    - <span data-ttu-id="c4557-115">여러 Windows Forms 컨트롤을 결합하여 필요한 기능을 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c4557-115">Can you get the functionality you need by combining several Windows Forms controls?</span></span>

2. <span data-ttu-id="c4557-116">컨트롤에 대한 개체 모델이 필요한 경우 개체 모델 전체에 기능을 분산할 방법을 결정하고 컨트롤과 하위 개체 간의 기능을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-116">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="c4557-117">개체 모델은 복잡한 컨트롤 계획하거나 여러 기능을 통합하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-117">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>

3. <span data-ttu-id="c4557-118">필요한 컨트롤의 형식을 확인합니다(예: 사용자 정의 컨트롤, 사용자 지정 컨트롤, 상속된 Windows Forms 컨트롤).</span><span class="sxs-lookup"><span data-stu-id="c4557-118">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="c4557-119">자세한 내용은 [컨트롤 형식 권장 사항](control-type-recommendations.md) 및 [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4557-119">For details, see [Control Type Recommendations](control-type-recommendations.md) and [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

4. <span data-ttu-id="c4557-120">기능을 컨트롤의 속성, 메서드 및 이벤트 및 해당 하위 개체 또는 보조 구조로 나타내고 적절한 액세스 수준(예: 공용, 보호 등)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-120">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>

5. <span data-ttu-id="c4557-121">컨트롤에 사용자 지정 그리기가 필요한 경우 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-121">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="c4557-122">자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-122">For details, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

6. <span data-ttu-id="c4557-123">컨트롤이 <xref:System.Windows.Forms.UserControl>에서 상속 되는 경우 컨트롤 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 실행 하 여 런타임 동작을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-123">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="c4557-124">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4557-124">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

7. <span data-ttu-id="c4557-125">또한 Windows 애플리케이션과 같이 새 프로젝트를 만들고 컨테이너에 배치하여 컨트롤을 테스트하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-125">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="c4557-126">이 프로세스는 [연습: 복합 컨트롤 작성](walkthrough-authoring-a-composite-control-with-visual-csharp.md)의 일부로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-126">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md).</span></span>

8. <span data-ttu-id="c4557-127">각 기능을 추가하면 기능을 테스트 프로젝트에 추가하여 새 기능을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-127">As you add each feature, add features to your test project to exercise the new functionality.</span></span>

9. <span data-ttu-id="c4557-128">반복하여 디자인을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-128">Repeat, refining the design.</span></span>

10. <span data-ttu-id="c4557-129">컨트롤을 패키지하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c4557-129">Package and deploy your control.</span></span> <span data-ttu-id="c4557-130">자세한 내용은 [Visual Studio에서 배포 살펴보기](/visualstudio/deployment/deploying-applications-services-and-components)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4557-130">For details, see [First look at deployment in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4557-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4557-131">See also</span></span>

- [<span data-ttu-id="c4557-132">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="c4557-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="c4557-133">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="c4557-133">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="c4557-134">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="c4557-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="c4557-135">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="c4557-135">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="c4557-136">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="c4557-136">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
