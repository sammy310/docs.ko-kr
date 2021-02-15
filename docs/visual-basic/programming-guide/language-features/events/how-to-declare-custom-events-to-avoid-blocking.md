---
description: '자세한 정보: 방법: 차단 방지를 위한 사용자 지정 이벤트 선언 (Visual Basic)'
title: '방법: 차단을 방지하는 사용자 지정 이벤트 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a4ad3162e8f95ebbf7567d427ea00060b19b2235
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469723"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="97f64-103">방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f64-103">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>

<span data-ttu-id="97f64-104">한 이벤트 처리기가 후속 이벤트 처리기를 차단 하지 않는 것이 중요 한 여러 가지 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-104">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="97f64-105">사용자 지정 이벤트를 사용 하면 이벤트에서 이벤트 처리기를 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-105">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="97f64-106">기본적으로 이벤트 선언의 백업 저장소 필드는 모든 이벤트 처리기를 순차적으로 결합 하는 멀티 캐스트 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-106">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="97f64-107">즉, 한 처리기를 완료 하는 데 시간이 오래 걸리면 다른 처리기가 완료 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-107">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="97f64-108">잘 작동 하는 이벤트 처리기는 긴 작업 또는 잠재적으로 차단 되는 작업을 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-108">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="97f64-109">Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 사용자 지정 이벤트를 사용 하 여 이벤트 처리기를 비동기적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-109">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f64-110">예</span><span class="sxs-lookup"><span data-stu-id="97f64-110">Example</span></span>  

 <span data-ttu-id="97f64-111">이 예제에서 접근자는 `AddHandler` 이벤트의 각 처리기에 대 한 대리자를 `Click` <xref:System.Collections.ArrayList> 필드에 저장 된에 추가 합니다 `EventHandlerList` .</span><span class="sxs-lookup"><span data-stu-id="97f64-111">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="97f64-112">코드가 이벤트를 발생 시키면 `Click` 접근자는 `RaiseEvent` 메서드를 사용 하 여 모든 이벤트 처리기 대리자를 비동기식으로 호출 합니다 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="97f64-112">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="97f64-113">이 메서드는 작업자 스레드의 각 처리기를 호출 하 고 즉시 반환 하므로 처리기는 서로를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97f64-113">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="97f64-114">참조</span><span class="sxs-lookup"><span data-stu-id="97f64-114">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="97f64-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="97f64-115">Events</span></span>](index.md)
- [<span data-ttu-id="97f64-116">방법: 메모리를 절약하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="97f64-116">How to: Declare Custom Events To Conserve Memory</span></span>](how-to-declare-custom-events-to-conserve-memory.md)
