---
title: Take 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349642"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="7fee8-102">Take 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fee8-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="7fee8-103">컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fee8-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fee8-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="7fee8-105">요소</span><span class="sxs-lookup"><span data-stu-id="7fee8-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="7fee8-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-106">Required.</span></span> <span data-ttu-id="7fee8-107">반환할 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fee8-108">주의</span><span class="sxs-lookup"><span data-stu-id="7fee8-108">Remarks</span></span>  
 <span data-ttu-id="7fee8-109">`Take` 절은 쿼리가 결과 목록의 시작 부분에서 지정 된 개수의 연속 요소를 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="7fee8-110">포함할 요소의 수는 `count` 매개 변수에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="7fee8-111">`Skip` 절과 함께 `Take` 절을 사용 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="7fee8-112">이렇게 하려면 범위의 첫 번째 요소 인덱스를 `Skip` 절에 전달 하 고 범위의 크기를 `Take` 절에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="7fee8-113">이 경우 `Skip` 절 뒤에 `Take` 절을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="7fee8-114">쿼리에서 `Take` 절을 사용 하는 경우 `Take` 절이 의도 된 결과를 포함 하도록 하는 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="7fee8-115">쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fee8-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="7fee8-116">`TakeWhile` 절을 사용 하 여 제공 된 조건에 따라 특정 요소만 반환 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fee8-117">예제</span><span class="sxs-lookup"><span data-stu-id="7fee8-117">Example</span></span>  
 <span data-ttu-id="7fee8-118">다음 코드 예제에서는 `Skip` 절과 함께 `Take` 절을 사용 하 여 페이지의 쿼리에서 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="7fee8-119">GetCustomers 함수는 `Skip` 절을 사용 하 여 목록의 고객이 제공 된 시작 인덱스 값까지 건너뛰고 `Take` 절을 사용 하 여 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fee8-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7fee8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fee8-120">See also</span></span>

- [<span data-ttu-id="7fee8-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="7fee8-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="7fee8-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="7fee8-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7fee8-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="7fee8-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="7fee8-124">From 절</span><span class="sxs-lookup"><span data-stu-id="7fee8-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="7fee8-125">Order By 절</span><span class="sxs-lookup"><span data-stu-id="7fee8-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="7fee8-126">Take While 절</span><span class="sxs-lookup"><span data-stu-id="7fee8-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="7fee8-127">Skip 절</span><span class="sxs-lookup"><span data-stu-id="7fee8-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
