---
title: '연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211413"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="a8c39-102">연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="a8c39-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="a8c39-103">Windows Forms 응용 프로그램에 대 한 폼 및 컨트롤을 구성할 때에 반복적으로 수행 하는 많은 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="a8c39-104">다음은 발생 하는 일반적으로 수행된 하는 작업의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="a8c39-105">추가 또는 탭에서 제거 된 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="a8c39-106">부모 컨트롤을 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="a8c39-107">방향 변경 된 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="a8c39-108">개발 속도 높이려면, 많은 컨트롤 디자인 타임에 단일 제스처로에서 다음과 같은 일반적인 작업을 수행할 수 있도록 하는 상황에 맞는 메뉴가 있는 스마트 태그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="a8c39-109">이러한 작업 이라고 *스마트 태그 동사*합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="a8c39-110">스마트 태그의 수명 주기 동안 디자이너에서 컨트롤 인스턴스를 연결 된 상태로 유지 하며 항상 사용할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="a8c39-111">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a8c39-112">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a8c39-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="a8c39-113">스마트 태그를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a8c39-113">Using smart tags</span></span>

- <span data-ttu-id="a8c39-114">사용 하도록 설정 하 고 스마트 태그를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8c39-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="a8c39-115">작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a8c39-116">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-116">Create the project</span></span>

<span data-ttu-id="a8c39-117">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="a8c39-118">Visual Studio에서 "SmartTagsExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트**  >  **시각적 C#**  하거나 **Visual Basic** > **클래식 데스크톱** > **Windows Forms 응용 프로그램**).</span><span class="sxs-lookup"><span data-stu-id="a8c39-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="a8c39-119">폼을 선택 합니다 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="a8c39-120">스마트 태그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-120">Use smart tags</span></span>

<span data-ttu-id="a8c39-121">스마트 태그는 항상 사용자에 게 제공 하는 컨트롤에 디자인 타임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="a8c39-122">끌어서를 <xref:System.Windows.Forms.TabControl> 에서 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="a8c39-123">스마트 태그 문자 모양을 확인 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 측면에 표시 되는 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="a8c39-124">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="a8c39-125">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **추가 탭** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="a8c39-126">탭 페이지를 새로 추가할 관찰 된 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="a8c39-127"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="a8c39-128">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="a8c39-129">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **열 추가** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="a8c39-130">새 열을 추가할 관찰 된 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="a8c39-131"><xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="a8c39-132">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="a8c39-133">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 합니다 **가로 분할자 방향** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="a8c39-134">확인 된 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대는 이제 가로 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="a8c39-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8c39-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8c39-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="a8c39-136">[연습: Windows Forms 구성 요소에 스마트 태그 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a8c39-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
