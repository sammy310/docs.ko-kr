---
title: RichTextBox 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: bfed42bcf3693ef744b3ed2b54ebe070931513a9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855741"
---
# <a name="richtextbox-overview"></a><span data-ttu-id="098a3-102">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="098a3-102">RichTextBox Overview</span></span>

<span data-ttu-id="098a3-103"><xref:System.Windows.Controls.RichTextBox> 컨트롤을 사용 하면 단락, 이미지, 테이블 등을 비롯 한 유동 콘텐츠를 표시 하거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-103">The <xref:System.Windows.Controls.RichTextBox> control enables you to display or edit flow content including paragraphs, images, tables, and more.</span></span> <span data-ttu-id="098a3-104">이 항목에서는 클래스 <xref:System.Windows.Controls.TextBox> 를 소개 하 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 C#에서이 클래스를 사용 하는 방법에 대 한 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-104">This topic introduces the <xref:System.Windows.Controls.TextBox> class and provides examples of how to use it in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and C#.</span></span>

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a><span data-ttu-id="098a3-105">TextBox 또는 RichTextBox?</span><span class="sxs-lookup"><span data-stu-id="098a3-105">TextBox or RichTextBox?</span></span>

<span data-ttu-id="098a3-106"><xref:System.Windows.Controls.RichTextBox> 및<xref:System.Windows.Controls.TextBox> 둘 다 사용자가 텍스트를 편집할 수 있도록 하지만 두 컨트롤이 서로 다른 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-106">Both <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.TextBox> allow users to edit text, however, the two controls are used in different scenarios.</span></span> <span data-ttu-id="098a3-107">는 <xref:System.Windows.Controls.RichTextBox> 사용자가 서식 있는 텍스트, 이미지, 테이블 또는 기타 풍부한 콘텐츠를 편집 해야 하는 경우에 더 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-107">A <xref:System.Windows.Controls.RichTextBox> is a better choice when it is necessary for the user to edit formatted text, images, tables, or other rich content.</span></span> <span data-ttu-id="098a3-108">예를 들어 형식 지정, 이미지 등이 필요한 문서, 문서 또는 블로그를 편집 하려면를 <xref:System.Windows.Controls.RichTextBox>사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-108">For example, editing a document, article, or blog that requires formatting, images, etc is best accomplished using a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="098a3-109">에 <xref:System.Windows.Controls.TextBox> 는 보다 작은 시스템 리소스가 <xref:System.Windows.Controls.RichTextBox> 필요 하 고, 일반 텍스트를 편집 해야 하는 경우 (예: 양식에서 사용)에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-109">A <xref:System.Windows.Controls.TextBox> requires less system resources then a <xref:System.Windows.Controls.RichTextBox> and it is ideal when only plain text needs to be edited (i.e. usage in forms).</span></span> <span data-ttu-id="098a3-110">에<xref:System.Windows.Controls.TextBox>대 한 자세한 내용은 [TextBox 개요](textbox-overview.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-110">See [TextBox Overview](textbox-overview.md) for more information on <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="098a3-111">아래 표에는 및 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox>의 주요 기능이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-111">The table below summarizes the main features of <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox>.</span></span>

|<span data-ttu-id="098a3-112">컨트롤</span><span class="sxs-lookup"><span data-stu-id="098a3-112">Control</span></span>|<span data-ttu-id="098a3-113">실시간 맞춤법 검사</span><span class="sxs-lookup"><span data-stu-id="098a3-113">Real-time Spellchecking</span></span>|<span data-ttu-id="098a3-114">상황에 맞는 메뉴</span><span class="sxs-lookup"><span data-stu-id="098a3-114">Context Menu</span></span>|<span data-ttu-id="098a3-115">명령 서식 지정 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)</span><span class="sxs-lookup"><span data-stu-id="098a3-115">Formatting commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B)</span></span>|<span data-ttu-id="098a3-116"><xref:System.Windows.Documents.FlowDocument>이미지, 단락, 테이블 등의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="098a3-116"><xref:System.Windows.Documents.FlowDocument> content like images, paragraphs, tables, etc.</span></span>|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="098a3-117">예</span><span class="sxs-lookup"><span data-stu-id="098a3-117">Yes</span></span>|<span data-ttu-id="098a3-118">예</span><span class="sxs-lookup"><span data-stu-id="098a3-118">Yes</span></span>|<span data-ttu-id="098a3-119">아니요</span><span class="sxs-lookup"><span data-stu-id="098a3-119">No</span></span>|<span data-ttu-id="098a3-120">아니요.</span><span class="sxs-lookup"><span data-stu-id="098a3-120">No.</span></span>|
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="098a3-121">예</span><span class="sxs-lookup"><span data-stu-id="098a3-121">Yes</span></span>|<span data-ttu-id="098a3-122">예</span><span class="sxs-lookup"><span data-stu-id="098a3-122">Yes</span></span>|<span data-ttu-id="098a3-123">예</span><span class="sxs-lookup"><span data-stu-id="098a3-123">Yes</span></span>|<span data-ttu-id="098a3-124">예</span><span class="sxs-lookup"><span data-stu-id="098a3-124">Yes</span></span>|

