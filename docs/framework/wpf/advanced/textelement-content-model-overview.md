---
title: TextElement 콘텐츠 모델 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: ddb2613dc924424b5f4b9d90f06d44b45b7b5e77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186899"
---
# <a name="textelement-content-model-overview"></a>TextElement 콘텐츠 모델 개요
이 콘텐츠 모델 개요는 <xref:System.Windows.Documents.TextElement>에 대해 지원되는 콘텐츠에 대해 설명합니다. 클래스는 <xref:System.Windows.Documents.Paragraph> 의 <xref:System.Windows.Documents.TextElement>유형입니다. 콘텐츠 모델은 어떤 개체/요소가 다른 개체/요소에 포함될 수 있는지를 설명합니다. 이 개요는 에서 <xref:System.Windows.Documents.TextElement>파생된 개체에 사용되는 콘텐츠 모델을 요약합니다. 자세한 내용은 [흐름 문서 개요를](flow-document-overview.md)참조하십시오.  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>콘텐츠 모델 다이어그램  
 다음 다이어그램은 파생된 <xref:System.Windows.Documents.TextElement> 클래스의 콘텐츠 모델과 다른 비클래스가 `TextElement` 이 모델에 어떻게 적합한지 요약합니다.  
  
 ![다이어그램: 유동 콘텐츠 포함 스키마](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 앞의 다이어그램에서 볼 수 있듯이 요소에 허용되는 자식은 클래스가 <xref:System.Windows.Documents.Block> 클래스또는 <xref:System.Windows.Documents.Inline> 클래스에서 파생되는지 여부에 의해 반드시 결정되지는 않습니다. 예를 들어 <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Inline>a(-derived 클래스)에는 <xref:System.Windows.Documents.Inline> 자식 요소만 <xref:System.Windows.Documents.Figure> 있을 <xref:System.Windows.Documents.Inline>수 있지만 a(파생 <xref:System.Windows.Documents.Block> 클래스도)에는 자식 요소만 있을 수 있습니다. 그러므로 이 다이어그램은 다른 요소에 포함될 수 있는 요소를 신속하게 판별하는 데 유용합니다. 예를 들어 다이어그램을 사용하여 <xref:System.Windows.Controls.RichTextBox>의 흐름 컨텐트를 구성하는 방법을 결정해 보겠습니다.  
  
1. A에는 <xref:System.Windows.Controls.RichTextBox> -derived 개체를 <xref:System.Windows.Documents.Block>포함해야 하는 a가 <xref:System.Windows.Documents.FlowDocument> 포함되어야 합니다. 이전 다이어그램에 해당하는 세그먼트는 다음과 같습니다.  
  
     ![다이어그램: RichTextBox 포함 규칙](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     따라서 지금까지 태그는 다음과 같을 수 있습니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. 다이어그램에 따르면 , <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.List>을 포함하여 선택할 수 있는 <xref:System.Windows.Documents.BlockUIContainer> 몇 가지 요소가 있습니다(이전 다이어그램의 블록 파생 클래스 참조). 을 원한다고 가정해 <xref:System.Windows.Documents.Table>보겠습니다. 앞의 다이어그램에 <xref:System.Windows.Documents.Table> 따르면 <xref:System.Windows.Documents.TableRowGroup> a에는 <xref:System.Windows.Documents.TableRow> <xref:System.Windows.Documents.Block>-derived <xref:System.Windows.Documents.TableCell> 개체를 포함하는 요소가 포함된 포함 요소가 포함됩니다. 다음은 이전 다이어그램에서 <xref:System.Windows.Documents.Table> 가져온 해당 세그먼트입니다.  
  
     ![다이어그램: 테이블에 대한 상위&#47;자식 스키마](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     다음은 해당 태그입니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. 다시 <xref:System.Windows.Documents.TableCell>말하지만, <xref:System.Windows.Documents.Block> 아래에 하나 이상의 요소가 필요합니다. 간단하게 셀 안에 텍스트를 배치해 보겠습니다. <xref:System.Windows.Documents.Paragraph> 요소와 함께 이 작업을 수행할 수 <xref:System.Windows.Documents.Run> 있습니다. <xref:System.Windows.Documents.Paragraph> 다음은 <xref:System.Windows.Documents.Inline> a가 요소를 취할 수 있고 <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.Inline> (요소)가 일반 텍스트만 가져갈 수 있음을 보여주는 다이어그램의 해당 세그먼트입니다.  
  
     ![다이어그램: 단락에 대한 부모&#47;자식 스키마](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![다이어그램: 실행을 위한 부모&#47;자식 스키마](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 다음은 태그의 전체 예제입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>프로그래밍 방식으로 TextElement 콘텐츠 작업  
 a의 <xref:System.Windows.Documents.TextElement> 내용은 컬렉션으로 구성되므로 이러한 컬렉션을 작업하여 개체의 <xref:System.Windows.Documents.TextElement> 내용을 프로그래밍 방식으로 조작합니다. <xref:System.Windows.Documents.TextElement> -derived 클래스에서 사용하는 세 가지 컬렉션이 있습니다.  
  
- <xref:System.Windows.Documents.InlineCollection>: 요소의 <xref:System.Windows.Documents.Inline> 컬렉션을 나타냅니다. <xref:System.Windows.Documents.InlineCollection> 는 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>및 <xref:System.Windows.Controls.TextBlock> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
- <xref:System.Windows.Documents.BlockCollection>: 요소의 <xref:System.Windows.Documents.Block> 컬렉션을 나타냅니다. <xref:System.Windows.Documents.BlockCollection>은 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> 및 <xref:System.Windows.Documents.Figure> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
- <xref:System.Windows.Documents.ListItemCollection>: 정렬되거나 정렬되지 <xref:System.Windows.Documents.List>않은 특정 콘텐츠 항목을 나타내는 흐름 콘텐츠 요소입니다.  
  
 **인라인,** **블록**및 ListItems 의 각 속성을 사용하여 이러한 컬렉션에서 항목을 조작(추가 또는 제거)할 수 **있습니다.** 다음 예제에서는 **Inlines** 속성을 사용하여 범위의 내용을 조작하는 방법을 보여 주습니다.  
  
> [!NOTE]
> 테이블에서는 콘텐츠를 조작하는 데 여러 컬렉션을 사용하지만 이러한 컬렉션은 여기에서 다루지 않습니다. 자세한 내용은 [테이블 개요](table-overview.md)를 참조하십시오.  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체를 만들고 `Add` 메서드를 사용 하 여 두 <xref:System.Windows.Documents.Span>개의 텍스트 실행을 의 콘텐츠 자식으로 추가 합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 만들고 <xref:System.Windows.Documents.Span>의 시작 부분에 삽입합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 다음 예제에서는 의 <xref:System.Windows.Documents.Inline> 마지막 요소를 <xref:System.Windows.Documents.Span>삭제합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 다음 예제에서는<xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span>에서 모든 내용(요소)을 지웁니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>이 콘텐츠 모델을 공유하는 형식  
 다음 형식은 <xref:System.Windows.Documents.TextElement> 클래스에서 상속되며 이 개요에 설명된 내용을 표시하는 데 사용할 수 있습니다.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 이 목록에는 Windows SDK와 함께 배포된 비추상형식만 포함됩니다. <xref:System.Windows.Documents.TextElement>에서 상속하는 다른 형식을 사용할 수 있습니다.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>TextElement 개체를 포함할 수 있는 형식  
 [WPF 콘텐츠 모델을](../controls/wpf-content-model.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [Blocks 속성을 통해 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Blocks 속성을 통해 유동 콘텐츠 요소 조작](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Blocks 속성을 통해 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Columns 속성을 통해 테이블의 열 조작](how-to-manipulate-table-columns-through-the-columns-property.md)
- [RowGroups 속성을 통해 테이블의 행 그룹 조작](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
