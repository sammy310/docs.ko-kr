---
title: '방법: 프로시저 (Visual Basic) 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320394"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="5a306-102">방법: 프로시저 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="5a306-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="5a306-103">선언문의 시작 사이 프로시저를 묶습니다 (`Sub` 나 `Function`) 및 선언문의 끝 (`End Sub` 또는 `End Function`).</span><span class="sxs-lookup"><span data-stu-id="5a306-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="5a306-104">프로시저의 모든 코드가 이러한 문 사이 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="5a306-105">프로시저를 다른 프로시저 밖에 서 해당 시작 및 끝 문 이어야 하므로 다른 프로시저를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="5a306-106">여러 위치에서 동일한 작업을 수행 하는 코드를 사용 하는 경우에 절차로 한 번 작업을 작성 수 있으며 다음 코드의 다른 위치에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="5a306-107">값을 반환 하지 않는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5a306-107">To create a procedure that does not return a value</span></span>  
  
1. <span data-ttu-id="5a306-108">다른 프로시저 밖에 서 사용 하 여는 `Sub` 문 뒤에 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="5a306-109">에 `Sub` 문을 따릅니다는 `Sub` 프로시저 이름이 매개 변수 목록 괄호를 사용 하 여 키워드.</span><span class="sxs-lookup"><span data-stu-id="5a306-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="5a306-110">간의 프로시저의 코드 문을 배치 합니다 `Sub` 및 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="5a306-111">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5a306-111">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="5a306-112">다른 프로시저 밖에 서 사용 하 여는 `Function` 문 뒤에 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="5a306-113">에 `Function` 문을 수행를 `Function` 키워드와 매개 변수 목록 괄호 안의 프로시저의 이름 차례로 `As` 반환 값의 데이터 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5a306-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3. <span data-ttu-id="5a306-114">간의 프로시저의 코드 문을 배치 합니다 `Function` 및 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4. <span data-ttu-id="5a306-115">사용 된 `Return` 호출 코드에 값을 반환 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="5a306-116">오래 되 고 반복적인 코드 블록을 사용 하 여 새 프로시저를 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="5a306-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1. <span data-ttu-id="5a306-117">이전 코드에 액세스할 수 있는 위치에 새 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2. <span data-ttu-id="5a306-118">이전 반복 코드 블록을 호출 하는 단일 문 사용 하 여 반복적인 작업을 수행 하는 문을 바꿉니다 합니다 `Sub` 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3. <span data-ttu-id="5a306-119">프로시저가 `Function` 값을 반환 하는 호출 문에서 반환된 된 값을 변수에 저장 하는 등을 사용 하 여 작업을 수행 합니다. 그러지 않으면 값이 손실 됩니다을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a306-120">예제</span><span class="sxs-lookup"><span data-stu-id="5a306-120">Example</span></span>  
 <span data-ttu-id="5a306-121">다음 `Function` 프로시저 제일 긴 쪽 또는 다른 두 가지 측면에 대 한 값이 지정 된 오른쪽 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a306-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5a306-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a306-122">See also</span></span>

- [<span data-ttu-id="5a306-123">절차</span><span class="sxs-lookup"><span data-stu-id="5a306-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5a306-124">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a306-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="5a306-125">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a306-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="5a306-126">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a306-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="5a306-127">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a306-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="5a306-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="5a306-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5a306-129">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="5a306-129">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="5a306-130">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="5a306-130">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="5a306-131">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="5a306-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="5a306-132">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a306-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
