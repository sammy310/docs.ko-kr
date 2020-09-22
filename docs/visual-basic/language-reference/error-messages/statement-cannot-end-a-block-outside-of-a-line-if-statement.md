---
title: 문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 5e75c29e57a9c04c66e6bca79d99bb18c513f667
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870745"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="22652-102">문이 'If' 문 줄 외부의 블록에서 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22652-102">Statement cannot end a block outside of a line 'If' statement</span></span>

<span data-ttu-id="22652-103">한 줄 문에는 `If` 콜론 (:)으로 구분 된 여러 문이 포함 되어 있습니다 .이 중 하나는 `End` 한 줄 외부의 제어 블록에 대 한 문입니다 `If` .</span><span class="sxs-lookup"><span data-stu-id="22652-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="22652-104">한 줄 `If` 문은 문을 사용 하지 않습니다 `End If` .</span><span class="sxs-lookup"><span data-stu-id="22652-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="22652-105">**오류 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="22652-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22652-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="22652-106">To correct this error</span></span>  
  
- <span data-ttu-id="22652-107">`If`문이 포함 된 제어 블록 밖으로 한 줄로 된 문을 이동 합니다 `End If` .</span><span class="sxs-lookup"><span data-stu-id="22652-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22652-108">참조</span><span class="sxs-lookup"><span data-stu-id="22652-108">See also</span></span>

- [<span data-ttu-id="22652-109">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="22652-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
