---
title: '방법: Blocks 속성을 통해 FlowDocument 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: c307d85bf24e2d8a20226856181e0758758d40c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130886"
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a><span data-ttu-id="d1fcb-102">방법: Blocks 속성을 통해 FlowDocument 조작</span><span class="sxs-lookup"><span data-stu-id="d1fcb-102">How to: Manipulate a FlowDocument through the Blocks Property</span></span>
<span data-ttu-id="d1fcb-103">이 예제에서 수행할 수 있는 보다 일반적인 작업 중 일부를 보여를 <xref:System.Windows.Documents.FlowDocument> 를 통해를 <xref:System.Windows.Documents.FlowDocument.Blocks%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-103">These examples demonstrate some of the more common operations that can be performed on a <xref:System.Windows.Documents.FlowDocument> through the <xref:System.Windows.Documents.FlowDocument.Blocks%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1fcb-104">예제</span><span class="sxs-lookup"><span data-stu-id="d1fcb-104">Example</span></span>  
 <span data-ttu-id="d1fcb-105">다음 예제에서는 새 <xref:System.Windows.Documents.FlowDocument> 한 다음 새를 추가 <xref:System.Windows.Documents.Paragraph> 요소는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-105">The following example creates a new <xref:System.Windows.Documents.FlowDocument> and then appends a new <xref:System.Windows.Documents.Paragraph> element to the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="d1fcb-106">예제</span><span class="sxs-lookup"><span data-stu-id="d1fcb-106">Example</span></span>  
 <span data-ttu-id="d1fcb-107">다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소 부분에 삽입 하는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-107">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="d1fcb-108">예제</span><span class="sxs-lookup"><span data-stu-id="d1fcb-108">Example</span></span>  
 <span data-ttu-id="d1fcb-109">다음 예제에서는 최상위 개수를 가져옵니다 <xref:System.Windows.Documents.Block> 에 포함 된 요소는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-109">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a><span data-ttu-id="d1fcb-110">예제</span><span class="sxs-lookup"><span data-stu-id="d1fcb-110">Example</span></span>  
 <span data-ttu-id="d1fcb-111">다음 예제에서는 마지막 삭제 <xref:System.Windows.Documents.Block> 요소에는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-111">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="d1fcb-112">예제</span><span class="sxs-lookup"><span data-stu-id="d1fcb-112">Example</span></span>  
 <span data-ttu-id="d1fcb-113">다음 예제에서는 모든 콘텐츠를 지웁니다 (<xref:System.Windows.Documents.Block> 요소)에서 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1fcb-113">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="d1fcb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1fcb-114">See also</span></span>

- [<span data-ttu-id="d1fcb-115">RowGroups 속성을 통해 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="d1fcb-115">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="d1fcb-116">Columns 속성을 통해 테이블의 열 조작</span><span class="sxs-lookup"><span data-stu-id="d1fcb-116">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="d1fcb-117">RowGroups 속성을 통해 테이블의 행 그룹 조작</span><span class="sxs-lookup"><span data-stu-id="d1fcb-117">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
