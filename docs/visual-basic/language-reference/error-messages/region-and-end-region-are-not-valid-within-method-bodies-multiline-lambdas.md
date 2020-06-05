---
title: "'#Region' 및 '#End Region' 문은 메서드 본문(multiline lambdas) 내에서 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400385"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="3e0ec-102">메서드 본문에서는 '#Region' 및 '#End Region' 문을 사용할 수 없습니다./multiline lambdas</span><span class="sxs-lookup"><span data-stu-id="3e0ec-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="3e0ec-103">`#Region`블록은 클래스, 모듈 또는 네임 스페이스 수준에서 선언 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ec-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="3e0ec-104">축소 가능한 영역은 하나 이상의 프로시저를 포함할 수 있지만 프로시저 내에서 시작 하거나 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ec-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="3e0ec-105">**오류 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="3e0ec-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3e0ec-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3e0ec-106">To correct this error</span></span>  
  
1. <span data-ttu-id="3e0ec-107">이전 프로시저가 또는 문을 사용 하 여 제대로 종료 되었는지 `End Function` 확인 `End Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ec-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="3e0ec-108">`#Region`및 `#End Region` 지시문이 동일한 코드 블록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ec-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0ec-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e0ec-109">See also</span></span>

- [<span data-ttu-id="3e0ec-110">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="3e0ec-110">#Region Directive</span></span>](../directives/region-directive.md)
