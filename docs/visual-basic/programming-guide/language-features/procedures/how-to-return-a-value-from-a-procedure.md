---
title: '방법: 프로시저 (Visual Basic)에서 값을 반환 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 8b53df1634d2b9971bc44c968a17db81cac3924f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665756"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="cceea-102">방법: 프로시저 (Visual Basic)에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="cceea-103">`Function` 프로시저 반환 값 호출 코드를 실행 하 여를 `Return` 문 또는 발생 하는 `Exit Function` 또는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="cceea-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="cceea-104">Return 문을 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="cceea-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="cceea-105">배치는 `Return` 문을 프로시저의 작업이 완료 되는 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="cceea-106">수행 합니다 `Return` 호출 코드로 반환 하려는 값을 생성 하는 식으로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="cceea-107">동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="cceea-108">다음 `Function` 프로시저 제일 긴 쪽 또는 정삼각형의 빗변을 계산 하 고 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="cceea-109">다음 예제에서는 일반적인 호출 `hypotenuse`, 반환 된 값을 저장 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="cceea-110">Exit 함수 또는 최종 함수를 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="cceea-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="cceea-111">하나 이상의 위치에는 `Function` 프로시저, 프로시저의 이름으로이 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="cceea-112">실행 하는 경우는 `Exit Function` 또는 `End Function` 문, Visual Basic 프로시저의 이름에 가장 최근에 할당 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="cceea-113">동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="cceea-114">하나만 사용할 수 있습니다 `End Function` 문에서 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="cceea-115">자세한 내용 및 예제에 나오는 "반환 값" [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cceea-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cceea-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="cceea-116">See also</span></span>

- [<span data-ttu-id="cceea-117">절차</span><span class="sxs-lookup"><span data-stu-id="cceea-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="cceea-118">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="cceea-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="cceea-119">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="cceea-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="cceea-120">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="cceea-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="cceea-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="cceea-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="cceea-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="cceea-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="cceea-123">Return 문</span><span class="sxs-lookup"><span data-stu-id="cceea-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="cceea-124">방법: 값을 반환 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="cceea-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="cceea-125">방법: 값을 반환 하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="cceea-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
