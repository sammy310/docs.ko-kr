---
description: "자세히 알아보기: BC30157: 선행 '. ' 또는 '! '는 ' With ' 문 내부에만 사용할 수 있습니다."
title: With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e0325ac3c54046718d71df37edaac1edaf12f43e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795900"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="f4986-103">BC30157: 선행 '. ' 또는 '! '는 ' With ' 문 내부에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-103">BC30157: Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="f4986-104">블록 내에 없는 마침표 (.) 또는 느낌표 (!)는 `With` 왼쪽에 식 없이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-104">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="f4986-105">멤버 액세스 ( `.` ) 및 사전 멤버 액세스 ( `!` )에는 멤버가 포함 된 요소를 지정 하는 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-105">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="f4986-106">이는 접근자의 왼쪽에 바로 나타나거나 `With` 멤버 액세스를 포함 하는 블록의 대상으로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-106">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>

 <span data-ttu-id="f4986-107">**오류 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="f4986-107">**Error ID:** BC30157</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f4986-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f4986-108">To correct this error</span></span>

1. <span data-ttu-id="f4986-109">`With`블록의 형식이 올바르게 지정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-109">Ensure that the `With` block is correctly formatted.</span></span>

2. <span data-ttu-id="f4986-110">블록이 없으면 멤버를 `With` 포함 하는 정의 된 요소로 계산 되는 식을 접근자의 왼쪽에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4986-110">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4986-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4986-111">See also</span></span>

- [<span data-ttu-id="f4986-112">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="f4986-112">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="f4986-113">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="f4986-113">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
