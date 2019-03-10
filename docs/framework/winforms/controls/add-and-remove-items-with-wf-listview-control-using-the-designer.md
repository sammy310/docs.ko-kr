---
title: '방법: 디자이너를 사용 하 여 Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 04fe8b1add938f4e7aaa35e08d9924102c91cb9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721227"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="89eee-102">방법: 디자이너를 사용 하 여 Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="89eee-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="89eee-103">Windows Forms에 항목을 추가 하는 프로세스 <xref:System.Windows.Forms.ListView> 컨트롤 주로 이루어져 항목을 지정 하 고 속성을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="89eee-104">목록 항목 추가 또는 제거를 언제 든 지 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="89eee-105">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="89eee-106">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89eee-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="89eee-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="89eee-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89eee-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="89eee-110">디자이너를 사용 하 여 항목을 추가 하거나 제거</span><span class="sxs-lookup"><span data-stu-id="89eee-110">To add or remove items using the designer</span></span>  
  
1.  <span data-ttu-id="89eee-111"><xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2.  <span data-ttu-id="89eee-112">에 **속성** 창에서 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.ListView.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-112">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="89eee-113">합니다 **ListViewItem 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3.  <span data-ttu-id="89eee-114">항목을 추가 하려면 클릭 합니다 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="89eee-115">새 항목의 속성을 같은 설정한 수는 <xref:System.Windows.Forms.ListView.Text%2A> 고 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4.  <span data-ttu-id="89eee-116">항목을 제거 하려면 선택 하 고 클릭 합니다 **제거** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89eee-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="89eee-117">See also</span></span>
- [<span data-ttu-id="89eee-118">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="89eee-118">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="89eee-119">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="89eee-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="89eee-120">방법: Windows Forms ListView 컨트롤을 사용 하 여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="89eee-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="89eee-121">방법: Windows Forms ListView 컨트롤에 대 한 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89eee-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="89eee-122">방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가</span><span class="sxs-lookup"><span data-stu-id="89eee-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="89eee-123">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="89eee-123">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
