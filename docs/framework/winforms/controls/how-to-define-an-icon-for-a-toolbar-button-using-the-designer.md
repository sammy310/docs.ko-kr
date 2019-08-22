---
title: '방법: 디자이너를 사용하여 도구 모음 단추에 대한 아이콘 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666199"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="7023f-102">방법: 디자이너를 사용하여 도구 모음 단추에 대한 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="7023f-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="7023f-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="7023f-104"><xref:System.Windows.Forms.ToolBar>사용자가 쉽게 식별할 수 있도록 단추 내에 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="7023f-105">이는 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가 하 고 <xref:System.Windows.Forms.ToolBar> 컨트롤에 연결 하는 과정을 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="7023f-106">다음 절차에는 <xref:System.Windows.Forms.ToolBar> 컨트롤과 <xref:System.Windows.Forms.ImageList> 구성 요소를 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="7023f-107">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="7023f-108">디자인 타임에 도구 모음 단추에 대 한 아이콘을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="7023f-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="7023f-109"><xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="7023f-110">자세한 내용은 [방법: 디자이너](how-to-add-or-remove-imagelist-images-with-the-designer.md)를 사용 하 여 ImageList 이미지를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="7023f-111">폼에서 <xref:System.Windows.Forms.ToolBar> 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="7023f-112">**속성** 창에서 <xref:System.Windows.Forms.ToolBar> 컨트롤 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 의속성을구성요소로설정합니다.<xref:System.Windows.Forms.ImageList></span><span class="sxs-lookup"><span data-stu-id="7023f-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="7023f-113">![](./media/visual-studio-ellipsis-button.png)컨트롤의 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 클릭 하 여 선택 하 고 줄임표 (Visual Studio 속성 창의 줄임표 단추 (...) 단추를 클릭 하 여 ToolBarButton 컬렉션 편집기를 엽니다. <xref:System.Windows.Forms.ToolBar></span><span class="sxs-lookup"><span data-stu-id="7023f-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="7023f-114">**추가** 단추를 사용 하 여 <xref:System.Windows.Forms.ToolBar> 컨트롤에 단추를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7023f-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="7023f-115">**ToolBarButton 컬렉션 편집기**의 오른쪽 창에 표시 되는 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> **속성** 창에서 각 도구 모음 단추의 속성을 목록에 있는 값 중 하나로 설정 합니다 .이 값은에 추가 된 이미지에서가져옵니다.<xref:System.Windows.Forms.ImageList> 구성 요소.</span><span class="sxs-lookup"><span data-stu-id="7023f-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="7023f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7023f-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="7023f-117">방법: 도구 모음 단추에 대 한 트리거 메뉴 이벤트</span><span class="sxs-lookup"><span data-stu-id="7023f-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="7023f-118">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7023f-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="7023f-119">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7023f-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