> [!NOTE]
> <span data-ttu-id="098a3-125">는 <xref:System.Windows.Controls.TextBox> (Ctr + B)와 같은 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> 형식 관련 명령을 지원 하지 않지만, 등의 두 컨트롤 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>에서 많은 기본 명령을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-125">Although <xref:System.Windows.Controls.TextBox> does not support formatting related commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B), many basic commands are supported by both controls such as <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span></span>

<span data-ttu-id="098a3-126">위 테이블의 기능은 나중에 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-126">The features from the table above are covered in more detail later.</span></span>

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a><span data-ttu-id="098a3-127">RichTextBox 만들기</span><span class="sxs-lookup"><span data-stu-id="098a3-127">Creating a RichTextBox</span></span>

<span data-ttu-id="098a3-128">아래 코드에서는 사용자가에서 서식 있는 <xref:System.Windows.Controls.RichTextBox> 콘텐츠를 편집할 수 있는을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-128">The code below shows how to create a <xref:System.Windows.Controls.RichTextBox> that a user can edit rich content in.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

<span data-ttu-id="098a3-129">특히에서 <xref:System.Windows.Controls.RichTextBox> 편집 된 콘텐츠는 유동 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-129">Specifically, the content edited in a <xref:System.Windows.Controls.RichTextBox> is flow content.</span></span> <span data-ttu-id="098a3-130">유동 콘텐츠에는 서식 있는 텍스트, 이미지, 목록 및 테이블과 같은 다양한 요소 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-130">Flow content can contain many types of elements including formatted text, images, lists, and tables.</span></span> <span data-ttu-id="098a3-131">유동 문서에 대한 자세한 내용은 [유동 문서 개요](../advanced/flow-document-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-131">See [Flow Document Overview](../advanced/flow-document-overview.md) for in depth information on flow documents.</span></span> <span data-ttu-id="098a3-132">는 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠를 포함 하기 위해 편집 가능한 콘텐츠 <xref:System.Windows.Documents.FlowDocument> 를 포함 하는 개체를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-132">In order to contain flow content, a <xref:System.Windows.Controls.RichTextBox> hosts a <xref:System.Windows.Documents.FlowDocument> object which in turn contains the editable content.</span></span> <span data-ttu-id="098a3-133">에서 <xref:System.Windows.Controls.RichTextBox>유동 콘텐츠를 시연 하기 위해 다음 코드에서는 단락과 굵게 표시 된 텍스트 <xref:System.Windows.Controls.RichTextBox> 를 사용 하 여을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-133">To demonstrate flow content in a <xref:System.Windows.Controls.RichTextBox>, the following code shows how to create a <xref:System.Windows.Controls.RichTextBox> with a paragraph and some bolded text.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

<span data-ttu-id="098a3-134">다음 그림은 이 샘플에서 렌더링하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-134">The following illustration shows how this sample renders.</span></span>

<span data-ttu-id="098a3-135">![콘텐츠가 있는 RichTextBox](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span><span class="sxs-lookup"><span data-stu-id="098a3-135">![RichTextBox with content](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span></span>

<span data-ttu-id="098a3-136"><xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Documents.Paragraph> 와같은요소는내의콘텐츠가표시되는방법을결정합니다.<xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="098a3-136">Elements like <xref:System.Windows.Documents.Paragraph> and <xref:System.Windows.Documents.Bold> determine how the content inside a <xref:System.Windows.Controls.RichTextBox> appears.</span></span> <span data-ttu-id="098a3-137">사용자가 콘텐츠를 <xref:System.Windows.Controls.RichTextBox> 편집 하는 경우이 유동 콘텐츠를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-137">As a user edits <xref:System.Windows.Controls.RichTextBox> content, they change this flow content.</span></span> <span data-ttu-id="098a3-138">유동 콘텐츠의 기능 및 이를 사용하는 방법에 대한 자세한 내용은 [유동 문서 개요](../advanced/flow-document-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-138">To learn more about the features of flow content and how to work with it, see [Flow Document Overview](../advanced/flow-document-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="098a3-139">내의 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠는 다른 컨트롤에 포함 된 유동 콘텐츠와 똑같이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-139">Flow content inside a <xref:System.Windows.Controls.RichTextBox> does not behave exactly like flow content contained in other controls.</span></span> <span data-ttu-id="098a3-140">예를 들어에 <xref:System.Windows.Controls.RichTextBox> 열이 없으므로 자동 크기 조정 동작이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-140">For example, there are no columns in a <xref:System.Windows.Controls.RichTextBox> and hence no automatic resizing behavior.</span></span> <span data-ttu-id="098a3-141">또한 검색, 보기 모드, 페이지 탐색 및 확대/축소와 같은 기본 제공 기능은 내 <xref:System.Windows.Controls.RichTextBox>에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-141">Also, built in features like search, viewing mode, page navigation, and zoom are not available within a <xref:System.Windows.Controls.RichTextBox>.</span></span>

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a><span data-ttu-id="098a3-142">실시간 맞춤법 검사</span><span class="sxs-lookup"><span data-stu-id="098a3-142">Real-time Spell Checking</span></span>

<span data-ttu-id="098a3-143"><xref:System.Windows.Controls.TextBox> 또는<xref:System.Windows.Controls.RichTextBox>에서 실시간 맞춤법 검사를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-143">You can enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="098a3-144">맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).</span><span class="sxs-lookup"><span data-stu-id="098a3-144">When spellchecking is turned on, a red line appears underneath any misspelled words (see picture below).</span></span>

<span data-ttu-id="098a3-145">![맞춤법 검사 기능이 있는 Textbox](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span><span class="sxs-lookup"><span data-stu-id="098a3-145">![Textbox with spell&#45;checking](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span></span>

<span data-ttu-id="098a3-146">맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-146">See [Enable Spell Checking in a Text Editing Control](how-to-enable-spell-checking-in-a-text-editing-control.md) to learn how to enable spellchecking.</span></span>

<a name="context_menu"></a>

## <a name="context-menu"></a><span data-ttu-id="098a3-147">상황에 맞는 메뉴</span><span class="sxs-lookup"><span data-stu-id="098a3-147">Context Menu</span></span>

<span data-ttu-id="098a3-148">기본적 <xref:System.Windows.Controls.TextBox> 으로 및 <xref:System.Windows.Controls.RichTextBox> 에는 사용자가 컨트롤 내에서 마우스 오른쪽 단추를 클릭할 때 표시 되는 상황에 맞는 메뉴가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-148">By default, both <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox> have a context menu that appears when a user right-clicks inside the control.</span></span> <span data-ttu-id="098a3-149">상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).</span><span class="sxs-lookup"><span data-stu-id="098a3-149">The context menu allows the user to cut, copy, or paste (see illustration below).</span></span>

<span data-ttu-id="098a3-150">![상황에 맞는 메뉴가 있는 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span><span class="sxs-lookup"><span data-stu-id="098a3-150">![TextBox with context menu](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span></span>

<span data-ttu-id="098a3-151">자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 상황에 맞는 메뉴를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-151">You can create your own custom context menu to override the default one.</span></span> <span data-ttu-id="098a3-152">자세한 내용은 [RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정](how-to-position-a-custom-context-menu-in-a-richtextbox.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-152">See [Position a Custom Context Menu in a RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) for more information.</span></span>

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a><span data-ttu-id="098a3-153">편집 명령</span><span class="sxs-lookup"><span data-stu-id="098a3-153">Editing Commands</span></span>

<span data-ttu-id="098a3-154">편집 명령을 사용 하면 사용자가 내에서 <xref:System.Windows.Controls.RichTextBox>편집 가능한 콘텐츠의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-154">Editing commands enable users to format editable content inside a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="098a3-155">기본 편집 명령 외에 <xref:System.Windows.Controls.RichTextBox> 도에는 <xref:System.Windows.Controls.TextBox> 를 지원 하지 않는 서식 지정 명령이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-155">Besides basic editing commands, <xref:System.Windows.Controls.RichTextBox> includes formatting commands that <xref:System.Windows.Controls.TextBox> does not support.</span></span> <span data-ttu-id="098a3-156">예를 들어에서 <xref:System.Windows.Controls.RichTextBox>편집할 때 사용자가 Ctr + B를 눌러 굵은 텍스트 서식 지정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-156">For example, when editing in a <xref:System.Windows.Controls.RichTextBox>, a user could press Ctr+B to toggle bold text formatting.</span></span> <span data-ttu-id="098a3-157">사용 <xref:System.Windows.Documents.EditingCommands> 가능한 명령의 전체 목록은를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-157">See <xref:System.Windows.Documents.EditingCommands> for a complete list of commands available.</span></span> <span data-ttu-id="098a3-158">바로 가기 키를 사용하는 방법 외에 단추와 같은 다른 컨트롤에 명령을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-158">In addition to using keyboard shortcuts, you can hook commands up to other controls like buttons.</span></span> <span data-ttu-id="098a3-159">다음 예제에서는 사용자가 텍스트 서식을 변경하는 데 사용할 수 있는 단추가 포함된 간단한 도구 모음을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-159">The following example shows how to create a simple tool bar containing buttons that the user can use to change text formatting.</span></span>

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

<span data-ttu-id="098a3-160">다음 그림은 이 샘플에서 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-160">The following illustration shows how this sample displays.</span></span>

<span data-ttu-id="098a3-161">![가 있는 RichTextBox](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span><span class="sxs-lookup"><span data-stu-id="098a3-161">![RichTextBox with ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span></span>

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a><span data-ttu-id="098a3-162">콘텐츠가 변경되는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="098a3-162">Detect when Content Changes</span></span>

<span data-ttu-id="098a3-163">일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 때마다 검색에 사용할 이벤트의 텍스트를 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox> 대신 변경 <xref:System.Windows.UIElement.KeyDown> 예상할 수 있듯이.</span><span class="sxs-lookup"><span data-stu-id="098a3-163">Usually the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event should be used to detect whenever the text in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox> changes rather then <xref:System.Windows.UIElement.KeyDown> as you might expect.</span></span> <span data-ttu-id="098a3-164">예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="098a3-164">See [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) for an example.</span></span>

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a><span data-ttu-id="098a3-165">RichTextBox 콘텐츠 저장, 로드 및 인쇄</span><span class="sxs-lookup"><span data-stu-id="098a3-165">Save, Load, and Print RichTextBox Content</span></span>

<span data-ttu-id="098a3-166">다음 예제에서는의 <xref:System.Windows.Controls.RichTextBox> 내용을 파일에 저장 하 고, 해당 콘텐츠를 다시 <xref:System.Windows.Controls.RichTextBox>에 로드 하 고, 내용을 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-166">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span> <span data-ttu-id="098a3-167">예제에 대한 태그는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-167">Below is the markup for the example.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

<span data-ttu-id="098a3-168">예제에 대한 코드 숨김은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="098a3-168">Below is the code behind for the example.</span></span>

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="098a3-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="098a3-169">See also</span></span>

- [<span data-ttu-id="098a3-170">방법 항목</span><span class="sxs-lookup"><span data-stu-id="098a3-170">How-to Topics</span></span>](richtextbox-how-to-topics.md)
- [<span data-ttu-id="098a3-171">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="098a3-171">TextBox Overview</span></span>](textbox-overview.md)
