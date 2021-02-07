---
description: '자세한 정보: Take While 절 (Visual Basic)'
title: Take While 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: a413223d4a85670c66f71e24addb92ae4d38a4a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719710"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="df77c-103">Take While 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df77c-103">Take While Clause (Visual Basic)</span></span>

<span data-ttu-id="df77c-104">지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-104">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df77c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="df77c-105">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="df77c-106">부분</span><span class="sxs-lookup"><span data-stu-id="df77c-106">Parts</span></span>  
  
|<span data-ttu-id="df77c-107">용어</span><span class="sxs-lookup"><span data-stu-id="df77c-107">Term</span></span>|<span data-ttu-id="df77c-108">정의</span><span class="sxs-lookup"><span data-stu-id="df77c-108">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="df77c-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="df77c-109">Required.</span></span> <span data-ttu-id="df77c-110">요소를 테스트할 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-110">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="df77c-111">식은 값을 반환 `Boolean` 하거나로 평가할와 같은 기능을 반환 해야 합니다 `Integer` `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="df77c-111">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df77c-112">설명</span><span class="sxs-lookup"><span data-stu-id="df77c-112">Remarks</span></span>  

 <span data-ttu-id="df77c-113">`Take While`절은 제공 된가 반환 될 때까지 쿼리 결과의 시작 부분에 있는 요소를 포함 합니다 `expression` `false` .</span><span class="sxs-lookup"><span data-stu-id="df77c-113">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="df77c-114">가 반환 된 후에는 `expression` `false` 쿼리에서 나머지 요소를 모두 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-114">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="df77c-115">`expression`나머지 결과에 대해서는이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-115">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="df77c-116">절은 `Take While` `Where` `Where` 특정 조건을 충족 하는 쿼리의 모든 요소를 포함 하는 데 사용할 수 있다는 점에서 절과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-116">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="df77c-117">`Take While`절은 조건이 충족 되지 않을 때까지 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-117">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="df77c-118">`Take While`절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-118">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df77c-119">예제</span><span class="sxs-lookup"><span data-stu-id="df77c-119">Example</span></span>  

 <span data-ttu-id="df77c-120">다음 코드 예에서는 절을 사용 하 여 `Take While` 주문이 없는 첫 번째 고객이 발견 될 때까지 결과를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="df77c-120">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="df77c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df77c-121">See also</span></span>

- [<span data-ttu-id="df77c-122">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="df77c-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="df77c-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="df77c-123">Queries</span></span>](index.md)
- [<span data-ttu-id="df77c-124">Select 절</span><span class="sxs-lookup"><span data-stu-id="df77c-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="df77c-125">From 절</span><span class="sxs-lookup"><span data-stu-id="df77c-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="df77c-126">Take 절</span><span class="sxs-lookup"><span data-stu-id="df77c-126">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="df77c-127">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="df77c-127">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="df77c-128">Where 절</span><span class="sxs-lookup"><span data-stu-id="df77c-128">Where Clause</span></span>](where-clause.md)
