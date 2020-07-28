---
title: 유동 문서 개요
description: 창 크기, 장치 해상도 및 사용자 기본 설정에 따라 콘텐츠를 동적으로 조정 하는 Windows Presentation Foundation의 유동 문서에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: dac0cb91175a1398a0124020c048e14d7bcd1f76
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165232"
---
# <a name="flow-document-overview"></a>유동 문서 개요

유동 문서는 보기와 가독성을 최적화하도록 설계되었습니다. 유동 문서는 미리 정의된 하나의 레이아웃으로 설정되는 것이 아니라, 창 크기, 디바이스 해상도 및 선택적 사용자 기본 설정 등의 런타임 변수에 따라 동적으로 콘텐츠를 조정하고 리플로우합니다. 유동 문서에서는 페이지 매김 및 열과 같은 고급 문서 기능을 제공합니다. 이 항목에서는 유동 문서의 개요와 해당 문서를 작성하는 방법을 제공합니다.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>유동 문서의 정의

유동 문서는 창 크기, 디바이스 해상도 및 기타 환경 변수에 따라 “콘텐츠의 흐름을 변경”하도록 설계되었습니다. 또한 유동 문서에는 검색, 가독성을 최적화하는 보기 모드 및 글꼴의 모양과 크기를 변경하는 기능 등의 여러 기본 제공 기능이 포함되어 있습니다. 유동 문서는 문서 이용 시 용이한 가독성이 주된 요인인 시나리오에서 최적으로 활용할 수 있습니다. 반대로 고정 문서는 정적 프레젠테이션을 사용하도록 설계되어 있습니다. 소스 콘텐츠의 정확도가 중요한 경우 고정 문서를 사용해야 합니다. 여러 문서 형식에 대 한 자세한 내용은 [WPF의 문서](documents-in-wpf.md) 를 참조 하세요.

다음 그림에서는 여러 다른 크기의 창에 표시되는 샘플 유동 문서를 보여줍니다. 표시 영역이 변경됨에 따라 사용 가능한 공간을 최적으로 활용하기 위해 콘텐츠의 흐름을 변경합니다.

![유동 문서 콘텐츠 흐름 변경](./media/edocs-flowdocument.png "eDocs_FlowDocument")

