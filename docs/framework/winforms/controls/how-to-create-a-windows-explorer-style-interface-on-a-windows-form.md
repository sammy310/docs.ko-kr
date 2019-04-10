---
title: '방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: dd70feaba29e29748ac56729632fa359582a6914
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327375"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="9166c-102">방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="9166c-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="9166c-103">Windows 탐색기는 쉽게 사용할 수 있으므로 응용 프로그램에 대 한 공통 사용자 인터페이스 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="9166c-104">Windows 탐색기가 기본적으로 <xref:System.Windows.Forms.TreeView> 컨트롤 및 <xref:System.Windows.Forms.ListView> 별도 패널에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="9166c-105">패널을 분할 하 여 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="9166c-106">이 컨트롤 배열을 표시 하 고 정보를 검색에 대 한 매우 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="9166c-107">다음 단계는 Windows 탐색기와 유사한 폼에서에서 컨트롤을 정렬 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="9166c-108">Windows 탐색기 응용 프로그램의 파일 검색 기능을 추가 하는 방법을 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9166c-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9166c-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9166c-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9166c-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="9166c-112">Windows 탐색기 스타일 Windows 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9166c-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1. <span data-ttu-id="9166c-113">새 Windows 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트** > **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="9166c-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="9166c-114">**도구 상자**:</span><span class="sxs-lookup"><span data-stu-id="9166c-114">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="9166c-115">끌어서를 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="9166c-116">끌어서를 <xref:System.Windows.Forms.TreeView> 컨트롤을 **SplitterPanel1** (의 패널을 합니다 <xref:System.Windows.Forms.SplitContainer> 표시 하는 컨트롤 **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="9166c-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="9166c-117">끌어서를 <xref:System.Windows.Forms.ListView> 컨트롤을 **SplitterPanel2** (의 패널 합니다 <xref:System.Windows.Forms.SplitContainer> 표시 컨트롤 **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="9166c-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3. <span data-ttu-id="9166c-118">CTRL 키를 차례로 클릭 하 여 모든 3 가지 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="9166c-119">선택 하는 경우는 <xref:System.Windows.Forms.SplitContainer> 컨트롤, 패널 대신 분할 막대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9166c-120">사용 하지 않는 합니다 **모두 선택** 명령을 합니다 **편집** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="9166c-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="9166c-121">이렇게 하면 다음 단계에 필요한 속성에 표시 되지 것입니다 합니다 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="9166c-122">**속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="9166c-123">F5 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="9166c-124">Windows 탐색기와 비슷한 두 부분으로 구성 사용자 인터페이스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9166c-125">분할자를 끌면 패널 자체 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9166c-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9166c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="9166c-126">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="9166c-127">방법: Windows Forms를 사용하여 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="9166c-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="9166c-128">방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의</span><span class="sxs-lookup"><span data-stu-id="9166c-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="9166c-129">방법: 가로로 창 분할</span><span class="sxs-lookup"><span data-stu-id="9166c-129">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="9166c-130">SplitContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9166c-130">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
