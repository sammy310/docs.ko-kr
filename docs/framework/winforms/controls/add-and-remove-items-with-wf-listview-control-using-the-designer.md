---
title: 디자이너를 사용 하 여 ListView 컨트롤에서 항목 추가 및 제거
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732301"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4a3bc-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="4a3bc-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="4a3bc-103">항목을 Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤에 추가 하는 프로세스는 주로 항목을 지정 하 고 여기에 속성을 할당 하는 것으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="4a3bc-104">언제 든 지 목록 항목 추가 또는 제거 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="4a3bc-105">다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4a3bc-106">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="4a3bc-107">디자이너를 사용 하 여 항목을 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4a3bc-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="4a3bc-108"><xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="4a3bc-109">**속성** 창에서 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆의 속성 창 Visual Studio.](./media/visual-studio-ellipsis-button.png)) 단추에 **있는 줄임표 단추** (...)를![클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="4a3bc-110">**ListViewItem 컬렉션 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="4a3bc-111">항목을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="4a3bc-112">그런 다음 <xref:System.Windows.Forms.ListView.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성과 같은 새 항목의 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="4a3bc-113">항목을 제거 하려면 항목을 선택 하 고 **제거** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3bc-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a3bc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a3bc-114">See also</span></span>

- [<span data-ttu-id="4a3bc-115">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4a3bc-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="4a3bc-116">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="4a3bc-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4a3bc-117">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="4a3bc-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4a3bc-118">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="4a3bc-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4a3bc-119">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4a3bc-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="4a3bc-120">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="4a3bc-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
