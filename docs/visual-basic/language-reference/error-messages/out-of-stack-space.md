---
title: 스택 공간이 부족합니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: afb6a42372bdbd2e49ac15fbbf2b9e254f8db431
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871307"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="0f145-102">스택 공간이 부족합니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="0f145-102">Out of stack space (Visual Basic)</span></span>

<span data-ttu-id="0f145-103">스택은 실행 중인 프로그램의 요구에 따라 동적으로 증가 하 고 축소 되는 메모리의 작업 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="0f145-104">제한을 초과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f145-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0f145-105">To correct this error</span></span>  
  
1. <span data-ttu-id="0f145-106">프로시저가 너무 많이 중첩 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="0f145-107">재귀 프로시저가 올바르게 종료 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="0f145-108">지역 변수를 사용할 수 있는 것 보다 더 많은 지역 변수 공간이 필요한 경우 모듈 수준에서 일부 변수를 선언 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="0f145-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="0f145-109">또한, 또는 키워드 앞에를 사용 하 여 프로시저의 모든 변수를 정적으로 선언할 수 있습니다 `Property` `Sub` `Function` `Static` .</span><span class="sxs-lookup"><span data-stu-id="0f145-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="0f145-110">또는 문을 사용 하 여 `Static` 프로시저 내에서 개별 정적 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="0f145-111">고정 길이 문자열이 가변 길이 문자열 보다 많은 스택 공간을 사용 하므로 고정 길이 문자열 중 일부를 가변 길이 문자열로 다시 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="0f145-112">스택 공간이 필요 없는 모듈 수준에서 문자열을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="0f145-113">`DoEvents`대화 상자를 사용 하 여 `Calls` 스택에서 활성화 된 프로시저를 확인 하 여 중첩 된 함수 호출 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="0f145-114">스택에서 이미 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 "이벤트 cascade"를 발생 시 키 지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="0f145-115">이벤트 캐스케이딩은 종결 되지 않은 재귀 프로시저 호출과 유사 하지만, 코드에서 명시적으로 호출 하는 것이 아니라 Visual Basic에 의해 호출이 수행 되기 때문에 명확 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="0f145-116">`Calls`대화 상자를 사용 하 여 스택에서 활성화 된 프로시저를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f145-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f145-117">참조</span><span class="sxs-lookup"><span data-stu-id="0f145-117">See also</span></span>

- [<span data-ttu-id="0f145-118">메모리 창</span><span class="sxs-lookup"><span data-stu-id="0f145-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
