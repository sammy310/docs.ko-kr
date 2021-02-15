---
description: '자세히 알아보기: 방법: 프로시저 만들기 (Visual Basic)'
title: '방법: 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: bca5ad24e845600642429273f6053787dd290b88
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472542"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="461d9-103">방법: 프로시저 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="461d9-103">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="461d9-104">시작 선언 문 ( `Sub` 또는 `Function` )과 끝 선언 문 ( `End Sub` 또는) 사이에 프로시저를 묶습니다 `End Function` .</span><span class="sxs-lookup"><span data-stu-id="461d9-104">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="461d9-105">프로시저의 모든 코드는 이러한 문 사이에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-105">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="461d9-106">프로시저는 다른 프로시저를 포함할 수 없으므로 시작 문과 종료 문은 다른 프로시저 외부에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-106">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="461d9-107">다른 위치에서 동일한 작업을 수행 하는 코드가 있는 경우 작업을 한 번에 한 번 작성 한 다음 코드의 다른 위치에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-107">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="461d9-108">값을 반환 하지 않는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="461d9-108">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="461d9-109">다른 프로시저 외부에서는 문을 사용 하 고 `Sub` `End Sub` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-109">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="461d9-110">`Sub`문에서 `Sub` 키워드를 프로시저 이름으로 따르고 매개 변수 목록을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-110">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="461d9-111">프로시저의 코드 문을 문과 문 사이에 `Sub` 놓습니다 `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="461d9-111">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="461d9-112">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="461d9-112">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="461d9-113">다른 프로시저 외부에서는 문을 사용 하 고 `Function` `End Function` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-113">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="461d9-114">`Function`문에서 `Function` 키워드를 프로시저 이름으로 따르고 매개 변수 목록을 괄호로 묶은 다음 `As` 반환 값의 데이터 형식을 지정 하는 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-114">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="461d9-115">프로시저의 코드 문을 문과 문 사이에 `Function` 놓습니다 `End Function` .</span><span class="sxs-lookup"><span data-stu-id="461d9-115">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="461d9-116">문을 사용 `Return` 하 여 호출 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-116">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="461d9-117">새 프로시저를 반복적인 코드 블록에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="461d9-117">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="461d9-118">이전 코드에서 액세스할 수 있는 위치에 새 프로시저를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-118">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="461d9-119">이전 반복적인 코드 블록에서 반복 작업을 수행 하는 문을 또는 프로시저를 호출 하는 단일 문으로 바꿉니다 `Sub` `Function` .</span><span class="sxs-lookup"><span data-stu-id="461d9-119">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="461d9-120">프로시저에서 `Function` 값을 반환 하는 인 경우 호출 문이 반환 된 값을 사용 하 여 작업을 변수에 저장 하는 등의 작업을 수행 해야 합니다. 그렇지 않으면 값이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-120">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="461d9-121">예</span><span class="sxs-lookup"><span data-stu-id="461d9-121">Example</span></span>

 <span data-ttu-id="461d9-122">다음 `Function` 프로시저는 다른 두 변의 값을 지정 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="461d9-122">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="461d9-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="461d9-123">See also</span></span>

- [<span data-ttu-id="461d9-124">절차</span><span class="sxs-lookup"><span data-stu-id="461d9-124">Procedures</span></span>](index.md)
- [<span data-ttu-id="461d9-125">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="461d9-125">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="461d9-126">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="461d9-126">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="461d9-127">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="461d9-127">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="461d9-128">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="461d9-128">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="461d9-129">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="461d9-129">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="461d9-130">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="461d9-130">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="461d9-131">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="461d9-131">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="461d9-132">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="461d9-132">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="461d9-133">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="461d9-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
