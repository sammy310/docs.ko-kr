---
title: 매개 변수 목록
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: ec4ce0f12b540478d889832fb18f1ef008613f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346476"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="cbe4d-102">매개 변수 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="cbe4d-103">프로시저를 호출할 때 프로시저에 필요한 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="cbe4d-104">여러 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="cbe4d-105">다음은 하나의 매개 변수에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbe4d-106">구문</span><span class="sxs-lookup"><span data-stu-id="cbe4d-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="cbe4d-107">요소</span><span class="sxs-lookup"><span data-stu-id="cbe4d-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="cbe4d-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-108">Optional.</span></span> <span data-ttu-id="cbe4d-109">이 매개 변수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="cbe4d-110">[특성 목록을](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호 ("`<`" 및 "`>`")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="cbe4d-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-111">Optional.</span></span> <span data-ttu-id="cbe4d-112">프로시저를 호출할 때이 매개 변수가 필요 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="cbe4d-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-113">Optional.</span></span> <span data-ttu-id="cbe4d-114">프로시저에서 호출 코드의 해당 인수를 기반으로 하는 변수 요소를 바꾸거나 다시 할당할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="cbe4d-115">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-115">Optional.</span></span> <span data-ttu-id="cbe4d-116">호출 하는 코드와 같은 방식으로 프로시저에서 호출 코드의 기본 변수 요소를 수정할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="cbe4d-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="cbe4d-117">Optional.</span></span> <span data-ttu-id="cbe4d-118">매개 변수 목록의 마지막 매개 변수가 지정 된 데이터 형식의 선택적 요소 배열 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="cbe4d-119">이를 통해 호출 코드는 프로시저에 임의 개수의 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="cbe4d-120">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-120">Required.</span></span> <span data-ttu-id="cbe4d-121">매개 변수를 나타내는 지역 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="cbe4d-122">`Option Strict` `On`경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="cbe4d-123">매개 변수를 나타내는 지역 변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="cbe4d-124">`Optional` 매개 변수에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="cbe4d-125">매개 변수의 데이터 형식으로 계산 되는 상수 또는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="cbe4d-126">형식이 `Object`이거나 클래스, 인터페이스, 배열 또는 구조 이면 기본값은 `Nothing`만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbe4d-127">주의</span><span class="sxs-lookup"><span data-stu-id="cbe4d-127">Remarks</span></span>

<span data-ttu-id="cbe4d-128">매개 변수는 괄호로 묶고 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="cbe4d-129">모든 데이터 형식을 사용 하 여 매개 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="cbe4d-130">`parametertype`지정 하지 않으면 기본적으로 `Object`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="cbe4d-131">호출 하는 코드는 프로시저를 호출할 때 각 필수 매개 변수에 *인수* 를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="cbe4d-132">자세한 내용은 [매개 변수와 인수 간의 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="cbe4d-133">호출 코드에서 각 매개 변수에 전달 하는 인수는 호출 코드의 내부 요소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="cbe4d-134">이 요소가 *비가변* (상수, 리터럴, 열거형 또는 식) 인 경우 코드를 변경 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="cbe4d-135">*변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조체 요소) 인 경우 호출 코드에서이를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="cbe4d-136">자세한 내용은 [수정 가능 인수와 수정할 가능성이 없는 인수 간의 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="cbe4d-137">변수 요소가 `ByRef`전달 되는 경우에도 프로시저에서 해당 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="cbe4d-138">자세한 내용은 [값으로 인수를 전달 하는 것과 참조로 인수를 전달 하는 차이점](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="cbe4d-139">규칙</span><span class="sxs-lookup"><span data-stu-id="cbe4d-139">Rules</span></span>

- <span data-ttu-id="cbe4d-140">**괄호.**</span><span class="sxs-lookup"><span data-stu-id="cbe4d-140">**Parentheses.**</span></span> <span data-ttu-id="cbe4d-141">매개 변수 목록을 지정 하는 경우 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="cbe4d-142">매개 변수가 없는 경우에도 빈 목록에 괄호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="cbe4d-143">이렇게 하면 요소가 프로시저 임을 명확 하 게 하 여 코드의 가독성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="cbe4d-144">**선택적 매개 변수입니다.**</span><span class="sxs-lookup"><span data-stu-id="cbe4d-144">**Optional Parameters.**</span></span> <span data-ttu-id="cbe4d-145">매개 변수에 `Optional` 한정자를 사용 하는 경우 목록에 있는 모든 후속 매개 변수도 선택적 이어야 하 고 `Optional` 한정자를 사용 하 여 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="cbe4d-146">모든 선택적 매개 변수 선언은 `defaultvalue` 절을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="cbe4d-147">자세한 내용은 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="cbe4d-148">**매개 변수 배열.**</span><span class="sxs-lookup"><span data-stu-id="cbe4d-148">**Parameter Arrays.**</span></span> <span data-ttu-id="cbe4d-149">`ParamArray` 매개 변수에 대 한 `ByVal` 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="cbe4d-150">동일한 매개 변수 목록에서 `Optional`와 `ParamArray`를 모두 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="cbe4d-151">자세한 내용은 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="cbe4d-152">**전달 메커니즘입니다.**</span><span class="sxs-lookup"><span data-stu-id="cbe4d-152">**Passing Mechanism.**</span></span> <span data-ttu-id="cbe4d-153">모든 인수에 대 한 기본 메커니즘은 `ByVal`입니다. 즉, 프로시저에서 기본 변수 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="cbe4d-154">그러나 요소가 참조 형식인 경우 프로시저는 개체 자체를 바꾸거나 재할당할 수 없더라도 기본 개체의 내용이 나 멤버를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="cbe4d-155">**매개 변수 이름.**</span><span class="sxs-lookup"><span data-stu-id="cbe4d-155">**Parameter Names.**</span></span> <span data-ttu-id="cbe4d-156">매개 변수의 데이터 형식이 배열인 경우에는 `parametername`를 즉시 괄호로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="cbe4d-157">매개 변수 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="cbe4d-158">예제</span><span class="sxs-lookup"><span data-stu-id="cbe4d-158">Example</span></span>

<span data-ttu-id="cbe4d-159">다음 예에서는 두 개의 매개 변수를 정의 하는 `Function` 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbe4d-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="cbe4d-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbe4d-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="cbe4d-161">Function 문</span><span class="sxs-lookup"><span data-stu-id="cbe4d-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="cbe4d-162">Sub 문</span><span class="sxs-lookup"><span data-stu-id="cbe4d-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="cbe4d-163">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="cbe4d-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="cbe4d-164">Structure 문</span><span class="sxs-lookup"><span data-stu-id="cbe4d-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="cbe4d-165">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="cbe4d-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="cbe4d-166">특성 개요</span><span class="sxs-lookup"><span data-stu-id="cbe4d-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="cbe4d-167">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="cbe4d-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
