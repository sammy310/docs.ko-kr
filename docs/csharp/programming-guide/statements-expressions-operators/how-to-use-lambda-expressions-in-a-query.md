---
title: 쿼리에 람다 식을 사용하는 방법 - C# 프로그래밍 가이드
description: 쿼리에 람다 식을 사용하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 501e67011707e2d165a3b9c1ff9f206db7f55448
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381634"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="869ea-104">쿼리에 람다 식을 사용하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="869ea-104">How to use lambda expressions in a query (C# Programming Guide)</span></span>
<span data-ttu-id="869ea-105">람다 식은 쿼리 구문에 직접 사용하지 않고 메서드 호출에 사용하며, 쿼리 식에 메서드 호출이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-105">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="869ea-106">실제로 일부 쿼리 작업은 메서드 구문으로만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-106">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="869ea-107">쿼리 구문과 메서드 구문 간의 차이점에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="869ea-107">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="869ea-108">예제</span><span class="sxs-lookup"><span data-stu-id="869ea-108">Example</span></span>  
 <span data-ttu-id="869ea-109">다음 예제에서는 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 표준 쿼리 연산자를 사용하여 메서드 기반 쿼리에 람다 식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-109">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standard query operator.</span></span> <span data-ttu-id="869ea-110">이 예제의 <xref:System.Linq.Enumerable.Where%2A> 메서드에는 대리자 형식 <xref:System.Func%602>의 입력 매개 변수가 있으며, 해당 대리자는 정수를 입력으로 사용하고 부울을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-110">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%602> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="869ea-111">람다 식을 해당 대리자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-111">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="869ea-112"><xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> 메서드를 사용하는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 쿼리인 경우 매개 변수 형식은 `Expression<Func<int,bool>>`이지만 람다 식은 정확히 동일하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-112">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> method, the parameter type would be an `Expression<Func<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="869ea-113">식 형식에 대한 자세한 내용은 <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="869ea-113">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a><span data-ttu-id="869ea-114">예제</span><span class="sxs-lookup"><span data-stu-id="869ea-114">Example</span></span>  
 <span data-ttu-id="869ea-115">다음 예제에서는 쿼리 식의 메서드 호출에 람다 식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-115">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="869ea-116">쿼리 구문을 사용하여 <xref:System.Linq.Enumerable.Sum%2A> 표준 쿼리 연산자를 호출할 수 없기 때문에 람다가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-116">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="869ea-117">쿼리는 먼저 `GradeLevel` 열거형에 정의된 성적 수준에 따라 학생을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-117">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="869ea-118">그런 다음 각 그룹에 대해 각 학생의 총 점수를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-118">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="869ea-119">이 경우 두 개의 `Sum` 연산이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-119">This requires two `Sum` operations.</span></span> <span data-ttu-id="869ea-120">안쪽 `Sum`은 각 학생의 총 점수를 계산하고, 바깥쪽 `Sum`은 그룹에 속한 모든 학생에 대해 합산된 누계를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-120">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="869ea-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="869ea-121">Compiling the Code</span></span>  
 <span data-ttu-id="869ea-122">이 코드를 실행하려면 메서드를 복사하고 [개체 컬렉션 쿼리](../../linq/query-a-collection-of-objects.md)에 제공된 `StudentClass`에 붙여넣은 다음 `Main` 메서드에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="869ea-122">To run this code, copy and paste the method into the `StudentClass` that is provided in [Query a collection of objects](../../linq/query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="869ea-123">참조</span><span class="sxs-lookup"><span data-stu-id="869ea-123">See also</span></span>

- [<span data-ttu-id="869ea-124">람다 식</span><span class="sxs-lookup"><span data-stu-id="869ea-124">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="869ea-125">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="869ea-125">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
