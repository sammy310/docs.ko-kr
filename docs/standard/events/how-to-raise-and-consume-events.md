---
title: '방법: 이벤트 발생 및 사용'
description: .NET에서 이벤트를 발생시키고 사용합니다. EventHandler 대리자, EventHandler<TEventArgs> 대리자 및 사용자 지정 대리자를 사용하는 예제를 참조하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET], raising
- raising events
- events [.NET], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 9d068981694c212c5cb29a67ccd2fcb19dcc907b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828298"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="58485-104">방법: 이벤트 발생 및 사용</span><span class="sxs-lookup"><span data-stu-id="58485-104">How to: Raise and Consume Events</span></span>
<span data-ttu-id="58485-105">이 항목의 예제에서는 이벤트로 작업하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58485-105">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="58485-106">여기서 <xref:System.EventHandler> 대리자, <xref:System.EventHandler%601> 대리자 및 사용자 지정 대리자의 예제를 통해 데이터를 사용하거나 사용하지 않는 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58485-106">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="58485-107">이 예제에서는 [이벤트](index.md) 문서에 설명된 개념을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58485-107">The examples use concepts described in the [Events](index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58485-108">예제</span><span class="sxs-lookup"><span data-stu-id="58485-108">Example</span></span>  
 <span data-ttu-id="58485-109">첫 번째 예제에서는 데이터가 없는 이벤트를 발생시키고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58485-109">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="58485-110">이벤트의 이름이 `Counter`인 `ThresholdReached`라는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58485-110">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="58485-111">이 이벤트는 카운터 값이 같거나 임계값을 초과할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="58485-111">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="58485-112">이벤트 데이터가 제공되지 않았으므로 <xref:System.EventHandler> 대리자는 이벤트와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="58485-112">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="58485-113">예제</span><span class="sxs-lookup"><span data-stu-id="58485-113">Example</span></span>  
 <span data-ttu-id="58485-114">다음 예제에서는 데이터를 제공하는 이벤트를 발생시키고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58485-114">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="58485-115"><xref:System.EventHandler%601> 대리자가 이벤트와 연결되었으며 사용자 지정 이벤트 데이터 개체의 인스턴스가 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58485-115">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="58485-116">예제</span><span class="sxs-lookup"><span data-stu-id="58485-116">Example</span></span>  
 <span data-ttu-id="58485-117">다음 예제에서는 이벤트의 대리자를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58485-117">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="58485-118">대리자의 이름은 `ThresholdReachedEventHandler`입니다.</span><span class="sxs-lookup"><span data-stu-id="58485-118">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="58485-119">이는 단지 예를 든 것이며,</span><span class="sxs-lookup"><span data-stu-id="58485-119">This is just an illustration.</span></span> <span data-ttu-id="58485-120">일반적으로 이벤트에 대한 대리자를 선언할 필요가 없습니다. <xref:System.EventHandler> 또는 <xref:System.EventHandler%601> 대리자 중 하나를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="58485-120">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="58485-121">대리자는 제네릭을 사용할 수 없는 레거시 코드에서 클래스를 사용할 수 있는 경우와 같이 드문 시나리오에서만 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58485-121">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="58485-122">참조</span><span class="sxs-lookup"><span data-stu-id="58485-122">See also</span></span>

- [<span data-ttu-id="58485-123">이벤트</span><span class="sxs-lookup"><span data-stu-id="58485-123">Events</span></span>](index.md)