위의 이미지에서와 같이 유동 콘텐츠에는 단락, 목록, 이미지 등의 많은 구성 요소가 포함될 수 있습니다. 이러한 구성 요소는 태그의 요소 및 프로시저 코드의 개체에 해당합니다. 이러한 클래스는 나중에이 개요의 [Flow 관련 클래스](#flow_related_classes) 단원에서 자세히 설명 합니다. 지금은 굵은 텍스트 및 목록이 있는 단락으로 구성 된 유동 문서를 만드는 간단한 코드 예제는 다음과 같습니다.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

아래 그림에서는 이 코드 조각을 보여줍니다.

![스크린 샷: 렌더링된 FlowDocument 예제](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

이 예제에서 컨트롤은 <xref:System.Windows.Controls.FlowDocumentReader> 유동 콘텐츠를 호스트 하는 데 사용 됩니다. 유동 콘텐츠 호스팅 컨트롤에 대 한 자세한 내용은 [유동 문서 형식](#flow_document_types) 을 참조 하세요. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List> , <xref:System.Windows.Documents.ListItem> 및 <xref:System.Windows.Documents.Bold> 요소는 태그의 순서에 따라 콘텐츠 형식을 제어 하는 데 사용 됩니다. 예를 들어 <xref:System.Windows.Documents.Bold> 요소는 단락에 있는 텍스트의 일부에만 걸쳐 있으므로 텍스트의 해당 부분만 굵게 표시 됩니다. HTML을 사용해 본 적이 있으면 익숙할 것입니다.

위의 그림에 강조 표시 된 것 처럼 유동 문서에는 몇 가지 기능이 기본적으로 제공 됩니다.

- 검색: 전체 문서에서 전체 텍스트 검색을 수행할 수 있습니다.

- 보기 모드: 단일 페이지(한 번에 한 페이지) 보기 모드, 한 번에 두 페이지(책 읽기 형식) 보기 모드 및 연속 스크롤링(바닥이 없음) 보기 모드 중에서 선호하는 보기 모드를 선택할 수 있습니다.  이러한 표시 모드에 대 한 자세한 내용은을 참조 하십시오 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> .

- 페이지 탐색 컨트롤: 문서의 보기 모드에서 페이지를 사용하면 페이지 탐색 컨트롤에 다음 페이지(아래쪽 화살표) 또는 이전 페이지(위쪽 화살표)로 이동하는 단추 외에도 현재 페이지 번호와 총 페이지 수 표시기도 포함되어 있습니다. 키보드 화살표 키를 사용하여 페이지 넘기기도 수행할 수 있습니다.

- 확대/축소: 확대/축소 컨트롤을 사용하면 더하기 또는 빼기 단추를 클릭하여 각각 확대/축소 수준을 늘리거나 줄일 수 있습니다. 확대/축소 컨트롤에는 확대/축소 수준을 조정하는 슬라이더도 포함되어 있습니다. 자세한 내용은 <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>을 참조하세요.

이러한 기능은 유동 콘텐츠를 호스트하는 데 사용되는 컨트롤을 통해 수정할 수 있습니다. 다음 섹션에서는 여러 다른 컨트롤에 대해 설명합니다.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>유동 문서 형식

유동 문서 콘텐츠 표시 및 표시 방법은 유동 콘텐츠를 호스트하는 데 사용되는 개체에 따라 달라집니다. 유동 콘텐츠 보기를 지 원하는 네 가지 컨트롤은 <xref:System.Windows.Controls.FlowDocumentReader> ,, <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 입니다. 이러한 컨트롤은 아래에서 간략하게 설명합니다.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>는 유동 콘텐츠를 직접 호스트 하는 데 필요 하므로 이러한 모든 보기 컨트롤은를 사용 <xref:System.Windows.Documents.FlowDocument> 하 여 유동 콘텐츠 호스팅을 사용 하도록 설정 합니다.

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>에는 사용자가 단일 페이지 (일회성) 보기 모드, 2 페이지 시간 (책 읽기 형식) 보기 모드 및 연속 스크롤 (무제한) 보기 모드를 포함 하 여 다양 한 보기 모드를 동적으로 선택할 수 있도록 하는 기능이 포함 되어 있습니다. 이러한 표시 모드에 대 한 자세한 내용은을 참조 하십시오 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> . 여러 보기 모드를 동적으로 전환 하는 기능이 필요 하지 않은 경우에 <xref:System.Windows.Controls.FlowDocumentPageViewer> 는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 특정 보기 모드에서 수정 되는 더 간단한 유동 콘텐츠 뷰어를 제공 합니다.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 및 FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>콘텐츠를 실시간 보기 모드로 표시 하지만는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 연속 스크롤 모드에서 콘텐츠를 표시 합니다. <xref:System.Windows.Controls.FlowDocumentPageViewer>및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 는 모두 특정 보기 모드로 고정 됩니다. 와 비교 합니다 <xref:System.Windows.Controls.FlowDocumentReader> . 여기에는 사용자가 열거형에서 제공 하는 다양 한 보기 모드를 동적으로 선택할 수 있는 기능이 포함 되며, <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 또는 보다 많은 리소스를 사용 하는 비용이 듭니다 <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> .

기본적으로 세로 스크롤 막대는 항상 표시되며 가로 스크롤 막대는 필요한 경우 표시됩니다. 의 기본 UI에는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 도구 모음이 포함 되어 있지 않지만 속성을 <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 사용 하 여 기본 제공 도구 모음을 활성화할 수 있습니다.

### <a name="richtextbox"></a>RichTextBox

<xref:System.Windows.Controls.RichTextBox>사용자가 유동 콘텐츠를 편집할 수 있도록 허용 하려는 경우를 사용 합니다. 예를 들어 사용자가 테이블, 기울임꼴 및 굵은 서식 등의 작업을 조작할 수 있도록 하는 편집기를 만들려는 경우를 사용 <xref:System.Windows.Controls.RichTextBox> 합니다. 자세한 내용은 [RichTextBox 개요](../controls/richtextbox-overview.md) 를 참조 하세요.

> [!NOTE]
> 내의 유동 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 다른 컨트롤에 포함 된 유동 콘텐츠와 똑같이 작동 하지 않습니다. 예를 들어에 열이 없으므로 <xref:System.Windows.Controls.RichTextBox> 자동 크기 조정 동작이 없습니다. 또한 검색, 보기 모드, 페이지 탐색 및 확대/축소와 같은 유동 콘텐츠의 일반적으로 기본 제공 되는 기능은 내에서 사용할 수 없습니다 <xref:System.Windows.Controls.RichTextBox> .

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>유동 콘텐츠 만들기

유동 콘텐츠는 복잡 해질 수 있으며, 텍스트, 이미지, 테이블, 컨트롤 등의 파생 클래스를 비롯 한 다양 한 요소로 구성 됩니다 <xref:System.Windows.UIElement> . 복합 유동 콘텐츠를 만드는 방법을 파악하려면 다음 사항의 중요합니다.

- **유동 관련 클래스**: 유동 콘텐츠에서 사용된 각 클래스에는 특정 용도가 있습니다. 또한 유동 클래스 사이의 계층 구조 관계를 파악하면 클래스 사용 방식을 이해할 수 있습니다. 예를 들어, 클래스에서 파생 된 클래스는 <xref:System.Windows.Documents.Block> 다른 개체를 포함 하는 데 사용 되 고에서 파생 된 클래스는 <xref:System.Windows.Documents.Inline> 표시 되는 개체를 포함 합니다.

- **콘텐츠 스키마**: 유동 문서에는 상당한 수의 중첩 요소가 필요할 수 있습니다. 콘텐츠 스키마는 요소 간 가능한 부모/자식 관계를 지정합니다.

다음 섹션에서는 이러한 각 영역에 대해 자세히 살펴봅니다.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>유동 관련 클래스

아래 다이어그램에서는 유동 콘텐츠와 가장 일반적으로 사용되는 개체를 보여줍니다.

![다이어그램: 유동 콘텐츠 요소 클래스 계층 구조](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

유동 콘텐츠에 사용되는 중요한 범주는 다음 두 가지가 있습니다.

1. **블록 파생 클래스**: “블록 콘텐츠 요소” 또는 “블록 요소”라고도 합니다. 에서 상속 되는 요소 <xref:System.Windows.Documents.Block> 를 사용 하 여 공통 부모에서 요소를 그룹화 하거나 그룹에 공통 특성을 적용할 수 있습니다.

2. **인라인 파생 클래스**: “인라인 콘텐츠 요소” 또는 “인라인 요소”라고도 합니다. 에서 상속 되는 요소 <xref:System.Windows.Documents.Inline> 는 블록 요소 또는 다른 인라인 요소에 포함 되어 있습니다. 인라인 요소는 종종 화면에 렌더링되는 콘텐츠의 직접 컨테이너로 사용됩니다. 예를 들어 <xref:System.Windows.Documents.Paragraph> (블록 요소)에는 <xref:System.Windows.Documents.Run> (인라인 요소)가 포함 될 수 있지만에는 <xref:System.Windows.Documents.Run> 화면에 렌더링 되는 텍스트가 실제로 포함 되어 있습니다.

이러한 두 범주의 각 클래스는 아래 간략하게 설명되어 있습니다.

### <a name="block-derived-classes"></a>블록 파생 클래스

**단락**

<xref:System.Windows.Documents.Paragraph>는 일반적으로 콘텐츠를 단락으로 그룹화 하는 데 사용 됩니다. 가장 간단하고 가장 일반적으로 단락을 이용하는 경우는 텍스트 단락을 만드는 것입니다.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

그러나 아래에서 볼 수 있는 것 처럼 다른 인라인 파생 요소를 포함할 수도 있습니다.

**섹션**

<xref:System.Windows.Documents.Section>는 다른 파생 요소를 포함 하는 데만 사용 됩니다 <xref:System.Windows.Documents.Block> . 포함된 요소에 기본 서식 지정을 적용하지 않습니다. 그러나에 설정 된 모든 속성 값은 <xref:System.Windows.Documents.Section> 자식 요소에 적용 됩니다. 또한 섹션을 사용하면 프로그래밍 방식으로 자식 컬렉션을 반복할 수 있습니다. <xref:System.Windows.Documents.Section>는 HTML의 태그와 유사한 방식으로 사용 됩니다 \<DIV> .

아래 예제에서는 3 개의 단락이 하나 아래에 정의 되어 <xref:System.Windows.Documents.Section> 있습니다. 섹션의 <xref:System.Windows.Documents.TextElement.Background%2A> 속성 값은 red 이므로 단락의 배경색도 빨강입니다.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer><xref:System.Windows.UIElement> <xref:System.Windows.Controls.Button> 블록 파생 흐름 내용에 요소 (즉, a)를 포함할 수 있도록 합니다. <xref:System.Windows.Documents.InlineUIContainer>(아래 참조)는 <xref:System.Windows.UIElement> 요소를 인라인 파생 유동 콘텐츠에 포함 하는 데 사용 됩니다. <xref:System.Windows.Documents.BlockUIContainer>및는 <xref:System.Windows.Documents.InlineUIContainer> <xref:System.Windows.UIElement> 이러한 두 요소 중 하나에 포함 되지 않은 경우 흐름 콘텐츠에서를 사용 하는 다른 방법이 없기 때문에 중요 합니다.

다음 예제에서는 요소를 사용 하 여 <xref:System.Windows.Documents.BlockUIContainer> <xref:System.Windows.UIElement> 유동 콘텐츠 내에서 개체를 호스트 하는 방법을 보여 줍니다.

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

다음 그림은이 예제에서 렌더링 하는 방법을 보여 줍니다.

![유동 콘텐츠에 포함 된 UIElement를 보여 주는 스크린샷](./media/flow-document-overview/embedded-blockuicontainer.png)

**목록**

<xref:System.Windows.Documents.List>는 글머리 기호 또는 숫자 목록을 만드는 데 사용 됩니다. 속성을 <xref:System.Windows.Documents.List.MarkerStyle%2A> <xref:System.Windows.TextMarkerStyle> 열거형 값으로 설정 하 여 목록의 스타일을 결정 합니다. 아래 예에서는 간단한 목록을 만드는 방법을 보여줍니다.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>는를 사용 하 여 자식 요소를 관리 하는 유일한 flow 요소입니다 <xref:System.Windows.Documents.ListItemCollection> .

**테이블**

<xref:System.Windows.Documents.Table>는 테이블을 만드는 데 사용 됩니다. <xref:System.Windows.Documents.Table>는 요소와 비슷하지만 <xref:System.Windows.Controls.Grid> 더 많은 기능을 포함 하므로 리소스 오버 헤드가 더 많이 필요 합니다. 는 이기 때문에 <xref:System.Windows.Controls.Grid> <xref:System.Windows.UIElement> 또는에 포함 되지 않은 경우에는 유동 콘텐츠에서 사용할 수 없습니다 <xref:System.Windows.Documents.BlockUIContainer> <xref:System.Windows.Documents.InlineUIContainer> . 에 대 한 자세한 내용은 <xref:System.Windows.Documents.Table> [테이블 개요](table-overview.md)를 참조 하세요.

### <a name="inline-derived-classes"></a>인라인 파생 클래스

**Run**

<xref:System.Windows.Documents.Run>서식 없는 텍스트를 포함 하는 데 사용 됩니다. <xref:System.Windows.Documents.Run>유동 콘텐츠에서 개체를 광범위 하 게 사용할 수 있습니다. 그러나 태그에서 <xref:System.Windows.Documents.Run> 요소는 명시적으로 사용할 필요가 없습니다. <xref:System.Windows.Documents.Run>는 코드를 사용 하 여 유동 문서를 만들거나 조작할 때 사용 해야 합니다. 예를 들어 아래 태그에서 첫 번째는 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> 요소를 명시적으로 지정 합니다. 두 단락 모두 동일한 출력을 생성합니다.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> .NET Framework 4부터 <xref:System.Windows.Documents.Run.Text%2A> 개체의 속성은 <xref:System.Windows.Documents.Run> 종속성 속성입니다. <xref:System.Windows.Documents.Run.Text%2A>속성을와 같은 데이터 소스에 바인딩할 수 있습니다 <xref:System.Windows.Controls.TextBlock> . <xref:System.Windows.Documents.Run.Text%2A>속성은 단방향 바인딩을 완벽 하 게 지원 합니다. <xref:System.Windows.Documents.Run.Text%2A>또한 속성은를 제외 하 고 양방향 바인딩을 지원 합니다 <xref:System.Windows.Controls.RichTextBox> . 예제를 보려면 <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>를 참조하세요.

**거칠**

<xref:System.Windows.Documents.Span>다른 인라인 콘텐츠 요소를 그룹화 합니다. 요소 내의 콘텐츠에는 내재 된 렌더링이 적용 되지 않습니다 <xref:System.Windows.Documents.Span> . 그러나, 및를 포함 하 여를 상속 하는 요소는 <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Documents.Bold> <xref:System.Windows.Documents.Italic> <xref:System.Windows.Documents.Underline> 텍스트에 서식을 적용 합니다.

다음은 <xref:System.Windows.Documents.Span> 텍스트, 요소 및를 포함 하는 인라인 콘텐츠를 포함 하는 데 사용 되는의 예입니다 <xref:System.Windows.Documents.Bold> <xref:System.Windows.Controls.Button> .

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

다음 스크린샷은 이 예제에서 렌더링하는 방법을 보여줍니다.

![스크린 샷: 렌더링된 Span 예제](./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer><xref:System.Windows.UIElement>요소 (즉,와 같은 컨트롤 <xref:System.Windows.Controls.Button> )를 <xref:System.Windows.Documents.Inline> 콘텐츠 요소에 포함할 수 있도록 합니다. 이 요소는 위에 설명 된 것과 동일한 인라인 요소입니다 <xref:System.Windows.Documents.BlockUIContainer> . 다음은를 사용 하 여에 인라인으로 삽입 하는 예제입니다 <xref:System.Windows.Documents.InlineUIContainer> <xref:System.Windows.Controls.Button> <xref:System.Windows.Documents.Paragraph> .

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>는 태그에서 명시적으로 사용할 필요가 없습니다. 생략 하면 <xref:System.Windows.Documents.InlineUIContainer> 코드가 컴파일될 때이 생성 됩니다.

**Figure 및 Floater**

<xref:System.Windows.Documents.Figure>및 <xref:System.Windows.Documents.Floater> 는 기본 콘텐츠 흐름과 별개로 사용자 지정할 수 있는 배치 속성을 사용 하 여 유동 문서에 콘텐츠를 포함 하는 데 사용 됩니다. <xref:System.Windows.Documents.Figure> 또는 <xref:System.Windows.Documents.Floater> 삽입할 느슨하게 관련 광고와 같이 콘텐츠 또는 요소 강조 하거나 부분 콘텐츠 지원 이미지나 다른 콘텐츠, 기본 콘텐츠 흐름 내에서 호스트를 주로 사용 됩니다.

다음 예제에서는를 텍스트 단락에 포함 하는 방법을 보여 줍니다 <xref:System.Windows.Documents.Figure> .

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.

![스크린 샷: Figure 예제](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure> 및 <xref:System.Windows.Documents.Floater> 다른 점이 몇 가지 및 다른 시나리오에 사용 됩니다.

**숫자**

- 배치 가능: 페이지, 콘텐츠, 열 또는 단락을 기준으로 고정하도록 가로 및 세로 앵커를 설정할 수 있습니다. 사용할 수도 있습니다 해당 <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> 고 <xref:System.Windows.Documents.Figure.VerticalOffset%2A> 임의 오프셋을 지정 하는 속성입니다.

- 둘 이상의 열에 맞게 크기 조정 가능: 설정할 수 있습니다 <xref:System.Windows.Documents.Figure> 높이 및 너비를 페이지, 콘텐츠 또는 열 높이나 너비의 배수로 청구 됩니다. 페이지와 콘텐츠의 경우 1보다 큰 배수는 허용되지 않습니다. 예를 들어의 너비를 설정할 수 있습니다는 <xref:System.Windows.Documents.Figure> "0.5 페이지" 또는 "0.25 콘텐츠" 또는 "2 열"입니다. 높이와 너비를 절대 픽셀 값으로 설정할 수도 있습니다.

- 페이지: 경우 내에서 콘텐츠를 <xref:System.Windows.Documents.Figure> 맞지 않으면를 <xref:System.Windows.Documents.Figure>, 않습니다 렌더링 됩니다 하 고 나머지 내용을 손실 됩니다.

**Floater:**

- 배치할 수 없으며 공간이 사용 가능하게 되면 렌더링됩니다. 오프셋 또는 앵커를 설정할 수 없습니다는 <xref:System.Windows.Documents.Floater>합니다.

- 둘 이상의 열 크기를 조정할 수 없습니다: 기본적으로 <xref:System.Windows.Documents.Floater> 크기입니다. 에 <xref:System.Windows.Documents.Floater.Width%2A> 속성 이지만이 값은 무시 되는 한 열 너비 및 floater 보다 큰 경우 절대 픽셀 값으로 설정할 수 있는 하나의 열 크기가 있습니다. 올바른 픽셀 너비로 설정 하 여 크기를 1 개 미만의 열 수 있지만 크기 조정 되지 않으므로 열을 기준 "0.5Column"에 올바른 식이 아닙니다. <xref:System.Windows.Documents.Floater> 너비입니다. <xref:System.Windows.Documents.Floater>에는 height 속성이 없으며 높이를 설정할 수 없습니다. 높이가 내용에 따라 달라 집니다.

- <xref:System.Windows.Documents.Floater> 페이지를 매깁니다: 두 개 이상의 열 높이를 확장 하는 지정 된 너비의 콘텐츠가 floater 중단 하 고 다음 열이 고, 다음 페이지에 페이지를 매깁니다.

 <xref:System.Windows.Documents.Figure> 독립 실행형 콘텐츠를 넣는 크기를 제어 하려는 및 위치 지정 및이 콘텐츠는 지정된 된 크기에 맞는지 확실 합니다. <xref:System.Windows.Documents.Floater> 기본 페이지 콘텐츠와 비슷하게 하지만에서 구분 되는 자세한 자유롭게 흐르는 콘텐츠를 넣는 곳이입니다.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>유동 콘텐츠에서 줄 바꿈을 발생 시킵니다. 다음 예에서는 <xref:System.Windows.Documents.LineBreak>의 사용법을 보여줍니다.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

다음 스크린샷은 이 예제에서 렌더링하는 방법을 보여줍니다.

![스크린 샷: LineBreak 예제](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>유동 컬렉션 요소

위의 많은 예제에서 <xref:System.Windows.Documents.BlockCollection> 및는 <xref:System.Windows.Documents.InlineCollection> 프로그래밍 방식으로 유동 콘텐츠를 생성 하는 데 사용 됩니다. 예를 들어에 요소를 추가 하려면 <xref:System.Windows.Documents.Paragraph> 다음 구문을 사용할 수 있습니다.

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

그러면의에가 추가 <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.InlineCollection> <xref:System.Windows.Documents.Paragraph> 됩니다.  태그의 내에 있는 암시적와 동일 합니다 <xref:System.Windows.Documents.Run> <xref:System.Windows.Documents.Paragraph> .

```xml
<Paragraph>
Some Text
</Paragraph>
```

를 사용 하는 예를 들어 <xref:System.Windows.Documents.BlockCollection> 다음 예제에서는 새을 만든 <xref:System.Windows.Documents.Section> 다음 **add** 메서드를 사용 하 여 내용에 새를 추가 합니다 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Section> .

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

유동 컬렉션에 항목을 추가할 수 있을 뿐만 아니라 항목을 제거할 수도 있습니다.  다음 예에서는에서 마지막 요소를 삭제 합니다 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

다음 예제에서는에서 모든 콘텐츠 ( <xref:System.Windows.Documents.Inline> 요소)를 지웁니다 <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

프로그래밍 방식으로 유동 콘텐츠에 대해 작업할 때 이러한 컬렉션을 광범위하게 사용할 가능성이 큽니다.

흐름 요소가 <xref:System.Windows.Documents.InlineCollection> 자식 요소를 포함 하는 데 (Inlines) 또는 <xref:System.Windows.Documents.BlockCollection> (블록)을 사용 하는지 여부 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Inline> 는 부모에 포함 될 수 있는 자식 요소 형식 (또는)에 따라 달라 집니다. 유동 콘텐츠 요소의 포함 규칙은 다음 섹션의 콘텐츠 스키마에 요약되어 있습니다.

> [!NOTE]
> 유동 콘텐츠에서 사용 되는 세 번째 형식의 컬렉션이 <xref:System.Windows.Documents.ListItemCollection> 있지만이 컬렉션은 에서만 사용 됩니다 <xref:System.Windows.Documents.List> . 또한와 함께 사용 되는 여러 컬렉션이 있습니다 <xref:System.Windows.Documents.Table> . 자세한 내용은 [테이블 개요](table-overview.md) 를 참조 하세요.

<a name="content_schema"></a>

## <a name="content-schema"></a>콘텐츠 스키마

여러 다른 수의 플로우 콘텐츠 요소가 있으므로, 요소에 포함될 수 있는 자식 요소의 유형을 계속 추적하는 것은 어려울 수 있습니다. 아래 다이어그램에는 유동 요소의 포함 규칙이 요약되어 있습니다. 화살표는 가능한 부모/자식 관계를 나타냅니다.

![다이어그램: 유동 콘텐츠 포함 스키마](./media/flow-content-schema.png "Flow_Content_Schema")

위의 다이어그램에서 볼 수 있듯이 요소에 대해 허용 되는 자식은 요소나 요소 인지 여부에 따라 결정 되는 것은 아닙니다 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Inline> . 예를 들어 <xref:System.Windows.Documents.Span> ( <xref:System.Windows.Documents.Inline> 요소)에는 자식 요소만 있을 수 있으며, 요소에는 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Figure> <xref:System.Windows.Documents.Inline> 자식 요소만 있을 수 있습니다 <xref:System.Windows.Documents.Block> . 그러므로 이 다이어그램은 다른 요소에 포함될 수 있는 요소를 신속하게 판별하는 데 유용합니다. 예를 들어 다이어그램을 사용 하 여의 유동 콘텐츠를 생성 하는 방법을 결정 하겠습니다 <xref:System.Windows.Controls.RichTextBox> .

**1.** 은 <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Documents.FlowDocument> 차례로 파생 된 개체를 포함 해야 하는를 포함 해야 합니다. <xref:System.Windows.Documents.Block> 위의 다이어그램에 해당되는 세그먼트는 다음과 같습니다.

![다이어그램: RichTextBox 포함 규칙](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

따라서 지금까지 태그는 다음과 같을 수 있습니다.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** 다이어그램에 따라,,, 및를 포함 하 여 몇 가지 요소를 선택할 수 있습니다 <xref:System.Windows.Documents.Block> <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.List> <xref:System.Windows.Documents.BlockUIContainer> (위의 블록 파생 클래스 참조). 을 사용 하려는 경우를 가정해 보겠습니다 <xref:System.Windows.Documents.Table> . 위의 다이어그램에 따라에는 <xref:System.Windows.Documents.Table> <xref:System.Windows.Documents.TableRowGroup> <xref:System.Windows.Documents.TableRow> 파생 개체가 포함 된 요소가 포함 된 포함 요소가 포함 <xref:System.Windows.Documents.TableCell> <xref:System.Windows.Documents.Block> 됩니다. 위의 다이어그램에서 가져온 해당 세그먼트는 다음과 같습니다 <xref:System.Windows.Documents.Table> .

![다이어그램: 테이블에 대 한 부모&#47;자식 스키마](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

다음은 해당 태그입니다.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** <xref:System.Windows.Documents.Block> 에는 하나 이상의 요소가 필요 <xref:System.Windows.Documents.TableCell> 합니다. 간단하게 셀 안에 텍스트를 배치해 보겠습니다. 요소와 함께를 사용 하 여이 작업을 수행할 수 있습니다 <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Run> . 다음은가 <xref:System.Windows.Documents.Paragraph> 요소를 사용 하 <xref:System.Windows.Documents.Inline> 고 <xref:System.Windows.Documents.Run> ( <xref:System.Windows.Documents.Inline> 요소)가 일반 텍스트를 사용할 수 있음을 보여 주는 다이어그램의 해당 세그먼트입니다.

![다이어그램: 단락의 부모&#47;자식 스키마](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")

![다이어그램: 실행을 위한 부모&#47;자식 스키마](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

다음은 태그의 전체 예제입니다.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>텍스트 사용자 지정

일반적으로 텍스트는 유동 문서에서 가장 많이 사용되는 콘텐츠 형식입니다. 위에 소개된 개체는 텍스트 렌더링 방식에 관한 대부분의 요소를 제어하는 데 사용할 수 있지만, 이 섹션에서 다루는 텍스트 사용자 지정에 사용하는 메서드는 다릅니다.

### <a name="text-decorations"></a>텍스트 장식

텍스트 장식을 사용하면 텍스트에 밑줄, 윗줄, 기준선 및 취소선 효과를 적용할 수 있습니다(아래 그림 참조). 이러한 데코레이션은 <xref:System.Windows.Documents.Inline.TextDecorations%2A> ,, 및를 비롯 한 여러 개체에 의해 노출 되는 속성을 사용 하 여 추가 됩니다 <xref:System.Windows.Documents.Inline> <xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.TextBox> .

다음 예제에서는 <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>의 <xref:System.Windows.Documents.Paragraph> 속성을 설정하는 방법을 보여 줍니다.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.

![스크린 샷: 기본 취소선 효과가 적용된 텍스트](./media/inline-textdec-strike.png "Inline_TextDec_Strike")

다음 그림은 **윗줄**, **기준선**및 **밑줄** 장식이 각각 렌더링 되는 방식을 보여 줍니다.

![스크린 샷: 윗줄 TextDecorator](./media/inline-textdec-over.png "Inline_TextDec_Over")

![스크린 샷: 텍스트의 기본 기준선 효과](./media/inline-textdec-base.png "Inline_TextDec_Base")

![스크린 샷: 밑줄 효과가 적용된 텍스트](./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>입력 체계

<xref:System.Windows.Documents.TextElement.Typography%2A>속성은,, 및를 포함 하 여 대부분의 흐름 관련 내용에 의해 노출 됩니다 <xref:System.Windows.Documents.TextElement> <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.TextBox> . 이 속성은 텍스트의 입력 체계 특성/변형(즉, 소문자 및 대문자, 위 첨자 및 아래 첨자 작성 등)을 제어하는 데 사용합니다.

다음 예제에서는 설정 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Documents.TextElement.Typography%2A> 특성을 사용 하 여 <xref:System.Windows.Documents.Paragraph> 를 예제 요소로 합니다.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.

![스크린 샷: 입력 체계가 변경된 텍스트](./media/textelement-typog.png "TextElement_Typog")

반면 다음 그림은 기본 입력 체계 속성이 있는 비슷한 예제가 렌더링되는 방식을 보여줍니다.

![스크린 샷: 입력 체계가 변경된 텍스트](./media/textelement-typog-default.png "TextElement_Typog_Default")

다음 예제에서는 설정 하는 방법의 <xref:System.Windows.Controls.TextBox.Typography%2A> 속성 프로그래밍 방식으로 합니다.

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

입력 체계에 대 한 자세한 내용은 [WPF의 입력 체계](typography-in-wpf.md) 를 참조 하세요.

## <a name="see-also"></a>참조

- [텍스트](optimizing-performance-text.md)
- [WPF의 입력 체계](typography-in-wpf.md)
- [방법 항목](flow-content-elements-how-to-topics.md)
- [TextElement 콘텐츠 모델 개요](textelement-content-model-overview.md)
- [RichTextBox 개요](../controls/richtextbox-overview.md)
- [WPF의 문서](documents-in-wpf.md)
- [테이블 개요](table-overview.md)
- [주석 개요](annotations-overview.md)
