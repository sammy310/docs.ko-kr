---
title: "'Is'의 피연산자는 참조 형식이어야 하는데 이 피연산자의 값 형식은 '<typename>'입니다."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: e5acc94a3738fca3a43740bdba727fc843132aa1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402813"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="9c4f9-102">'Is'의 피연산자는 참조 형식이어야 하는데 이 피연산자의 값 형식은 '\<typename>'입니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="9c4f9-103">`Is`비교 연산자는 두 개체 변수가 같은 인스턴스를 참조 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="9c4f9-104">이 비교는 값 형식에 대해 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="9c4f9-105">**오류 ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="9c4f9-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c4f9-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9c4f9-106">To correct this error</span></span>  
  
- <span data-ttu-id="9c4f9-107">적절 한 산술 비교 연산자 또는 연산자를 사용 `Like` 하 여 두 개의 값 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c4f9-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4f9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c4f9-108">See also</span></span>

- [<span data-ttu-id="9c4f9-109">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="9c4f9-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="9c4f9-110">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="9c4f9-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="9c4f9-111">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="9c4f9-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
