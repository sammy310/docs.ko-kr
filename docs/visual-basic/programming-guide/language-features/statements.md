---
title: 문
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: 09fe53f4bc2b6d025b762c6595c5337263456bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401981"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="019c2-102">Visual Basic의 문</span><span class="sxs-lookup"><span data-stu-id="019c2-102">Statements in Visual Basic</span></span>

<span data-ttu-id="019c2-103">Visual Basic 문은 전체 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="019c2-104">키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="019c2-105">각 문은 다음 범주 중 하나에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="019c2-106">변수, 상수 또는 프로시저의 이름을 지정 하는 **선언문**을 지정 하 고 데이터 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="019c2-107">작업을 시작 하는 **실행 가능한 문**</span><span class="sxs-lookup"><span data-stu-id="019c2-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="019c2-108">이러한 문은 메서드나 함수를 호출할 수 있으며 코드 블록을 통해 루프 또는 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="019c2-109">실행 문에는 변수나 상수에 값 또는 식을 할당 하는 **대입문**이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="019c2-110">이 항목에서는 각 범주에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-110">This topic describes each category.</span></span> <span data-ttu-id="019c2-111">또한이 항목에서는 여러 문을 한 줄에 결합 하는 방법과 문을 여러 줄로 계속 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="019c2-112">선언문</span><span class="sxs-lookup"><span data-stu-id="019c2-112">Declaration statements</span></span>

