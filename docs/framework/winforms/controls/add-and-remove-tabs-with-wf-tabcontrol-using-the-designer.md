---
title: 디자이너를 사용 하 여 TabControl에서 탭 추가 및 제거
description: 디자이너를 사용 하 여 Windows Forms TabControl 컨트롤을 사용 하 여 탭을 추가 및 제거 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 955a671693243ab212180046bb60241c8113a854
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622876"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="d9fac-103">방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="d9fac-103">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="d9fac-104"><xref:System.Windows.Forms.TabControl>폼에 컨트롤을 두면 기본적으로 두 개의 탭이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fac-104">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="d9fac-105">디자이너를 사용 하 여 탭을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fac-105">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="d9fac-106">다음 절차에는 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다 <xref:System.Windows.Forms.TabControl> .</span><span class="sxs-lookup"><span data-stu-id="d9fac-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="d9fac-107">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9fac-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="d9fac-108">디자이너를 사용 하 여 탭을 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d9fac-108">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="d9fac-109">컨트롤의 스마트 태그에서 **탭 추가** 또는 **탭 제거** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fac-109">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="d9fac-110">또는</span><span class="sxs-lookup"><span data-stu-id="d9fac-110">-or-</span></span>

     <span data-ttu-id="d9fac-111">**속성** 창에서 속성 옆에 있는 **줄임표 단추** ( ![ ...)를 클릭 ](./media/visual-studio-ellipsis-button.png) 하 여 <xref:System.Windows.Forms.TabControl.TabPages%2A> **TabPage 컬렉션 편집기**를 엽니다 (Visual Studio의 속성 창).</span><span class="sxs-lookup"><span data-stu-id="d9fac-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="d9fac-112">**추가** 또는 **제거** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fac-112">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9fac-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9fac-113">See also</span></span>

- [<span data-ttu-id="d9fac-114">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d9fac-114">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="d9fac-115">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d9fac-115">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="d9fac-116">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="d9fac-116">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="d9fac-117">방법: 탭 페이지를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d9fac-117">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="d9fac-118">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="d9fac-118">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
