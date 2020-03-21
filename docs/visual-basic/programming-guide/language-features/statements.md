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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401468"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="9260a-102">Visual Basic의 문</span><span class="sxs-lookup"><span data-stu-id="9260a-102">Statements in Visual Basic</span></span>

<span data-ttu-id="9260a-103">Visual Basic의 문은 완전한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="9260a-104">키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="9260a-105">각 문은 다음 범주 중 하나에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="9260a-106">**Declaration Statements**변수, 상수 또는 프로시저의 이름을 지정하고 데이터 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="9260a-107">작업을 시작하는 **실행 문입니다.**</span><span class="sxs-lookup"><span data-stu-id="9260a-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="9260a-108">이러한 문은 메서드 또는 함수를 호출할 수 있으며 코드 블록을 통해 루프 또는 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="9260a-109">실행 가능한 문에는 변수 또는 상수에 값 또는 식을 할당하는 **할당 문이**포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="9260a-110">이 항목에서는 각 범주에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-110">This topic describes each category.</span></span> <span data-ttu-id="9260a-111">또한 이 항목에서는 한 줄에 여러 문을 결합하는 방법과 여러 줄을 통해 문을 계속 하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="9260a-112">선언문</span><span class="sxs-lookup"><span data-stu-id="9260a-112">Declaration statements</span></span>

