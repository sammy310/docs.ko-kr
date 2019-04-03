---
title: 매개 변수 목록(Visual Basic)
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
ms.openlocfilehash: 651f08812032aa1c5aacc04fdb3d7f491f12b607
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836287"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="0a8c9-102">매개 변수 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a8c9-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="0a8c9-103">프로시저를 호출할 때에 필요한 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="0a8c9-104">여러 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="0a8c9-105">다음은 하나의 매개 변수에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8c9-106">구문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="0a8c9-107">요소</span><span class="sxs-lookup"><span data-stu-id="0a8c9-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="0a8c9-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-108">Optional.</span></span> <span data-ttu-id="0a8c9-109">이 매개 변수에 적용 되는 특성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="0a8c9-110">묶어야 합니다 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="0a8c9-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="0a8c9-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-111">Optional.</span></span> <span data-ttu-id="0a8c9-112">프로시저를 호출할 때이 매개 변수가 필요한 아님을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="0a8c9-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-113">Optional.</span></span> <span data-ttu-id="0a8c9-114">프로시저를 대체 하거나 호출 코드의 해당 인수를 기본 변수 요소를 재할당할 수 없습니다는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="0a8c9-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-115">Optional.</span></span> <span data-ttu-id="0a8c9-116">프로시저 요소를 수정할 수 기본 변수는 호출 코드에서 호출 코드 자체를 동일한 방식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="0a8c9-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-117">Optional.</span></span> <span data-ttu-id="0a8c9-118">매개 변수 목록의 마지막 매개 변수는 선택적 요소를 지정 된 데이터 형식의 배열을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="0a8c9-119">그러면 호출 코드를 프로시저에 임의 개수의 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="0a8c9-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-120">Required.</span></span> <span data-ttu-id="0a8c9-121">매개 변수를 나타내는 지역 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="0a8c9-122">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="0a8c9-123">매개 변수를 나타내는 지역 변수 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="0a8c9-124">에 필요한 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="0a8c9-125">매개 변수의 데이터 형식으로 계산 되는 모든 상수 또는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="0a8c9-126">형식이 `Object`, 또는 기본 값의 수만 지정 클래스, 인터페이스, 배열 또는 구조를 `Nothing`입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a8c9-127">설명</span><span class="sxs-lookup"><span data-stu-id="0a8c9-127">Remarks</span></span>  
 <span data-ttu-id="0a8c9-128">매개 변수는 괄호로 묶어 이며 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="0a8c9-129">데이터 형식과 매개 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="0a8c9-130">지정 하지 않는 경우 `parametertype`, 기본값은 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="0a8c9-131">호출 코드에서 프로시저를 호출 하면 전달 하는 *인수* 각 필수 매개 변수를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="0a8c9-132">자세한 내용은 [매개 변수 간의 차이점 및 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="0a8c9-133">호출 코드에서 각 매개 변수에 전달 인수가 호출 코드의 내부 요소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="0a8c9-134">이 요소가 있으면 *비가변* (상수, 리터럴, 열거형 또는 식)를 변경 하는 코드에 대 한 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="0a8c9-135">경우는 *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조 요소)를 호출 하는 코드에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="0a8c9-136">자세한 내용은 [수정할 간의 차이점 및 수정할 수 없는 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="0a8c9-137">Variable 요소에 전달 되는 경우 `ByRef`, 프로시저도 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="0a8c9-138">자세한 내용은 [차이점 간의 값과 By Reference 인수를 전달](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0a8c9-139">규칙</span><span class="sxs-lookup"><span data-stu-id="0a8c9-139">Rules</span></span>  
  
-   <span data-ttu-id="0a8c9-140">**괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8c9-140">**Parentheses.**</span></span> <span data-ttu-id="0a8c9-141">매개 변수 목록을 지정 하는 경우 괄호로 묶습니다 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="0a8c9-142">매개 변수가 없는 경우 빈 목록을 묶는 괄호를 여전히 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="0a8c9-143">이 요소는 프로시저 임을 명확히 설명 하 여 코드의 가독성을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="0a8c9-144">**선택적 매개 변수입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8c9-144">**Optional Parameters.**</span></span> <span data-ttu-id="0a8c9-145">사용 하는 경우는 `Optional` 매개 변수 한정자를 모든 후속 매개 변수 목록의 선택적 및를 사용 하 여 선언할 수는 `Optional` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="0a8c9-146">모든 선택적 매개 변수 선언을 제공 해야 합니다는 `defaultvalue` 절.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="0a8c9-147">자세한 내용은 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="0a8c9-148">**매개 변수 배열입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8c9-148">**Parameter Arrays.**</span></span> <span data-ttu-id="0a8c9-149">지정 해야 합니다 `ByVal` 에 대 한는 `ParamArray` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="0a8c9-150">둘 다 사용할 수 없습니다 `Optional` 고 `ParamArray` 동일한 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="0a8c9-151">자세한 내용은 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="0a8c9-152">**전달 메커니즘입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8c9-152">**Passing Mechanism.**</span></span> <span data-ttu-id="0a8c9-153">모든 인수에 대 한 기본 메커니즘은 `ByVal`, 프로시저를 의미 하는 내부 변수 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="0a8c9-154">그러나 요소 참조 형식이 면 프로시저를 수정할 수 내용이 나 기본 개체의 멤버는 대체 없거나 개체 자체를 다시 할당 하는 경우에.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="0a8c9-155">**매개 변수 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a8c9-155">**Parameter Names.**</span></span> <span data-ttu-id="0a8c9-156">매개 변수의 데이터 형식 배열인 경우에 따라 `parametername` 괄호 바로 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="0a8c9-157">매개 변수 이름에 대 한 자세한 내용은 참조 하세요. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a8c9-158">예제</span><span class="sxs-lookup"><span data-stu-id="0a8c9-158">Example</span></span>  
 <span data-ttu-id="0a8c9-159">다음 예제와 `Function` 두 매개 변수를 정의 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8c9-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0a8c9-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a8c9-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="0a8c9-161">Function 문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="0a8c9-162">Sub 문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0a8c9-163">Declare 문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="0a8c9-164">Structure 문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0a8c9-165">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="0a8c9-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="0a8c9-166">특성 개요</span><span class="sxs-lookup"><span data-stu-id="0a8c9-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="0a8c9-167">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="0a8c9-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
