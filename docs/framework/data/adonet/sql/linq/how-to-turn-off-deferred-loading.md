---
description: '자세한 정보: 방법: 지연 된 로드 해제'
title: '방법: 지연 콘텐츠 해제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 739c9b0b65eda73d6c504409395eb805b0c02873
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785837"
---
# <a name="how-to-turn-off-deferred-loading"></a><span data-ttu-id="d0e65-103">방법: 지연 콘텐츠 해제</span><span class="sxs-lookup"><span data-stu-id="d0e65-103">How to: Turn Off Deferred Loading</span></span>

<span data-ttu-id="d0e65-104"><xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0e65-104">You can turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span> <span data-ttu-id="d0e65-105">자세한 내용은 [지연 된 로드 및 즉시 로드](deferred-versus-immediate-loading.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0e65-105">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0e65-106">개체 추적이 해제되면 지연된 로드는 암시적으로 해제된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0e65-106">Deferred loading is turned off by implication when object tracking is turned off.</span></span> <span data-ttu-id="d0e65-107">자세한 내용은 [방법: 읽기 전용으로 정보 검색](how-to-retrieve-information-as-read-only.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0e65-107">For more information, see [How to: Retrieve Information As Read-Only](how-to-retrieve-information-as-read-only.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e65-108">예제</span><span class="sxs-lookup"><span data-stu-id="d0e65-108">Example</span></span>  

 <span data-ttu-id="d0e65-109">다음 예제에서는 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0e65-109">The following example shows how to turn off deferred loading by setting <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> to `false`.</span></span>  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d0e65-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0e65-110">See also</span></span>

- [<span data-ttu-id="d0e65-111">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="d0e65-111">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="d0e65-112">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="d0e65-112">Querying the Database</span></span>](querying-the-database.md)
