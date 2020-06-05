---
title: With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 149acc2baac0f45fa971a11f254d694526d140d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397326"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="d75fa-102">With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="d75fa-103">블록 내에 없는 마침표 (.) 또는 느낌표 (!)는 `With` 왼쪽에 식 없이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="d75fa-104">멤버 액세스 ( `.` ) 및 사전 멤버 액세스 ( `!` )에는 멤버가 포함 된 요소를 지정 하는 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="d75fa-105">이는 접근자의 왼쪽에 바로 나타나거나 `With` 멤버 액세스를 포함 하는 블록의 대상으로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="d75fa-106">**오류 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="d75fa-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d75fa-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d75fa-107">To correct this error</span></span>  
  
1. <span data-ttu-id="d75fa-108">`With`블록의 형식이 올바르게 지정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="d75fa-109">블록이 없으면 멤버를 `With` 포함 하는 정의 된 요소로 계산 되는 식을 접근자의 왼쪽에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75fa-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75fa-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d75fa-110">See also</span></span>

- [<span data-ttu-id="d75fa-111">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="d75fa-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="d75fa-112">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="d75fa-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
