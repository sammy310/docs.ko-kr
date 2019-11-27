---
title: '방법: 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344903"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="65b42-102">방법: 프로시저 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65b42-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="65b42-103">시작 선언 문 (`Sub` 또는 `Function`)과 끝 선언 문 (`End Sub` 또는 `End Function`) 사이에 프로시저를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="65b42-104">프로시저의 모든 코드는 이러한 문 사이에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="65b42-105">프로시저는 다른 프로시저를 포함할 수 없으므로 시작 문과 종료 문은 다른 프로시저 외부에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="65b42-106">다른 위치에서 동일한 작업을 수행 하는 코드가 있는 경우 작업을 한 번에 한 번 작성 한 다음 코드의 다른 위치에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="65b42-107">값을 반환 하지 않는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="65b42-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="65b42-108">다른 프로시저 외부에서 `Sub` 문을 사용 하 고 그 뒤에 `End Sub` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="65b42-109">`Sub` 문에서 `Sub` 키워드를 프로시저의 이름과 괄호로 묶은 매개 변수 목록을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="65b42-110">프로시저의 코드 문을 `Sub` 문과 `End Sub` 문 사이에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="65b42-111">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="65b42-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="65b42-112">다른 프로시저 외부에서 `Function` 문을 사용 하 고 그 뒤에 `End Function` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="65b42-113">`Function` 문에서 `Function` 키워드를 프로시저 이름과 함께 사용 하 고 매개 변수 목록을 괄호로 묶은 다음 반환 값의 데이터 형식을 지정 하는 `As` 절을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="65b42-114">프로시저의 코드 문을 `Function` 문과 `End Function` 문 사이에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="65b42-115">`Return` 문을 사용 하 여 호출 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="65b42-116">새 프로시저를 반복적인 코드 블록에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="65b42-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="65b42-117">이전 코드에서 액세스할 수 있는 위치에 새 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="65b42-118">반복 된 이전 코드 블록에서 반복 작업을 수행 하는 문을 `Sub` 또는 `Function` 프로시저를 호출 하는 단일 문으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="65b42-119">프로시저가 값을 반환 하는 `Function` 경우 호출 문이 반환 된 값을 사용 하 여 작업을 수행 해야 합니다 (예: 변수에 저장 하는 경우). 그렇지 않으면 값이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="65b42-120">예제</span><span class="sxs-lookup"><span data-stu-id="65b42-120">Example</span></span>

 <span data-ttu-id="65b42-121">다음 `Function` 프로시저는 다른 두 변의 값을 고려 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b42-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="65b42-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65b42-122">See also</span></span>

- [<span data-ttu-id="65b42-123">절차</span><span class="sxs-lookup"><span data-stu-id="65b42-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="65b42-124">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="65b42-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="65b42-125">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="65b42-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="65b42-126">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="65b42-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="65b42-127">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="65b42-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="65b42-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="65b42-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="65b42-129">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="65b42-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="65b42-130">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="65b42-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="65b42-131">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="65b42-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="65b42-132">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65b42-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
