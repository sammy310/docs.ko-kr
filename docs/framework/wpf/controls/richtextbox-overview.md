---
title: RichTextBox 개요
description: 'Windows Presentation Foundation RichTextBox 컨트롤을 사용 하 여 사용자가 텍스트, 이미지, 테이블 등의 콘텐츠를 표시 하거나 편집 하는 방법을 알아봅니다. XAML 및 c # 예제를 참조 하세요.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: 525e27f9602136c68f160c738fd1c92ea761536c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166237"
---
# <a name="richtextbox-overview"></a><span data-ttu-id="1dd45-104">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="1dd45-104">RichTextBox Overview</span></span>

<span data-ttu-id="1dd45-105"><xref:System.Windows.Controls.RichTextBox>컨트롤을 사용 하면 단락, 이미지, 테이블 등을 비롯 한 유동 콘텐츠를 표시 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-105">The <xref:System.Windows.Controls.RichTextBox> control enables you to display or edit flow content including paragraphs, images, tables, and more.</span></span> <span data-ttu-id="1dd45-106">이 항목에서는 클래스를 소개 하 <xref:System.Windows.Controls.TextBox> 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 c #에서이를 사용 하는 방법에 대 한 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-106">This topic introduces the <xref:System.Windows.Controls.TextBox> class and provides examples of how to use it in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and C#.</span></span>

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a><span data-ttu-id="1dd45-107">TextBox 또는 RichTextBox?</span><span class="sxs-lookup"><span data-stu-id="1dd45-107">TextBox or RichTextBox?</span></span>

<span data-ttu-id="1dd45-108">및 둘 다 <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.TextBox> 사용자가 텍스트를 편집할 수 있도록 하지만 두 컨트롤이 서로 다른 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-108">Both <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.TextBox> allow users to edit text, however, the two controls are used in different scenarios.</span></span> <span data-ttu-id="1dd45-109">는 <xref:System.Windows.Controls.RichTextBox> 사용자가 서식 있는 텍스트, 이미지, 테이블 또는 기타 풍부한 콘텐츠를 편집 해야 하는 경우에 더 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-109">A <xref:System.Windows.Controls.RichTextBox> is a better choice when it is necessary for the user to edit formatted text, images, tables, or other rich content.</span></span> <span data-ttu-id="1dd45-110">예를 들어 형식 지정, 이미지 등이 필요한 문서, 문서 또는 블로그를 편집 하려면를 사용 하는 것이 가장 좋습니다 <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-110">For example, editing a document, article, or blog that requires formatting, images, etc is best accomplished using a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="1dd45-111">에는 <xref:System.Windows.Controls.TextBox> 보다 작은 시스템 리소스가 필요 <xref:System.Windows.Controls.RichTextBox> 하 고, 일반 텍스트를 편집 해야 하는 경우 (예: 양식에서 사용)에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-111">A <xref:System.Windows.Controls.TextBox> requires less system resources then a <xref:System.Windows.Controls.RichTextBox> and it is ideal when only plain text needs to be edited (i.e. usage in forms).</span></span> <span data-ttu-id="1dd45-112">에 대 한 자세한 내용은 [TextBox 개요](textbox-overview.md) 를 참조 하세요 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-112">See [TextBox Overview](textbox-overview.md) for more information on <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="1dd45-113">아래 표에는 및의 주요 기능이 요약 <xref:System.Windows.Controls.TextBox> 되어 <xref:System.Windows.Controls.RichTextBox> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-113">The table below summarizes the main features of <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox>.</span></span>

