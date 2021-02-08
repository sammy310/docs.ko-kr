---
description: '자세히 알아보기: 방법: 한 번에 여러 개체 검색'
title: '방법: 한 번에 여러 개체 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 2bc202e09c64f2a1956b8688be30cfd87fb655c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802010"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="1e831-103">방법: 한 번에 여러 개체 검색</span><span class="sxs-lookup"><span data-stu-id="1e831-103">How to: Retrieve Many Objects At Once</span></span>

<span data-ttu-id="1e831-104"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>를 사용하여 한 쿼리에서 여러 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e831-104">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e831-105">예제</span><span class="sxs-lookup"><span data-stu-id="1e831-105">Example</span></span>  

 <span data-ttu-id="1e831-106">다음 코드에서는 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 메서드를 사용하여 `Customer` 및 `Order` 개체를 모두 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1e831-106">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="1e831-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e831-107">See also</span></span>

- [<span data-ttu-id="1e831-108">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="1e831-108">Query Concepts</span></span>](query-concepts.md)
