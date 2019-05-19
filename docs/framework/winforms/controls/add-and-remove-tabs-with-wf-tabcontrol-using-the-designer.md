---
title: '방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 560bb35bf9685abbc40bc7b87a4490752c546ea4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880641"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="37109-102">방법: 디자이너를 사용하여 Windows Forms TabControl에서 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="37109-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="37109-103">배치 하는 경우는 <xref:System.Windows.Forms.TabControl> 컨트롤이 폼에 기본적으로 두 개의 탭 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="37109-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="37109-104">추가 하거나 디자이너를 사용 하 여 탭을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37109-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="37109-105">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="37109-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="37109-106">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="37109-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37109-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37109-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="37109-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37109-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="37109-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37109-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="37109-110">추가 하거나 디자이너를 사용 하 여 탭을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="37109-110">To add or remove a tab using the designer</span></span>  
  
- <span data-ttu-id="37109-111">컨트롤의 스마트 태그를 클릭 **추가 탭** 또는 **탭 제거**</span><span class="sxs-lookup"><span data-stu-id="37109-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="37109-112">또는</span><span class="sxs-lookup"><span data-stu-id="37109-112">-or-</span></span>  
  
     <span data-ttu-id="37109-113">에 **속성** 창 클릭 합니다 **줄임표** 단추 (![The 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 옆에 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성 열려는 합니다 **TabPage 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="37109-113">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="37109-114">클릭 합니다 **추가** 하거나 **제거** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="37109-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37109-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="37109-115">See also</span></span>

- [<span data-ttu-id="37109-116">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="37109-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="37109-117">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="37109-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="37109-118">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="37109-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="37109-119">방법: 탭 페이지를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="37109-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="37109-120">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="37109-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
