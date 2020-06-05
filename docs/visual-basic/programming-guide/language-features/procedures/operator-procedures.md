---
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
ms.openlocfilehash: a1dd183570c8aa50efff85bdaebef90bd3b0120f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364320"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="965f1-102">연산자 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="965f1-102">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="965f1-103">연산자 프로시저는 `*` `<>` `And` 사용자가 정의한 클래스 또는 구조체에서 표준 연산자 (예:, 또는)의 동작을 정의 하는 일련의 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="965f1-104">이를 *연산자 오버 로드*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-104">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="965f1-105">연산자 프로시저를 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="965f1-105">When to Define Operator Procedures</span></span>

<span data-ttu-id="965f1-106">클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="965f1-107">때로는 이러한 변수가 식의 일부로 작업에 참여 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="965f1-108">이렇게 하려면 연산자의 피연산자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-108">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="965f1-109">Visual Basic은 기본 데이터 형식에 대해서만 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="965f1-110">피연산자 중 하나 또는 둘 다가 클래스 또는 구조체의 형식인 경우 연산자의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="965f1-111">자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="965f1-111">For more information, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="965f1-112">연산자 프로시저 유형</span><span class="sxs-lookup"><span data-stu-id="965f1-112">Types of Operator Procedure</span></span>

<span data-ttu-id="965f1-113">연산자 프로시저는 다음 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-113">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="965f1-114">인수가 클래스 또는 구조체의 형식인 단항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="965f1-115">하나 이상의 인수가 클래스 또는 구조체의 형식인 이항 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="965f1-116">인수가 클래스 또는 구조체의 형식인 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="965f1-117">클래스 또는 구조체의 형식을 반환 하는 변환 연산자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="965f1-118">변환 연산자는 항상 단항 이며, 정의 하는 연산자로 항상를 사용 `CType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="965f1-119">선언 구문</span><span class="sxs-lookup"><span data-stu-id="965f1-119">Declaration Syntax</span></span>

<span data-ttu-id="965f1-120">연산자 프로시저를 선언 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-120">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="965f1-121">`Widening` `Narrowing` 형식 변환 연산자에 대해서만 또는 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-121">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="965f1-122">연산자 기호는 형식 변환 연산자에 대해 항상 [CType 함수](../../../language-reference/functions/ctype-function.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-122">The operator symbol is always [CType Function](../../../language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="965f1-123">이항 연산자를 정의 하는 두 개의 피연산자를 선언 하 고, 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 피연산자 하나를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-123">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="965f1-124">모든 피연산자를 선언 해야 합니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="965f1-124">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="965f1-125">[Sub 프로시저](./sub-procedures.md)에 대 한 매개 변수를 선언 하는 것과 동일한 방식으로 각 피연산자를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-125">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="965f1-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="965f1-126">Data Type</span></span>

<span data-ttu-id="965f1-127">정의한 클래스 또는 구조체에서 연산자를 정의 하기 때문에 하나 이상의 피연산자는 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-127">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="965f1-128">형식 변환 연산자의 경우 피연산자 또는 반환 형식이 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-128">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="965f1-129">자세한 내용은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="965f1-129">For more details, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="965f1-130">호출 구문</span><span class="sxs-lookup"><span data-stu-id="965f1-130">Calling Syntax</span></span>

<span data-ttu-id="965f1-131">식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-131">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="965f1-132">미리 정의 된 연산자에 대해 수행 하는 것과 동일한 방식으로 피연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-132">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="965f1-133">연산자 프로시저에 대 한 암시적 호출 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-133">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="965f1-134">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="965f1-134">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="965f1-135">`Dim testNewStruct As`  *structurename* `= testStruct` *operatorsymbol*      `10`</span><span class="sxs-lookup"><span data-stu-id="965f1-135">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="965f1-136">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="965f1-136">Illustration of Declaration and Call</span></span>

<span data-ttu-id="965f1-137">다음 구조체는 부호 있는 128 비트 정수 값을 구성 된 상위 및 하위 부분으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-137">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="965f1-138">`+`두 값을 추가 하 `veryLong` 고 결과 값을 생성 하는 연산자를 정의 `veryLong` 합니다.</span><span class="sxs-lookup"><span data-stu-id="965f1-138">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="965f1-139">다음 예에서는에 정의 된 연산자에 대 한 일반적인 호출을 보여 줍니다 `+` `veryLong` .</span><span class="sxs-lookup"><span data-stu-id="965f1-139">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="965f1-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="965f1-140">See also</span></span>

- [<span data-ttu-id="965f1-141">절차</span><span class="sxs-lookup"><span data-stu-id="965f1-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="965f1-142">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="965f1-142">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="965f1-143">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="965f1-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="965f1-144">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="965f1-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="965f1-145">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="965f1-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="965f1-146">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="965f1-146">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="965f1-147">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="965f1-147">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="965f1-148">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="965f1-148">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="965f1-149">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="965f1-149">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="965f1-150">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="965f1-150">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
