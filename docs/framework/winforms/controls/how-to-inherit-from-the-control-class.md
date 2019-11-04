---
title: '방법: Control 클래스에서 상속'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458376"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="9b2c5-102">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="9b2c5-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="9b2c5-103">Windows Form에서 사용할 완전히 사용자 지정 컨트롤을 만들려면 <xref:System.Windows.Forms.Control> 클래스에서 상속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="9b2c5-104"><xref:System.Windows.Forms.Control> 클래스에서 상속 하는 동안 추가 계획 및 구현을 수행 해야 하는 반면, 가장 큰 범위의 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="9b2c5-105"><xref:System.Windows.Forms.Control>에서 상속 하는 경우 컨트롤이 작동 하 게 하는 매우 기본적인 기능을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="9b2c5-106"><xref:System.Windows.Forms.Control> 클래스의 고유한 기능은 키보드와 마우스를 통해 사용자 입력을 처리 하 고, 컨트롤의 범위와 크기를 정의 하 고, windows 핸들을 제공 하 고, 메시지 처리 및 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="9b2c5-107">이 경우에는 컨트롤의 그래픽 인터페이스의 실제 렌더링인 그리기를 통합하거나 특정 사용자 상호 작용 기능을 통합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="9b2c5-108">사용자 지정 코드를 통해 이러한 모든 사항을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="9b2c5-109">사용자 지정 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9b2c5-109">To create a custom control</span></span>

1. <span data-ttu-id="9b2c5-110">Visual Studio에서 새 **Windows 응용 프로그램** 또는 **windows 컨트롤 라이브러리** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="9b2c5-111">**프로젝트** 메뉴에서 **클래스 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="9b2c5-112">**새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="9b2c5-113">새 사용자 지정 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="9b2c5-114">**F7** 키를 눌러 사용자 지정 컨트롤에 대 한 **코드 편집기** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="9b2c5-115"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 찾습니다 .이 메서드는 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출 하는 경우를 제외 하 고는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="9b2c5-116">코드를 수정하여 컨트롤에 원하는 사용자 지정 그리기를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="9b2c5-117">컨트롤의 그래픽을 렌더링하는 코드를 작성하는 방법에 대한 정보는 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="9b2c5-118">컨트롤이 통합하는 사용자 지정 메서드, 속성 또는 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="9b2c5-119">컨트롤을 저장하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2c5-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b2c5-120">참조</span><span class="sxs-lookup"><span data-stu-id="9b2c5-120">See also</span></span>

- [<span data-ttu-id="9b2c5-121">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="9b2c5-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="9b2c5-122">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="9b2c5-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="9b2c5-123">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="9b2c5-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="9b2c5-124">방법: Windows Forms 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="9b2c5-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="9b2c5-125">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9b2c5-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="9b2c5-126">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="9b2c5-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
