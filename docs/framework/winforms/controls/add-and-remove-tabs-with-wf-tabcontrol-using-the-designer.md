---
title: 디자이너를 사용 하 여 TabControl에서 탭 추가 및 제거
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 445342ffb3b53c880ac38da52076e0c0cb0a9f23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746290"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="0b12c-102">방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="0b12c-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="0b12c-103">폼에 <xref:System.Windows.Forms.TabControl> 컨트롤을 두면 기본적으로 두 개의 탭이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="0b12c-104">디자이너를 사용 하 여 탭을 추가 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-104">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="0b12c-105">다음 절차에는 <xref:System.Windows.Forms.TabControl> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="0b12c-106">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [How to: ](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms 응용 프로그램 프로젝트를 만들고 방법을 [합니다. Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="0b12c-107">디자이너를 사용 하 여 탭을 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="0b12c-107">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="0b12c-108">컨트롤의 스마트 태그에서 **탭 추가** 또는 **탭 제거** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-108">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="0b12c-109">또는</span><span class="sxs-lookup"><span data-stu-id="0b12c-109">-or-</span></span>

     <span data-ttu-id="0b12c-110">**속성** 창에서 속성 옆에 속성 창 있는 **줄임표** 단추 (...)를 클릭 하 여 **TabPage 컬렉션 편집기**를 엽니다. 이 단추를 클릭 하 여 속성 옆에<xref:System.Windows.Forms.TabControl.TabPages%2A> ![있는 줄임표 단추 (...)를](./media/visual-studio-ellipsis-button.png)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-110">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="0b12c-111">**추가** 또는 **제거** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b12c-111">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b12c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b12c-112">See also</span></span>

- [<span data-ttu-id="0b12c-113">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0b12c-113">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="0b12c-114">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0b12c-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="0b12c-115">방법: 탭 페이지에 컨트롤을 추가</span><span class="sxs-lookup"><span data-stu-id="0b12c-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="0b12c-116">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0b12c-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="0b12c-117">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="0b12c-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
