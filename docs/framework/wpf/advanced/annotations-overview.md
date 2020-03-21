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
# <a name="annotations-overview"></a>주석 개요
종이 문서에 메모나 설명을 적는 것은 당연하게 받아들이는 매우 일반적인 행동입니다. 이러한 메모나 설명은 나중에 참조하기 위해 관심 있는 항목을 강조 표시하거나 정보를 첨부하기 위해 문서에 추가하는 "주석"입니다. 인쇄된 문서에 메모를 적는 것은 간단하고 일반적이지만 전자 문서에 개인적인 주석을 추가하는 기능은 대개 가능하더라도 매우 제한적입니다.  
  
 이 항목에서는 몇 가지 일반적인 주석 유형, 특히 스티커 메모 및 강조 표시를 검토하고 Microsoft 주석 프레임워크가 Windows 프레젠테이션 재단(WPF)을 통해 응용 프로그램에서 이러한 유형의 주석을 용이하게 하는 방법을 보여 줍니다. )을 문서 보기 컨트롤로 설정합니다.  주석을 지원하는 WPF 문서 보기 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentScrollViewer>컨트롤에는 및 <xref:System.Windows.Controls.Primitives.DocumentViewerBase> <xref:System.Windows.Controls.FlowDocumentPageViewer>에서 파생된 <xref:System.Windows.Controls.DocumentViewer> 컨트롤이 포함됩니다.  

<a name="caf1_type_stickynotes"></a>
## <a name="sticky-notes"></a>스티커 메모  
 일반적인 스티커 메모는 작은 색지에 정보를 작성하여 문서에 "붙입니다". 디지털 스티커 메모는 전자 문서에 대해 유사한 기능을 제공하지만 입력된 텍스트, 필기 노트(예: Tablet PC "잉크" 스트로크) 또는 웹 링크와 같은 다른 많은 유형의 콘텐츠를 포함할 수 있는 유연성이 추가되었습니다.  
  
 다음 그림에서는 강조 표시, 텍스트 스티커 메모 및 잉크 스티커 메모 주석의 몇 가지 예를 보여 줍니다.  
  
 ![강조 표시, 텍스트 및 잉크 스티커 메모 주석](./media/caf-stickynote.jpg "CAF_StickyNote")  
  
 다음 예제에서는 애플리케이션에서 주석 지원을 설정하는 데 사용할 수 있는 메서드를 보여 줍니다.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>
## <a name="highlights"></a>주요 사항  
 사람들은 종이 문서에 표시할 때 밑줄 긋기, 강조 표시, 문장에 포함된 단어에 동그라미 표시, 여백에 표식이나 주석 그리기 등의 창조적인 방법으로 관심 있는 항목에 주의를 끌도록 합니다.  Microsoft 주석 프레임워크의 강조 표시 주석은 WPF 문서 보기 컨트롤에 표시되는 정보를 표시하는 것과 유사한 기능을 제공합니다.  
  
 다음 그림에서는 강조 표시 주석의 예를 보여 줍니다.  
  
 ![강조 표시 주석](./media/caf-callouts.png "CAF_Callouts")  
  
 사용자는 일반적으로 먼저 일부 텍스트 또는 관심 항목을 선택한 다음 마우스 오른쪽 단추로 클릭하여 주석 옵션을 표시하여 주석을 <xref:System.Windows.Controls.ContextMenu> 만듭니다.  다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용자가 주석을 만들고 <xref:System.Windows.Controls.ContextMenu> 관리하기 위해 액세스할 수 있는 라우팅된 명령을 사용하여 a를 선언하는 데 사용할 수 있습니다.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>
## <a name="data-anchoring"></a>데이터 고정  
 주석 프레임워크는 표시 뷰의 위치뿐만 아니라 사용자가 선택한 데이터에 주석을 바인딩합니다. 따라서 사용자가 표시 창을 스크롤하거나 크기를 조정할 때와 같이 문서 보기가 변경되면 주석은 바인딩된 데이터 선택 항목과 함께 그대로 유지됩니다. 예를 들어 다음 그래픽에서는 사용자가 텍스트를 선택하여 만든 주석을 보여 줍니다. 문서 보기가 변경되면(스크롤, 크기 조정, 배율 또는 이동 등) 강조 표시 주석은 원래의 데이터 선택 항목과 함께 이동합니다.  
  
 ![주석 데이터 고정](./media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>
## <a name="matching-annotations-with-annotated-objects"></a>주석이 지정된 개체에 주석 연결  
 주석을 해당 주석이 지정된 개체와 연결할 수 있습니다. 예를 들어 주석 창이 있는 간단한 문서 판독기 애플리케이션을 생각해 보겠습니다. 주석 창은 문서에 고정된 주석 목록의 텍스트를 표시하는 목록 상자일 수 있습니다. 사용자가 목록 상자에서 항목을 선택하면 애플리케이션에서 해당 주석 개체에 고정된 문서의 단락을 표시합니다.  
  
 다음 예제에서는 주석 창으로 사용되는 목록 상자의 이벤트 처리기를 구현하는 방법을 보여 줍니다.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 또 다른 예제 시나리오에는 전자 메일을 통해 문서 판독기 간에 주석과 스티커 메모를 교환할 수 있는 응용 프로그램이 포함됩니다. 이러한 애플리케이션은 이 기능을 통해 판독기에서 교환하는 주석이 포함된 페이지로 이동할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [주석 스키마](annotations-schema.md)
- [ContextMenu 개요](../controls/contextmenu-overview.md)
- [명령 개요](commanding-overview.md)
- [유동 문서 개요](flow-document-overview.md)
- [How to: Add a Command to a MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))(방법: MenuItem에 명령 추가)
