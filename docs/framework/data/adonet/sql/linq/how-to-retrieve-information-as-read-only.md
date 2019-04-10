---
title: '방법: 읽기 전용 정보 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 131562e9ee0fbfde8c94f580bcb6d452918f42ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148982"
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="67e59-102">방법: 읽기 전용 정보 검색</span><span class="sxs-lookup"><span data-stu-id="67e59-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="67e59-103">데이터를 변경하지 않으려면 읽기 전용 결과를 검색하여 쿼리의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e59-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="67e59-104"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정하여 읽기 전용 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="67e59-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67e59-105"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정한 경우 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>는 암시적으로 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e59-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e59-106">예제</span><span class="sxs-lookup"><span data-stu-id="67e59-106">Example</span></span>  
 <span data-ttu-id="67e59-107">다음 코드에서는 직원 고용 날짜의 읽기 전용 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="67e59-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="67e59-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="67e59-108">See also</span></span>

- [<span data-ttu-id="67e59-109">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="67e59-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="67e59-110">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="67e59-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [<span data-ttu-id="67e59-111">지연된 로드 및 즉시 로드 비교</span><span class="sxs-lookup"><span data-stu-id="67e59-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