|<span data-ttu-id="1dd45-114">제어</span><span class="sxs-lookup"><span data-stu-id="1dd45-114">Control</span></span>|<span data-ttu-id="1dd45-115">실시간 맞춤법 검사</span><span class="sxs-lookup"><span data-stu-id="1dd45-115">Real-time Spellchecking</span></span>|<span data-ttu-id="1dd45-116">상황에 맞는 메뉴</span><span class="sxs-lookup"><span data-stu-id="1dd45-116">Context Menu</span></span>|<span data-ttu-id="1dd45-117">명령 서식 지정 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)</span><span class="sxs-lookup"><span data-stu-id="1dd45-117">Formatting commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B)</span></span>|<span data-ttu-id="1dd45-118"><xref:System.Windows.Documents.FlowDocument>이미지, 단락, 테이블 등의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="1dd45-118"><xref:System.Windows.Documents.FlowDocument> content like images, paragraphs, tables, etc.</span></span>|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="1dd45-119">yes</span><span class="sxs-lookup"><span data-stu-id="1dd45-119">Yes</span></span>|<span data-ttu-id="1dd45-120">예</span><span class="sxs-lookup"><span data-stu-id="1dd45-120">Yes</span></span>|<span data-ttu-id="1dd45-121">예</span><span class="sxs-lookup"><span data-stu-id="1dd45-121">No</span></span>|<span data-ttu-id="1dd45-122">아니요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-122">No.</span></span>|
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="1dd45-123">yes</span><span class="sxs-lookup"><span data-stu-id="1dd45-123">Yes</span></span>|<span data-ttu-id="1dd45-124">yes</span><span class="sxs-lookup"><span data-stu-id="1dd45-124">Yes</span></span>|<span data-ttu-id="1dd45-125">yes</span><span class="sxs-lookup"><span data-stu-id="1dd45-125">Yes</span></span>|<span data-ttu-id="1dd45-126">예</span><span class="sxs-lookup"><span data-stu-id="1dd45-126">Yes</span></span>|

> [!NOTE]
> <span data-ttu-id="1dd45-127"><xref:System.Windows.Controls.TextBox>는 (Ctr + B)와 같은 형식 관련 명령을 지원 하지 않지만, 등의 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> 두 컨트롤에서 많은 기본 명령을 지원 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-127">Although <xref:System.Windows.Controls.TextBox> does not support formatting related commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B), many basic commands are supported by both controls such as <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span></span>

<span data-ttu-id="1dd45-128">위 테이블의 기능은 나중에 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-128">The features from the table above are covered in more detail later.</span></span>

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a><span data-ttu-id="1dd45-129">RichTextBox 만들기</span><span class="sxs-lookup"><span data-stu-id="1dd45-129">Creating a RichTextBox</span></span>

<span data-ttu-id="1dd45-130">아래 코드에서는 <xref:System.Windows.Controls.RichTextBox> 사용자가에서 서식 있는 콘텐츠를 편집할 수 있는을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-130">The code below shows how to create a <xref:System.Windows.Controls.RichTextBox> that a user can edit rich content in.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

