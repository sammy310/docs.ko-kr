---
title: 주석 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 433fee08d44720640d3f9d1bf2511a6a267eb58e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145464"
---
# <a name="annotations-overview"></a><span data-ttu-id="bac9a-102">주석 개요</span><span class="sxs-lookup"><span data-stu-id="bac9a-102">Annotations Overview</span></span>
<span data-ttu-id="bac9a-103">종이 문서에 메모나 설명을 적는 것은 당연하게 받아들이는 매우 일반적인 행동입니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="bac9a-104">이러한 메모나 설명은 나중에 참조하기 위해 관심 있는 항목을 강조 표시하거나 정보를 첨부하기 위해 문서에 추가하는 "주석"입니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="bac9a-105">인쇄된 문서에 메모를 적는 것은 간단하고 일반적이지만 전자 문서에 개인적인 주석을 추가하는 기능은 대개 가능하더라도 매우 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="bac9a-106">이 항목에서는 몇 가지 일반적인 주석 유형, 특히 스티커 메모 및 강조 표시를 검토하고 Microsoft 주석 프레임워크가 Windows 프레젠테이션 재단(WPF)을 통해 응용 프로그램에서 이러한 유형의 주석을 용이하게 하는 방법을 보여 줍니다. )을 문서 보기 컨트롤로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the Microsoft Annotations Framework facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  <span data-ttu-id="bac9a-107">주석을 지원하는 WPF 문서 보기 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentScrollViewer>컨트롤에는 및 <xref:System.Windows.Controls.Primitives.DocumentViewerBase> <xref:System.Windows.Controls.FlowDocumentPageViewer>에서 파생된 <xref:System.Windows.Controls.DocumentViewer> 컨트롤이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-107">WPF document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  

<a name="caf1_type_stickynotes"></a>
## <a name="sticky-notes"></a><span data-ttu-id="bac9a-108">스티커 메모</span><span class="sxs-lookup"><span data-stu-id="bac9a-108">Sticky Notes</span></span>  
 <span data-ttu-id="bac9a-109">일반적인 스티커 메모는 작은 색지에 정보를 작성하여 문서에 "붙입니다".</span><span class="sxs-lookup"><span data-stu-id="bac9a-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="bac9a-110">디지털 스티커 메모는 전자 문서에 대해 유사한 기능을 제공하지만 입력된 텍스트, 필기 노트(예: Tablet PC "잉크" 스트로크) 또는 웹 링크와 같은 다른 많은 유형의 콘텐츠를 포함할 수 있는 유연성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, Tablet PC "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="bac9a-111">다음 그림에서는 강조 표시, 텍스트 스티커 메모 및 잉크 스티커 메모 주석의 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="bac9a-112">![강조 표시, 텍스트 및 잉크 스티커 메모 주석](./media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="bac9a-112">![Highlight, text and ink sticky note annotations.](./media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="bac9a-113">다음 예제에서는 애플리케이션에서 주석 지원을 설정하는 데 사용할 수 있는 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>
## <a name="highlights"></a><span data-ttu-id="bac9a-114">주요 사항</span><span class="sxs-lookup"><span data-stu-id="bac9a-114">Highlights</span></span>  
 <span data-ttu-id="bac9a-115">사람들은 종이 문서에 표시할 때 밑줄 긋기, 강조 표시, 문장에 포함된 단어에 동그라미 표시, 여백에 표식이나 주석 그리기 등의 창조적인 방법으로 관심 있는 항목에 주의를 끌도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="bac9a-116">Microsoft 주석 프레임워크의 강조 표시 주석은 WPF 문서 보기 컨트롤에 표시되는 정보를 표시하는 것과 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-116">Highlight annotations in Microsoft Annotations Framework provide a similar feature for marking up information displayed in WPF document viewing controls.</span></span>  
  
 <span data-ttu-id="bac9a-117">다음 그림에서는 강조 표시 주석의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="bac9a-118">![강조 표시 주석](./media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="bac9a-118">![Highlight Annotation](./media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="bac9a-119">사용자는 일반적으로 먼저 일부 텍스트 또는 관심 항목을 선택한 다음 마우스 오른쪽 단추로 클릭하여 주석 옵션을 표시하여 주석을 <xref:System.Windows.Controls.ContextMenu> 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="bac9a-120">다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용자가 주석을 만들고 <xref:System.Windows.Controls.ContextMenu> 관리하기 위해 액세스할 수 있는 라우팅된 명령을 사용하여 a를 선언하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>
## <a name="data-anchoring"></a><span data-ttu-id="bac9a-121">데이터 고정</span><span class="sxs-lookup"><span data-stu-id="bac9a-121">Data Anchoring</span></span>  
 <span data-ttu-id="bac9a-122">주석 프레임워크는 표시 뷰의 위치뿐만 아니라 사용자가 선택한 데이터에 주석을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-122">The Annotations Framework binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="bac9a-123">따라서 사용자가 표시 창을 스크롤하거나 크기를 조정할 때와 같이 문서 보기가 변경되면 주석은 바인딩된 데이터 선택 항목과 함께 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="bac9a-124">예를 들어 다음 그래픽에서는 사용자가 텍스트를 선택하여 만든 주석을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="bac9a-125">문서 보기가 변경되면(스크롤, 크기 조정, 배율 또는 이동 등) 강조 표시 주석은 원래의 데이터 선택 항목과 함께 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="bac9a-126">![주석 데이터 고정](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="bac9a-126">![Annotation Data Anchoring](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="bac9a-127">주석이 지정된 개체에 주석 연결</span><span class="sxs-lookup"><span data-stu-id="bac9a-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="bac9a-128">주석을 해당 주석이 지정된 개체와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="bac9a-129">예를 들어 주석 창이 있는 간단한 문서 판독기 애플리케이션을 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="bac9a-130">주석 창은 문서에 고정된 주석 목록의 텍스트를 표시하는 목록 상자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="bac9a-131">사용자가 목록 상자에서 항목을 선택하면 애플리케이션에서 해당 주석 개체에 고정된 문서의 단락을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="bac9a-132">다음 예제에서는 주석 창으로 사용되는 목록 상자의 이벤트 처리기를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="bac9a-133">또 다른 예제 시나리오에는 전자 메일을 통해 문서 판독기 간에 주석과 스티커 메모를 교환할 수 있는 응용 프로그램이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="bac9a-134">이러한 애플리케이션은 이 기능을 통해 판독기에서 교환하는 주석이 포함된 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac9a-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac9a-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bac9a-135">See also</span></span>

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [<span data-ttu-id="bac9a-136">주석 스키마</span><span class="sxs-lookup"><span data-stu-id="bac9a-136">Annotations Schema</span></span>](annotations-schema.md)
- [<span data-ttu-id="bac9a-137">ContextMenu 개요</span><span class="sxs-lookup"><span data-stu-id="bac9a-137">ContextMenu Overview</span></span>](../controls/contextmenu-overview.md)
- [<span data-ttu-id="bac9a-138">명령 개요</span><span class="sxs-lookup"><span data-stu-id="bac9a-138">Commanding Overview</span></span>](commanding-overview.md)
- [<span data-ttu-id="bac9a-139">유동 문서 개요</span><span class="sxs-lookup"><span data-stu-id="bac9a-139">Flow Document Overview</span></span>](flow-document-overview.md)
- <span data-ttu-id="bac9a-140">[How to: Add a Command to a MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))(방법: MenuItem에 명령 추가)</span><span class="sxs-lookup"><span data-stu-id="bac9a-140">[How to: Add a Command to a MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span></span>
