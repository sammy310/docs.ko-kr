---
title: 수량자 작업(C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635485"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="a93ed-102">수량자 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="a93ed-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="a93ed-103">수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="a93ed-104">다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="a93ed-105">첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="a93ed-106">두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 수량자 작업](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="a93ed-108">다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a93ed-109">메서드</span><span class="sxs-lookup"><span data-stu-id="a93ed-109">Methods</span></span>  
  
|<span data-ttu-id="a93ed-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="a93ed-110">Method Name</span></span>|<span data-ttu-id="a93ed-111">설명</span><span class="sxs-lookup"><span data-stu-id="a93ed-111">Description</span></span>|<span data-ttu-id="a93ed-112">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="a93ed-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="a93ed-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a93ed-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="a93ed-114">모두</span><span class="sxs-lookup"><span data-stu-id="a93ed-114">All</span></span>|<span data-ttu-id="a93ed-115">시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="a93ed-116">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a93ed-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a93ed-117">임의의 값</span><span class="sxs-lookup"><span data-stu-id="a93ed-117">Any</span></span>|<span data-ttu-id="a93ed-118">시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="a93ed-119">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a93ed-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a93ed-120">포함</span><span class="sxs-lookup"><span data-stu-id="a93ed-120">Contains</span></span>|<span data-ttu-id="a93ed-121">시퀀스에 지정된 요소가 들어 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="a93ed-122">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a93ed-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="a93ed-123">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a93ed-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="a93ed-124">모두</span><span class="sxs-lookup"><span data-stu-id="a93ed-124">All</span></span>  
<span data-ttu-id="a93ed-125">다음 예제에서는 `All`을 사용하여 모든 문자열이 특정 길이인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="a93ed-126">임의의 값</span><span class="sxs-lookup"><span data-stu-id="a93ed-126">Any</span></span>  
<span data-ttu-id="a93ed-127">다음 예제에서는 `Any`를 사용하여 모든 문자열이 'o'로 시작하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="a93ed-128">포함</span><span class="sxs-lookup"><span data-stu-id="a93ed-128">Contains</span></span>  
<span data-ttu-id="a93ed-129">다음 예제에서는 `Contains`를 사용하여 배열에 특정 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a93ed-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="a93ed-130">참조</span><span class="sxs-lookup"><span data-stu-id="a93ed-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a93ed-131">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="a93ed-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="a93ed-132">런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="a93ed-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="a93ed-133">지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="a93ed-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
