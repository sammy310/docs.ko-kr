---
title: '방법: 텍스트 장식 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: d586eef8d1308070da38a0a54c63c3ba64d30c8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133837"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="fecd6-102">방법: 텍스트 장식 만들기</span><span class="sxs-lookup"><span data-stu-id="fecd6-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="fecd6-103"><xref:System.Windows.TextDecoration> 개체가 시각적 장식 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="fecd6-104">텍스트 장식의 네 가지가: 밑줄, 기준, 취소선 및 윗줄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="fecd6-105">다음 예제에서는 텍스트를 기준으로 텍스트 장식의 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![텍스트 장식 종류의 다이어그램](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="fecd6-107">텍스트 장식에 텍스트를 추가 하려면 만들기를 <xref:System.Windows.TextDecoration> 개체 및 해당 속성을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="fecd6-108">사용 된 <xref:System.Windows.TextDecoration.Location%2A> 밑줄 등 텍스트 장식 나타나는 위치를 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="fecd6-109">사용 된 <xref:System.Windows.TextDecoration.Pen%2A> 텍스트 장식 단색 또는 그라데이션 색 등의 모양을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="fecd6-110">에 대 한 값을 지정 하지 않으면 경우는 <xref:System.Windows.TextDecoration.Pen%2A> 속성에 장식 텍스트와 동일한 색의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="fecd6-111">정의한 후는 <xref:System.Windows.TextDecoration> 개체에 추가 하는 <xref:System.Windows.TextDecorations> 원하는 텍스트 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="fecd6-112">다음 예제에서는 파선된 펜 선형 그라데이션 브러시와 스타일이 지정 된 텍스트 장식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![선형 그라데이션 밑줄로 텍스트 장식](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="fecd6-114"><xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에서 하이퍼링크를 호스트할 수 있는 인라인 수준의 유동 콘텐츠 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="fecd6-115">기본적으로 <xref:System.Windows.Documents.Hyperlink> 사용을 <xref:System.Windows.TextDecoration> 밑줄을 표시 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="fecd6-116"><xref:System.Windows.TextDecoration> 많을 경우에 특히 개체를 인스턴스화할 때 성능이 저하 될 수 있습니다 <xref:System.Windows.Documents.Hyperlink> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="fecd6-117">광범위 하 게 사용 한다면 <xref:System.Windows.Documents.Hyperlink> 와 같은 경우 트리거될 때만 밑줄이 표시 하려는 요소를 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="fecd6-118">다음 예제에서는 "My MSN" 링크 밑줄은 동적-만 표시 될 때를 <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![TextDecoration을 표시하는 하이퍼링크](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  
   
 <span data-ttu-id="fecd6-120">자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fecd6-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fecd6-121">예제</span><span class="sxs-lookup"><span data-stu-id="fecd6-121">Example</span></span>  
 <span data-ttu-id="fecd6-122">다음 코드 예제에서 밑줄 텍스트 장식의 기본 글꼴 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="fecd6-123">다음 코드 예제에서 밑줄 텍스트 장식은 펜에 대 한 단색 브러시를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="fecd6-124">다음 코드 예제에서 밑줄 텍스트 장식은 파선된 펜에 대 한 선형 그라데이션 브러시를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fecd6-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="fecd6-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="fecd6-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="fecd6-126">하이퍼링크에 밑줄이 그어지는지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="fecd6-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
