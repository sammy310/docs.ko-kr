---
title: <variable> 범위 변수가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822715"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="07fb5-102">범위 변수 \<변수 >의 변수는 바깥쪽 블록, 이전에 정의한 범위 변수 또는 쿼리 식에서 암시적으로 선언한 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="07fb5-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="07fb5-103">에 지정 된 범위 변수 이름이 `Select`, `From`를 `Aggregate`, 또는 `Let` 절 쿼리 또는 쿼리에 의해 암시적으로 선언 된 변수 이름에 이미 이전에 지정한 범위 변수 이름과 중복 필드 이름 등을 집계 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07fb5-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="07fb5-104">**오류 ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="07fb5-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07fb5-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="07fb5-105">To correct this error</span></span>  
  
-   <span data-ttu-id="07fb5-106">특정 쿼리 범위 안에 있는 모든 범위 변수 이름이 고유한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07fb5-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="07fb5-107">쿼리를 중첩된 쿼리 고유한 범위를 갖도록 괄호로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07fb5-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fb5-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="07fb5-108">See also</span></span>

- [<span data-ttu-id="07fb5-109">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="07fb5-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="07fb5-110">From 절</span><span class="sxs-lookup"><span data-stu-id="07fb5-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="07fb5-111">Let 절</span><span class="sxs-lookup"><span data-stu-id="07fb5-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="07fb5-112">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="07fb5-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="07fb5-113">Select 절</span><span class="sxs-lookup"><span data-stu-id="07fb5-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
