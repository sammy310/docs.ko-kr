---
title: '연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015760"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="f294e-102">연습: 스마트 태그를 사용 하 여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="f294e-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="f294e-103">Windows Forms 응용 프로그램에 대 한 폼과 컨트롤을 구성할 때 반복적으로 수행 하는 많은 태스크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="f294e-104">일반적으로 수행 되는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="f294e-105">에서 <xref:System.Windows.Forms.TabControl>탭 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="f294e-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="f294e-106">컨트롤을 부모에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="f294e-107"><xref:System.Windows.Forms.SplitContainer> 컨트롤의 방향 변경</span><span class="sxs-lookup"><span data-stu-id="f294e-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="f294e-108">개발 속도를 높이기 위해 많은 컨트롤은 디자인 타임에 단일 제스처로 이와 같은 일반적인 작업을 수행할 수 있는 상황에 맞는 메뉴 인 스마트 태그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="f294e-109">이러한 작업을 *스마트 태그 동사*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="f294e-110">스마트 태그는 디자이너에서 수명 동안 컨트롤 인스턴스에 연결 된 상태로 유지 되며 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f294e-111">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-111">Create the project</span></span>

<span data-ttu-id="f294e-112">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="f294e-113">Visual Studio에서 **SmartTagsExample**이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="f294e-114">**Windows Forms 디자이너**에서 양식을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="f294e-115">스마트 태그 사용</span><span class="sxs-lookup"><span data-stu-id="f294e-115">Use smart tags</span></span>

<span data-ttu-id="f294e-116">스마트 태그는 디자인 타임에이를 제공 하는 컨트롤에서 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="f294e-117">를 <xref:System.Windows.Forms.TabControl> **도구 상자** 에서 폼으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="f294e-118">의 측면![에표시](./media/vs-winformsmttagglyph.gif)되는 스마트 태그 문자 모양 (스마트 태그 문자 모양)을 확인 합니다. <xref:System.Windows.Forms.TabControl></span><span class="sxs-lookup"><span data-stu-id="f294e-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="f294e-119">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="f294e-120">문자 모양 옆에 나타나는 바로 가기 메뉴에서 **추가 탭** 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="f294e-121">새 탭 페이지가에 추가 <xref:System.Windows.Forms.TabControl>되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="f294e-122"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="f294e-123">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="f294e-124">문자 모양 옆에 나타나는 바로 가기 메뉴에서 **열 추가** 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="f294e-125">새 열이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 추가 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="f294e-126"><xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="f294e-127">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="f294e-128">문자 모양 옆에 나타나는 바로 가기 메뉴에서 **가로 분할자 방향** 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="f294e-129"><xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할자 막대가 이제 가로 방향으로 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f294e-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="f294e-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="f294e-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
