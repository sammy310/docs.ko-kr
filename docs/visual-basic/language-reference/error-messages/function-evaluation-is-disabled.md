---
title: 이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315779"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="dd081-102">이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="dd081-103">함수 평가 이전 함수 실행 시간이 초과 되어 비활성화 됩니다. 함수 실행을 다시 활성화 하려면 다시 단계별로 실행 하거나 디버깅 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="dd081-104">Visual Studio 디버거에서 식이 프로시저 호출을 지정 하지만 다른 평가 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="dd081-105">제한 시간을 초과 하는 프로시저 호출에 대 한 가능한 원인 무한 루프를 포함 하거나 *무한 루프*합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="dd081-106">자세한 내용은 참조 하세요. [에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="dd081-107">무한 루프의 특별 한 경우 *재귀*합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="dd081-108">자세한 내용은 [재귀 프로시저](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="dd081-109">**오류 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="dd081-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd081-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="dd081-110">To correct this error</span></span>  
  
1. <span data-ttu-id="dd081-111">가능한 경우 이전 함수 실행 던 및 시간 초과 원인을 결정 합니다. 그렇지 않은 경우이 오류가 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="dd081-112">디버거를 다시 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd081-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd081-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd081-113">See also</span></span>

- [<span data-ttu-id="dd081-114">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="dd081-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="dd081-115">디버거로 코드 탐색</span><span class="sxs-lookup"><span data-stu-id="dd081-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
