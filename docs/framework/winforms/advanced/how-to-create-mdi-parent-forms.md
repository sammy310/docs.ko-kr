---
title: '방법: MDI 부모 양식 만들기'
description: Windows Forms 디자이너를 사용 하 여 프로그래밍 방식으로 MDI 부모 폼을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d387837a565ca247f62828c19f353990b35117c7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174707"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="d4812-103">방법: MDI 부모 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="d4812-103">How to: Create MDI Parent Forms</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4812-104">이 항목에서는 <xref:System.Windows.Forms.MainMenu> 컨트롤로 대체된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-104">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="d4812-105"><xref:System.Windows.Forms.MainMenu> 컨트롤은 이전 버전과의 호환성을 유지하고 원하는 경우 이후에 사용할 수 있도록 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-105">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d4812-106">을 사용 하 여 MDI 부모 폼을 만드는 방법에 대 한 자세한 내용은 <xref:System.Windows.Forms.MenuStrip> [방법: MenuStrip을 사용 하 여 Mdi 창 목록 만들기](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4812-106">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>

<span data-ttu-id="d4812-107">MDI(다중 문서 인터페이스) 부모 폼은 MDI(다중 문서 인터페이스) 애플리케이션의 기반이 되는 요소로,</span><span class="sxs-lookup"><span data-stu-id="d4812-107">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="d4812-108">사용자가 MDI 애플리케이션과 상호 작용하는 하위 창인 MDI 자식 창을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-108">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="d4812-109">MDI 부모 폼은 Windows Forms 디자이너에서 그리고 프로그래밍 방식으로 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-109">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>

## <a name="create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="d4812-110">디자인 타임에 MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="d4812-110">Create an MDI parent form at design time</span></span>

1. <span data-ttu-id="d4812-111">Visual Studio에서 Windows 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-111">Create a Windows Application project in Visual Studio.</span></span>

2. <span data-ttu-id="d4812-112">**속성** 창에서 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 **true**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-112">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>

     <span data-ttu-id="d4812-113">그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-113">This designates the form as an MDI container for child windows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4812-114">**속성** 창에서 속성을 설정하는 중에 원하는 경우 `WindowState` 속성을 **Maximized**(최대화)로 설정할 수도 있습니다. 부모 양식을 최대화하면 MDI 자식 창을 가장 쉽게 조작할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-114">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="d4812-115">또한 MDI 부모 폼에는 <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> 속성을 사용하여 설정하는 배경색이 아니라 Windows 시스템 제어판에 설정된 시스템 색이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-115">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>

3. <span data-ttu-id="d4812-116">**도구 상자**에서 **MenuStrip** 컨트롤을 양식으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-116">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="d4812-117">**텍스트** 속성을 **새로 만들기(&N)** 및 **닫기(&C)** 라는 하위 항목이 있는 **파일(&F)** 로 설정하여 최상위 메뉴 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-117">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="d4812-118">**창(&W)** 이라는 최상위 메뉴 항목도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-118">Also create a top-level menu item called **&Window**.</span></span>

     <span data-ttu-id="d4812-119">런타임에 첫 번째 메뉴가 작성되고 메뉴 항목은 숨겨지며 두 번째 메뉴는 열려 있는 MDI 자식 창을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-119">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="d4812-120">이제 MDI 부모 창이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-120">At this point, you have created an MDI parent window.</span></span>

4. <span data-ttu-id="d4812-121">**F5** 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4812-121">Press **F5** to run the application.</span></span> <span data-ttu-id="d4812-122">MDI 부모 양식 내에서 조작하는 MDI 자식 창을 만드는 방법에 대한 자세한 내용은 [방법: MDI 자식 양식 만들기](how-to-create-mdi-child-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4812-122">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4812-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4812-123">See also</span></span>

- [<span data-ttu-id="d4812-124">MDI(다중 문서 인터페이스) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="d4812-124">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="d4812-125">방법: MDI 자식 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="d4812-125">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="d4812-126">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="d4812-126">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="d4812-127">방법: 활성 MDI 자식으로 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="d4812-127">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="d4812-128">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="d4812-128">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
