---
description: '자세한 정보: Let 절 (Visual Basic)'
title: Let 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88a7d96bb790a1e6ec5adfa4337c51f807930168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653643"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="a9159-103">Let 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9159-103">Let Clause (Visual Basic)</span></span>

<span data-ttu-id="a9159-104">값을 계산 하 여 쿼리 내의 새 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-104">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9159-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9159-105">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="a9159-106">부분</span><span class="sxs-lookup"><span data-stu-id="a9159-106">Parts</span></span>  
  
|<span data-ttu-id="a9159-107">용어</span><span class="sxs-lookup"><span data-stu-id="a9159-107">Term</span></span>|<span data-ttu-id="a9159-108">정의</span><span class="sxs-lookup"><span data-stu-id="a9159-108">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="a9159-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a9159-109">Required.</span></span> <span data-ttu-id="a9159-110">제공 된 식의 결과를 참조 하는 데 사용할 수 있는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-110">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="a9159-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-111">Required.</span></span> <span data-ttu-id="a9159-112">지정 된 변수에 계산 되어 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-112">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9159-113">설명</span><span class="sxs-lookup"><span data-stu-id="a9159-113">Remarks</span></span>  

 <span data-ttu-id="a9159-114">절을 사용 하면 `Let` 각 쿼리 결과의 값을 계산 하 고 별칭을 사용 하 여 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-114">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="a9159-115">이 별칭은 절과 같은 다른 절에서 사용할 수 있습니다 `Where` .</span><span class="sxs-lookup"><span data-stu-id="a9159-115">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="a9159-116">`Let`절을 사용 하면 쿼리에 포함 된 식 절에 별칭을 지정 하 고 expression 절을 사용할 때마다 별칭을 대체할 수 있기 때문에 더 쉽게 읽을 수 있는 쿼리 문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-116">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="a9159-117">절에는 개수와 할당을 모두 포함할 수 있습니다 `variable` `expression` `Let` .</span><span class="sxs-lookup"><span data-stu-id="a9159-117">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="a9159-118">각 할당을 쉼표 (,)로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-118">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9159-119">예제</span><span class="sxs-lookup"><span data-stu-id="a9159-119">Example</span></span>  

 <span data-ttu-id="a9159-120">다음 코드 예에서는 절을 사용 하 여 `Let` 제품에 대해 10% 할인을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9159-120">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="a9159-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9159-121">See also</span></span>

- [<span data-ttu-id="a9159-122">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="a9159-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a9159-123">쿼리</span><span class="sxs-lookup"><span data-stu-id="a9159-123">Queries</span></span>](index.md)
- [<span data-ttu-id="a9159-124">Select 절</span><span class="sxs-lookup"><span data-stu-id="a9159-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="a9159-125">From 절</span><span class="sxs-lookup"><span data-stu-id="a9159-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="a9159-126">Where 절</span><span class="sxs-lookup"><span data-stu-id="a9159-126">Where Clause</span></span>](where-clause.md)
