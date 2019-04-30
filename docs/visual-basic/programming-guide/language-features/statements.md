---
title: Visual Basic의 문
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
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946460"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="259c2-102">Visual Basic의 문</span><span class="sxs-lookup"><span data-stu-id="259c2-102">Statements in Visual Basic</span></span>

<span data-ttu-id="259c2-103">Visual Basic의 문은 전체 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="259c2-104">키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="259c2-105">각 문에 다음 범주 중 하나에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="259c2-106">**선언문**는 변수, 상수 또는 프로시저 이름을 지정 하 고 데이터 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="259c2-107">**실행 가능 문을**, 하는 작업을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="259c2-108">이러한 문은 메서드 또는 함수를 호출할 수 있으며 루프 하거나 코드 블록에서 분기 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="259c2-109">실행 가능 문을 포함 **대입문**, 변수 또는 상수 값 이나 식을 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="259c2-110">이 항목에서는 각 범주를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-110">This topic describes each category.</span></span> <span data-ttu-id="259c2-111">또한이 항목에서는 여러 문을 한 줄에 결합 하는 방법 및 여러 줄 문을 계속 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="259c2-112">선언문</span><span class="sxs-lookup"><span data-stu-id="259c2-112">Declaration statements</span></span>

<span data-ttu-id="259c2-113">프로시저, 변수, 속성, 배열 및 상수를 정의 하 고 이름을 선언 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="259c2-114">프로그래밍 요소를 선언 하면 해당 데이터 형식, 액세스 수준 및 범위 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="259c2-115">자세한 내용은 [선언 요소의 특징](./declared-elements/declared-element-characteristics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="259c2-116">다음 예제에서는 세 가지 선언이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="259c2-117">첫 번째 선언이 `Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="259c2-118">해당 일치와 함께 `End Sub` 라는 프로시저 선언 문을 `applyFormat`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="259c2-119">또한 지정 하는 `applyFormat` 는 `Public`, 즉, 변수를 참조할 수 있는 모든 코드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="259c2-120">두 번째 선언이 `Const` 상수를 선언 하는 문을 `limit`을 지정 하 고는 `Integer` 데이터 형식과 33 값.</span><span class="sxs-lookup"><span data-stu-id="259c2-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="259c2-121">세 번째 선언 되는 `Dim` 변수를 선언 하는 문을 `thisWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="259c2-122">데이터 형식은 특정 개체, 즉에서 생성 된 개체는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="259c2-123">변수를 사용 하는 응용 프로그램에서 제공 되는 임의의 개체 형식 또는 모든 기본 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="259c2-124">초기 값</span><span class="sxs-lookup"><span data-stu-id="259c2-124">Initial Values</span></span>

<span data-ttu-id="259c2-125">선언문을 포함 하는 코드를 실행 하는 경우 Visual Basic에서는 선언된 된 요소에 필요한 메모리를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="259c2-126">요소 값을 갖는 경우 Visual Basic 데이터 형식에 대 한 기본값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="259c2-127">자세한 내용은 "동작"를 참조 하세요 [Dim 문](../../language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="259c2-128">다음 예제와 같이 해당 선언의 일부로 변수에 초기 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="259c2-129">변수는 개체 변수를 명시적으로 만들면 해당 클래스의 인스턴스를 사용 하 여 선언 하는 경우는 [새 운영자](../../../visual-basic/language-reference/operators/new-operator.md) 키워드, 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="259c2-130">실행 선언문에 도달할 때까지 선언문에 지정 된 초기 값을 변수에 할당 되지 않았는지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="259c2-131">그 전 까지는 변수의 데이터 형식에 대 한 기본값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="259c2-132">실행문</span><span class="sxs-lookup"><span data-stu-id="259c2-132">Executable statements</span></span>

<span data-ttu-id="259c2-133">실행 가능 문이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-133">An executable statement performs an action.</span></span> <span data-ttu-id="259c2-134">여러 문 반복 코드에서 다른 위치로 분기 프로시저를 호출 하거나 식을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="259c2-135">대입문에는 실행 가능 문이의 특수 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="259c2-136">다음 예제에서는 `If...Then...Else` 제어 구조를 다른 변수 값을 기반으로 하는 코드 블록을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="259c2-137">각 코드 블록 내에서 `For...Next` 루프 실행 횟수를 지정된 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="259c2-138">합니다 `If` 문 앞의 예제에서 매개 변수의 값을 확인 `clockwise`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="259c2-139">값이 `True`를 호출 합니다 `spinClockwise` 메서드의 `aWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="259c2-140">값이 `False`를 호출 합니다 `spinCounterClockwise` 메서드의 `aWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="259c2-141">합니다 `If...Then...Else` 제어 구조 끝나는 `End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="259c2-142">합니다 `For...Next` 각 블록 내에서 루프 적절 한 메서드 호출 된 횟수 만큼의 값과 같은 `revolutions` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="259c2-143">대입문</span><span class="sxs-lookup"><span data-stu-id="259c2-143">Assignment statements</span></span>

<span data-ttu-id="259c2-144">대입문 대입 연산자의 오른쪽에 값을 수행 하는 할당 작업을 수행 (`=`) 하 고 다음 예제와 같이 왼쪽 요소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="259c2-145">앞의 예에서 대입문은 저장 변수에 리터럴 값 42 `v`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="259c2-146">사용할 수 있는 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="259c2-146">Eligible programming elements</span></span>

<span data-ttu-id="259c2-147">대입 연산자의 좌 변에 있는 프로그래밍 요소를 받아 값을 저장 하기 위해 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="259c2-148">즉, 변수 또는 아닌 속성 이어야 합니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), 또는 배열 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="259c2-149">대입문의 컨텍스트에서 이러한 요소 라고도 함은 *lvalue*, "왼쪽 값입니다."</span><span class="sxs-lookup"><span data-stu-id="259c2-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="259c2-150">대입 연산자의 오른쪽에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소를 다른 식 또는 함수 호출의 조합으로 구성 될 수 있는 식에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="259c2-151">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="259c2-152">위의 예제에서는 변수에 저장 된 값 `y` 변수에 저장 된 값을 `z`, 다음 함수를 호출 하 여 반환 되는 값을 추가 하 고 `findResult`입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="259c2-153">이 식의 합계 값은 변수에 저장 한 다음 `x`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="259c2-154">대입문의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="259c2-154">Data types in assignment statements</span></span>

<span data-ttu-id="259c2-155">숫자 값 외에도 할당 연산자를 할당할 수도 `String` 다음 예제와 같이 값입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="259c2-156">할당할 수도 있습니다 `Boolean` 중 하나를 사용 하 여 값을 `Boolean` 리터럴 또는 `Boolean` 다음 예제와 같이 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="259c2-157">마찬가지로, 적절 한 값의 프로그래밍 요소에 할당할 수 있습니다 합니다 `Char`, `Date`, 또는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="259c2-158">또한 해당 인스턴스에 만들어집니다 클래스도 선언 된 요소에 개체 인스턴스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="259c2-159">복합 대입문</span><span class="sxs-lookup"><span data-stu-id="259c2-159">Compound assignment statements</span></span>

<span data-ttu-id="259c2-160">*복합 대입문* 먼저 프로그래밍 요소에 할당 하기 전에 식에 대 한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="259c2-161">다음 예제에서는 다음이 연산자 중 하나를 보여 줍니다 `+=`는 오른쪽에 있는 식의 값으로 연산자의 좌 변에 있는 변수의 값을 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="259c2-162">앞의 예제 값 1을 더하여 `n`, 다음에 새 값을 저장 하 고 `n`입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="259c2-163">이것은 다음 문과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="259c2-164">이러한 종류의 연산자를 사용 하 여 다양 한 복합 할당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="259c2-165">목록과 이러한 연산자에 대 한 자세한 내용은 참조 하세요 [대입 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="259c2-166">연결 대입 연산자 (`&=`) 기존의 끝에 문자열을 추가 하는 데는 다음 예제와 같이 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="259c2-167">대입문의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="259c2-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="259c2-168">변수, 속성 또는 배열 요소에 할당 하는 값은 해당 대상 요소에 적절 한 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="259c2-169">일반적으로 대상 요소와 동일한 데이터 형식의 값을 생성 하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="259c2-170">그러나 일부 형식 할당 중에 다른 형식에서 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="259c2-171">데이터 형식 간 변환에 대 한 내용은 참조 하세요 [Visual Basic의 형식 변환](./data-types/type-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="259c2-172">간단히 말해, Visual Basic는 자동으로 확대 하는 다른 모든 형식에 지정 된 형식의 값을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="259c2-173">A *확대 변환* 은 하나는 항상 런타임에 성공 하 고 데이터가 손실 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="259c2-174">예를 들어 Visual Basic 변환를 `Integer` 값을 `Double` 해당 되는 경우 때문 `Integer` 로 확대 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="259c2-175">자세한 내용은 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="259c2-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="259c2-176">*축소 변환* 런타임 시 오류 또는 데이터 손실의 위험을 수행 (확대 하지 해당).</span><span class="sxs-lookup"><span data-stu-id="259c2-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="259c2-177">형식 변환 함수를 사용 하 여 명시적으로 축소 변환을 수행 하거나 설정 하 여 모든 변환을 암시적으로 수행 하기 위해 컴파일러에 지시할 수 있습니다 `Option Strict Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="259c2-178">자세한 내용은 [암시적 변환과 명시적 변환](./data-types/implicit-and-explicit-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="259c2-179">한 줄에 여러 문 배치</span><span class="sxs-lookup"><span data-stu-id="259c2-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="259c2-180">콜론으로 구분 된 단일 줄에 여러 문을 포함할 수 있습니다 (`:`) 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="259c2-181">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="259c2-182">경우에 따라 편리 하지만이 형식의 구문 사용 하면 코드 읽고 유지 관리 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="259c2-183">따라서 하나의 문으로 줄으로 유지 하는 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="259c2-184">여러 줄 문을 계속</span><span class="sxs-lookup"><span data-stu-id="259c2-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="259c2-185">문을 한 줄에 일반적으로 적합 하지만 너무 긴 경우 뒤에 밑줄 문자가 공백으로 구성 된 순서 줄 연속 문자를 사용 하 여 다음 줄으로 계속 수 있습니다 (`_`) 뒤에 캐리지 리턴입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="259c2-186">다음 예제에서는 `MsgBox` 실행 문은 두 줄에 걸쳐 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="259c2-187">암시적 줄 연속 문자</span><span class="sxs-lookup"><span data-stu-id="259c2-187">Implicit line continuation</span></span>

<span data-ttu-id="259c2-188">대부분의 경우 계속할 수 있습니다 문을 다음 연속 줄에서 밑줄 문자를 사용 하지 않고 (`_`).</span><span class="sxs-lookup"><span data-stu-id="259c2-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="259c2-189">다음 구문 요소는 암시적으로 코드의 다음 줄에서 문을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="259c2-190">쉼표 뒤 (`,`).</span><span class="sxs-lookup"><span data-stu-id="259c2-190">After a comma (`,`).</span></span> <span data-ttu-id="259c2-191">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="259c2-192">여는 괄호 뒤 (`(`) 또는 닫는 괄호 앞 (`)`).</span><span class="sxs-lookup"><span data-stu-id="259c2-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="259c2-193">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="259c2-194">열린 중괄호 (`{`) 또는 닫는 중괄호 이전 (`}`).</span><span class="sxs-lookup"><span data-stu-id="259c2-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="259c2-195">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="259c2-196">자세한 내용은 참조 하세요. [개체 이니셜라이저: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md) 나 [컬렉션 이니셜라이저](./collection-initializers/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="259c2-197">열린 후 포함 식 (`<%=`) 또는 포함 된 식의 닫기 전에 (`%>`) XML 리터럴 내에서.</span><span class="sxs-lookup"><span data-stu-id="259c2-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="259c2-198">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="259c2-199">자세한 내용은 [XML의 포함 식](./xml/embedded-expressions-in-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="259c2-200">연결 연산자 뒤 (`&`).</span><span class="sxs-lookup"><span data-stu-id="259c2-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="259c2-201">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="259c2-202">자세한 내용은 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="259c2-203">후 할당 연산자 (`=`, `&=`, `:=`, `+=`, `-=`를 `*=`, `/=`, `\=`, `^=`를 `<<=`, `>>=`).</span><span class="sxs-lookup"><span data-stu-id="259c2-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="259c2-204">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="259c2-205">자세한 내용은 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="259c2-206">이항 연산자 (`+`, `-`, `/`, `*`, `Mod`를 `<>`, `<`를 `>`, `<=`를 `>=`, `^`, `>>`, `<<`, `And`를 `AndAlso`를 `Or`를 `OrElse`를 `Like`, `Xor`) 식 내에서.</span><span class="sxs-lookup"><span data-stu-id="259c2-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="259c2-207">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="259c2-208">자세한 내용은 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="259c2-209">후 합니다 `Is` 고 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="259c2-210">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="259c2-211">자세한 내용은 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="259c2-212">멤버 한정자 문자 뒤 (`.`) 및 멤버 이름 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="259c2-213">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="259c2-214">하지만 줄 연속 문자를 포함 해야 (`_`) 멤버 한정자 문자를 사용 하는 경우 다음을 `With` 문이나 형식의 초기화 목록에서 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="259c2-215">대입 연산자 뒤에서 줄 바꿈 하는 것이 좋습니다 (예를 들어 `=`)을 사용할 때 `With` 문이나 개체 초기화 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="259c2-216">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="259c2-217">자세한 내용은 참조 하세요. [사용 하 여는 중... 문을 사용 하 여 종료](../../../visual-basic/language-reference/statements/with-end-with-statement.md) 또는 [개체 이니셜라이저: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="259c2-218">XML 축 속성 한정자를 후 (`.` 나 `.@` 또는 `...`).</span><span class="sxs-lookup"><span data-stu-id="259c2-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="259c2-219">하지만 줄 연속 문자를 포함 해야 (`_`)를 사용 하는 경우 멤버 한정자를 지정 하면를 `With` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="259c2-220">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="259c2-221">자세한 내용은 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="259c2-222">작음-기호 (<) 보다 이전의 큼-기호 (`>`) 특성을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="259c2-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="259c2-223">뒤에 큼-기호 (`>`) 특성을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="259c2-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="259c2-224">하지만 줄 연속 문자를 포함 해야 (`_`) 어셈블리 수준 또는 모듈 수준 특성을 지정 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="259c2-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="259c2-225">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="259c2-226">자세한 내용은 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="259c2-227">쿼리 연산자 앞뒤 (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`를 `Join`, `Let`를 `Order By`, `Select`를 `Skip`, `Skip While`, `Take`, `Take While`, `Where`를 `In`를 `Into`, `On`를 `Ascending`, 및 `Descending`).</span><span class="sxs-lookup"><span data-stu-id="259c2-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="259c2-228">여러 키워드 이루어져 하는 쿼리 연산자 키워드 사이 줄을 바꿀 수 없습니다 (`Order By`, `Group Join`를 `Take While`, 및 `Skip While`).</span><span class="sxs-lookup"><span data-stu-id="259c2-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="259c2-229">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="259c2-230">자세한 내용은 [쿼리](../../../visual-basic/language-reference/queries/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="259c2-231">후 합니다 `In` 키워드를 `For Each` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="259c2-232">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="259c2-233">자세한 내용은 참조 하세요. [각각에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="259c2-234">후는 `From` 컬렉션 이니셜라이저에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="259c2-235">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="259c2-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="259c2-236">자세한 내용은 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="259c2-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="259c2-237">주석 추가</span><span class="sxs-lookup"><span data-stu-id="259c2-237">Adding comments</span></span>

<span data-ttu-id="259c2-238">항상 소스 코드를 작성 한 프로그래머에도 쉽게 이해할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="259c2-239">따라서 해당 코드를 문서화를 위해 대부분의 프로그래머에 게가 포함 된 주석의 자유롭게 사용 하 여를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="259c2-240">코드의 주석을 프로시저나 읽기 또는 나중에 작업을 모든 사용자에 게 특정 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="259c2-241">Visual Basic 컴파일 중 메모를 무시 하 고 컴파일된 코드가 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="259c2-242">주석 줄에 아포스트로피가 시작 (`'`) 또는 `REM` 뒤에 공백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="259c2-243">추가할 수 있습니다 어디서 나 코드에서 제외 하 고 문자열 내에서.</span><span class="sxs-lookup"><span data-stu-id="259c2-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="259c2-244">주석 문을 추가할 아포스트로피를 삽입 또는 `REM` 주석 뒤에 문 뒤 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="259c2-245">별도 줄에 주석을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="259c2-246">다음 예제에서는 이러한 가능성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="259c2-247">컴파일 오류를 확인 하는 중</span><span class="sxs-lookup"><span data-stu-id="259c2-247">Checking compilation errors</span></span>

<span data-ttu-id="259c2-248">코드 줄을 입력 한 후 줄 (오류 메시지가 나타날 수 있음) 파란색 물결 무늬 밑줄로 표시 됩니다, 그리고 문에 구문 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="259c2-249">무엇이 문을 사용 하 여 작업 목록에서 또는 마우스 포인터를 사용 하 여 오류를 가리키면 찾고 기록 된 오류 메시지) (에서 확인 하 고 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="259c2-250">코드에서 모든 구문 오류를 수정 하기 전에 올바르게 컴파일되도록 하려면 프로그램이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="259c2-251">관련 단원</span><span class="sxs-lookup"><span data-stu-id="259c2-251">Related sections</span></span>

|<span data-ttu-id="259c2-252">용어</span><span class="sxs-lookup"><span data-stu-id="259c2-252">Term</span></span>|<span data-ttu-id="259c2-253">정의</span><span class="sxs-lookup"><span data-stu-id="259c2-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="259c2-254">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="259c2-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="259c2-255">와 같은 할당 연산자를 포함 하는 언어 참조 페이지 링크를 제공 `=`, `*=`, 및 `&=`합니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="259c2-256">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="259c2-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="259c2-257">새 값을 산출 하는 연산자를 사용 하 여 요소를 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="259c2-258">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="259c2-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="259c2-259">단일 문에 여러 줄으로 분할 하는 방법과 같은 줄에 여러 문 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="259c2-260">방법: 레이블 문</span><span class="sxs-lookup"><span data-stu-id="259c2-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="259c2-261">코드 줄 레이블을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="259c2-261">Shows how to label a line of code.</span></span>|
