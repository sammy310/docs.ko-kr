---
title: '연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 2805ebc66be5908c333e9a5db41076518ad77c1a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705859"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="ac730-102">연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ac730-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="ac730-103">Windows Forms 응용 프로그램에 대 한 폼 및 컨트롤을 구성할 때에 반복적으로 수행 하는 많은 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="ac730-104">다음은 발생 하는 일반적으로 수행된 하는 작업의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="ac730-105">추가 또는 탭에서 제거 된 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="ac730-106">부모 컨트롤을 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="ac730-107">방향 변경 된 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="ac730-108">개발 속도 높이려면, 많은 컨트롤 디자인 타임에 단일 제스처로에서 다음과 같은 일반적인 작업을 수행할 수 있도록 하는 상황에 맞는 메뉴가 있는 스마트 태그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="ac730-109">이러한 작업 이라고 *스마트 태그 동사*합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="ac730-110">스마트 태그의 수명 주기 동안 디자이너에서 컨트롤 인스턴스를 연결 된 상태로 유지 하며 항상 사용할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="ac730-111">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ac730-112">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ac730-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="ac730-113">스마트 태그를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ac730-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="ac730-114">사용 하도록 설정 하 고 스마트 태그를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ac730-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="ac730-115">작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac730-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ac730-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ac730-118">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac730-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ac730-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="ac730-119">Creating the Project</span></span>  
 <span data-ttu-id="ac730-120">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ac730-121">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ac730-121">To create the project</span></span>  
  
1.  <span data-ttu-id="ac730-122">"SmartTagsExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >   **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="ac730-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ac730-123">폼을 선택 합니다 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="ac730-124">스마트 태그를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ac730-124">Using Smart Tags</span></span>  
 <span data-ttu-id="ac730-125">스마트 태그는 항상 사용자에 게 제공 하는 컨트롤에 디자인 타임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="ac730-126">스마트 태그를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="ac730-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="ac730-127">끌어서를 <xref:System.Windows.Forms.TabControl> 에서 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ac730-128">스마트 태그 문자 모양을 확인 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 측면에 표시 되는 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-128">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="ac730-129">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="ac730-130">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **추가 탭** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="ac730-131">탭 페이지를 새로 추가할 관찰 된 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="ac730-132"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="ac730-133">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="ac730-134">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **열 추가** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="ac730-135">새 열을 추가할 관찰 된 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="ac730-136"><xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="ac730-137">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="ac730-138">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **가로 분할자 방향** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="ac730-139">확인 된 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대는 이제 가로 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="ac730-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac730-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac730-140">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="ac730-141">[연습: Windows Forms 구성 요소에 스마트 태그 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ac730-141">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