<span data-ttu-id="019c2-113">선언 문을 사용 하 여 프로시저, 변수, 속성, 배열 및 상수를 이름 지정 하 고 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="019c2-114">프로그래밍 요소를 선언 하는 경우 해당 데이터 형식, 액세스 수준 및 범위를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="019c2-115">자세한 내용은 [선언 된 요소 특성](./declared-elements/declared-element-characteristics.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="019c2-116">다음 예제에는 세 개의 선언이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="019c2-117">첫 번째 선언은 `Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="019c2-118">일치 하는 `End Sub` 문과 함께 이라는 프로시저를 선언 `applyFormat` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="019c2-119">또한 `applyFormat` 이 `Public` 를 참조 하는 모든 코드가이를 호출할 수 있음을 의미 하는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="019c2-120">두 번째 선언은 `Const` `limit` `Integer` 데이터 형식 및 값 33를 지정 하 여 상수를 선언 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="019c2-121">세 번째 선언은 변수를 `Dim` 선언 하는 문입니다 `thisWidget` .</span><span class="sxs-lookup"><span data-stu-id="019c2-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="019c2-122">데이터 형식은 특정 개체, 즉 클래스에서 만든 개체입니다 `Widget` .</span><span class="sxs-lookup"><span data-stu-id="019c2-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="019c2-123">변수를 기본 데이터 형식이 나 사용 중인 응용 프로그램에 노출 되는 모든 개체 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="019c2-124">초기 값</span><span class="sxs-lookup"><span data-stu-id="019c2-124">Initial Values</span></span>

<span data-ttu-id="019c2-125">선언 문을 포함 하는 코드를 실행 하면 Visual Basic는 선언 된 요소에 필요한 메모리를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="019c2-126">요소가 값을 포함 하는 경우에는 Visual Basic 해당 데이터 형식에 대 한 기본값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="019c2-127">자세한 내용은 [Dim 문의](../../language-reference/statements/dim-statement.md)"Behavior"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="019c2-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="019c2-128">다음 예제와 같이 변수의 초기 값을 선언의 일부로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="019c2-129">변수가 개체 변수인 경우에는 다음 예제와 같이 [New Operator](../../language-reference/operators/new-operator.md) 키워드를 사용 하 여 선언할 때 해당 클래스의 인스턴스를 명시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="019c2-130">선언 문에 지정 하는 초기 값은 실행이 해당 선언문에 도달할 때까지 변수에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="019c2-131">이 시간까지 변수는 해당 데이터 형식에 대 한 기본값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="019c2-132">실행 문</span><span class="sxs-lookup"><span data-stu-id="019c2-132">Executable statements</span></span>

<span data-ttu-id="019c2-133">실행 문은 동작을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-133">An executable statement performs an action.</span></span> <span data-ttu-id="019c2-134">프로시저를 호출 하 고, 코드의 다른 위치로 분기 하거나, 여러 문을 반복 하거나, 식을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="019c2-135">대입문은 실행 가능한 문의 특수 한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="019c2-136">다음 예제에서는 컨트롤 구조를 사용 하 여 `If...Then...Else` 변수 값을 기반으로 여러 코드 블록을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="019c2-137">각 코드 블록 내에서 루프는 `For...Next` 지정 된 횟수 만큼 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="019c2-138">`If`위의 예에 있는 문은 매개 변수의 값을 확인 합니다 `clockwise` .</span><span class="sxs-lookup"><span data-stu-id="019c2-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="019c2-139">값이 이면는 `True` 의 메서드를 호출 합니다 `spinClockwise` `aWidget` .</span><span class="sxs-lookup"><span data-stu-id="019c2-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="019c2-140">값이 이면는 `False` 의 메서드를 호출 합니다 `spinCounterClockwise` `aWidget` .</span><span class="sxs-lookup"><span data-stu-id="019c2-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="019c2-141">`If...Then...Else`컨트롤 구조는로 끝납니다 `End If` .</span><span class="sxs-lookup"><span data-stu-id="019c2-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="019c2-142">`For...Next`각 블록 내의 루프는 매개 변수의 값과 같은 횟수 만큼 적절 한 메서드를 호출 합니다 `revolutions` .</span><span class="sxs-lookup"><span data-stu-id="019c2-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="019c2-143">대입문</span><span class="sxs-lookup"><span data-stu-id="019c2-143">Assignment statements</span></span>

<span data-ttu-id="019c2-144">대입문은 다음 예제와 같이 대입 연산자의 오른쪽에 있는 값 ()을 가져와 왼쪽의 요소에 저장 하는 것으로 구성 된 할당 작업을 수행 `=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="019c2-145">위의 예에서 대입문은 변수에 리터럴 값 42를 저장 합니다 `v` .</span><span class="sxs-lookup"><span data-stu-id="019c2-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="019c2-146">적합 한 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="019c2-146">Eligible programming elements</span></span>

<span data-ttu-id="019c2-147">할당 연산자의 좌 변에 있는 프로그래밍 요소는 값을 허용 하 고 저장할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="019c2-148">즉, [ReadOnly](../../language-reference/modifiers/readonly.md)이거나 배열 요소 여야 하는 변수 또는 속성 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-148">This means it must be a variable or property that is not [ReadOnly](../../language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="019c2-149">대입문의 컨텍스트에서 "left value"의 경우 이러한 요소를 *lvalue*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="019c2-150">대입 연산자의 오른쪽에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소, 기타 식 또는 함수 호출의 조합으로 구성 될 수 있는 식에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="019c2-151">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="019c2-152">앞의 예제에서는 변수에 저장 된 값을 `y` 변수에 저장 된 값에 추가 하 `z` 고 함수에 대 한 호출에서 반환 된 값을 추가 합니다 `findResult` .</span><span class="sxs-lookup"><span data-stu-id="019c2-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="019c2-153">그런 다음이 식의 합계 값이 변수에 저장 됩니다 `x` .</span><span class="sxs-lookup"><span data-stu-id="019c2-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="019c2-154">대입문의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="019c2-154">Data types in assignment statements</span></span>

<span data-ttu-id="019c2-155">다음 예제와 같이 숫자 값 외에도 할당 연산자는 `String` 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="019c2-156">`Boolean` `Boolean` `Boolean` 다음 예제에 나와 있는 것 처럼 리터럴 또는 식을 사용 하 여 값을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="019c2-157">마찬가지로 `Char` , `Date` 또는 데이터 형식의 프로그래밍 요소에 적절 한 값을 할당할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="019c2-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="019c2-158">또한 해당 인스턴스가 생성 된 클래스로 선언 된 요소에 개체 인스턴스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="019c2-159">복합 대입문</span><span class="sxs-lookup"><span data-stu-id="019c2-159">Compound assignment statements</span></span>

<span data-ttu-id="019c2-160">*복합 대입문* 은 먼저 식에 대해 작업을 수행한 다음 프로그래밍 요소에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="019c2-161">다음 예에서는 `+=` 연산자의 좌 변에 있는 변수의 값을 오른쪽에 있는 식의 값으로 증가 시키는 이러한 연산자 중 하나를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="019c2-162">앞의 예제에서는의 값에 1을 추가한 `n` 다음 새 값을에 저장 `n` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="019c2-163">이는 다음 문과 동일한 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="019c2-164">이 형식의 연산자를 사용 하 여 다양 한 복합 할당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="019c2-165">이러한 연산자의 목록과 이러한 연산자에 대 한 자세한 내용은 [할당 연산자](../../language-reference/operators/assignment-operators.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-165">For a list of these operators and more information about them, see [Assignment Operators](../../language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="019c2-166">연결 할당 연산자 ( `&=` )는 다음 예제에 나와 있는 것 처럼 기존 문자열의 끝에 문자열을 추가 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="019c2-167">대입문의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="019c2-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="019c2-168">변수, 속성 또는 배열 요소에 할당 하는 값은 해당 대상 요소에 적합 한 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="019c2-169">일반적으로 대상 요소와 동일한 데이터 형식의 값을 생성 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="019c2-170">그러나 할당 하는 동안 일부 형식을 다른 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="019c2-171">데이터 형식 간의 변환에 대 한 자세한 내용은 [Visual Basic 형식 변환](./data-types/type-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="019c2-172">간단히 말해서 Visual Basic는 지정 된 형식의 값을 자동으로 확대 되는 다른 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="019c2-173">*확대 변환은* 항상 런타임에 성공 하 고 데이터를 손실 하지 않는의 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="019c2-174">예를 들어 Visual Basic는 `Integer` `Double` 로 확대 되기 때문에 적절 한 경우 값을로 변환 `Integer` `Double` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="019c2-175">자세한 내용은 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="019c2-176">*축소 변환* (확대 되지 않은 변환)은 런타임에 오류가 발생 하거나 데이터 손실이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="019c2-177">형식 변환 함수를 사용 하 여 명시적으로 축소 변환을 수행 하거나를 설정 하 여 모든 변환을 암시적으로 수행 하도록 컴파일러에 지시할 수 있습니다 `Option Strict Off` .</span><span class="sxs-lookup"><span data-stu-id="019c2-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="019c2-178">자세한 내용은 [암시적 변환과 명시적 변환](./data-types/implicit-and-explicit-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="019c2-179">여러 문을 한 줄에 배치</span><span class="sxs-lookup"><span data-stu-id="019c2-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="019c2-180">한 줄에 콜론 () 문자로 구분 된 문이 여러 개 있을 수 있습니다 `:` .</span><span class="sxs-lookup"><span data-stu-id="019c2-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="019c2-181">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="019c2-182">이러한 형태의 구문을 사용 하면 코드를 읽고 유지 관리 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="019c2-183">따라서 문을 한 줄에 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="019c2-184">문을 여러 줄에 걸쳐 계속</span><span class="sxs-lookup"><span data-stu-id="019c2-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="019c2-185">문은 일반적으로 한 줄에 배치 되지만 너무 길면 줄 연속 시퀀스를 사용 하 여 다음 줄로 계속 진행할 수 있습니다 .이 시퀀스는 공백 뒤에 밑줄 문자 ()와 캐리지 리턴이 차례로 오는 줄 연속 시퀀스를 사용 합니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="019c2-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="019c2-186">다음 예에서는 `MsgBox` 실행 가능한 문이 두 줄에 걸쳐 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="019c2-187">암시적 줄 연속</span><span class="sxs-lookup"><span data-stu-id="019c2-187">Implicit line continuation</span></span>

<span data-ttu-id="019c2-188">대부분의 경우 밑줄 문자 ()를 사용 하지 않고 다음 연속 줄에서 문을 계속할 수 있습니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="019c2-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="019c2-189">다음 구문 요소는 코드의 다음 줄에서 문을 암시적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="019c2-190">쉼표 () 뒤 `,` .</span><span class="sxs-lookup"><span data-stu-id="019c2-190">After a comma (`,`).</span></span> <span data-ttu-id="019c2-191">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="019c2-192">여는 괄호 ( `(` ) 또는 닫는 괄호 () 앞에 `)` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="019c2-193">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="019c2-194">여는 중괄호 ( `{` ) 또는 닫는 중괄호 () 앞에 `}` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="019c2-195">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="019c2-196">자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 [컬렉션 이니셜라이저](./collection-initializers/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="019c2-197">XML 리터럴 내에서 포함 된 식 ( `<%=` ) 또는 포함 된 식 ()이 가까이 있는 경우 `%>`</span><span class="sxs-lookup"><span data-stu-id="019c2-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="019c2-198">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="019c2-199">자세한 내용은 [XML의 포함 식](./xml/embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="019c2-200">연결 연산자 () 다음에 `&`</span><span class="sxs-lookup"><span data-stu-id="019c2-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="019c2-201">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="019c2-202">자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-202">For more information, see [Operators Listed by Functionality](../../language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="019c2-203">할당 연산자 (,,,,,,,,, `=` `&=` ,)를 지정 `:=` `+=` `-=` `*=` `/=` `\=` `^=` `<<=` `>>=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="019c2-204">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="019c2-205">자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-205">For more information, see [Operators Listed by Functionality](../../language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="019c2-206">식 내에서 이항 연산자 (,,,,,,,,,,,,,,,,,, `+` `-` `/` `*` `Mod` `<>` `<` `>` `<=` `>=` )가 `^` `>>` `<<` `And` `AndAlso` `Or` `OrElse` `Like` `Xor` 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="019c2-207">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="019c2-208">자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-208">For more information, see [Operators Listed by Functionality](../../language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="019c2-209">`Is`및 연산자 뒤 `IsNot`</span><span class="sxs-lookup"><span data-stu-id="019c2-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="019c2-210">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="019c2-211">자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-211">For more information, see [Operators Listed by Functionality](../../language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="019c2-212">멤버 한정자 문자 ( `.` )와 멤버 이름 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="019c2-213">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="019c2-214">그러나 `_` `With` 문을 사용 하거나 형식에 대 한 초기화 목록에 값을 제공 하는 경우 멤버 한정자 문자 뒤에 줄 연속 문자 ()를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="019c2-215">`=`문이나 개체 초기화 목록을 사용 하는 경우 할당 연산자 (예:) 뒤의 줄을 분리 하는 것이 좋습니다 `With` .</span><span class="sxs-lookup"><span data-stu-id="019c2-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="019c2-216">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="019c2-217">자세한 내용은 다음 [을 참조 하세요. 문](../../language-reference/statements/with-end-with-statement.md) 또는 [개체 이니셜라이저가 있는 End: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-217">For more information, see [With...End With Statement](../../language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="019c2-218">XML 축 속성 한정자 ( `.` 또는 `.@` 또는 `...` ) 뒤</span><span class="sxs-lookup"><span data-stu-id="019c2-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="019c2-219">그러나 `_` 키워드를 사용할 때 멤버 한정자를 지정 하는 경우에는 줄 연속 문자 ()를 포함 해야 합니다 `With` .</span><span class="sxs-lookup"><span data-stu-id="019c2-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="019c2-220">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="019c2-221">자세한 내용은 [XML 축 속성](../../language-reference/xml-axis/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-221">For more information, see [XML Axis Properties](../../language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="019c2-222">특성을 지정할 때 보다 작음 기호 (<) 또는 보다 큼 부호 () 앞에 `>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="019c2-223">또한 특성을 지정할 때 보다 큼 기호 () 뒤에 `>` .</span><span class="sxs-lookup"><span data-stu-id="019c2-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="019c2-224">그러나 `_` 어셈블리 수준 또는 모듈 수준 특성을 지정 하는 경우에는 줄 연속 문자 ()를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="019c2-225">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="019c2-226">자세한 내용은 [특성 개요](../concepts/attributes/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-226">For more information, see [Attributes overview](../concepts/attributes/index.md).</span></span>

- <span data-ttu-id="019c2-227">Before 및 after 쿼리 연산자 (,,,,,,,,,,,,,,,,,, `Aggregate` `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending` )</span><span class="sxs-lookup"><span data-stu-id="019c2-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="019c2-228">여러 키워드 ( `Order By` ,, `Group Join` `Take While` 및)로 구성 된 쿼리 연산자의 키워드 사이에 줄을 나눌 수 없습니다 `Skip While` .</span><span class="sxs-lookup"><span data-stu-id="019c2-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="019c2-229">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="019c2-230">자세한 내용은 [쿼리](../../language-reference/queries/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-230">For more information, see [Queries](../../language-reference/queries/index.md).</span></span>

- <span data-ttu-id="019c2-231">`In`문의 키워드 뒤에 `For Each` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="019c2-232">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="019c2-233">자세한 내용은 For Each ...를 참조 하십시오. [ 다음 문](../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="019c2-233">For more information, see [For Each...Next Statement](../../language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="019c2-234">`From`컬렉션 이니셜라이저의 키워드 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="019c2-235">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="019c2-236">자세한 내용은 [컬렉션 이니셜라이저](collection-initializers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="019c2-236">For more information, see [Collection Initializers](collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="019c2-237">주석 추가</span><span class="sxs-lookup"><span data-stu-id="019c2-237">Adding comments</span></span>

<span data-ttu-id="019c2-238">소스 코드는 코드를 작성 하는 프로그래머에 게는 항상 설명이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="019c2-239">따라서 대부분의 프로그래머는 코드를 문서화할 수 있도록 포함 된 주석을 자유롭게 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="019c2-240">코드의 주석은 나중에 읽거나 작업 하는 모든 사용자에 게 프로시저 또는 특정 지침을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="019c2-241">컴파일하는 동안 Visual Basic는 주석을 무시 하 고 컴파일된 코드에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="019c2-242">주석 줄은 아포스트로피 ()로 시작 `'` 하거나 `REM` 뒤에 공백이 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="019c2-243">문자열 내에서를 제외 하 고 코드의 모든 위치에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="019c2-244">문에 주석을 추가 하려면 아포스트로피 또는 `REM` 문 뒤에 주석을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="019c2-245">주석은 별도의 줄로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="019c2-246">다음 예제에서는 이러한 가능성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="019c2-247">컴파일 오류 확인</span><span class="sxs-lookup"><span data-stu-id="019c2-247">Checking compilation errors</span></span>

<span data-ttu-id="019c2-248">코드 줄을 입력 한 후 물결선이 파란색 물결선으로 표시 되 면 (오류 메시지가 표시 될 수 있음) 문에 구문 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="019c2-249">문에 무엇이 잘못 되었는지 확인 해야 합니다 (작업 목록에서 확인 하거나 마우스 포인터로 오류를 가리키고 오류 메시지를 읽은 후).</span><span class="sxs-lookup"><span data-stu-id="019c2-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="019c2-250">코드의 모든 구문 오류를 해결할 때까지 프로그램을 올바르게 컴파일하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="019c2-251">관련 단원</span><span class="sxs-lookup"><span data-stu-id="019c2-251">Related sections</span></span>

|<span data-ttu-id="019c2-252">용어</span><span class="sxs-lookup"><span data-stu-id="019c2-252">Term</span></span>|<span data-ttu-id="019c2-253">정의</span><span class="sxs-lookup"><span data-stu-id="019c2-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="019c2-254">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="019c2-254">Assignment Operators</span></span>](../../language-reference/operators/assignment-operators.md)|<span data-ttu-id="019c2-255">, 및와 같은 할당 연산자를 다루는 언어 참조 페이지에 대 한 링크를 제공 `=` `*=` `&=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="019c2-256">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="019c2-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="019c2-257">요소와 연산자를 결합 하 여 새 값을 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="019c2-258">방법: 코드에서 명령문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="019c2-258">How to: Break and Combine Statements in Code</span></span>](../program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="019c2-259">단일 문을 여러 줄로 나누고 여러 문을 같은 줄에 넣는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="019c2-260">방법: Label 문</span><span class="sxs-lookup"><span data-stu-id="019c2-260">How to: Label Statements</span></span>](../program-structure/how-to-label-statements.md)|<span data-ttu-id="019c2-261">코드 줄에 레이블을 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="019c2-261">Shows how to label a line of code.</span></span>|
