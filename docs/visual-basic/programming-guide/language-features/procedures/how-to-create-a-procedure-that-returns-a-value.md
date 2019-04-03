---
title: '방법: (Visual Basic) 값을 반환 하는 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 88e30caed97938501302c05830df6546a6822a48
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831256"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="a9374-102">방법: (Visual Basic) 값을 반환 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="a9374-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="a9374-103">사용할를 `Function` 프로시저를 호출 하는 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="a9374-104">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a9374-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="a9374-105">다른 프로시저 밖에 서 사용 하 여는 `Function` 문 뒤에 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="a9374-106">에 `Function` 문을 따릅니다는 `Function` 키워드 이름 절차 및 다음 매개 변수 목록 괄호를 사용 하 여.</span><span class="sxs-lookup"><span data-stu-id="a9374-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="a9374-107">괄호 다음에 `As` 절 반환된 된 값의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="a9374-108">간의 프로시저의 코드 문을 배치 합니다 `Function` 및 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="a9374-109">사용 된 `Return` 호출 코드에 값을 반환 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="a9374-110">다음 `Function` 프로시저 제일 긴 쪽 또는 다른 두 가지 측면에 대 한 값이 지정 된 오른쪽 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="a9374-111">다음 예제에서는 일반적인 호출 `hypotenuse`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a9374-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9374-112">See also</span></span>

- [<span data-ttu-id="a9374-113">절차</span><span class="sxs-lookup"><span data-stu-id="a9374-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a9374-114">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="a9374-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a9374-115">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="a9374-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a9374-116">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="a9374-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a9374-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="a9374-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a9374-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="a9374-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a9374-119">방법: 프로시저에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9374-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="a9374-120">방법: 값을 반환 하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="a9374-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
