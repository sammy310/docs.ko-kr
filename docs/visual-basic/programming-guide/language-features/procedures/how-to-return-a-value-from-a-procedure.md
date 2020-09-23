---
title: '방법: 프로시저에서 값 반환'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: cbc785a07aa8a7b299508a093e08d5d0510b838a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071380"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="71042-102">방법: 프로시저에서 값 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71042-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>

<span data-ttu-id="71042-103">`Function`프로시저는 `Return` 문을 실행 하거나 `Exit Function` 또는 문을 실행 하 여 호출 코드에 값을 반환 합니다 `End Function` .</span><span class="sxs-lookup"><span data-stu-id="71042-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="71042-104">Return 문을 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="71042-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="71042-105">`Return`프로시저 태스크가 완료 된 지점에 문을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="71042-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="71042-106">`Return`호출 코드에 반환 하려는 값을 생성 하는 식을 사용 하 여 키워드를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="71042-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="71042-107">동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71042-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="71042-108">다음 `Function` 프로시저는 오른쪽 삼각형의 가장 긴 변 또는 빗변을 계산 하 고 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71042-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="71042-109">다음 예제에서는 반환 된 값을 저장 하는에 대 한 일반적인 호출을 보여 줍니다 `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="71042-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="71042-110">Exit Function 또는 End 함수를 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="71042-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="71042-111">프로시저의 하나 이상의 위치에서 `Function` 프로시저의 이름에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="71042-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="71042-112">또는 문을 실행할 때 `Exit Function` `End Function` Visual Basic은 프로시저 이름에 가장 최근에 할당 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71042-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="71042-113">동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71042-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="71042-114">`End Function`프로시저에는 문을 하나만 사용할 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="71042-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="71042-115">자세한 내용 및 예제는 [함수 문의](../../../language-reference/statements/function-statement.md)"Return Value"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71042-115">For more information and an example, see "Return Value" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71042-116">참조</span><span class="sxs-lookup"><span data-stu-id="71042-116">See also</span></span>

- [<span data-ttu-id="71042-117">절차</span><span class="sxs-lookup"><span data-stu-id="71042-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="71042-118">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="71042-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="71042-119">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="71042-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="71042-120">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="71042-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="71042-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="71042-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="71042-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="71042-122">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="71042-123">Return 문</span><span class="sxs-lookup"><span data-stu-id="71042-123">Return Statement</span></span>](../../../language-reference/statements/return-statement.md)
- [<span data-ttu-id="71042-124">방법: 값을 반환하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="71042-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="71042-125">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="71042-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
