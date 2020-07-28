---
title: ScrollViewer 개요
description: Windows Presentation Foundation 응용 프로그램에서 콘텐츠를 스크롤할 수 있도록 하는 ScrollViewer 컨트롤에 대해 알아봅니다. 사용 예제를 참조 하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1ef680bb004315a2b523814714d5533535d044e5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164636"
---
# <a name="scrollviewer-overview"></a>ScrollViewer 개요
사용자 인터페이스 내의 콘텐츠는 대개 컴퓨터 화면의 표시 영역보다 더 큽니다. <xref:System.Windows.Controls.ScrollViewer>컨트롤은 응용 프로그램에서 콘텐츠를 스크롤할 수 있는 편리한 방법을 제공 합니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . 이 항목에서는 요소를 소개 <xref:System.Windows.Controls.ScrollViewer> 하 고 몇 가지 사용 예를 제공 합니다.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>ScrollViewer 컨트롤  
 응용 프로그램에서 스크롤할 수 있는 두 가지 미리 정의 된 요소인 및가 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer> <xref:System.Windows.Controls.ScrollViewer>컨트롤은 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Panel> 스크롤할 수 있는 영역에 표시 되는 다른 요소를 표시 하기 위해 가로 및 세로 요소와 콘텐츠 컨테이너 (예: 요소)를 캡슐화 합니다. 콘텐츠 스크롤에 요소를 사용 하려면 사용자 지정 개체를 빌드해야 합니다 <xref:System.Windows.Controls.Primitives.ScrollBar> . 그러나 <xref:System.Windows.Controls.ScrollViewer> 요소는 기능을 캡슐화 하는 복합 컨트롤 이므로 단독으로 사용할 수 있습니다 <xref:System.Windows.Controls.Primitives.ScrollBar> .  
  
 <xref:System.Windows.Controls.ScrollViewer>컨트롤은 마우스 및 키보드 명령에 응답 하 고 미리 결정 된 증분으로 콘텐츠를 스크롤 하는 데 사용할 수 있는 다양 한 메서드를 정의 합니다. 이벤트를 사용 하 여 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 상태의 변경을 검색할 수 있습니다 <xref:System.Windows.Controls.ScrollViewer> .  
  
 에는 <xref:System.Windows.Controls.ScrollViewer> 자식 요소를 하나만 포함할 수 있습니다. 일반적으로 요소 <xref:System.Windows.Controls.Panel> 컬렉션을 호스트할 수 있는 요소 <xref:System.Windows.Controls.Panel.Children%2A> 입니다. <xref:System.Windows.Controls.ContentPresenter.Content%2A>속성은의 유일한 자식을 정의 합니다 <xref:System.Windows.Controls.ScrollViewer> .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>물리적 및 논리적 스크롤 비교  
 실제 스크롤은 미리 결정된 실제 증분만큼(일반적으로 픽셀 단위로 선언된 값만큼) 콘텐츠를 스크롤하는 데 사용됩니다. 논리적 스크롤은 논리 트리에서 다음 항목으로 스크롤하는 데 사용됩니다. 대부분의 요소에 대 한 기본 스크롤 동작은 물리적 스크롤입니다 <xref:System.Windows.Controls.Panel> . [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 두 가지 스크롤 형식을 모두 지원합니다.  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 인터페이스  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>인터페이스는 또는 파생 된 컨트롤 내의 주 스크롤 영역을 나타냅니다 <xref:System.Windows.Controls.ScrollViewer> . 이 인터페이스는 <xref:System.Windows.Controls.Panel> 물리적 증가값이 아니라 논리 단위로 스크롤이 필요한 요소에 의해 구현 될 수 있는 스크롤 속성 및 메서드를 정의 합니다. 인스턴스를 파생 된 <xref:System.Windows.Controls.Primitives.IScrollInfo> 로 캐스팅 한 <xref:System.Windows.Controls.Panel> 다음 스크롤 메서드를 사용 하면 픽셀 증분이 아닌 자식 컬렉션의 다음 논리 단위로 스크롤할 수 있습니다. 기본적으로 컨트롤은 <xref:System.Windows.Controls.ScrollViewer> 물리적 단위로 스크롤을 지원 합니다.  
  
 <xref:System.Windows.Controls.StackPanel>및는 <xref:System.Windows.Controls.VirtualizingStackPanel> 모두 <xref:System.Windows.Controls.Primitives.IScrollInfo> 논리적 스크롤을 구현 하 고 기본적으로 지원 합니다. 기본적으로 논리적 스크롤을 지 원하는 레이아웃 컨트롤의 경우에서 호스트 요소를 래핑하고 <xref:System.Windows.Controls.Panel> 속성을로 설정 하 여 물리적 스크롤을 수행할 수 있습니다 <xref:System.Windows.Controls.ScrollViewer> <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> `false` .  
  
 다음 코드 예제에서는의 인스턴스를로 캐스팅 하 <xref:System.Windows.Controls.Primitives.IScrollInfo> <xref:System.Windows.Controls.StackPanel> 고 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 인터페이스에 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> 의해 정의 된 콘텐츠 스크롤 메서드 (및)를 사용 하는 방법을 보여 줍니다.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>ScrollViewer 요소 정의 및 사용  
 다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 일부 텍스트 및 사각형이 포함 된 창에서를 만듭니다. <xref:System.Windows.Controls.Primitives.ScrollBar>요소가 필요한 경우에만 표시 됩니다. 창의 크기를 조정 하면 <xref:System.Windows.Controls.Primitives.ScrollBar> 및 속성의 업데이트 된 값으로 인해 요소가 표시 되 고 사라집니다 <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> .  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>ScrollViewer 스타일 지정  
 Windows Presentation Foundation의 모든 컨트롤과 마찬가지로, <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 기본 렌더링 동작을 변경 하기 위해를 스타일 지정할 수 있습니다. 컨트롤 스타일 지정에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조하세요.  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>문서 페이지 매김  
 문서 콘텐츠의 경우 스크롤 대신 페이지 매김을 지원하는 문서 컨테이너를 선택할 수 있습니다. <xref:System.Windows.Documents.FlowDocument>는 <xref:System.Windows.Controls.FlowDocumentPageViewer> 여러 페이지에서 콘텐츠 페이지 매김을 지원 하 여 스크롤에 대 한 필요성을 방지 하는 등의 보기 컨트롤 내에서 호스팅하도록 설계 된 문서에 대 한 것입니다. <xref:System.Windows.Controls.DocumentViewer>콘텐츠를 보기 위한 솔루션을 제공 합니다 .이 솔루션은 <xref:System.Windows.Documents.FixedDocument> 일반적인 스크롤을 사용 하 여 표시 영역의 영역 외부에 콘텐츠를 표시 합니다.  
  
 문서 서식 및 프레젠테이션 옵션에 대한 자세한 내용은 [WPF의 문서](../advanced/documents-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [방법: 스크롤 뷰어 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [WPF의 문서](../advanced/documents-in-wpf.md)
- [ScrollBar 스타일 및 템플릿](scrollbar-styles-and-templates.md)
- [컨트롤](../advanced/optimizing-performance-controls.md)
