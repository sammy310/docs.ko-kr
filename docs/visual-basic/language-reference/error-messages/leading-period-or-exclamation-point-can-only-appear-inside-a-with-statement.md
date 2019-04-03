---
title: With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4821dbab90eec3c99c0996e8bff10d51b5a8f99d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824951"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="55c66-102">With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="55c66-103">내부는 마침표 (.) 또는 느낌표 (!)을 `With` 블록 왼쪽 식을 없이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="55c66-104">멤버 액세스 (`.`) 및 사전 멤버 액세스 (`!`) 멤버가 포함 된 요소를 지정 하는 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="55c66-105">이 값은 왼쪽 접근자의 또는의 대상으로 즉시 표시 되어야 합니다는 `With` 멤버 액세스를 포함 하는 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="55c66-106">**오류 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="55c66-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="55c66-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="55c66-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="55c66-108">확인 된 `With` 블록 형식이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="55c66-109">없는 경우 없는 `With` 차단, 멤버를 포함 하는 정의 된 요소가 계산 되는 접근자의 왼쪽에 식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c66-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c66-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="55c66-110">See also</span></span>

- [<span data-ttu-id="55c66-111">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="55c66-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="55c66-112">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="55c66-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
