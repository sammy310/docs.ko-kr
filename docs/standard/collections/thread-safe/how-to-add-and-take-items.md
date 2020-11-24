---
title: '방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
ms.openlocfilehash: 5501e108d1866fc1ae6fc66f9fe665b63373414b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818637"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="2f058-102">방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="2f058-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="2f058-103">이 예제에서는 차단 및 비차단 방식으로 <xref:System.Collections.Concurrent.BlockingCollection%601>에서 항목을 추가하고 제거하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and a non-blocking manner.</span></span> <span data-ttu-id="2f058-104"><xref:System.Collections.Concurrent.BlockingCollection%601>에 대한 자세한 내용은 [BlockingCollection 개요](blockingcollection-overview.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f058-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="2f058-105">빈 상태가 되고 요소가 더 이상 추가되지 않을 때까지 <xref:System.Collections.Concurrent.BlockingCollection%601>를 열거하는 방법에 대한 예제는 [방법: ForEach를 사용하여 BlockingCollection 항목 제거](how-to-use-foreach-to-remove.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f058-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](how-to-use-foreach-to-remove.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="2f058-106">예제</span><span class="sxs-lookup"><span data-stu-id="2f058-106">Example</span></span>  
 <span data-ttu-id="2f058-107">이 첫 번째 예제에서는 컬렉션이 일시적으로 비어있거나(가져올 때) 최대 용량일 경우(추가할 때) 또는 지정된 제한 시간이 경과되었을 경우 작업이 차단되도록 항목을 추가하거나 가져오는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or if a specified timeout period has elapsed.</span></span> <span data-ttu-id="2f058-108">최대 용량에서 차단은 생성자에서 최대 용량이 지정된 상태에서 BlockingCollection이 만들어졌을 때에만 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="2f058-109">예제</span><span class="sxs-lookup"><span data-stu-id="2f058-109">Example</span></span>  
 <span data-ttu-id="2f058-110">이 두 번째 예제에서는 작업이 차단되지 않도록 항목을 추가하고 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-110">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="2f058-111">항목이 없거나, 바인딩된 컬렉션에서 최대 용량에 도달했거나, 제한 시간이 경과한 경우 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 또는 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 작업에서 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-111">If no item is present, maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="2f058-112">이를 통해 스레드는 잠깐 다른 몇 가지 유용한 작업을 수행한 다음, 나중에 다시 한번 새 항목을 검색하거나 이전에 추가할 수 없었던 동일한 항목을 추가하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-112">This allows the thread to do some other useful work for a while and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="2f058-113">프로그램은 또한 <xref:System.Collections.Concurrent.BlockingCollection%601>에 액세스할 때 취소를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f058-113">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="2f058-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f058-114">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="2f058-115">BlockingCollection 개요</span><span class="sxs-lookup"><span data-stu-id="2f058-115">BlockingCollection Overview</span></span>](blockingcollection-overview.md)
