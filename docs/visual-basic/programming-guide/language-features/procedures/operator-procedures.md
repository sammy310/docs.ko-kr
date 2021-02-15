---
description: '자세한 정보: 연산자 프로시저 (Visual Basic)'
title: 연산자 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 836eeb2e705a96c49b5fa53e277ccf025d1915b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479961"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="a8f64-103">연산자 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8f64-103">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="a8f64-104">연산자 프로시저는 `*` `<>` `And` 사용자가 정의한 클래스 또는 구조체에서 표준 연산자 (예:, 또는)의 동작을 정의 하는 일련의 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-104">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="a8f64-105">이를 *연산자 오버 로드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-105">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="a8f64-106">연산자 프로시저를 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a8f64-106">When to Define Operator Procedures</span></span>

<span data-ttu-id="a8f64-107">클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-107">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="a8f64-108">때로는 이러한 변수가 식의 일부로 작업에 참여 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-108">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="a8f64-109">이렇게 하려면 연산자의 피연산자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-109">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="a8f64-110">Visual Basic은 기본 데이터 형식에 대해서만 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-110">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="a8f64-111">피연산자 중 하나 또는 둘 다가 클래스 또는 구조체의 형식인 경우 연산자의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-111">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="a8f64-112">자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f64-112">For more information, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="a8f64-113">연산자 프로시저 유형</span><span class="sxs-lookup"><span data-stu-id="a8f64-113">Types of Operator Procedure</span></span>

<span data-ttu-id="a8f64-114">연산자 프로시저는 다음 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-114">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="a8f64-115">인수가 클래스 또는 구조체의 형식인 단항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-115">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="a8f64-116">하나 이상의 인수가 클래스 또는 구조체의 형식인 이항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-116">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="a8f64-117">인수가 클래스 또는 구조체의 형식인 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-117">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="a8f64-118">클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-118">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="a8f64-119">변환 연산자는 항상 단항 이며, 정의 하는 연산자로 항상를 사용 `CType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-119">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="a8f64-120">선언 구문</span><span class="sxs-lookup"><span data-stu-id="a8f64-120">Declaration Syntax</span></span>

<span data-ttu-id="a8f64-121">연산자 프로시저를 선언 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-121">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="a8f64-122">`Widening` `Narrowing` 형식 변환 연산자에 대해서만 또는 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="a8f64-123">연산자 기호는 형식 변환 연산자에 대해 항상 [CType 함수](../../../language-reference/functions/ctype-function.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-123">The operator symbol is always [CType Function](../../../language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="a8f64-124">이항 연산자를 정의 하는 두 개의 피연산자를 선언 하 고, 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 피연산자 하나를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="a8f64-125">모든 피연산자를 선언 해야 합니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="a8f64-125">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="a8f64-126">[Sub 프로시저](./sub-procedures.md)에 대 한 매개 변수를 선언 하는 것과 동일한 방식으로 각 피연산자를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="a8f64-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8f64-127">Data Type</span></span>

<span data-ttu-id="a8f64-128">정의한 클래스 또는 구조체에서 연산자를 정의 하기 때문에 하나 이상의 피연산자는 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="a8f64-129">형식 변환 연산자의 경우 피연산자 또는 반환 형식이 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="a8f64-130">자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f64-130">For more details, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="a8f64-131">호출 구문</span><span class="sxs-lookup"><span data-stu-id="a8f64-131">Calling Syntax</span></span>

<span data-ttu-id="a8f64-132">식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="a8f64-133">미리 정의 된 연산자에 대해 수행 하는 것과 동일한 방식으로 피연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-133">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="a8f64-134">연산자 프로시저에 대 한 암시적 호출 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="a8f64-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="a8f64-135">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="a8f64-136">`Dim testNewStruct As`  *structurename* `= testStruct` *operatorsymbol*      `10`</span><span class="sxs-lookup"><span data-stu-id="a8f64-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="a8f64-137">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="a8f64-137">Illustration of Declaration and Call</span></span>

<span data-ttu-id="a8f64-138">다음 구조체는 부호 있는 128 비트 정수 값을 구성 된 상위 및 하위 부분으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="a8f64-139">`+`두 값을 추가 하 `veryLong` 고 결과 값을 생성 하는 연산자를 정의 `veryLong` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f64-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="a8f64-140">다음 예에서는에 정의 된 연산자에 대 한 일반적인 호출을 보여 줍니다 `+` `veryLong` .</span><span class="sxs-lookup"><span data-stu-id="a8f64-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="a8f64-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a8f64-141">See also</span></span>

- [<span data-ttu-id="a8f64-142">절차</span><span class="sxs-lookup"><span data-stu-id="a8f64-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a8f64-143">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="a8f64-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a8f64-144">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="a8f64-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a8f64-145">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="a8f64-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a8f64-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="a8f64-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a8f64-147">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a8f64-147">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="a8f64-148">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="a8f64-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="a8f64-149">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="a8f64-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="a8f64-150">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="a8f64-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="a8f64-151">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="a8f64-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
