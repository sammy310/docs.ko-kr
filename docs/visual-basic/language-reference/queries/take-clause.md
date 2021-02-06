---
description: '자세한 정보: Take 절 (Visual Basic)'
title: Take 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 6542d262490d9d4acff893b2a99ffb60dd1446a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653539"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="cbe45-103">Take 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbe45-103">Take Clause (Visual Basic)</span></span>

<span data-ttu-id="cbe45-104">컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-104">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe45-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbe45-105">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="cbe45-106">부분</span><span class="sxs-lookup"><span data-stu-id="cbe45-106">Parts</span></span>  

 `count`  
 <span data-ttu-id="cbe45-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-107">Required.</span></span> <span data-ttu-id="cbe45-108">반환할 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-108">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbe45-109">설명</span><span class="sxs-lookup"><span data-stu-id="cbe45-109">Remarks</span></span>  

 <span data-ttu-id="cbe45-110">`Take`절을 실행 하면 결과 목록의 시작 부분에서 지정 된 개수의 연속 요소가 쿼리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-110">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="cbe45-111">포함할 요소의 수는 `count` 매개 변수로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-111">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="cbe45-112">절 `Take` 과 함께 절을 사용 `Skip` 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-112">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="cbe45-113">이렇게 하려면 범위의 첫 번째 요소 인덱스를 절에 전달 하 `Skip` 고 범위의 크기를 절에 전달 `Take` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-113">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="cbe45-114">이 경우 절 뒤에 `Take` 절을 지정 해야 합니다 `Skip` .</span><span class="sxs-lookup"><span data-stu-id="cbe45-114">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="cbe45-115">쿼리에서 절을 사용 하는 경우에는 `Take` 절에서 의도 된 결과를 포함 하도록 하는 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다 `Take` .</span><span class="sxs-lookup"><span data-stu-id="cbe45-115">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="cbe45-116">쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](order-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbe45-116">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="cbe45-117">절을 사용 하 여 `TakeWhile` 제공 된 조건에 따라 특정 요소만 반환 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-117">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbe45-118">예제</span><span class="sxs-lookup"><span data-stu-id="cbe45-118">Example</span></span>  

 <span data-ttu-id="cbe45-119">다음 코드 예에서는 절과 함께 절을 사용 하 여 `Take` `Skip` 페이지의 쿼리에서 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-119">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="cbe45-120">GetCustomers 함수는 절을 사용 하 여 `Skip` 목록에서 제공 된 시작 인덱스 값까지 고객을 우회 하 고 절을 사용 하 여 `Take` 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe45-120">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cbe45-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbe45-121">See also</span></span>

- [<span data-ttu-id="cbe45-122">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="cbe45-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="cbe45-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="cbe45-123">Queries</span></span>](index.md)
- [<span data-ttu-id="cbe45-124">Select 절</span><span class="sxs-lookup"><span data-stu-id="cbe45-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="cbe45-125">From 절</span><span class="sxs-lookup"><span data-stu-id="cbe45-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="cbe45-126">Order By 절</span><span class="sxs-lookup"><span data-stu-id="cbe45-126">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="cbe45-127">Take While 절</span><span class="sxs-lookup"><span data-stu-id="cbe45-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="cbe45-128">Skip 절</span><span class="sxs-lookup"><span data-stu-id="cbe45-128">Skip Clause</span></span>](skip-clause.md)
