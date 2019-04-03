---
title: "'Is'의 피연산자는 참조 형식이어야 하는데 이 피연산자의 값 형식은 '<typename>'입니다."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: b828de196a12128a9f34ee1f9ff1e57fee22c687
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843853"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="3068a-102">'Is' 피연산자는 참조 형식 이어야 하는데이 피연산자의 값 형식은 '\<typename >'</span><span class="sxs-lookup"><span data-stu-id="3068a-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="3068a-103">`Is` 비교 연산자는 두 개의 개체 변수가 같은 인스턴스를 참조 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3068a-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="3068a-104">이 비교 값 형식에 대해 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3068a-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="3068a-105">**오류 ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="3068a-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3068a-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3068a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3068a-107">적절 한 산술 비교 연산자를 사용 하 여 또는 `Like` 두 개의 값 형식을 비교 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3068a-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3068a-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="3068a-108">See also</span></span>

- [<span data-ttu-id="3068a-109">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="3068a-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="3068a-110">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="3068a-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="3068a-111">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="3068a-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
