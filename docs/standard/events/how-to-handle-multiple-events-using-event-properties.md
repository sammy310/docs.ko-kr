---
title: '방법: 이벤트 속성을 사용하여 여러 이벤트 처리'
description: 이벤트 속성을 사용하여 여러 이벤트를 처리하는 방법을 알아봅니다. 대리자 컬렉션, 이벤트 키, 이벤트 속성을 정의합니다. 추가 및 제거 접근자 메서드를 구현합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: 5b528aa2145ba703ce605ce22ae7d643f1e5b8d0
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769017"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="fc277-105">방법: 이벤트 속성을 사용하여 여러 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="fc277-105">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="fc277-106">이벤트 속성을 사용하려면 이벤트를 발생시키는 클래스에서 이벤트 속성을 정의한 다음 이벤트를 처리하는 클래스에서 이벤트 속성의 대리자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-106">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="fc277-107">클래스에서 여러 이벤트 속성을 구현하려면 클래스가 각 이벤트에 대해 정의된 대리자를 내부적으로 저장 및 유지 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-107">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="fc277-108">일반적인 방법은 이벤트 키로 인덱싱된 대리자 컬렉션을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-108">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="fc277-109">각 이벤트에 대한 대리자를 저장하려면 <xref:System.ComponentModel.EventHandlerList> 클래스를 사용하거나 고유한 컬렉션을 구현하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-109">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="fc277-110">컬렉션 클래스는 이벤트 키에 따라 이벤트 처리기 대리자를 설정, 액세스 및 검색하는 메서드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-110">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="fc277-111">예를 들어 <xref:System.Collections.Hashtable> 클래스를 사용하거나 <xref:System.Collections.DictionaryBase> 클래스에서 사용자 지정 클래스를 파생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-111">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="fc277-112">대리자 컬렉션의 구현 세부 정보는 클래스 외부에 노출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-112">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="fc277-113">클래스 내의 각 이벤트 속성은 add 접근자 메서드 및 remove 접근자 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-113">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="fc277-114">이벤트 속성에 대한 add 접근자는 대리자 컬렉션에 입력 대리자 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-114">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="fc277-115">이벤트 속성에 대한 remove 접근자는 대리자 컬렉션에서 입력 대리자 인스턴스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-115">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="fc277-116">이벤트 속성 접근자는 이벤트 속성의 미리 정의된 키를 사용하여 대리자 컬렉션에서 인스턴스를 추가 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-116">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="fc277-117">이벤트 속성을 사용하여 여러 이벤트 처리하려면</span><span class="sxs-lookup"><span data-stu-id="fc277-117">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="fc277-118">이벤트를 발생시키는 클래스 내에서 대리자 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-118">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="fc277-119">각 이벤트에 대한 키를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-119">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="fc277-120">이벤트를 발생시키는 클래스에서 이벤트 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-120">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="fc277-121">대리자 컬렉션을 사용하여 이벤트 속성에 대한 add 및 remove 접근자 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-121">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="fc277-122">public 이벤트 속성을 사용하여 이벤트를 처리하는 클래스에서 이벤트 처리기 대리자를 추가 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-122">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc277-123">예제</span><span class="sxs-lookup"><span data-stu-id="fc277-123">Example</span></span>  
 <span data-ttu-id="fc277-124">다음 C# 예제에서는 <xref:System.ComponentModel.EventHandlerList>를 사용하여 각 이벤트의 대리자를 저장하는 이벤트 속성 `MouseDown` 및 `MouseUp`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-124">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="fc277-125">이벤트 속성 구문의 키워드는 굵은 글꼴로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc277-125">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="fc277-126">참조</span><span class="sxs-lookup"><span data-stu-id="fc277-126">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="fc277-127">이벤트</span><span class="sxs-lookup"><span data-stu-id="fc277-127">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fc277-128">방법: 메모리를 절약하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="fc277-128">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
