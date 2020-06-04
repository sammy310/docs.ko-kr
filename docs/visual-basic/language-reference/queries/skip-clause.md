---
title: Skip 절
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359660"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="fbfff-102">Skip 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbfff-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="fbfff-103">컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbfff-104">구문</span><span class="sxs-lookup"><span data-stu-id="fbfff-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="fbfff-105">부분</span><span class="sxs-lookup"><span data-stu-id="fbfff-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="fbfff-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fbfff-106">Required.</span></span> <span data-ttu-id="fbfff-107">건너뛸 시퀀스의 요소 수로 계산 되는 값 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbfff-108">설명</span><span class="sxs-lookup"><span data-stu-id="fbfff-108">Remarks</span></span>  
 <span data-ttu-id="fbfff-109">절을 사용 `Skip` 하면 쿼리가 결과 목록의 시작 부분에 있는 요소를 무시 하 고 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="fbfff-110">건너뛸 요소의 수는 `count` 매개 변수로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="fbfff-111">절 `Skip` 과 함께 절을 사용 `Take` 하 여 쿼리 세그먼트의 데이터 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="fbfff-112">이렇게 하려면 범위의 첫 번째 요소 인덱스를 절에 전달 하 `Skip` 고 범위의 크기를 절에 전달 `Take` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="fbfff-113">쿼리에서 절을 사용 하는 경우 절에서 의도 한 결과를 무시 하도록 하는 `Skip` 순서로 결과가 반환 되는지 확인 해야 할 수도 있습니다 `Skip` .</span><span class="sxs-lookup"><span data-stu-id="fbfff-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="fbfff-114">쿼리 결과를 정렬 하는 방법에 대 한 자세한 내용은 [Order By 절](order-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfff-114">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="fbfff-115">`SkipWhile`제공 된 조건에 따라 특정 요소만 무시 되도록 지정 하려면 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbfff-116">예제</span><span class="sxs-lookup"><span data-stu-id="fbfff-116">Example</span></span>  
 <span data-ttu-id="fbfff-117">다음 코드 예에서는 절과 함께 절을 사용 하 여 `Skip` `Take` 페이지의 쿼리에서 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="fbfff-118">함수는 절을 사용 하 여 `GetCustomers` `Skip` 제공 된 시작 인덱스 값까지 목록의 고객을 우회 하 고 절을 사용 하 여 `Take` 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfff-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbfff-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbfff-119">See also</span></span>

- [<span data-ttu-id="fbfff-120">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="fbfff-120">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="fbfff-121">쿼리</span><span class="sxs-lookup"><span data-stu-id="fbfff-121">Queries</span></span>](index.md)
- [<span data-ttu-id="fbfff-122">Select 절</span><span class="sxs-lookup"><span data-stu-id="fbfff-122">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="fbfff-123">From 절</span><span class="sxs-lookup"><span data-stu-id="fbfff-123">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="fbfff-124">Order By 절</span><span class="sxs-lookup"><span data-stu-id="fbfff-124">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="fbfff-125">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="fbfff-125">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="fbfff-126">Take 절</span><span class="sxs-lookup"><span data-stu-id="fbfff-126">Take Clause</span></span>](take-clause.md)
