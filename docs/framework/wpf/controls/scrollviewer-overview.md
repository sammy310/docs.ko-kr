---
title: ScrollViewer 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186980"
---
# <a name="scrollviewer-overview"></a>ScrollViewer 개요
사용자 인터페이스 내의 콘텐츠는 대개 컴퓨터 화면의 표시 영역보다 더 큽니다. 이 <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 콘텐츠를 스크롤할 수 있는 편리한 방법을 제공합니다. 이 항목에서는 <xref:System.Windows.Controls.ScrollViewer> 요소를 소개하고 몇 가지 사용 예제를 제공합니다.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>ScrollViewer 컨트롤  
 응용 프로그램에서 스크롤을 활성화하는 두 가지 미리 <xref:System.Windows.Controls.ScrollViewer>정의된 요소가 있습니다. <xref:System.Windows.Controls.Primitives.ScrollBar> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 <xref:System.Windows.Controls.ScrollViewer> 스크롤 가능한 영역에 다른 <xref:System.Windows.Controls.Primitives.ScrollBar> 가시 요소를 표시하기 <xref:System.Windows.Controls.Panel> 위해 수평 및 수직 요소와 콘텐츠 컨테이너(예: 요소)를 캡슐화합니다. 콘텐츠 스크롤에 요소를 사용하려면 사용자 <xref:System.Windows.Controls.Primitives.ScrollBar> 지정 개체를 빌드해야 합니다. 그러나 <xref:System.Windows.Controls.ScrollViewer> <xref:System.Windows.Controls.Primitives.ScrollBar> 기능을 캡슐화하는 복합 컨트롤이므로 요소 자체를 사용할 수 있습니다.  
  
 컨트롤은 <xref:System.Windows.Controls.ScrollViewer> 마우스 및 키보드 명령에 모두 응답하고 미리 결정된 증분으로 콘텐츠를 스크롤하는 수많은 방법을 정의합니다. 이벤트를 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 사용하여 상태의 변화를 검색할 <xref:System.Windows.Controls.ScrollViewer> 수 있습니다.  
  
 A는 <xref:System.Windows.Controls.ScrollViewer> 하나의 자식(일반적으로 <xref:System.Windows.Controls.Panel> 요소 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션을 호스트할 수 있는 요소)만 가질 수 있습니다. 속성은 <xref:System.Windows.Controls.ContentPresenter.Content%2A> 의 유일한 자식을 정의합니다. <xref:System.Windows.Controls.ScrollViewer>  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>물리적 및 논리 스크롤  
 실제 스크롤은 미리 결정된 실제 증분만큼(일반적으로 픽셀 단위로 선언된 값만큼) 콘텐츠를 스크롤하는 데 사용됩니다. 논리적 스크롤은 논리 트리에서 다음 항목으로 스크롤하는 데 사용됩니다. 물리적 스크롤은 대부분의 <xref:System.Windows.Controls.Panel> 요소에 대한 기본 스크롤 동작입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 두 가지 스크롤 형식을 모두 지원합니다.  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 인터페이스  
 인터페이스는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 또는 파생된 컨트롤 <xref:System.Windows.Controls.ScrollViewer> 내의 기본 스크롤 영역을 나타냅니다. 인터페이스는 물리적 증분이 아닌 논리적 단위로 <xref:System.Windows.Controls.Panel> 스크롤해야 하는 요소로 구현할 수 있는 스크롤 속성 및 메서드를 정의합니다. 파생 된 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인스턴스를 캐스팅 <xref:System.Windows.Controls.Panel> 한 다음 스크롤 메서드를 사용하면 픽셀 증분대신 자식 컬렉션의 다음 논리 단위로 스크롤할 수 있는 유용한 방법이 제공됩니다. 기본적으로 컨트롤은 <xref:System.Windows.Controls.ScrollViewer> 물리적 단위로 스크롤을 지원합니다.  
  
 <xref:System.Windows.Controls.StackPanel>논리적 <xref:System.Windows.Controls.VirtualizingStackPanel> 스크롤을 구현하고 <xref:System.Windows.Controls.Primitives.IScrollInfo> 기본적으로 지원합니다. 기본적으로 논리적 스크롤을 지원하는 레이아웃 컨트롤의 경우 호스트 요소를 <xref:System.Windows.Controls.Panel> 에 <xref:System.Windows.Controls.ScrollViewer> 래핑하고 <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> 속성을 로 `false`설정하여 물리적 스크롤을 수행할 수 있습니다.  
  
 다음 코드 <xref:System.Windows.Controls.Primitives.IScrollInfo> 예제에서는 인스턴스를 에 <xref:System.Windows.Controls.StackPanel> 캐스팅하고 인터페이스에 정의된 콘텐츠<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>스크롤 메서드(및)를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>ScrollViewer 요소 정의 및 사용  
 다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 일부 텍스트와 사각형이 포함된 창에 a를 만듭니다. <xref:System.Windows.Controls.Primitives.ScrollBar>요소는 필요할 때만 나타납니다. 창 크기를 조정하면 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> 및 <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> 속성의 업데이트된 값으로 인해 요소가 나타나고 사라집니다.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>ScrollViewer 스타일 지정  
 Windows 프레젠테이션 재단의 모든 컨트롤과 마찬가지로 컨트롤의 기본 렌더링 동작을 변경하기 위해 스타일을 만들 <xref:System.Windows.Controls.ScrollViewer> 수 있습니다. 컨트롤 스타일 지정에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조하세요.  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>문서 페이지 매김  
 문서 콘텐츠의 경우 스크롤 대신 페이지 매김을 지원하는 문서 컨테이너를 선택할 수 있습니다. <xref:System.Windows.Documents.FlowDocument>는 여러 페이지에서 콘텐츠를 페이그나팅하는 것을 <xref:System.Windows.Controls.FlowDocumentPageViewer>지원하는 와 같은 보기 컨트롤 내에서 호스팅되도록 설계된 문서에 대한 것입니다. <xref:System.Windows.Controls.DocumentViewer>기존 스크롤을 <xref:System.Windows.Documents.FixedDocument> 사용하여 디스플레이 영역 외부의 콘텐츠를 표시하는 콘텐츠를 볼 수 있는 솔루션을 제공합니다.  
  
 문서 서식 및 프레젠테이션 옵션에 대한 자세한 내용은 [WPF의 문서](../advanced/documents-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [방법: 스크롤 뷰어 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [WPF의 문서](../advanced/documents-in-wpf.md)
- [ScrollBar 스타일 및 템플릿](scrollbar-styles-and-templates.md)
- [컨트롤](../advanced/optimizing-performance-controls.md)
