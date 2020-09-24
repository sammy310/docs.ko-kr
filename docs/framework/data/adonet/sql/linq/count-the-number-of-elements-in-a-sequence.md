---
title: 시퀀스의 요소 수 계산
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164352"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="e757b-102">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="e757b-102">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="e757b-103"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하여 시퀀스의 요소 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e757b-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="e757b-104">Northwind 샘플 데이터베이스에 대한 쿼리를 실행하여 `91`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e757b-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e757b-105">예제</span><span class="sxs-lookup"><span data-stu-id="e757b-105">Example</span></span>  

 <span data-ttu-id="e757b-106">다음 예제에서는 데이터베이스의 `Customers` 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e757b-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e757b-107">예제</span><span class="sxs-lookup"><span data-stu-id="e757b-107">Example</span></span>  

 <span data-ttu-id="e757b-108">다음 예제에서는 데이터베이스에서 중지되지 않은 제품의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e757b-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="e757b-109">Northwind 샘플 데이터베이스에 대한 예제를 실행하여 `69`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e757b-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e757b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e757b-110">See also</span></span>

- [<span data-ttu-id="e757b-111">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="e757b-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="e757b-112">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="e757b-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