<span data-ttu-id="1dd45-131">특히에서 편집 된 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-131">Specifically, the content edited in a <xref:System.Windows.Controls.RichTextBox> is flow content.</span></span> <span data-ttu-id="1dd45-132">유동 콘텐츠에는 서식 있는 텍스트, 이미지, 목록 및 테이블과 같은 다양한 요소 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-132">Flow content can contain many types of elements including formatted text, images, lists, and tables.</span></span> <span data-ttu-id="1dd45-133">유동 문서에 대한 자세한 내용은 [유동 문서 개요](../advanced/flow-document-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-133">See [Flow Document Overview](../advanced/flow-document-overview.md) for in depth information on flow documents.</span></span> <span data-ttu-id="1dd45-134">는 유동 콘텐츠를 포함 하기 위해 <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Documents.FlowDocument> 편집 가능한 콘텐츠를 포함 하는 개체를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-134">In order to contain flow content, a <xref:System.Windows.Controls.RichTextBox> hosts a <xref:System.Windows.Documents.FlowDocument> object which in turn contains the editable content.</span></span> <span data-ttu-id="1dd45-135">에서 유동 콘텐츠를 시연 하기 위해 <xref:System.Windows.Controls.RichTextBox> 다음 코드에서는 단락과 굵게 표시 된 텍스트를 사용 하 여을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-135">To demonstrate flow content in a <xref:System.Windows.Controls.RichTextBox>, the following code shows how to create a <xref:System.Windows.Controls.RichTextBox> with a paragraph and some bolded text.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

<span data-ttu-id="1dd45-136">다음 그림은 이 샘플에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-136">The following illustration shows how this sample renders.</span></span>

<span data-ttu-id="1dd45-137">![콘텐츠가 있는 RichTextBox](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span><span class="sxs-lookup"><span data-stu-id="1dd45-137">![RichTextBox with content](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span></span>

<span data-ttu-id="1dd45-138">및와 같은 요소는 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Bold> 내의 콘텐츠가 표시 되는 방법을 결정 <xref:System.Windows.Controls.RichTextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-138">Elements like <xref:System.Windows.Documents.Paragraph> and <xref:System.Windows.Documents.Bold> determine how the content inside a <xref:System.Windows.Controls.RichTextBox> appears.</span></span> <span data-ttu-id="1dd45-139">사용자가 <xref:System.Windows.Controls.RichTextBox> 콘텐츠를 편집 하는 경우이 유동 콘텐츠를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-139">As a user edits <xref:System.Windows.Controls.RichTextBox> content, they change this flow content.</span></span> <span data-ttu-id="1dd45-140">유동 콘텐츠의 기능 및 이를 사용하는 방법에 대한 자세한 내용은 [유동 문서 개요](../advanced/flow-document-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-140">To learn more about the features of flow content and how to work with it, see [Flow Document Overview](../advanced/flow-document-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1dd45-141">내의 유동 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 다른 컨트롤에 포함 된 유동 콘텐츠와 똑같이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-141">Flow content inside a <xref:System.Windows.Controls.RichTextBox> does not behave exactly like flow content contained in other controls.</span></span> <span data-ttu-id="1dd45-142">예를 들어에 열이 없으므로 <xref:System.Windows.Controls.RichTextBox> 자동 크기 조정 동작이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-142">For example, there are no columns in a <xref:System.Windows.Controls.RichTextBox> and hence no automatic resizing behavior.</span></span> <span data-ttu-id="1dd45-143">또한 검색, 보기 모드, 페이지 탐색 및 확대/축소와 같은 기본 제공 기능은 내에서 사용할 수 없습니다 <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-143">Also, built in features like search, viewing mode, page navigation, and zoom are not available within a <xref:System.Windows.Controls.RichTextBox>.</span></span>

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a><span data-ttu-id="1dd45-144">실시간 맞춤법 검사</span><span class="sxs-lookup"><span data-stu-id="1dd45-144">Real-time Spell Checking</span></span>

<span data-ttu-id="1dd45-145">또는에서 실시간 맞춤법 검사를 사용 하도록 설정할 수 <xref:System.Windows.Controls.TextBox> 있습니다 <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-145">You can enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="1dd45-146">맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).</span><span class="sxs-lookup"><span data-stu-id="1dd45-146">When spellchecking is turned on, a red line appears underneath any misspelled words (see picture below).</span></span>

<span data-ttu-id="1dd45-147">![맞춤법&#45;검사를 사용 하는 텍스트 상자](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span><span class="sxs-lookup"><span data-stu-id="1dd45-147">![Textbox with spell&#45;checking](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span></span>

<span data-ttu-id="1dd45-148">맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-148">See [Enable Spell Checking in a Text Editing Control](how-to-enable-spell-checking-in-a-text-editing-control.md) to learn how to enable spellchecking.</span></span>

<a name="context_menu"></a>

## <a name="context-menu"></a><span data-ttu-id="1dd45-149">상황에 맞는 메뉴</span><span class="sxs-lookup"><span data-stu-id="1dd45-149">Context Menu</span></span>

<span data-ttu-id="1dd45-150">기본적으로 및에 <xref:System.Windows.Controls.TextBox> 는 <xref:System.Windows.Controls.RichTextBox> 사용자가 컨트롤 내에서 마우스 오른쪽 단추를 클릭할 때 표시 되는 상황에 맞는 메뉴가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-150">By default, both <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox> have a context menu that appears when a user right-clicks inside the control.</span></span> <span data-ttu-id="1dd45-151">상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).</span><span class="sxs-lookup"><span data-stu-id="1dd45-151">The context menu allows the user to cut, copy, or paste (see illustration below).</span></span>

<span data-ttu-id="1dd45-152">![상황에 맞는 메뉴가 있는 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span><span class="sxs-lookup"><span data-stu-id="1dd45-152">![TextBox with context menu](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span></span>

<span data-ttu-id="1dd45-153">자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 상황에 맞는 메뉴를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-153">You can create your own custom context menu to override the default one.</span></span> <span data-ttu-id="1dd45-154">자세한 내용은 [RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정](how-to-position-a-custom-context-menu-in-a-richtextbox.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-154">See [Position a Custom Context Menu in a RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) for more information.</span></span>

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a><span data-ttu-id="1dd45-155">명령 편집</span><span class="sxs-lookup"><span data-stu-id="1dd45-155">Editing Commands</span></span>

<span data-ttu-id="1dd45-156">편집 명령을 사용 하면 사용자가 내에서 편집 가능한 콘텐츠의 서식을 지정할 수 <xref:System.Windows.Controls.RichTextBox> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-156">Editing commands enable users to format editable content inside a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="1dd45-157">기본 편집 명령 외에도에 <xref:System.Windows.Controls.RichTextBox> 는를 지원 하지 않는 서식 지정 명령이 포함 되어 있습니다 <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="1dd45-157">Besides basic editing commands, <xref:System.Windows.Controls.RichTextBox> includes formatting commands that <xref:System.Windows.Controls.TextBox> does not support.</span></span> <span data-ttu-id="1dd45-158">예를 들어에서 편집할 때 <xref:System.Windows.Controls.RichTextBox> 사용자가 Ctr + B를 눌러 굵은 텍스트 서식 지정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-158">For example, when editing in a <xref:System.Windows.Controls.RichTextBox>, a user could press Ctr+B to toggle bold text formatting.</span></span> <span data-ttu-id="1dd45-159"><xref:System.Windows.Documents.EditingCommands>사용 가능한 명령의 전체 목록은를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-159">See <xref:System.Windows.Documents.EditingCommands> for a complete list of commands available.</span></span> <span data-ttu-id="1dd45-160">바로 가기 키를 사용하는 방법 외에 단추와 같은 다른 컨트롤에 명령을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-160">In addition to using keyboard shortcuts, you can hook commands up to other controls like buttons.</span></span> <span data-ttu-id="1dd45-161">다음 예제에서는 사용자가 텍스트 서식을 변경하는 데 사용할 수 있는 단추가 포함된 간단한 도구 모음을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-161">The following example shows how to create a simple tool bar containing buttons that the user can use to change text formatting.</span></span>

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

<span data-ttu-id="1dd45-162">다음 그림은 이 샘플에서 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-162">The following illustration shows how this sample displays.</span></span>

<span data-ttu-id="1dd45-163">![도구 모음이 있는 RichTextBox](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span><span class="sxs-lookup"><span data-stu-id="1dd45-163">![RichTextBox with ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span></span>

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a><span data-ttu-id="1dd45-164">콘텐츠가 변경되는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="1dd45-164">Detect when Content Changes</span></span>

<span data-ttu-id="1dd45-165">일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 때마다 검색에 사용할 이벤트의 텍스트를 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox> 대신 변경 <xref:System.Windows.UIElement.KeyDown> 예상할 수 있듯이.</span><span class="sxs-lookup"><span data-stu-id="1dd45-165">Usually the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event should be used to detect whenever the text in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox> changes rather then <xref:System.Windows.UIElement.KeyDown> as you might expect.</span></span> <span data-ttu-id="1dd45-166">예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd45-166">See [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) for an example.</span></span>

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a><span data-ttu-id="1dd45-167">RichTextBox 콘텐츠 저장, 로드 및 인쇄</span><span class="sxs-lookup"><span data-stu-id="1dd45-167">Save, Load, and Print RichTextBox Content</span></span>

<span data-ttu-id="1dd45-168">다음 예제에서는의 내용을 파일에 저장 하 고, 해당 <xref:System.Windows.Controls.RichTextBox> 콘텐츠를 다시에 로드 하 <xref:System.Windows.Controls.RichTextBox> 고, 내용을 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-168">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span> <span data-ttu-id="1dd45-169">예제에 대한 태그는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-169">Below is the markup for the example.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

<span data-ttu-id="1dd45-170">예제에 대한 코드 숨김은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd45-170">Below is the code behind for the example.</span></span>

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="1dd45-171">참조</span><span class="sxs-lookup"><span data-stu-id="1dd45-171">See also</span></span>

- [<span data-ttu-id="1dd45-172">방법 항목</span><span class="sxs-lookup"><span data-stu-id="1dd45-172">How-to Topics</span></span>](richtextbox-how-to-topics.md)
- [<span data-ttu-id="1dd45-173">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="1dd45-173">TextBox Overview</span></span>](textbox-overview.md)
