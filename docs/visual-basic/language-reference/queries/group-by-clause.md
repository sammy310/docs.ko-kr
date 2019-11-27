---
title: Group By 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 87080254ad5d237a593f0c35e7c3fdaef3a8ad59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350472"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="a7f30-102">Group By 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7f30-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="a7f30-103">쿼리 결과의 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-103">Groups the elements of a query result.</span></span> <span data-ttu-id="a7f30-104">각 그룹에 집계 함수를 적용하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="a7f30-105">그룹화 작업은 하나 이상의 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f30-106">구문</span><span class="sxs-lookup"><span data-stu-id="a7f30-106">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="a7f30-107">요소</span><span class="sxs-lookup"><span data-stu-id="a7f30-107">Parts</span></span>  
  
- <span data-ttu-id="a7f30-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="a7f30-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="a7f30-109">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a7f30-109">Optional.</span></span> <span data-ttu-id="a7f30-110">그룹화된 결과에 포함할 필드를 명시적으로 식별하는 쿼리 변수의 하나 이상 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="a7f30-111">필드를 지정하지 않으면 쿼리 변수의 모든 필드가 그룹화된 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="a7f30-112">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-112">Required.</span></span> <span data-ttu-id="a7f30-113">요소 그룹을 결정하는 데 사용할 키를 식별하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="a7f30-114">둘 이상의 키를 지정하여 복합 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="a7f30-115">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a7f30-115">Optional.</span></span> <span data-ttu-id="a7f30-116">복합 키를 만들기 위해 `keyExp1` 와 결합되는 하나 이상의 추가 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="a7f30-117">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-117">Required.</span></span> <span data-ttu-id="a7f30-118">그룹의 집계 방법을 식별하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="a7f30-119">그룹화된 결과의 멤버 이름을 식별하려면 다음 형식 중 하나일 수 있는 `Group` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="a7f30-120">-또는-</span><span class="sxs-lookup"><span data-stu-id="a7f30-120">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="a7f30-121">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7f30-122">주의</span><span class="sxs-lookup"><span data-stu-id="a7f30-122">Remarks</span></span>  
 <span data-ttu-id="a7f30-123">`Group By` 절을 사용하여 쿼리 결과를 그룹으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="a7f30-124">그룹화는 키 또는 여러 키로 구성된 복합 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="a7f30-125">일치하는 키 값과 연결된 요소는 동일한 그룹에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="a7f30-126">`aggregateList` 절의 `Into` 매개 변수와 `Group` 키워드를 사용하여 그룹을 참조하는 데 사용되는 멤버 이름을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="a7f30-127">`Into` 절에 집계 함수를 포함하여 그룹화된 요소의 값을 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="a7f30-128">표준 집계 함수 목록은 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7f30-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7f30-129">예제</span><span class="sxs-lookup"><span data-stu-id="a7f30-129">Example</span></span>  
 <span data-ttu-id="a7f30-130">다음 코드 예제에서는 해당 위치 (국가/지역)를 기준으로 고객 목록을 그룹화 하 고 각 그룹의 고객 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="a7f30-131">결과는 국가/지역 이름별로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="a7f30-132">그룹화된 결과는 도시 이름별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7f30-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="a7f30-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7f30-133">See also</span></span>

- [<span data-ttu-id="a7f30-134">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="a7f30-134">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a7f30-135">쿼리</span><span class="sxs-lookup"><span data-stu-id="a7f30-135">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a7f30-136">Select 절</span><span class="sxs-lookup"><span data-stu-id="a7f30-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="a7f30-137">From 절</span><span class="sxs-lookup"><span data-stu-id="a7f30-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="a7f30-138">Order By 절</span><span class="sxs-lookup"><span data-stu-id="a7f30-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="a7f30-139">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="a7f30-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="a7f30-140">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="a7f30-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
