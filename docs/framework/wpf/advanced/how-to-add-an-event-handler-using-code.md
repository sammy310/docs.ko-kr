---
title: '방법: 코드를 사용하여 이벤트 처리기 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 017b32dc07f62cc4553a84f7b91687fb34a53c65
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937468"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="126ec-102">방법: 코드를 사용하여 이벤트 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="126ec-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="126ec-103">이 예제에서는 코드를 사용 하 여 요소에 이벤트 처리기를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="126ec-104">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소에 이벤트 처리기를 추가 하 고 요소를 포함 하는 태그 페이지가 이미 로드 된 경우 코드를 사용 하 여 처리기를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="126ec-105">또는를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]요소를 선언 하지 않고 코드를 사용 하 여 응용 프로그램에 대 한 요소 트리를 완전히 빌드하는 경우 특정 메서드를 호출 하 여 생성 된 요소 트리에 이벤트 처리기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="126ec-106">예제</span><span class="sxs-lookup"><span data-stu-id="126ec-106">Example</span></span>  
 <span data-ttu-id="126ec-107">다음 예에서는에서 <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]초기에 정의 된 기존 페이지에 새를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="126ec-108">코드 숨겨진 파일은 이벤트 처리기 메서드를 구현 하 고 해당 메서드를의 새 이벤트 처리기 <xref:System.Windows.Controls.Button>로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="126ec-109">이 C# 예제에서는 `+=` 연산자를 사용 하 여 이벤트에 처리기를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="126ec-110">이 연산자는 CLR (공용 언어 런타임) 이벤트 처리 모델에서 처리기를 할당 하는 데 사용 되는 연산자와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="126ec-111">Microsoft Visual Basic는 이벤트 처리기를 추가 하는 수단으로이 연산자를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="126ec-112">대신, 다음 두 가지 방법 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="126ec-113">메서드를 `AddressOf` 연산자와 함께 사용 하 여 이벤트 처리기 구현을 참조 합니다. <xref:System.Windows.UIElement.AddHandler%2A></span><span class="sxs-lookup"><span data-stu-id="126ec-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="126ec-114">키워드를 `Handles` 이벤트 처리기 정의의 일부로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="126ec-115">이 기법은 여기에 표시 되지 않습니다. [Visual Basic 및 WPF 이벤트 처리를](visual-basic-and-wpf-event-handling.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="126ec-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="126ec-116">처음에 구문 분석 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 된 페이지에서 이벤트 처리기를 추가 하는 것이 훨씬 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="126ec-117">이벤트 처리기를 추가 하려는 개체 요소 내에서 처리할 이벤트의 이름과 일치 하는 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="126ec-118">그런 다음 해당 특성의 값을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 코드 파일에 정의 된 이벤트 처리기 메서드의 이름으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="126ec-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="126ec-119">자세한 내용은 [XAML 개요 (WPF)](xaml-overview-wpf.md) 또는 [라우트된 이벤트 개요](routed-events-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="126ec-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126ec-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="126ec-120">See also</span></span>

- [<span data-ttu-id="126ec-121">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="126ec-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="126ec-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="126ec-122">How-to Topics</span></span>](events-how-to-topics.md)
