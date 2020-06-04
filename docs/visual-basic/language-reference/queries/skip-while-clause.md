---
title: Skip While 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359647"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="3113c-102">Skip While 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3113c-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="3113c-103">지정된 조건이 `true`이면 컬렉션에 있는 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3113c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3113c-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3113c-105">부분</span><span class="sxs-lookup"><span data-stu-id="3113c-105">Parts</span></span>  
  
|<span data-ttu-id="3113c-106">용어</span><span class="sxs-lookup"><span data-stu-id="3113c-106">Term</span></span>|<span data-ttu-id="3113c-107">정의</span><span class="sxs-lookup"><span data-stu-id="3113c-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="3113c-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3113c-108">Required.</span></span> <span data-ttu-id="3113c-109">요소를 테스트할 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="3113c-110">식은 값을 반환 `Boolean` 하거나로 평가할와 같은 기능을 반환 해야 합니다 `Integer` `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="3113c-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3113c-111">설명</span><span class="sxs-lookup"><span data-stu-id="3113c-111">Remarks</span></span>  
 <span data-ttu-id="3113c-112">`Skip While`절은 제공 된가 반환 될 때까지 쿼리 결과의 시작 부분에서 요소를 무시 합니다 `expression` `false` .</span><span class="sxs-lookup"><span data-stu-id="3113c-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="3113c-113">`expression`가 반환 된 후 `false` 쿼리는 나머지 요소를 모두 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="3113c-114">`expression`나머지 결과에 대해서는이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="3113c-115">절은 절 `Skip While` 과 다르므로 절은 `Where` `Where` 특정 조건을 충족 하지 않는 쿼리에서 모든 요소를 제외 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="3113c-116">`Skip While`절은 조건이 충족 되지 않을 때까지 요소만 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="3113c-117">`Skip While`절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="3113c-118">절을 사용 하 여 쿼리 결과의 시작 부분에서 특정 개수의 결과를 무시할 수 있습니다 `Skip` .</span><span class="sxs-lookup"><span data-stu-id="3113c-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3113c-119">예제</span><span class="sxs-lookup"><span data-stu-id="3113c-119">Example</span></span>  
 <span data-ttu-id="3113c-120">다음 코드 예제에서는 `Skip While` 미국에서 첫 번째 고객이 발견 될 때까지 절을 사용 하 여 결과를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3113c-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3113c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3113c-121">See also</span></span>

- [<span data-ttu-id="3113c-122">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="3113c-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="3113c-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="3113c-123">Queries</span></span>](index.md)
- [<span data-ttu-id="3113c-124">Select 절</span><span class="sxs-lookup"><span data-stu-id="3113c-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="3113c-125">From 절</span><span class="sxs-lookup"><span data-stu-id="3113c-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="3113c-126">Skip 절</span><span class="sxs-lookup"><span data-stu-id="3113c-126">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="3113c-127">Take While 절</span><span class="sxs-lookup"><span data-stu-id="3113c-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="3113c-128">Where 절</span><span class="sxs-lookup"><span data-stu-id="3113c-128">Where Clause</span></span>](where-clause.md)
