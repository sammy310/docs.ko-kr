---
title: 수량자 작업
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346589"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="2873a-102">수량자 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2873a-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="2873a-103">수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="2873a-104">다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="2873a-105">첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="2873a-106">두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 수량자 작업](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="2873a-108">다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2873a-109">메서드</span><span class="sxs-lookup"><span data-stu-id="2873a-109">Methods</span></span>  
  
|<span data-ttu-id="2873a-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="2873a-110">Method Name</span></span>|<span data-ttu-id="2873a-111">설명</span><span class="sxs-lookup"><span data-stu-id="2873a-111">Description</span></span>|<span data-ttu-id="2873a-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="2873a-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2873a-113">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="2873a-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="2873a-114">모두</span><span class="sxs-lookup"><span data-stu-id="2873a-114">All</span></span>|<span data-ttu-id="2873a-115">시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2873a-116">Any</span><span class="sxs-lookup"><span data-stu-id="2873a-116">Any</span></span>|<span data-ttu-id="2873a-117">시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2873a-118">포함</span><span class="sxs-lookup"><span data-stu-id="2873a-118">Contains</span></span>|<span data-ttu-id="2873a-119">시퀀스에 지정된 요소가 들어 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="2873a-120">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="2873a-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="2873a-121">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="2873a-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="2873a-122">이 예에서는 LINQ 쿼리에서 필터링 조건의 일부로 Visual Basic의 `Aggregate` 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="2873a-123">다음 예제에서는 `Aggregate` 절과 <xref:System.Linq.Enumerable.All%2A> 확장 메서드를 사용 하 여 애완 동물가 지정 된 기간 보다 오래 된 사용자를 컬렉션에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="2873a-124">다음 예제에서는 `Aggregate` 절과 <xref:System.Linq.Enumerable.Any%2A> 확장 메서드를 사용 하 여 지정 된 기간 보다 오래 된 pet가 하나 이상 있는 사용자를 컬렉션에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2873a-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2873a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2873a-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2873a-126">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2873a-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="2873a-127">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="2873a-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="2873a-128">방법: 지정 된 단어 집합이 들어 있는 문장 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2873a-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
