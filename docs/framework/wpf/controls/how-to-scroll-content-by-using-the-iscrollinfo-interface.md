---
title: '방법: IScrollInfo 인터페이스를 사용하여 콘텐츠 스크롤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 6ebd8268e1358b45709885c07e6b096d5f806ebb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098548"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="59ea6-102">방법: IScrollInfo 인터페이스를 사용하여 콘텐츠 스크롤</span><span class="sxs-lookup"><span data-stu-id="59ea6-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="59ea6-103">사용 하 여 콘텐츠 스크롤 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59ea6-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ea6-104">예제</span><span class="sxs-lookup"><span data-stu-id="59ea6-104">Example</span></span>  
 <span data-ttu-id="59ea6-105">다음 예제에서는 기능의 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59ea6-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="59ea6-106">이 예에서는 만듭니다는 <xref:System.Windows.Controls.StackPanel> 요소에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 부모에 중첩 된 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea6-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="59ea6-107">자식 요소를 <xref:System.Windows.Controls.StackPanel> 정의한 메서드를 사용 하 여 논리적으로 스크롤할 수 합니다 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스와의 인스턴스로 캐스트 <xref:System.Windows.Controls.StackPanel> (`sp1`) 코드에서.</span><span class="sxs-lookup"><span data-stu-id="59ea6-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="59ea6-108">각 <xref:System.Windows.Controls.Button> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에서 스크롤 동작을 제어 하는 연결 된 사용자 지정 메서드를 트리거합니다 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea6-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="59ea6-109">다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 및 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> ; 메서드 또한 일반적으로 모든 위치 지정 메서드를 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ea6-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="59ea6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="59ea6-110">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="59ea6-111">ScrollViewer 개요</span><span class="sxs-lookup"><span data-stu-id="59ea6-111">ScrollViewer Overview</span></span>](scrollviewer-overview.md)
- [<span data-ttu-id="59ea6-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="59ea6-112">How-to Topics</span></span>](scrollviewer-how-to-topics.md)
- [<span data-ttu-id="59ea6-113">Panel 개요</span><span class="sxs-lookup"><span data-stu-id="59ea6-113">Panels Overview</span></span>](panels-overview.md)
