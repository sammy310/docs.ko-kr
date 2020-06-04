---
title: <variable> 범위 변수가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 290ca81dea500558ed73956c91bdf7bfec312014
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400398"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="c3e3e-102">\<variable> 범위 변수가 바깥쪽 블록의 변수, 이전에 정의한 범위 변수 또는 쿼리 식에 암시적으로 선언한 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="c3e3e-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="c3e3e-103">,, 또는 절에 지정 된 범위 변수 이름이 `Select` `From` `Aggregate` `Let` 쿼리에서 이미 이전에 지정 된 범위 변수의 이름 또는 쿼리에서 암시적으로 선언 된 변수 이름 (예: 필드 이름 또는 집계 함수의 이름)을 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e3e-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="c3e3e-104">**오류 ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="c3e3e-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3e3e-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c3e3e-105">To correct this error</span></span>  
  
- <span data-ttu-id="c3e3e-106">특정 쿼리 범위의 모든 범위 변수 이름이 고유한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e3e-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="c3e3e-107">쿼리를 괄호로 묶어 중첩 된 쿼리에 고유한 범위가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3e3e-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e3e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3e3e-108">See also</span></span>

- [<span data-ttu-id="c3e3e-109">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="c3e3e-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c3e3e-110">From 절</span><span class="sxs-lookup"><span data-stu-id="c3e3e-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="c3e3e-111">Let 절</span><span class="sxs-lookup"><span data-stu-id="c3e3e-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="c3e3e-112">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="c3e3e-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="c3e3e-113">Select 절</span><span class="sxs-lookup"><span data-stu-id="c3e3e-113">Select Clause</span></span>](../queries/select-clause.md)
