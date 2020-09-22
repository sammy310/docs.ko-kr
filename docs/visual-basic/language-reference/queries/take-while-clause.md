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
ms.openlocfilehash: 632e9e2195f21a3aa1d1ffd28e9838905c471156
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869657"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="9e53e-102">Take While 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e53e-102">Take While Clause (Visual Basic)</span></span>

<span data-ttu-id="9e53e-103">지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e53e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e53e-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9e53e-105">부분</span><span class="sxs-lookup"><span data-stu-id="9e53e-105">Parts</span></span>  
  
|<span data-ttu-id="9e53e-106">용어</span><span class="sxs-lookup"><span data-stu-id="9e53e-106">Term</span></span>|<span data-ttu-id="9e53e-107">정의</span><span class="sxs-lookup"><span data-stu-id="9e53e-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="9e53e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9e53e-108">Required.</span></span> <span data-ttu-id="9e53e-109">요소를 테스트할 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="9e53e-110">식은 값을 반환 `Boolean` 하거나로 평가할와 같은 기능을 반환 해야 합니다 `Integer` `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="9e53e-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e53e-111">설명</span><span class="sxs-lookup"><span data-stu-id="9e53e-111">Remarks</span></span>  

 <span data-ttu-id="9e53e-112">`Take While`절은 제공 된가 반환 될 때까지 쿼리 결과의 시작 부분에 있는 요소를 포함 합니다 `expression` `false` .</span><span class="sxs-lookup"><span data-stu-id="9e53e-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="9e53e-113">가 반환 된 후에는 `expression` `false` 쿼리에서 나머지 요소를 모두 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="9e53e-114">`expression`나머지 결과에 대해서는이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="9e53e-115">절은 `Take While` `Where` `Where` 특정 조건을 충족 하는 쿼리의 모든 요소를 포함 하는 데 사용할 수 있다는 점에서 절과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="9e53e-116">`Take While`절은 조건이 충족 되지 않을 때까지 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="9e53e-117">`Take While`절은 순서가 지정 된 쿼리 결과를 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e53e-118">예제</span><span class="sxs-lookup"><span data-stu-id="9e53e-118">Example</span></span>  

 <span data-ttu-id="9e53e-119">다음 코드 예에서는 절을 사용 하 여 `Take While` 주문이 없는 첫 번째 고객이 발견 될 때까지 결과를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e53e-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e53e-120">참조</span><span class="sxs-lookup"><span data-stu-id="9e53e-120">See also</span></span>

- [<span data-ttu-id="9e53e-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="9e53e-121">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9e53e-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="9e53e-122">Queries</span></span>](index.md)
- [<span data-ttu-id="9e53e-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="9e53e-123">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9e53e-124">From 절</span><span class="sxs-lookup"><span data-stu-id="9e53e-124">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="9e53e-125">Take 절</span><span class="sxs-lookup"><span data-stu-id="9e53e-125">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="9e53e-126">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="9e53e-126">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="9e53e-127">Where 절</span><span class="sxs-lookup"><span data-stu-id="9e53e-127">Where Clause</span></span>](where-clause.md)