<span data-ttu-id="9260a-113">선언 문을 사용하여 프로시저, 변수, 속성, 배열 및 상수의 이름을 지정하고 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="9260a-114">프로그래밍 요소를 선언할 때 해당 데이터 형식, 액세스 수준 및 범위를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="9260a-115">자세한 내용은 [선언된 요소 특성](./declared-elements/declared-element-characteristics.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="9260a-116">다음 예제에는 세 개의 선언이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="9260a-117">첫 번째 선언은 명령문입니다. `Sub`</span><span class="sxs-lookup"><span data-stu-id="9260a-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="9260a-118">일치 `End Sub` 하는 문과 함께 `applyFormat`라는 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="9260a-119">또한 참조할 수 `applyFormat` `Public`있는 모든 코드가 호출할 수 있음을 의미하는 것을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="9260a-120">두 번째 선언은 `Const` `limit` `Integer` 데이터 형식과 값 33을 지정하는 상수를 선언하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="9260a-121">세 번째 선언은 변수를 `Dim` `thisWidget`선언하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="9260a-122">데이터 형식은 특정 개체, 즉 클래스에서 `Widget` 만든 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="9260a-123">변수를 기본 데이터 형식또는 사용 중인 응용 프로그램에서 노출되는 개체 형식의 변수로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="9260a-124">초기 값</span><span class="sxs-lookup"><span data-stu-id="9260a-124">Initial Values</span></span>

<span data-ttu-id="9260a-125">선언 문을 포함하는 코드가 실행되면 Visual Basic은 선언된 요소에 필요한 메모리를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="9260a-126">요소에 값이 있는 경우 Visual Basic은 해당 데이터 형식의 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="9260a-127">자세한 내용은 [Dim 명령문의](../../language-reference/statements/dim-statement.md)"동작"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="9260a-128">다음 예제에서 와 같이 선언의 일부로 변수에 초기 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="9260a-129">변수가 개체 변수인 경우 다음 예제에서 와 같이 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 사용하여 선언할 때 해당 클래스의 인스턴스를 명시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="9260a-130">선언 문에 지정 한 초기 값실행선언문에 도달할 때까지 변수에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="9260a-131">이 때까지 변수에는 데이터 형식에 대한 기본값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="9260a-132">실행 문</span><span class="sxs-lookup"><span data-stu-id="9260a-132">Executable statements</span></span>

<span data-ttu-id="9260a-133">실행 문이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-133">An executable statement performs an action.</span></span> <span data-ttu-id="9260a-134">프로시저를 호출하거나 코드의 다른 위치에 분기하거나 여러 문을 반복하거나 식을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="9260a-135">할당 문은 실행 문특수의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="9260a-136">다음 예제에서는 `If...Then...Else` 컨트롤 구조를 사용하여 변수 값을 기반으로 다양한 코드 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="9260a-137">각 코드 블록 내에서 `For...Next` 루프는 지정된 횟수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="9260a-138">앞의 예제에서 `If` 문은 매개 변수의 `clockwise`값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="9260a-139">값이 `True`있는 경우 의 `spinClockwise` 메서드를 `aWidget`호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="9260a-140">값이 `False`있는 경우 의 `spinCounterClockwise` 메서드를 `aWidget`호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="9260a-141">제어 `If...Then...Else` 구조는 `End If`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="9260a-142">각 `For...Next` 블록 내의 루프는 `revolutions` 적절한 메서드를 매개 변수 값과 동일한 횟수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="9260a-143">대입문</span><span class="sxs-lookup"><span data-stu-id="9260a-143">Assignment statements</span></span>

<span data-ttu-id="9260a-144">할당 문은 다음 예제와 같이 할당 연산자()의`=`오른쪽에 있는 값을 가져 와서 왼쪽의 요소에 저장하는 할당 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="9260a-145">앞의 예제에서 할당 문은 변수에 `v`리터럴 값 42를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="9260a-146">적격 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="9260a-146">Eligible programming elements</span></span>

<span data-ttu-id="9260a-147">할당 연산자의 왼쪽에 있는 프로그래밍 요소는 값을 수락하고 저장할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="9260a-148">즉, [ReadOnly가](../../../visual-basic/language-reference/modifiers/readonly.md)아닌 변수 또는 속성이거나 배열 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="9260a-149">할당 문의 컨텍스트에서 이러한 요소를 "왼쪽 값"에 대해 *lvalue라고도*합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="9260a-150">할당 연산자의 오른쪽에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소, 기타 식 또는 함수 호출의 조합으로 구성될 수 있는 식에 의해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="9260a-151">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="9260a-152">앞의 예제에서는 변수에 보유된 값을 `y` 변수에 `z`보유한 값에 추가한 다음 함수 `findResult`호출에서 반환된 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="9260a-153">이 식의 총 값은 변수에 `x`저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="9260a-154">할당 문의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9260a-154">Data types in assignment statements</span></span>

<span data-ttu-id="9260a-155">할당 연산자는 숫자 값 외에도 다음 `String` 예제에서 설명하는 것처럼 값을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="9260a-156">다음 예제에서 `Boolean` 와 같이 리터럴 또는 `Boolean` 식을 `Boolean` 사용하여 값을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="9260a-157">`Char`마찬가지로, 에 `Date`대한 정보 또는 `Object` 데이터 형식의 프로그래밍 요소에 적절한 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="9260a-158">해당 인스턴스가 생성되는 클래스로 선언된 요소에 개체 인스턴스를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="9260a-159">복합 할당 문</span><span class="sxs-lookup"><span data-stu-id="9260a-159">Compound assignment statements</span></span>

<span data-ttu-id="9260a-160">*복합 할당 문은* 먼저 식에 대한 작업을 수행한 후 프로그래밍 요소에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="9260a-161">다음 예제에서는 이러한 연산자 `+=`중 하나를 보여 주며, 이 연산자의 왼쪽에 있는 변수 값을 오른쪽의 식 값으로 증분합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="9260a-162">앞의 예제에서는 `n`의 값에 1을 추가한 다음 `n`해당 새 값을 에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="9260a-163">다음 명령문과 동일한 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="9260a-164">이 유형의 연산자를 사용하여 다양한 복합 할당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="9260a-165">이러한 연산자 목록과 해당 연산자에 대한 자세한 내용은 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="9260a-166">연결 할당 연산자`&=`() 는 다음 예제에서 와 같이 이미 기존 문자열의 끝에 문자열을 추가하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="9260a-167">할당 명세서에서 변환 유형</span><span class="sxs-lookup"><span data-stu-id="9260a-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="9260a-168">변수, 속성 또는 배열 요소에 할당하는 값은 해당 대상 요소에 적합한 데이터 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="9260a-169">일반적으로 대상 요소와 동일한 데이터 형식의 값을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="9260a-170">그러나 일부 형식은 할당 하는 동안 다른 유형으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="9260a-171">데이터 형식 간의 변환에 대한 자세한 내용은 [Visual Basic의 변환 유형을](./data-types/type-conversions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="9260a-172">간단히 말해서 Visual Basic은 지정된 형식의 값을 확대되는 다른 유형으로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="9260a-173">*확대 변환은* 항상 런타임에 성공하고 데이터를 잃지 않는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="9260a-174">예를 들어 Visual Basic은 `Integer` 값을 `Double` 로 확장하기 `Integer` 때문에 `Double`적절한 경우 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="9260a-175">자세한 내용은 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9260a-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="9260a-176">*축소* 변환(확장되지 않은 전환)은 런타임에 실패하거나 데이터 손실이 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="9260a-177">형식 변환 함수를 사용하여 명시적으로 축소 변환을 수행하거나 컴파일러를 설정하여 `Option Strict Off`암시적으로 모든 변환을 수행하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="9260a-178">자세한 내용은 [암시적 및 명시적 변환을](./data-types/implicit-and-explicit-conversions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="9260a-179">한 줄에 여러 명령문 배치</span><span class="sxs-lookup"><span data-stu-id="9260a-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="9260a-180">콜론 ()`:`문자로 구분 된 한 줄에 여러 문을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="9260a-181">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="9260a-182">때때로 편리하지만 이러한 형태의 구문은 코드를 읽고 유지 관리하기 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="9260a-183">따라서 한 문을 한 줄에 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="9260a-184">여러 줄에 걸쳐 문 계속</span><span class="sxs-lookup"><span data-stu-id="9260a-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="9260a-185">문은 일반적으로 한 줄에 맞지만 너무 길면 밑줄 문자 ()`_`뒤에 캐리지 반환이 뒤따르는 공백으로 구성된 줄 연속 시퀀스를 사용하여 다음 줄로 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="9260a-186">다음 예제에서는 `MsgBox` 실행 문이 두 줄로 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="9260a-187">암시적 줄 연속</span><span class="sxs-lookup"><span data-stu-id="9260a-187">Implicit line continuation</span></span>

<span data-ttu-id="9260a-188">대부분의 경우 밑줄 문자()를`_`사용하지 않고 다음 연속 줄에 문을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="9260a-189">다음 구문 요소는 다음 코드 줄에서 문을 암시적으로 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="9260a-190">쉼표 후`,`().</span><span class="sxs-lookup"><span data-stu-id="9260a-190">After a comma (`,`).</span></span> <span data-ttu-id="9260a-191">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="9260a-192">열린 괄호 후 ()`(`또는 닫는 괄호`)`전 ().</span><span class="sxs-lookup"><span data-stu-id="9260a-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="9260a-193">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="9260a-194">열린 곱슬 버팀대`{`후 () 또는 닫기 곱슬 대괄호 ()`}`전에.</span><span class="sxs-lookup"><span data-stu-id="9260a-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="9260a-195">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="9260a-196">자세한 내용은 [개체 초기화자: 명명된 및 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 컬렉션 [초기화 자를 참조하십시오.](./collection-initializers/index.md)</span><span class="sxs-lookup"><span data-stu-id="9260a-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="9260a-197">열린 임베디드`<%=`식 () 후 ()`%>`또는 XML 리터럴 내에서 임베디드 식 ()의 닫기 전에.</span><span class="sxs-lookup"><span data-stu-id="9260a-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="9260a-198">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="9260a-199">자세한 내용은 [XML의 임베디드 식을](./xml/embedded-expressions-in-xml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="9260a-200">연결 연산자 ()를`&`참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="9260a-201">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="9260a-202">자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="9260a-203">할당 후 연산자 `:=` `+=` `-=`(, `*=` `/=` `\=` `^=``=` `&=`" , `<<=` `>>=`" , " , " , ) .</span><span class="sxs-lookup"><span data-stu-id="9260a-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="9260a-204">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="9260a-205">자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="9260a-206">[이진 연산자] `*` `Mod`[이진연산자] `<>` `<` `>` `<=` `>=` `^` `>>` `<<` `And` `AndAlso` `Or``+` `-` `/` `OrElse` `Like` `Xor`</span><span class="sxs-lookup"><span data-stu-id="9260a-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="9260a-207">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="9260a-208">자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="9260a-209">`Is` 및 `IsNot` 연산자 후.</span><span class="sxs-lookup"><span data-stu-id="9260a-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="9260a-210">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="9260a-211">자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="9260a-212">멤버 한정자 문자`.`() 및 멤버 이름 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="9260a-213">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="9260a-214">그러나 `With` 문을 사용하거나 형식의 초기화 목록에`_`값을 제공할 때 멤버 한정자 문자 다음에 줄 연속 문자 () 를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="9260a-215">문 또는 개체 초기화 목록을 사용하는 `=` `With` 경우 할당 연산자(예:) 다음으로 선을 끊는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="9260a-216">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="9260a-217">자세한 내용은 [다음을 참조하십시오. 명령문](../../../visual-basic/language-reference/statements/with-end-with-statement.md) 또는 [개체 초기화자로 끝: 명명된 형식 및 익명 형식.](./objects-and-classes/object-initializers-named-and-anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="9260a-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="9260a-218">XML 축 속성 한정자(또는`.` 또는)를 `.@` `...`사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="9260a-219">그러나 키워드를 사용할 때 멤버 한정자를`_`지정할 때 줄 연속 문자 () 를 `With` 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="9260a-220">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="9260a-221">자세한 내용은 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="9260a-222">특성을 지정할 때 보다 작은 기호(<)`>`또는 보다 큰 기호() 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="9260a-223">또한 특성을 지정할`>`때 보다 큰 기호 () 후에.</span><span class="sxs-lookup"><span data-stu-id="9260a-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="9260a-224">그러나 어셈블리 수준 또는 모듈 수준 특성을 지정할 때 선 연속 문자 ()`_`포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="9260a-225">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="9260a-226">자세한 내용은 [특성 개요를](../../../visual-basic/programming-guide/concepts/attributes/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="9260a-227">`Aggregate`[] [ ] `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending`</span><span class="sxs-lookup"><span data-stu-id="9260a-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="9260a-228">여러`Order By`키워드 (, `Group Join`및)로 `Take While` `Skip While`구성된 쿼리 연산자의 키워드 사이의 선을 끊을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="9260a-229">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="9260a-230">자세한 내용은 [쿼리 를](../../../visual-basic/language-reference/queries/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9260a-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="9260a-231">`For Each` 명령문의 `In` 키워드 다음.</span><span class="sxs-lookup"><span data-stu-id="9260a-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="9260a-232">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="9260a-233">자세한 내용은 [각 에 대해 참조하세요... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9260a-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="9260a-234">컬렉션 `From` 초기화의 키워드 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="9260a-235">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="9260a-236">자세한 내용은 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9260a-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="9260a-237">댓글 추가</span><span class="sxs-lookup"><span data-stu-id="9260a-237">Adding comments</span></span>

<span data-ttu-id="9260a-238">소스 코드가 항상 자명한 것은 아니며, 심지어 소스를 작성한 프로그래머에게도 설명이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="9260a-239">따라서 대부분의 프로그래머는 코드를 문서화하기 위해 임베디드 주석을 자유롭게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="9260a-240">코드의 주석은 나중에 읽거나 작업하는 모든 사람에게 프로시저 또는 특정 명령을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="9260a-241">Visual Basic은 컴파일 하는 동안 주석을 무시 하 고 컴파일된 코드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="9260a-242">주석 줄은 아포스트로피()`'`또는 `REM` 공백 뒤에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="9260a-243">문자열 을 제외한 코드의 아무 곳에나 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="9260a-244">명령문에 주석을 추가하려면 아포스트로피를 삽입하거나 `REM` 문 뒤에 주석을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="9260a-245">주석은 별도의 줄로 진행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="9260a-246">다음 예제에서는 이러한 가능성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="9260a-247">컴파일 오류 확인</span><span class="sxs-lookup"><span data-stu-id="9260a-247">Checking compilation errors</span></span>

<span data-ttu-id="9260a-248">코드 줄을 입력한 후 줄에 물결 모양의 파란색 밑줄이 표시되면(오류 메시지도 나타날 수 있음) 문에 구문 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="9260a-249">명령문에 무엇이 잘못되었는지 (작업 목록에서 보거나 마우스 포인터로 오류를 가리키고 오류 메시지를 읽으면) 오류를 수정해야합니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="9260a-250">코드의 모든 구문 오류를 수정할 때까지 프로그램이 올바르게 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="9260a-251">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9260a-251">Related sections</span></span>

|<span data-ttu-id="9260a-252">용어</span><span class="sxs-lookup"><span data-stu-id="9260a-252">Term</span></span>|<span data-ttu-id="9260a-253">정의</span><span class="sxs-lookup"><span data-stu-id="9260a-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="9260a-254">대입 연산자</span><span class="sxs-lookup"><span data-stu-id="9260a-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="9260a-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span><span class="sxs-lookup"><span data-stu-id="9260a-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="9260a-256">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="9260a-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="9260a-257">요소를 연산자와 결합하여 새 값을 산출하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="9260a-258">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="9260a-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="9260a-259">단일 문을 여러 줄로 나누는 방법과 동일한 줄에 여러 문을 배치하는 방법을 보여 주시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="9260a-260">방법: Label 문</span><span class="sxs-lookup"><span data-stu-id="9260a-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="9260a-261">코드 줄에 레이블을 지정하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="9260a-261">Shows how to label a line of code.</span></span>|
