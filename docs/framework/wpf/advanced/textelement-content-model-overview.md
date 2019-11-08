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
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740763"
---
# <a name="textelement-content-model-overview"></a>TextElement 콘텐츠 모델 개요
이 콘텐츠 모델 개요에서는 <xref:System.Windows.Documents.TextElement>에 대해 지원 되는 콘텐츠를 설명 합니다. <xref:System.Windows.Documents.Paragraph> 클래스는 <xref:System.Windows.Documents.TextElement>형식입니다. 콘텐츠 모델은 어떤 개체/요소가 다른 개체/요소에 포함될 수 있는지를 설명합니다. 이 개요에서는 <xref:System.Windows.Documents.TextElement>에서 파생 된 개체에 사용 되는 콘텐츠 모델을 요약 합니다. 자세한 내용은 [유동 문서 개요](flow-document-overview.md)를 참조 하세요.  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>콘텐츠 모델 다이어그램  
 다음 다이어그램에서는 <xref:System.Windows.Documents.TextElement>에서 파생 된 클래스에 대 한 콘텐츠 모델과 다른 비 `TextElement` 클래스를이 모델에 맞추는 방법에 대해 간략하게 설명 합니다.  
  
 ![다이어그램: 유동 콘텐츠 포함 스키마](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 위의 다이어그램에서 볼 수 있듯이 요소에 허용 되는 자식은 클래스가 <xref:System.Windows.Documents.Block> 클래스에서 파생 되었는지 아니면 <xref:System.Windows.Documents.Inline> 클래스에서 파생 되는지에 따라 결정 되지 않을 수도 있습니다. 예를 들어 <xref:System.Windows.Documents.Span> (<xref:System.Windows.Documents.Inline>파생 클래스)에는 <xref:System.Windows.Documents.Inline> 자식 요소만 포함 될 수 있지만 <xref:System.Windows.Documents.Figure> (<xref:System.Windows.Documents.Inline>파생 클래스)에는 <xref:System.Windows.Documents.Block> 자식 요소만 포함 될 수 있습니다. 그러므로 이 다이어그램은 다른 요소에 포함될 수 있는 요소를 신속하게 판별하는 데 유용합니다. 예를 들어 다이어그램을 사용 하 여 <xref:System.Windows.Controls.RichTextBox>의 유동 콘텐츠를 생성 하는 방법을 결정 하겠습니다.  
  
1. <xref:System.Windows.Controls.RichTextBox>에는 <xref:System.Windows.Documents.Block>파생 개체가 포함 된 <xref:System.Windows.Documents.FlowDocument> 포함 되어야 합니다. 이전 다이어그램에 해당하는 세그먼트는 다음과 같습니다.  
  
     ![다이어그램: RichTextBox 포함 규칙](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     따라서 지금까지 태그는 다음과 같을 수 있습니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. 다이어그램에는 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>및 <xref:System.Windows.Documents.BlockUIContainer>를 포함 하 여 선택할 수 있는 몇 가지 <xref:System.Windows.Documents.Block> 요소가 있습니다 (위 다이어그램의 블록 파생 클래스 참조). <xref:System.Windows.Documents.Table>하려는 경우를 가정해 보겠습니다. 위의 다이어그램에 따라 <xref:System.Windows.Documents.Table>에는 <xref:System.Windows.Documents.Block>파생 개체가 포함 된 <xref:System.Windows.Documents.TableCell> 요소를 포함 하는 <xref:System.Windows.Documents.TableRow> 요소를 포함 하는 <xref:System.Windows.Documents.TableRowGroup> 포함 되어 있습니다. 다음은 앞의 다이어그램에서 가져온 <xref:System.Windows.Documents.Table>의 해당 세그먼트입니다.  
  
     ![다이어그램: 테이블&#47;의 부모 자식 스키마](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     다음은 해당 태그입니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. <xref:System.Windows.Documents.TableCell>아래에는 하나 이상의 <xref:System.Windows.Documents.Block> 요소가 필요 합니다. 간단하게 셀 안에 텍스트를 배치해 보겠습니다. <xref:System.Windows.Documents.Run> 요소가 있는 <xref:System.Windows.Documents.Paragraph>를 사용 하 여이 작업을 수행할 수 있습니다. 다음은 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Inline> 요소를 사용 하 고 <xref:System.Windows.Documents.Run> (<xref:System.Windows.Documents.Inline> 요소)에서 일반 텍스트만 사용할 수 있음을 보여 주는 다이어그램의 해당 세그먼트입니다.  
  
     ![다이어그램: 단락의&#47;부모 자식 스키마](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![다이어그램: 실행&#47;을 위한 부모 자식 스키마](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 다음은 태그의 전체 예제입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>프로그래밍 방식으로 TextElement 콘텐츠 작업  
 <xref:System.Windows.Documents.TextElement> 내용은 컬렉션에 의해 구성 되므로 이러한 컬렉션을 사용 하 여 프로그래밍 방식으로 <xref:System.Windows.Documents.TextElement> 개체의 콘텐츠를 조작 합니다. <xref:System.Windows.Documents.TextElement> 파생 클래스에서 사용 되는 세 가지 컬렉션이 있습니다.  
  
- <xref:System.Windows.Documents.InlineCollection>: <xref:System.Windows.Documents.Inline> 요소의 컬렉션을 나타냅니다. <xref:System.Windows.Documents.InlineCollection> <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>및 <xref:System.Windows.Controls.TextBlock> 요소의 허용 되는 자식 콘텐츠를 정의 합니다.  
  
- <xref:System.Windows.Documents.BlockCollection>: <xref:System.Windows.Documents.Block> 요소의 컬렉션을 나타냅니다. <xref:System.Windows.Documents.BlockCollection>은 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> 및 <xref:System.Windows.Documents.Figure> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
- <xref:System.Windows.Documents.ListItemCollection>: 순서가 지정 되거나 순서가 지정 되지 않은 <xref:System.Windows.Documents.List>의 특정 콘텐츠 항목을 나타내는 유동 콘텐츠 요소입니다.  
  
 **Inlines**, **Blocks**및 **ListItems**의 각 속성을 사용 하 여 이러한 컬렉션에서 항목을 조작 (추가 또는 제거) 할 수 있습니다. 다음 예제에서는 **Inlines** 속성을 사용 하 여 범위의 콘텐츠를 조작 하는 방법을 보여 줍니다.  
  
> [!NOTE]
> 테이블에서는 콘텐츠를 조작하는 데 여러 컬렉션을 사용하지만 이러한 컬렉션은 여기에서 다루지 않습니다. 자세한 내용은 [테이블 개요](table-overview.md)를 참조 하세요.  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체를 만든 다음 `Add` 메서드를 사용 하 여 두 개의 텍스트 실행을 <xref:System.Windows.Documents.Span>의 콘텐츠 자식으로 추가 합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 만들어 <xref:System.Windows.Documents.Span>의 시작 부분에 삽입 합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 다음 예에서는 <xref:System.Windows.Documents.Span>에서 마지막 <xref:System.Windows.Documents.Inline> 요소를 삭제 합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에서 모든 콘텐츠 (<xref:System.Windows.Documents.Inline> 요소)를 지웁니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>이 콘텐츠 모델을 공유하는 형식  
 다음 형식은 <xref:System.Windows.Documents.TextElement> 클래스에서 상속 되며이 개요에 설명 된 콘텐츠를 표시 하는 데 사용할 수 있습니다.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 이 목록에는 Windows SDK를 사용 하 여 배포 된 비추상 형식만 포함 됩니다. <xref:System.Windows.Documents.TextElement>에서 상속 되는 다른 형식을 사용할 수 있습니다.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>TextElement 개체를 포함할 수 있는 형식  
 [WPF 콘텐츠 모델](../controls/wpf-content-model.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Blocks 속성을 통한 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Blocks 속성을 통한 유동 콘텐츠 요소 조작](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Blocks 속성을 통한 FlowDocument 조작](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Columns 속성을 통해 테이블의 열 조작](how-to-manipulate-table-columns-through-the-columns-property.md)
- [RowGroups 속성을 통한 테이블의 행 그룹 조작](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
