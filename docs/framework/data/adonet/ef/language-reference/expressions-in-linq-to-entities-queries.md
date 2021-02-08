---
description: '자세한 정보: LINQ to Entities 쿼리의 식'
title: LINQ to Entities 쿼리의 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 3ab9e04adb7e823538638ae262f0e481b6948a24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786370"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="cdfcf-103">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="cdfcf-103">Expressions in LINQ to Entities Queries</span></span>

<span data-ttu-id="cdfcf-104">식은 단일 값, 개체, 메서드, 네임스페이스 등으로 계산될 수 있는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-104">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="cdfcf-105">식에는 리터럴 값, 메서드 호출, 연산자와 해당 피연산자, 단순한 이름 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-105">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="cdfcf-106">단순한 이름이란 변수, 형식 멤버, 메서드 매개 변수, 네임스페이스 또는 형식의 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-106">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="cdfcf-107">식은 다른 식을 매개 변수로 사용하는 연산자를 사용할 수 있으며 다른 메서드 호출을 매개 변수로 가지는 메서드 호출을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-107">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="cdfcf-108">따라서 식은 단순한 형태에서 매우 복잡한 형태까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-108">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="cdfcf-109">LINQ to Entities 쿼리에서 식에는 람다 식을 포함 하 여 네임 스페이스 내의 형식에서 허용 되는 모든 항목이 포함 될 수 있습니다 <xref:System.Linq.Expressions> .</span><span class="sxs-lookup"><span data-stu-id="cdfcf-109">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="cdfcf-110">LINQ to Entities 쿼리에서 사용할 수 있는 식은 Entity Framework을 쿼리 하는 데 사용할 수 있는 식의 상위 집합입니다. Entity Framework에 대 한 쿼리의 일부인 식은 `ObjectQuery<T>` 및 기본 데이터 원본에서 지원 되는 작업으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-110">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the Entity Framework.Expressions that are part of queries against the Entity Framework are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="cdfcf-111">다음 예제에서 `Where` 절의 비교는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="cdfcf-112">C #과 같은 특정 언어 구문은 `unchecked` LINQ to Entities에서 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdfcf-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdfcf-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cdfcf-113">In This Section</span></span>  

 [<span data-ttu-id="cdfcf-114">상수 식</span><span class="sxs-lookup"><span data-stu-id="cdfcf-114">Constant Expressions</span></span>](constant-expressions.md)  
  
 [<span data-ttu-id="cdfcf-115">비교 식</span><span class="sxs-lookup"><span data-stu-id="cdfcf-115">Comparison Expressions</span></span>](comparison-expressions.md)  
  
 [<span data-ttu-id="cdfcf-116">null 비교</span><span class="sxs-lookup"><span data-stu-id="cdfcf-116">Null Comparisons</span></span>](null-comparisons.md)  
  
 [<span data-ttu-id="cdfcf-117">초기화 식</span><span class="sxs-lookup"><span data-stu-id="cdfcf-117">Initialization Expressions</span></span>](initialization-expressions.md)  
  
 [<span data-ttu-id="cdfcf-118">관계, 탐색 속성 및 외래 키</span><span class="sxs-lookup"><span data-stu-id="cdfcf-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="cdfcf-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdfcf-119">See also</span></span>

- [<span data-ttu-id="cdfcf-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cdfcf-120">ADO.NET Entity Framework</span></span>](../index.md)
