---
description: '자세한 정보: BC30957: 이전 함수 실행 시간이 초과 되었으므로 함수 실행을 사용할 수 없습니다.'
title: 이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 32e4b460a0334a542d59091bfc0b9a2337fdd089
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796186"
---
# <a name="bc30957-function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="47d8a-103">BC30957: 이전 함수 실행 시간이 초과 되었으므로 함수 실행을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-103">BC30957: Function evaluation is disabled because a previous function evaluation timed out</span></span>

<span data-ttu-id="47d8a-104">이전 함수 실행 시간이 초과 되었으므로 함수 실행을 사용할 수 없습니다. 함수 실행을 다시 사용 하도록 설정 하려면 다시 한 단계씩 실행 하거나 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-104">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>

 <span data-ttu-id="47d8a-105">Visual Studio 디버거에서 식이 프로시저 호출을 지정 하지만 다른 계산 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>

 <span data-ttu-id="47d8a-106">프로시저 호출 시간이 초과 될 경우 무한 루프 또는 *무한 루프* 를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="47d8a-107">자세한 내용은 다음 [을 참조 하세요. 다음 문](../statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="47d8a-107">For more information, see [For...Next Statement](../statements/for-next-statement.md).</span></span>

 <span data-ttu-id="47d8a-108">무한 루프의 특수 한 경우는 *재귀* 입니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="47d8a-109">자세한 내용은 [재귀 프로시저](../../programming-guide/language-features/procedures/recursive-procedures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47d8a-109">For more information, see [Recursive Procedures](../../programming-guide/language-features/procedures/recursive-procedures.md).</span></span>

 <span data-ttu-id="47d8a-110">**오류 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="47d8a-110">**Error ID:** BC30957</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="47d8a-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="47d8a-111">To correct this error</span></span>

1. <span data-ttu-id="47d8a-112">가능 하면 이전 함수 평가가 무엇이 었는 지와 그 원인을 확인 하십시오. 그렇지 않으면이 오류가 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-112">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>

2. <span data-ttu-id="47d8a-113">디버거를 다시 한 단계씩 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d8a-113">Either step the debugger again, or terminate and restart debugging.</span></span>

## <a name="see-also"></a><span data-ttu-id="47d8a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47d8a-114">See also</span></span>

- [<span data-ttu-id="47d8a-115">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="47d8a-115">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="47d8a-116">디버거로 코드 탐색</span><span class="sxs-lookup"><span data-stu-id="47d8a-116">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
