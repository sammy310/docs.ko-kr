---
title: 스택 공간이 부족합니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 29dbdf74808fc98bb856483c3fd8e3a09a72113b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318795"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="052a5-102">스택 공간이 부족합니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="052a5-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="052a5-103">스택의는 실행 중인 프로그램의 요구를 사용 하 여 동적으로 메모리 증가 및 축소 하는 작업 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="052a5-104">해당 제한은 초과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="052a5-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="052a5-105">To correct this error</span></span>  
  
1. <span data-ttu-id="052a5-106">프로시저 너무 많이 중첩 되지 않은 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="052a5-107">재귀 프로시저 올바르게 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="052a5-108">로컬 변수 공간이 사용 가능한 것 보다 모듈 수준에서 일부 변수를 선언 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="052a5-109">선언할 수도 있습니다 절차에서는 모든 변수가 정적 앞 합니다 `Property`, `Sub`, 또는 `Function` 키워드를 `Static`입니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="052a5-110">사용할 수 있습니다는 `Static` 문을 프로시저 내에서 개별 정적 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="052a5-111">가변 길이 문자열 보다 더 많은 스택 공간을 사용 하는 고정 길이 문자열 가변 길이 문자열로 고정 길이 문자열의 일부를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="052a5-112">또한 없는 스택 공간이 요구 되는 모듈 수준에서 문자열을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="052a5-113">횟수를 확인 중첩 `DoEvents` 를 사용 하 여 함수 호출을 `Calls` 스택에 활성화 되어 있는 프로시저 보기 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="052a5-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="052a5-114">"이벤트 cascade" 스택에서 이미 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 발생 하지 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="052a5-115">종결 되지 않은 재귀 프로시저 호출을 이벤트 캐스케이딩 비슷합니다 이지만 명확 하지 호출 코드에 대 한 명시적 호출 보다는 Visual Basic에서 하므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="052a5-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="052a5-116">사용 된 `Calls` 스택에 활성화 되어 있는 프로시저 보기 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="052a5-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052a5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="052a5-117">See also</span></span>

- [<span data-ttu-id="052a5-118">메모리 창</span><span class="sxs-lookup"><span data-stu-id="052a5-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
