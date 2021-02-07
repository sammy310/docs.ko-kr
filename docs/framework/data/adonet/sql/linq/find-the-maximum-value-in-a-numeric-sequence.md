---
description: '자세한 정보: 숫자 시퀀스에서 최대값 찾기'
title: 숫자 시퀀스에서 최대값 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: ab311f29d776c1ef4647967d391c7e4122ae7d38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672103"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="7fe82-103">숫자 시퀀스에서 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="7fe82-103">Find the Maximum Value in a Numeric Sequence</span></span>

<span data-ttu-id="7fe82-104"><xref:System.Linq.Enumerable.Max%2A> 연산자를 사용하여 숫자 값 시퀀스에서 최대값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-104">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fe82-105">예제</span><span class="sxs-lookup"><span data-stu-id="7fe82-105">Example</span></span>  

 <span data-ttu-id="7fe82-106">다음 예제에서는 직원의 최근 고용 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-106">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="7fe82-107">이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `11/15/1994 12:00:00 AM`이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-107">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="7fe82-108">예제</span><span class="sxs-lookup"><span data-stu-id="7fe82-108">Example</span></span>  

 <span data-ttu-id="7fe82-109">다음 예제에서는 제품의 최대 재고 수량을 찾습니다. </span><span class="sxs-lookup"><span data-stu-id="7fe82-109">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="7fe82-110">이 예제를 Northwind 샘플 데이터베이스에 대해 실행하면 `125`가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-110">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="7fe82-111">예제</span><span class="sxs-lookup"><span data-stu-id="7fe82-111">Example</span></span>  

 <span data-ttu-id="7fe82-112">다음 예제에서는 Max를 사용하여 각 범주에서 가장 비싼 가격의 `Products`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-112">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="7fe82-113">그런 다음 범주별로 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-113">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="7fe82-114">Northwind 샘플 데이터베이스에 대해 이전 쿼리를 실행할 경우 결과는 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe82-114">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="7fe82-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fe82-115">See also</span></span>

- [<span data-ttu-id="7fe82-116">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="7fe82-116">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="7fe82-117">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="7fe82-117">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
