---
title: '방법: 라우트된 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: edb3d6724af89b7e85986c50b579084e3c4e5070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211597"
---
# <a name="how-to-handle-a-routed-event"></a><span data-ttu-id="70671-102">방법: 라우트된 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="70671-102">How to: Handle a Routed Event</span></span>
<span data-ttu-id="70671-103">이 예제에서는 버블링 이벤트가 작동하는 방법과 라우트된 이벤트 데이터를 처리할 수 있는 처리기를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70671-103">This example shows how bubbling events work and how to write a handler that can process the routed event data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70671-104">예제</span><span class="sxs-lookup"><span data-stu-id="70671-104">Example</span></span>  
 <span data-ttu-id="70671-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 요소는 요소 트리 구조로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="70671-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], elements are arranged in an element tree structure.</span></span> <span data-ttu-id="70671-106">부모 요소는 초기에 요소 트리의 자식 요소에 의해 발생된 이벤트 처리에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70671-106">The parent element can participate in the handling of events that are initially raised by child elements in the element tree.</span></span> <span data-ttu-id="70671-107">이는 이벤트 라우팅으로 인해 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="70671-107">This is possible because of event routing.</span></span>  
  
 <span data-ttu-id="70671-108">라우트된 이벤트는 일반적으로 두 가지 라우팅 전략(버블링 또는 터널링) 중 하나를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="70671-108">Routed events typically follow one of two routing strategies, bubbling or tunneling.</span></span> <span data-ttu-id="70671-109">이 예제에서는 버블링 이벤트에 중점을 두고 사용 하 여 <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> 라우팅 작동 방법을 보여 주는 이벤트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="70671-109">This example focuses on the bubbling event and uses the <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> event to show how routing works.</span></span>  
  
 <span data-ttu-id="70671-110">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 제어 하 고 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성은이 예제는 공통 부모 요소에 이벤트 처리기를 연결 하는 구문을 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="70671-110">The following example creates two <xref:System.Windows.Controls.Button> controls and uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax to attach an event handler to a common parent element, which in this example is <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="70671-111">각 개별 이벤트 처리기를 연결 하는 대신 <xref:System.Windows.Controls.Button> 자식 요소를이 예제에서는 특성 구문을 사용 하 여 이벤트 처리기를 연결 합니다 <xref:System.Windows.Controls.StackPanel> 부모 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="70671-111">Instead of attaching individual event handlers for each <xref:System.Windows.Controls.Button> child element, the example uses attribute syntax to attach the event handler to the <xref:System.Windows.Controls.StackPanel> parent element.</span></span> <span data-ttu-id="70671-112">이 이벤트 처리 패턴은 처리기가 연결되어 있는 요소의 수를 줄이는 기술로서 이벤트 라우팅을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70671-112">This event-handling pattern shows how to use event routing as a technique for reducing the number of elements where a handler is attached.</span></span> <span data-ttu-id="70671-113">각각에 대 한 모든 버블링 이벤트 <xref:System.Windows.Controls.Button> 부모 요소를 통해 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="70671-113">All the bubbling events for each <xref:System.Windows.Controls.Button> route through the parent element.</span></span>  
  
 <span data-ttu-id="70671-114">부모에 유의 <xref:System.Windows.Controls.StackPanel> 요소를 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 특성을 부분적으로 정규화 하는 이름으로 지정 하는 이벤트 이름을 <xref:System.Windows.Controls.Button> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="70671-114">Note that on the parent <xref:System.Windows.Controls.StackPanel> element, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event name specified as the attribute is partially qualified by naming the <xref:System.Windows.Controls.Button> class.</span></span> <span data-ttu-id="70671-115">합니다 <xref:System.Windows.Controls.Button> 클래스는를 <xref:System.Windows.Controls.Primitives.ButtonBase> 파생 된 클래스는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 해당 멤버 목록에 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="70671-115">The <xref:System.Windows.Controls.Button> class is a <xref:System.Windows.Controls.Primitives.ButtonBase> derived class that has the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in its members listing.</span></span> <span data-ttu-id="70671-116">처리중인 이벤트가 라우트된 이벤트 처리기가 연결된 요소의 멤버 목록에 있지 않은 경우 이벤트 처리기 연결을 위해 이러한 부분 한정 기술이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70671-116">This partial qualification technique for attaching an event handler is necessary if the event that is being handled does not exist in the members listing of the element where the routed event handler is attached.</span></span>  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 <span data-ttu-id="70671-117">다음 예제에서는 처리 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="70671-117">The following example handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  <span data-ttu-id="70671-118">이 예제에서는 이벤트를 처리하는 요소와 이벤트를 발생시키는 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70671-118">The example reports which element handles the event and which element raises the event.</span></span> <span data-ttu-id="70671-119">이벤트 처리기는 두 버튼 중 하나를 클릭할 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="70671-119">The event handler is executed when the user clicks either button.</span></span>  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="70671-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="70671-120">See also</span></span>

- <xref:System.Windows.RoutedEvent>
- [<span data-ttu-id="70671-121">입력 개요</span><span class="sxs-lookup"><span data-stu-id="70671-121">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="70671-122">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="70671-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="70671-123">방법 항목</span><span class="sxs-lookup"><span data-stu-id="70671-123">How-to Topics</span></span>](events-how-to-topics.md)
- [<span data-ttu-id="70671-124">XAML 구문 정보</span><span class="sxs-lookup"><span data-stu-id="70671-124">XAML Syntax In Detail</span></span>](xaml-syntax-in-detail.md)
