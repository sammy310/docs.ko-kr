---
title: 이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: d004c89b742944622ce45e6a2be8d96116252745
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197571"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="c08c0-102">이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="c08c0-103">이전 함수 실행 시간이 초과 되었으므로 함수 실행을 사용할 수 없습니다. 함수 실행을 다시 사용 하도록 설정 하려면 다시 한 단계씩 실행 하거나 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="c08c0-104">Visual Studio 디버거에서 식이 프로시저 호출을 지정 하지만 다른 계산 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="c08c0-105">프로시저 호출 시간이 초과 될 경우 무한 루프 또는 *무한 루프*를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="c08c0-106">자세한 내용은 다음 [을 참조 하세요. 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c08c0-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="c08c0-107">무한 루프의 특수 한 경우는 *재귀*입니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="c08c0-108">자세한 내용은 [재귀 프로시저](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c08c0-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="c08c0-109">**오류 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="c08c0-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c08c0-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c08c0-110">To correct this error</span></span>  
  
1. <span data-ttu-id="c08c0-111">가능 하면 이전 함수 평가가 무엇이 었는 지와 그 원인을 확인 하십시오. 그렇지 않으면이 오류가 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="c08c0-112">디버거를 다시 한 단계씩 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c08c0-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08c0-113">참조</span><span class="sxs-lookup"><span data-stu-id="c08c0-113">See also</span></span>

- [<span data-ttu-id="c08c0-114">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="c08c0-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="c08c0-115">디버거로 코드 탐색</span><span class="sxs-lookup"><span data-stu-id="c08c0-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
