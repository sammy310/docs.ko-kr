---
title: Skip 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: db2d79596895505ddaa7778e831082a94c7ad44e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821103"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="85f0f-102">Skip 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85f0f-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="85f0f-103">컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="85f0f-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="85f0f-105">요소</span><span class="sxs-lookup"><span data-stu-id="85f0f-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="85f0f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85f0f-106">Required.</span></span> <span data-ttu-id="85f0f-107">값 또는 표시 하지 않으려면 시퀀스의 요소 수가 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f0f-108">설명</span><span class="sxs-lookup"><span data-stu-id="85f0f-108">Remarks</span></span>  
 <span data-ttu-id="85f0f-109">`Skip` 절로 인해 쿼리 결과 목록 맨 앞에 요소를 무시 하 고 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="85f0f-110">건너뛸 요소 수로 식별 되는 `count` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="85f0f-111">사용할 수는 `Skip` 절을 `Take` 쿼리의 모든 세그먼트에서 데이터의 범위를 반환 하는 절.</span><span class="sxs-lookup"><span data-stu-id="85f0f-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="85f0f-112">이 작업을 수행 하려면 범위의 첫 번째 요소의 인덱스를 전달 합니다 `Skip` 절과 범위의 크기를 `Take` 절.</span><span class="sxs-lookup"><span data-stu-id="85f0f-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="85f0f-113">사용 하는 경우는 `Skip` 쿼리에서 절 있습니다도 확인 해야 할 수 있도록 순서 대로 결과가 반환 되도록는 `Skip` 절에서 의도 한 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="85f0f-114">쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 하세요. [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="85f0f-115">사용할 수는 `SkipWhile` 절을 제공 된 조건에 따라 특정 요소에만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85f0f-116">예제</span><span class="sxs-lookup"><span data-stu-id="85f0f-116">Example</span></span>  
 <span data-ttu-id="85f0f-117">다음 코드 예제에서는 합니다 `Skip` 절과 함께 `Take` 페이지의 쿼리에서 데이터를 반환 하는 절.</span><span class="sxs-lookup"><span data-stu-id="85f0f-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="85f0f-118">`GetCustomers` 함수는 `Skip` 절까지을 건너뛰고 고객 목록에서 값을 사용 하 여 제공 된 시작 인덱스는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f0f-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="85f0f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="85f0f-119">See also</span></span>

- [<span data-ttu-id="85f0f-120">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="85f0f-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="85f0f-121">쿼리</span><span class="sxs-lookup"><span data-stu-id="85f0f-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="85f0f-122">Select 절</span><span class="sxs-lookup"><span data-stu-id="85f0f-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="85f0f-123">From 절</span><span class="sxs-lookup"><span data-stu-id="85f0f-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="85f0f-124">Order By 절</span><span class="sxs-lookup"><span data-stu-id="85f0f-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="85f0f-125">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="85f0f-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="85f0f-126">Take 절</span><span class="sxs-lookup"><span data-stu-id="85f0f-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
