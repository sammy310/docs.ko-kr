---
title: RichTextBox 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 9d26ec7bfc4d75b304bbc9dc98dbbeaed64effe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743127"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="d5814-102">RichTextBox 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d5814-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="d5814-103">Windows Forms `RichTextBox` 컨트롤은 서식을 사용 하 여 텍스트를 표시, 입력 및 조작 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="d5814-104">`RichTextBox` 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤에서 수행 하는 모든 작업을 수행 하지만 글꼴, 색 및 링크를 표시할 수도 있습니다. 파일에서 텍스트 및 포함 된 이미지 로드 편집 작업을 실행 취소 하 고 다시 실행 합니다. 지정 된 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="d5814-105">`RichTextBox` 컨트롤은 일반적으로 텍스트 조작을 제공 하 고 Microsoft Word와 같은 워드 프로세싱 응용 프로그램과 비슷한 기능을 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="d5814-106"><xref:System.Windows.Forms.TextBox> 컨트롤과 마찬가지로 `RichTextBox` 컨트롤은 스크롤 막대를 표시할 수 있습니다. 그러나 <xref:System.Windows.Forms.TextBox> 컨트롤과 달리 가로 및 세로 스크롤 막대를 기본적으로 표시 하 고 추가 스크롤 막대 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5814-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d5814-107">In This Section</span></span>  
 [<span data-ttu-id="d5814-108">RichTextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d5814-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="d5814-109">사용자가 서식 옵션을 사용 하 여 텍스트를 입력, 표시 및 조작할 수 있도록 하는 `RichTextBox` 컨트롤의 일반적인 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="d5814-110">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="d5814-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="d5814-111">`RichTextBox` 컨트롤에서 글꼴 및 단락 서식의 변경 내용을 추적 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-112">방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시</span><span class="sxs-lookup"><span data-stu-id="d5814-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d5814-113">`RichTextBox` 컨트롤에서 스크롤 막대에 사용할 수 있는 다양 한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-114">방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시</span><span class="sxs-lookup"><span data-stu-id="d5814-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d5814-115">`RichTextBox` 컨트롤에서 웹 사이트에 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-116">방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용</span><span class="sxs-lookup"><span data-stu-id="d5814-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="d5814-117">`RichTextBox` 컨트롤로 데이터를 끌어서 놓는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-118">방법: Windows Forms RichTextBox 컨트롤에 파일 로드</span><span class="sxs-lookup"><span data-stu-id="d5814-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d5814-119">`RichTextBox` 컨트롤에 기존 파일을 로드 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-120">방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="d5814-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d5814-121">`RichTextBox` 컨트롤의 내용을 파일에 저장 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="d5814-122">방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정</span><span class="sxs-lookup"><span data-stu-id="d5814-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d5814-123">`RichTextBox` 컨트롤에서 텍스트의 글꼴 패밀리, 크기, 스타일 및 색을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d5814-124">방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정</span><span class="sxs-lookup"><span data-stu-id="d5814-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="d5814-125">`RichTextBox` 컨트롤에서 단락의 서식을 지정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5814-126">참조</span><span class="sxs-lookup"><span data-stu-id="d5814-126">Reference</span></span>  
 <span data-ttu-id="d5814-127"><xref:System.Windows.Forms.RichTextBox> 클래스</span><span class="sxs-lookup"><span data-stu-id="d5814-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="d5814-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5814-129">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="d5814-129">Related Sections</span></span>  
 [<span data-ttu-id="d5814-130">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d5814-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="d5814-131">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="d5814-132">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d5814-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="d5814-133">사용자가 편집할 수 있는 여러 줄 입력을 허용 하는 <xref:System.Windows.Forms.TextBox> 컨트롤의 일반적인 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5814-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
