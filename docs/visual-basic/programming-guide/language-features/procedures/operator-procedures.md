---
title: 연산자 프로시저(Visual Basic)
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
ms.openlocfilehash: e6e65b1a75d7a80caff3e7cbacdb9dd706e46cdf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815572"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="3a4d0-102">연산자 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a4d0-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="3a4d0-103">연산자 프로시저는 일련의 표준 연산자의 동작을 정의 하는 Visual Basic 문 (같은 `*`, `<>`, 또는 `And`) 클래스 또는 구조체 정의에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="3a4d0-104">또한이 호출 됩니다 *연산자 오버 로드*합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="3a4d0-105">연산자 프로시저를 정의 하는 경우</span><span class="sxs-lookup"><span data-stu-id="3a4d0-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="3a4d0-106">클래스 또는 구조체를 정의한 경우 해당 클래스 또는 구조체의 형식으로 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="3a4d0-107">경우에 따라 이러한 변수는 식의 일부로 작업에 참여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="3a4d0-108">이렇게 하려면 연산자의 피연산자 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="3a4d0-109">Visual Basic의 기본 데이터 형식에 대해서만 연산자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="3a4d0-110">두 피연산자는 클래스 또는 구조체의 형식 또는 경우 연산자의 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3a4d0-111">자세한 내용은 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="3a4d0-112">연산자 프로시저의 형식</span><span class="sxs-lookup"><span data-stu-id="3a4d0-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="3a4d0-113">연산자 프로시저는 다음 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="3a4d0-114">정의 클래스 또는 구조체 형식의 인수가 있는 단항 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3a4d0-115">정의 클래스 또는 구조체 형식의 인수 중 하나가 이상는 이항 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3a4d0-116">클래스 또는 구조체 형식의 인수가 있는 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3a4d0-117">클래스 또는 구조체의 형식을 반환 하는 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3a4d0-118">변환 연산자는 단항, 항상 및 항상 사용 `CType` 정의 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="3a4d0-119">선언 구문</span><span class="sxs-lookup"><span data-stu-id="3a4d0-119">Declaration Syntax</span></span>  
 <span data-ttu-id="3a4d0-120">연산자 프로시저를 선언 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="3a4d0-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="3a4d0-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="3a4d0-122">사용 된 `Widening` 또는 `Narrowing` 형식 변환 연산자만 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="3a4d0-123">연산자 기호는 항상 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) 형식 변환 연산자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="3a4d0-124">이항 연산자가 정의 하는 두 개의 피연산자를 선언 및 형식 변환 연산자를 포함 하 여 단항 연산자를 정의 하는 하나의 피연산자를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="3a4d0-125">모든 피연산자를 선언 해야 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="3a4d0-126">에 대 한 매개 변수를 선언 하면 동일한 방식으로 각 피연산자를 선언 [Sub 프로시저](./sub-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="3a4d0-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3a4d0-127">Data Type</span></span>  
 <span data-ttu-id="3a4d0-128">연산자를 정의 하는 클래스 또는 구조체 정의에 있으므로 피연산자 중 하나 이상이 해당 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="3a4d0-129">형식 변환 연산자에 대 한 피연산자 또는 반환 형식은 클래스 또는 구조체의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="3a4d0-130">자세한 내용은 참조 하세요. [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="3a4d0-131">호출 구문</span><span class="sxs-lookup"><span data-stu-id="3a4d0-131">Calling Syntax</span></span>  
 <span data-ttu-id="3a4d0-132">식에서 연산자 기호를 사용 하 여 연산자 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="3a4d0-133">미리 정의 된 연산자에 대해 수행한 동일한 방식으로 피연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="3a4d0-134">연산자 프로시저에 대 한 암시적 호출에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="3a4d0-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="3a4d0-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="3a4d0-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span><span class="sxs-lookup"><span data-stu-id="3a4d0-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="3a4d0-137">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="3a4d0-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="3a4d0-138">다음과 같은 구조를 구성 하는 상위 및 하위 부분으로 128 비트의 부호 있는 정수 값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="3a4d0-139">정의 된 `+` 두 연산자 `veryLong` 값 및 결과 생성 `veryLong` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="3a4d0-140">다음 예제에서는 일반적인 호출을 `+` 에 정의 된 운영자 `veryLong`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  
  
  
## <a name="see-also"></a><span data-ttu-id="3a4d0-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a4d0-141">See also</span></span>

- [<span data-ttu-id="3a4d0-142">절차</span><span class="sxs-lookup"><span data-stu-id="3a4d0-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3a4d0-143">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="3a4d0-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="3a4d0-144">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="3a4d0-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="3a4d0-145">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="3a4d0-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="3a4d0-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="3a4d0-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3a4d0-147">Operator 문</span><span class="sxs-lookup"><span data-stu-id="3a4d0-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3a4d0-148">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="3a4d0-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="3a4d0-149">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="3a4d0-150">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="3a4d0-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="3a4d0-151">방법: 연산자를 정의 하는 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4d0-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
