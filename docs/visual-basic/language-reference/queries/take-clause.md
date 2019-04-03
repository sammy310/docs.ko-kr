---
title: Take 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: cb109eaf43fee19b77ac690492b85919c9d78301
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816956"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="0ee91-102">Take 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ee91-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="0ee91-103">컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee91-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ee91-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="0ee91-105">요소</span><span class="sxs-lookup"><span data-stu-id="0ee91-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="0ee91-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0ee91-106">Required.</span></span> <span data-ttu-id="0ee91-107">값 또는 반환 된 시퀀스의 요소 수가 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ee91-108">설명</span><span class="sxs-lookup"><span data-stu-id="0ee91-108">Remarks</span></span>  
 <span data-ttu-id="0ee91-109">`Take` 절로 인해 지정 된 수의 결과 목록 시작 지점에서 연속 요소를 포함 하도록 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="0ee91-110">지정 된 요소를 포함할 수는 `count` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="0ee91-111">사용할 수는 `Take` 절을 `Skip` 쿼리의 모든 세그먼트에서 데이터의 범위를 반환 하는 절.</span><span class="sxs-lookup"><span data-stu-id="0ee91-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="0ee91-112">이 작업을 수행 하려면 범위의 첫 번째 요소의 인덱스를 전달 합니다 `Skip` 절과 범위의 크기를 `Take` 절.</span><span class="sxs-lookup"><span data-stu-id="0ee91-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="0ee91-113">이 경우에 `Take` 후 절을 지정 해야 합니다 `Skip` 절.</span><span class="sxs-lookup"><span data-stu-id="0ee91-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="0ee91-114">사용 하는 경우는 `Take` 쿼리에서 절 있습니다도 확인 해야 할 수 있도록 순서 대로 결과가 반환 되도록는 `Take` 의도 한 결과 포함 하는 절.</span><span class="sxs-lookup"><span data-stu-id="0ee91-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="0ee91-115">쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 하세요. [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="0ee91-116">사용할 수는 `TakeWhile` 절 제공 된 조건에 따라 특정 요소에만 반환 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee91-117">예제</span><span class="sxs-lookup"><span data-stu-id="0ee91-117">Example</span></span>  
 <span data-ttu-id="0ee91-118">다음 코드 예제에서는 합니다 `Take` 절과 함께 `Skip` 페이지의 쿼리에서 데이터를 반환 하는 절.</span><span class="sxs-lookup"><span data-stu-id="0ee91-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="0ee91-119">GetCustomers 함수 사용을 `Skip` 절까지을 건너뛰고 고객 목록에서 값을 사용 하 여 제공 된 시작 인덱스는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee91-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ee91-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ee91-120">See also</span></span>

- [<span data-ttu-id="0ee91-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="0ee91-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0ee91-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="0ee91-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0ee91-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="0ee91-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="0ee91-124">From 절</span><span class="sxs-lookup"><span data-stu-id="0ee91-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="0ee91-125">Order By 절</span><span class="sxs-lookup"><span data-stu-id="0ee91-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="0ee91-126">Take While 절</span><span class="sxs-lookup"><span data-stu-id="0ee91-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="0ee91-127">Skip 절</span><span class="sxs-lookup"><span data-stu-id="0ee91-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
