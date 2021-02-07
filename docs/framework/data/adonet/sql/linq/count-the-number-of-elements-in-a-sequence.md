---
description: '자세한 정보: 시퀀스의 요소 수 계산'
title: 시퀀스의 요소 수 계산
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 91030516098e900229a1e131ea0c9a7d8bef4034
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663081"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="e4368-103">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="e4368-103">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="e4368-104"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하여 시퀀스의 요소 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e4368-104">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="e4368-105">Northwind 샘플 데이터베이스에 대한 쿼리를 실행하여 `91`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e4368-105">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4368-106">예제</span><span class="sxs-lookup"><span data-stu-id="e4368-106">Example</span></span>  

 <span data-ttu-id="e4368-107">다음 예제에서는 데이터베이스의 `Customers` 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e4368-107">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e4368-108">예제</span><span class="sxs-lookup"><span data-stu-id="e4368-108">Example</span></span>  

 <span data-ttu-id="e4368-109">다음 예제에서는 데이터베이스에서 중지되지 않은 제품의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e4368-109">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="e4368-110">Northwind 샘플 데이터베이스에 대한 예제를 실행하여 `69`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e4368-110">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e4368-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4368-111">See also</span></span>

- [<span data-ttu-id="e4368-112">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="e4368-112">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="e4368-113">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="e4368-113">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
