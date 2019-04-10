---
title: "'#Region' 및 ' #End Region' 문은 메서드 본문-여러 줄 람다 식 내에서 유효 하지 않습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c41b95da7e3565ae7aaf332fe49361336e79f7c7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303910"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="2ccec-102">메서드 본문에서는 '#Region' 및 '#End Region' 문을 사용할 수 없습니다./multiline lambdas</span><span class="sxs-lookup"><span data-stu-id="2ccec-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="2ccec-103">`#Region` 블록 클래스, 모듈 또는 네임 스페이스 수준에서 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccec-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="2ccec-104">축소 가능한 영역에는 하나 이상의 프로시저 포함할 수 있지만 시작 하거나 프로시저 내부에서 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccec-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="2ccec-105">**오류 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="2ccec-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ccec-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="2ccec-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2ccec-107">앞의 절차와 올바르게 종료 확인을 `End Function` 또는 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2ccec-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="2ccec-108">있는지 확인 합니다 `#Region` 및 `#End Region` 지시문은 같은 코드 블록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccec-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccec-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ccec-109">See also</span></span>

- [<span data-ttu-id="2ccec-110">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="2ccec-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
