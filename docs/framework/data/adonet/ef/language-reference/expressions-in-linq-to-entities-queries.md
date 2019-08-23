---
title: LINQ to Entities 쿼리의 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 383339241194c56d0c3178f538f2ac08b2f1b437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950398"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="9f959-102">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="9f959-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="9f959-103">식은 단일 값, 개체, 메서드, 네임스페이스 등으로 계산될 수 있는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="9f959-104">식에는 리터럴 값, 메서드 호출, 연산자와 해당 피연산자, 단순한 이름 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="9f959-105">단순한 이름이란 변수, 형식 멤버, 메서드 매개 변수, 네임스페이스 또는 형식의 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="9f959-106">식은 다른 식을 매개 변수로 사용하는 연산자를 사용할 수 있으며 다른 메서드 호출을 매개 변수로 가지는 메서드 호출을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="9f959-107">따라서 식은 단순한 형태에서 매우 복잡한 형태까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="9f959-108">LINQ to Entities 쿼리에서 식에는 람다 식을 포함 하 여 <xref:System.Linq.Expressions> 네임 스페이스 내의 형식에서 허용 되는 모든 항목이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="9f959-109">LINQ to Entities 쿼리에서 사용할 수 있는 식은를 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]쿼리 하는 데 사용할 수 있는 식의 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="9f959-110">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에 대한 쿼리의 일부를 구성하는 식은 `ObjectQuery<T>` 및 기본 데이터 원본에서 지원되는 연산으로 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="9f959-111">다음 예제에서 `Where` 절의 비교는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="9f959-112">C# 과`unchecked`같은 특정 언어 구문은 LINQ to Entities 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f959-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f959-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9f959-113">In This Section</span></span>  
 [<span data-ttu-id="9f959-114">상수 식</span><span class="sxs-lookup"><span data-stu-id="9f959-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="9f959-115">식 비교</span><span class="sxs-lookup"><span data-stu-id="9f959-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="9f959-116">null 비교</span><span class="sxs-lookup"><span data-stu-id="9f959-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="9f959-117">초기화 식</span><span class="sxs-lookup"><span data-stu-id="9f959-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="9f959-118">관계, 탐색 속성 및 외래 키</span><span class="sxs-lookup"><span data-stu-id="9f959-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="9f959-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f959-119">See also</span></span>

- [<span data-ttu-id="9f959-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9f959-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
