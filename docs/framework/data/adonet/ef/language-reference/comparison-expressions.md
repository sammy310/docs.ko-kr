---
description: '자세히 알아보기: 비교 식'
title: 비교 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: 95d93597048b36e48227387e2135afab1486e1ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696999"
---
# <a name="comparison-expressions"></a><span data-ttu-id="d0a70-103">비교 식</span><span class="sxs-lookup"><span data-stu-id="d0a70-103">Comparison Expressions</span></span>

<span data-ttu-id="d0a70-104">비교 식은 상수 값, 속성 값, 메서드 결과가 다른 값과 같은지, 같지 않은지, 다른 값보다 큰지, 작은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-104">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="d0a70-105">LINQ to Entities에 대 한 특정 비교가 유효 하지 않으면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-105">If a particular comparison is not valid for LINQ to Entities, an exception will be thrown.</span></span> <span data-ttu-id="d0a70-106">암시적이든 명시적이든 모든 비교를 수행하려면 데이터 소스의 모든 구성 요소가 비교 가능한 항목이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-106">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="d0a70-107">비교 식은 쿼리 결과를 제한하기 위해 `Where` 절에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-107">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="d0a70-108">다음 쿼리 식 구문 예제에서는 판매 주문 번호가 "SO43663"인 경우 결과를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-108">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="d0a70-109">다음 메서드 기반 쿼리 구문 예제에서는 판매 주문 번호가 "SO43663"인 경우 결과를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-109">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="d0a70-110">다음 쿼리 식 구문 예제에서는 운송 날짜가 2001년 7월 8일인 경우 판매 주문 정보를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-110">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="d0a70-111">다음 메서드 기반 쿼리 구문 예제에서는 운송 날짜가 2001년 7월 8일인 경우 판매 주문 정보를 반환하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-111">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="d0a70-112">상수를 생성하는 식은 서버에서 변환되며 로컬 계산은 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-112">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="d0a70-113">다음 예제에서는 상수를 생성하는 `Where` 절의 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-113">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="d0a70-114">LINQ to Entities는 사용자 클래스를 상수로 사용 하도록 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-114">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="d0a70-115">하지만 사용자 클래스에서 속성 참조는 상수로 간주되며 명령 트리 상수 식으로 변환되고 데이터 소스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-115">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="d0a70-116">상수 식을 반환하는 메서드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-116">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="d0a70-117">다음 예제에는 상수를 반환하는 `Where` 절의 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-117">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="d0a70-118">이 예제에서는 런타임에 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-118">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="d0a70-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0a70-119">See also</span></span>

- [<span data-ttu-id="d0a70-120">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="d0a70-120">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
