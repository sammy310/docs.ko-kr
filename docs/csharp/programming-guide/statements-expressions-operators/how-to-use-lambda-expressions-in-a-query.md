---
title: '방법: 쿼리에 람다 식 사용 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: e7e7da211599b5ce0263377ecaf25b404399ce9c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423161"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="3bb1f-102">방법: 쿼리에 람다 식 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3bb1f-102">How to: Use Lambda Expressions in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="3bb1f-103">람다 식은 쿼리 구문에 직접 사용하지 않고 메서드 호출에 사용하며, 쿼리 식에 메서드 호출이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="3bb1f-104">실제로 일부 쿼리 작업은 메서드 구문으로만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="3bb1f-105">쿼리 구문과 메서드 구문 간의 차이점에 대한 자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bb1f-106">예</span><span class="sxs-lookup"><span data-stu-id="3bb1f-106">Example</span></span>  
 <span data-ttu-id="3bb1f-107">다음 예제에서는 <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 표준 쿼리 연산자를 사용하여 메서드 기반 쿼리에 람다 식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standard query operator.</span></span> <span data-ttu-id="3bb1f-108">이 예제의 <xref:System.Linq.Enumerable.Where%2A> 메서드에는 대리자 형식 <xref:System.Func%602>의 입력 매개 변수가 있으며, 해당 대리자는 정수를 입력으로 사용하고 부울을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%602> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="3bb1f-109">람다 식을 해당 대리자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="3bb1f-110"><xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> 메서드를 사용하는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 쿼리인 경우 매개 변수 형식은 `Expression<Func<int,bool>>`이지만 람다 식은 정확히 동일하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> method, the parameter type would be an `Expression<Func<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="3bb1f-111">식 형식에 대한 자세한 내용은 <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a><span data-ttu-id="3bb1f-112">예</span><span class="sxs-lookup"><span data-stu-id="3bb1f-112">Example</span></span>  
 <span data-ttu-id="3bb1f-113">다음 예제에서는 쿼리 식의 메서드 호출에 람다 식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-113">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="3bb1f-114">쿼리 구문을 사용하여 <xref:System.Linq.Enumerable.Sum%2A> 표준 쿼리 연산자를 호출할 수 없기 때문에 람다가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-114">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="3bb1f-115">쿼리는 먼저 `GradeLevel` 열거형에 정의된 성적 수준에 따라 학생을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-115">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="3bb1f-116">그런 다음 각 그룹에 대해 각 학생의 총 점수를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-116">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="3bb1f-117">이 경우 두 개의 `Sum` 연산이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-117">This requires two `Sum` operations.</span></span> <span data-ttu-id="3bb1f-118">안쪽 `Sum`은 각 학생의 총 점수를 계산하고, 바깥쪽 `Sum`은 그룹에 속한 모든 학생에 대해 합산된 누계를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-118">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bb1f-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3bb1f-119">Compiling the Code</span></span>  
 <span data-ttu-id="3bb1f-120">이 코드를 실행하려면 메서드를 복사하여 [방법: 개체 컬렉션 쿼리](../../linq/query-a-collection-of-objects.md)에 제공된 로 붙여넣은 후 `Main` 메서드에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb1f-120">To run this code, copy and paste the method into the `StudentClass` that is provided in [How to: Query a Collection of Objects](../../linq/query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb1f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bb1f-121">See also</span></span>

- [<span data-ttu-id="3bb1f-122">람다 식</span><span class="sxs-lookup"><span data-stu-id="3bb1f-122">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="3bb1f-123">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="3bb1f-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
