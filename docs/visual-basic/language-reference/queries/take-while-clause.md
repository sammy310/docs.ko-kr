---
title: Take While 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347107"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="af728-102">Take While 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af728-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="af728-103">지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af728-104">구문</span><span class="sxs-lookup"><span data-stu-id="af728-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="af728-105">요소</span><span class="sxs-lookup"><span data-stu-id="af728-105">Parts</span></span>  
  
|<span data-ttu-id="af728-106">용어</span><span class="sxs-lookup"><span data-stu-id="af728-106">Term</span></span>|<span data-ttu-id="af728-107">정의</span><span class="sxs-lookup"><span data-stu-id="af728-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="af728-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="af728-108">Required.</span></span> <span data-ttu-id="af728-109">요소를 테스트할 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="af728-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="af728-110">식은 `Boolean`으로 평가할 `Integer`와 같이 `Boolean` 값 또는 기능적으로 동일한 기능을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af728-111">주의</span><span class="sxs-lookup"><span data-stu-id="af728-111">Remarks</span></span>  
 <span data-ttu-id="af728-112">`Take While` 절은 제공 된 `expression` `false`반환 될 때까지 쿼리 결과의 시작 부분에 있는 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="af728-113">`expression`에서 `false`를 반환한 후 쿼리는 나머지 요소를 모두 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="af728-114">나머지 결과에 대해서는 `expression` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af728-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="af728-115">`Take While` 절은 `Where` 절을 사용 하 여 특정 조건을 충족 하는 쿼리의 모든 요소를 포함할 수 있다는 점에서 `Where` 절과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="af728-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="af728-116">`Take While` 절은 조건이 충족 되지 않을 때까지 요소만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="af728-117">`Take While` 절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af728-118">예제</span><span class="sxs-lookup"><span data-stu-id="af728-118">Example</span></span>  
 <span data-ttu-id="af728-119">다음 코드 예제에서는 `Take While` 절을 사용 하 여 주문이 없는 첫 번째 고객이 발견 될 때까지 결과를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="af728-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="af728-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af728-120">See also</span></span>

- [<span data-ttu-id="af728-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="af728-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="af728-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="af728-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="af728-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="af728-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="af728-124">From 절</span><span class="sxs-lookup"><span data-stu-id="af728-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="af728-125">Take 절</span><span class="sxs-lookup"><span data-stu-id="af728-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="af728-126">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="af728-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="af728-127">Where 절</span><span class="sxs-lookup"><span data-stu-id="af728-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
