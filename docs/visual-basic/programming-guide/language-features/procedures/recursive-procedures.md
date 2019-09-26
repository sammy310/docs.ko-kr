---
title: 재귀 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: b08a06a07f134b7c95251848862d39339e59fe61
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274350"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="e1fbc-102">재귀 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1fbc-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="e1fbc-103">*재귀* 프로시저는 자신을 호출 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="e1fbc-104">일반적으로 Visual Basic 코드를 작성 하는 가장 효과적인 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="e1fbc-105">다음 절차에서는 재귀를 사용 하 여 원래 인수의 계승을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="e1fbc-106">재귀 프로시저에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e1fbc-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="e1fbc-107">**제한 조건**.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-107">**Limiting Conditions**.</span></span> <span data-ttu-id="e1fbc-108">재귀를 종료할 수 있는 조건을 하나 이상 테스트 하는 재귀 프로시저를 디자인 해야 하며, 적절 한 수의 재귀 호출 내에서 이러한 조건이 충족 되지 않는 경우도 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="e1fbc-109">실패 없이 충족 될 수 있는 조건이 하나 이상 없으면 프로시저에서 무한 루프에서 실행 될 위험이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="e1fbc-110">**메모리 사용량**.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-110">**Memory Usage**.</span></span> <span data-ttu-id="e1fbc-111">응용 프로그램에는 지역 변수에 대해 제한 된 공간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="e1fbc-112">프로시저는 자신을 호출할 때마다 해당 지역 변수의 추가 복사본에 대해 더 많은 공간을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="e1fbc-113">이 프로세스가 무기한 지속 되 면 결국 <xref:System.StackOverflowException> 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="e1fbc-114">**효율성**-</span><span class="sxs-lookup"><span data-stu-id="e1fbc-114">**Efficiency**.</span></span> <span data-ttu-id="e1fbc-115">루프를 거의 항상 재귀로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="e1fbc-116">루프는 인수를 전달 하 고, 추가 저장소를 초기화 하 고, 값을 반환 하는 오버 헤드를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="e1fbc-117">재귀 호출 없이 성능이 훨씬 더 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="e1fbc-118">**상호 재귀**.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-118">**Mutual Recursion**.</span></span> <span data-ttu-id="e1fbc-119">두 프로시저가 서로를 호출 하는 경우 성능이 저하 되거나 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="e1fbc-120">이러한 디자인은 단일 재귀 프로시저와 동일한 문제를 표시 하지만 검색 하 고 디버깅 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="e1fbc-121">**괄호를 사용 하 여를 호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="e1fbc-122">`Function` 프로시저 자체를 재귀적으로 호출 하는 경우에는 인수 목록이 없는 경우에도 프로시저 이름 뒤에 괄호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="e1fbc-123">그렇지 않으면 함수 이름은 함수의 반환 값을 나타내는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="e1fbc-124">**테스트**.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-124">**Testing**.</span></span> <span data-ttu-id="e1fbc-125">재귀 프로시저를 작성 하는 경우이를 신중 하 게 테스트 하 여 항상 제한 조건을 충족 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="e1fbc-126">또한 재귀 호출이 너무 많기 때문에 메모리가 부족 하지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbc-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1fbc-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1fbc-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="e1fbc-128">절차</span><span class="sxs-lookup"><span data-stu-id="e1fbc-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="e1fbc-129">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="e1fbc-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="e1fbc-130">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="e1fbc-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="e1fbc-131">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="e1fbc-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="e1fbc-132">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="e1fbc-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="e1fbc-133">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="e1fbc-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e1fbc-134">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="e1fbc-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="e1fbc-135">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e1fbc-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="e1fbc-136">루프 구조</span><span class="sxs-lookup"><span data-stu-id="e1fbc-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
