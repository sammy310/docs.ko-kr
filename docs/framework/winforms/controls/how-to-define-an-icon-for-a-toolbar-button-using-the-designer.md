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
ms.openlocfilehash: 04b4b2ddeadf5a86bd191d5a173659032461dfc5
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960214"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="1fd64-102">방법: 디자이너를 사용하여 도구 모음 단추에 대한 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="1fd64-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="1fd64-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="1fd64-104"><xref:System.Windows.Forms.ToolBar> 단추는 사용자가 쉽게 식별할 수 있도록 내에 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="1fd64-105">추가 이미지를 통해 얻을 수는 <xref:System.Windows.Forms.ImageList> 구성 요소와 연결할 때와 <xref:System.Windows.Forms.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="1fd64-106">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ToolBar> 컨트롤 및 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="1fd64-107">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1fd64-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1fd64-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1fd64-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fd64-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="1fd64-111">디자인 타임에 도구 모음 단추의 아이콘을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1fd64-111">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="1fd64-112">이미지를 추가 합니다 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="1fd64-113">자세한 내용은 [방법: 디자이너를 사용 하 여 ImageList 이미지 추가 또는 제거](how-to-add-or-remove-imagelist-images-with-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="1fd64-114">선택 된 <xref:System.Windows.Forms.ToolBar> 양식에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="1fd64-115">에 **속성** 창에서 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 속성을는 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="1fd64-116">클릭 합니다 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 줄임표 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 버튼을 클릭 하는 **ToolBarButton 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="1fd64-117">사용 합니다 **추가** 단추를 추가 하는 단추는 <xref:System.Windows.Forms.ToolBar> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="1fd64-118">에 **속성** 의 오른쪽 창에 표시 되는 창을 **ToolBarButton 컬렉션 편집기**설정는 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 목록의 값 중 하나로 각 도구 모음 단추의 속성은 추가할 이미지에서 출발 하는 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1fd64-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fd64-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="1fd64-119">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="1fd64-120">방법: Toolbar 단추의 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="1fd64-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="1fd64-121">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1fd64-121">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="1fd64-122">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1fd64-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
