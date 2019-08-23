---
title: '방법: UserControl 클래스에서 상속'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 77233517203989f188a2b3ddf436656bc8da82a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966559"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="5d51a-102">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="5d51a-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="5d51a-103">사용자 지정 코드를 사용하여 하나 이상의 Windows Forms 컨트롤의 기능을 결합하려면 *사용자 정의 컨트롤*을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="5d51a-104">사용자 정의 컨트롤은 빠른 컨트롤 개발, 표준 Windows Forms 컨트롤 기능 및 사용자 지정 속성 및 메서드의 다양성을 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="5d51a-105">사용자 정의 컨트롤을 만들기 시작하면 표준 Windows Forms 컨트롤을 배치할 수 있는 시각적인 디자이너로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="5d51a-106">이러한 컨트롤은 표준 컨트롤의 모양 및 동작(모양 및 느낌)뿐만 아니라 고유 기능을 모두 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="5d51a-107">그러나 이러한 컨트롤이 사용자 정의 컨트롤에 기본 제공되지 않으면 더 이상 코드를 통해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="5d51a-108">사용자 정의 컨트롤은 고유한 그리기를 수행하고 컨트롤과 관련된 모든 기본 기능을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="5d51a-109">사용자 정의 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5d51a-109">To create a user control</span></span>

1. <span data-ttu-id="5d51a-110">새 **Windows 컨트롤 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-110">Create a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="5d51a-111">새 프로젝트는 빈 사용자 정의 컨트롤을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="5d51a-112">디자이너의 **도구 상자**에 있는 **Windows Forms** 탭에서 컨트롤을 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="5d51a-113">최종 사용자 정의 컨트롤에 표시하려는 대로 이러한 컨트롤을 배치하고 디자인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="5d51a-114">개발자가 구성 요소 컨트롤에 액세스할 수 있도록 하려는 경우 공용으로 선언하거나 선택적으로 구성 요소 컨트롤의 속성을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="5d51a-115">자세한 내용은 [방법: 구성 요소 컨트롤](how-to-expose-properties-of-constituent-controls.md)의 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="5d51a-116">컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="5d51a-117">F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-117">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="5d51a-118">자세한 내용은 [방법: UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)의 런타임 동작을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d51a-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d51a-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d51a-119">See also</span></span>

- [<span data-ttu-id="5d51a-120">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="5d51a-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="5d51a-121">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="5d51a-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="5d51a-122">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="5d51a-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="5d51a-123">방법: Windows Forms에 대 한 Author 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5d51a-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="5d51a-124">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5d51a-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="5d51a-125">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="5d51a-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
