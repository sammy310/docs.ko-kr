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
ms.openlocfilehash: f2377d8d1635912885a310b2b0429a6a00083b47
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869680"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="867f6-102">Take 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="867f6-102">Take Clause (Visual Basic)</span></span>

<span data-ttu-id="867f6-103">컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="867f6-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="867f6-105">부분</span><span class="sxs-lookup"><span data-stu-id="867f6-105">Parts</span></span>  

 `count`  
 <span data-ttu-id="867f6-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-106">Required.</span></span> <span data-ttu-id="867f6-107">반환할 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="867f6-108">설명</span><span class="sxs-lookup"><span data-stu-id="867f6-108">Remarks</span></span>  

 <span data-ttu-id="867f6-109">`Take`절을 실행 하면 결과 목록의 시작 부분에서 지정 된 개수의 연속 요소가 쿼리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="867f6-110">포함할 요소의 수는 `count` 매개 변수로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="867f6-111">절 `Take` 과 함께 절을 사용 `Skip` 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="867f6-112">이렇게 하려면 범위의 첫 번째 요소 인덱스를 절에 전달 하 `Skip` 고 범위의 크기를 절에 전달 `Take` 합니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="867f6-113">이 경우 절 뒤에 `Take` 절을 지정 해야 합니다 `Skip` .</span><span class="sxs-lookup"><span data-stu-id="867f6-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="867f6-114">쿼리에서 절을 사용 하는 경우에는 `Take` 절에서 의도 된 결과를 포함 하도록 하는 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다 `Take` .</span><span class="sxs-lookup"><span data-stu-id="867f6-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="867f6-115">쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](order-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="867f6-115">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="867f6-116">절을 사용 하 여 `TakeWhile` 제공 된 조건에 따라 특정 요소만 반환 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="867f6-117">예제</span><span class="sxs-lookup"><span data-stu-id="867f6-117">Example</span></span>  

 <span data-ttu-id="867f6-118">다음 코드 예에서는 절과 함께 절을 사용 하 여 `Take` `Skip` 페이지의 쿼리에서 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="867f6-119">GetCustomers 함수는 절을 사용 하 여 `Skip` 목록에서 제공 된 시작 인덱스 값까지 고객을 우회 하 고 절을 사용 하 여 `Take` 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="867f6-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="867f6-120">참조</span><span class="sxs-lookup"><span data-stu-id="867f6-120">See also</span></span>

- [<span data-ttu-id="867f6-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="867f6-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="867f6-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="867f6-122">Queries</span></span>](index.md)
- [<span data-ttu-id="867f6-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="867f6-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="867f6-124">From 절</span><span class="sxs-lookup"><span data-stu-id="867f6-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="867f6-125">Order By 절</span><span class="sxs-lookup"><span data-stu-id="867f6-125">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="867f6-126">Take While 절</span><span class="sxs-lookup"><span data-stu-id="867f6-126">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="867f6-127">Skip 절</span><span class="sxs-lookup"><span data-stu-id="867f6-127">Skip Clause</span></span>](skip-clause.md)
