---
title: Let 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350430"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="3a486-102">Let 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a486-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="3a486-103">값을 계산 하 여 쿼리 내의 새 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a486-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a486-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="3a486-105">요소</span><span class="sxs-lookup"><span data-stu-id="3a486-105">Parts</span></span>  
  
|<span data-ttu-id="3a486-106">용어</span><span class="sxs-lookup"><span data-stu-id="3a486-106">Term</span></span>|<span data-ttu-id="3a486-107">정의</span><span class="sxs-lookup"><span data-stu-id="3a486-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="3a486-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3a486-108">Required.</span></span> <span data-ttu-id="3a486-109">제공 된 식의 결과를 참조 하는 데 사용할 수 있는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="3a486-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3a486-110">Required.</span></span> <span data-ttu-id="3a486-111">지정 된 변수에 계산 되어 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a486-112">설명</span><span class="sxs-lookup"><span data-stu-id="3a486-112">Remarks</span></span>  
 <span data-ttu-id="3a486-113">`Let` 절을 사용 하면 각 쿼리 결과의 값을 계산 하 고 별칭을 사용 하 여 값을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="3a486-114">별칭은 `Where` 절과 같은 다른 절에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="3a486-115">`Let` 절을 사용 하면 쿼리에 포함 된 식 절에 별칭을 지정 하 고 expression 절이 사용 될 때마다 별칭을 대체할 수 있기 때문에 더 쉽게 읽을 수 있는 쿼리 문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="3a486-116">`variable` 및 `expression` 할당을 `Let` 절에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="3a486-117">각 할당을 쉼표 (,)로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a486-118">예제</span><span class="sxs-lookup"><span data-stu-id="3a486-118">Example</span></span>  
 <span data-ttu-id="3a486-119">다음 코드 예제에서는 `Let` 절을 사용 하 여 제품에 대해 10% 할인을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a486-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="3a486-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a486-120">See also</span></span>

- [<span data-ttu-id="3a486-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="3a486-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="3a486-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="3a486-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3a486-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="3a486-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="3a486-124">From 절</span><span class="sxs-lookup"><span data-stu-id="3a486-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="3a486-125">Where 절</span><span class="sxs-lookup"><span data-stu-id="3a486-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
