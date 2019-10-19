---
title: Operator 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: c4fae40992fa665121aff637ae427ef0cafbf547
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582378"
---
# <a name="operator-statement"></a><span data-ttu-id="e3ed1-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="e3ed1-102">Operator Statement</span></span>

<span data-ttu-id="e3ed1-103">클래스 또는 구조체에서 연산자 프로시저를 정의 하는 연산자 기호, 피연산자 및 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3ed1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3ed1-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="e3ed1-105">요소</span><span class="sxs-lookup"><span data-stu-id="e3ed1-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="e3ed1-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e3ed1-106">Optional.</span></span> <span data-ttu-id="e3ed1-107">[특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="e3ed1-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-108">Required.</span></span> <span data-ttu-id="e3ed1-109">이 연산자 프로시저에 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 권한이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="e3ed1-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e3ed1-110">Optional.</span></span> <span data-ttu-id="e3ed1-111">[오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="e3ed1-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-112">Required.</span></span> <span data-ttu-id="e3ed1-113">이 연산자 프로시저가 [공유](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="e3ed1-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e3ed1-114">Optional.</span></span> <span data-ttu-id="e3ed1-115">[그림자](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="e3ed1-116">@No__t_0를 지정 하지 않는 한 변환 연산자에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="e3ed1-117">이 연산자 프로시저가 [확대](../../../visual-basic/language-reference/modifiers/widening.md) 변환을 정의 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="e3ed1-118">이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="e3ed1-119">@No__t_0를 지정 하지 않는 한 변환 연산자에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="e3ed1-120">이 연산자 프로시저가 [축소](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환을 정의 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="e3ed1-121">이 도움말 페이지의 "확대 및 축소 변환"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="e3ed1-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-122">Required.</span></span> <span data-ttu-id="e3ed1-123">이 연산자 프로시저가 정의 하는 연산자의 기호 또는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="e3ed1-124">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-124">Required.</span></span> <span data-ttu-id="e3ed1-125">단항 연산자의 단일 피연산자 이름 및 형식 (변환 연산자 포함) 또는 이항 연산자의 왼쪽 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="e3ed1-126">이항 연산자에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-126">Required for binary operators.</span></span> <span data-ttu-id="e3ed1-127">이항 연산자 오른쪽 피연산자의 이름과 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="e3ed1-128">`operand1` 및 `operand2`에는 다음과 같은 구문과 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="e3ed1-129">파트</span><span class="sxs-lookup"><span data-stu-id="e3ed1-129">Part</span></span>|<span data-ttu-id="e3ed1-130">설명</span><span class="sxs-lookup"><span data-stu-id="e3ed1-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="e3ed1-131">선택 사항 이지만 전달 메커니즘이 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="e3ed1-132">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-132">Required.</span></span> <span data-ttu-id="e3ed1-133">이 피연산자를 나타내는 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="e3ed1-134">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="e3ed1-135">@No__t_0 `On` 하지 않는 한 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="e3ed1-136">이 피연산자의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="e3ed1-137">@No__t_0 `On` 하지 않는 한 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="e3ed1-138">연산자 프로시저에서 반환 하는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="e3ed1-139">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e3ed1-139">Optional.</span></span> <span data-ttu-id="e3ed1-140">연산자 프로시저에서 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="e3ed1-141">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-141">Required.</span></span> <span data-ttu-id="e3ed1-142">연산자 프로시저가 호출 코드에 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="e3ed1-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-143">`End` `Operator`</span></span>  
<span data-ttu-id="e3ed1-144">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-144">Required.</span></span> <span data-ttu-id="e3ed1-145">이 연산자 프로시저의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3ed1-146">주의</span><span class="sxs-lookup"><span data-stu-id="e3ed1-146">Remarks</span></span>

<span data-ttu-id="e3ed1-147">클래스 또는 구조체 에서만 `Operator`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="e3ed1-148">즉, 연산자의 *선언 컨텍스트* 는 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="e3ed1-149">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="e3ed1-150">모든 연산자는 `Public Shared` 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="e3ed1-151">두 피연산자 중 하나에 대해 `ByRef`, `Optional` 또는 `ParamArray`를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="e3ed1-152">연산자 기호 또는 식별자를 사용 하 여 반환 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="e3ed1-153">@No__t_0 문을 사용 해야 하 고 값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="e3ed1-154">프로시저의 아무 곳에 나 원하는 수의 `Return` 문이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="e3ed1-155">이러한 방식으로 연산자를 정의 하는 것은 `Overloads` 키워드를 사용 하는지 여부에 관계 없이 *연산자 오버 로드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="e3ed1-156">다음 표에는 정의할 수 있는 연산자가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="e3ed1-157">Type</span><span class="sxs-lookup"><span data-stu-id="e3ed1-157">Type</span></span>|<span data-ttu-id="e3ed1-158">연산자</span><span class="sxs-lookup"><span data-stu-id="e3ed1-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="e3ed1-159">단항</span><span class="sxs-lookup"><span data-stu-id="e3ed1-159">Unary</span></span>|<span data-ttu-id="e3ed1-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="e3ed1-161">이항</span><span class="sxs-lookup"><span data-stu-id="e3ed1-161">Binary</span></span>|<span data-ttu-id="e3ed1-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="e3ed1-163">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="e3ed1-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="e3ed1-164">이진 목록의 `=` 연산자는 대입 연산자가 아닌 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="e3ed1-165">@No__t_0를 정의 하는 경우 `Widening` 또는 `Narrowing`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="e3ed1-166">짝이 되는 쌍</span><span class="sxs-lookup"><span data-stu-id="e3ed1-166">Matched Pairs</span></span>

<span data-ttu-id="e3ed1-167">특정 연산자를 일치 하는 쌍으로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="e3ed1-168">이러한 쌍의 연산자 중 하나를 정의 하는 경우 다른 연산자도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="e3ed1-169">일치 하는 쌍은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="e3ed1-170">`=` 및 `<>`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-170">`=` and `<>`</span></span>

- <span data-ttu-id="e3ed1-171">`>` 및 `<`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-171">`>` and `<`</span></span>

- <span data-ttu-id="e3ed1-172">`>=` 및 `<=`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-172">`>=` and `<=`</span></span>

- <span data-ttu-id="e3ed1-173">`IsTrue` 및 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="e3ed1-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="e3ed1-174">데이터 형식 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e3ed1-174">Data Type Restrictions</span></span>

<span data-ttu-id="e3ed1-175">정의 하는 모든 연산자는 정의 하는 클래스 또는 구조체를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="e3ed1-176">즉, 클래스 또는 구조체는 다음의 데이터 형식으로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="e3ed1-177">단항 연산자의 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="e3ed1-178">이항 연산자의 피연산자 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="e3ed1-179">변환 연산자의 피연산자 또는 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="e3ed1-180">특정 연산자에는 다음과 같은 추가 데이터 형식 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="e3ed1-181">@No__t_0 및 `IsFalse` 연산자를 정의 하는 경우 둘 다 `Boolean` 형식을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="e3ed1-182">@No__t_0 및 `>>` 연산자를 정의 하는 경우 `operand2` `operandtype`에 대 한 `Integer` 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="e3ed1-183">반환 형식은 두 피연산자의 형식에 해당 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="e3ed1-184">예를 들어 `=` 또는 `<>` 같은 비교 연산자는 두 피연산자가 모두 `Boolean` 되지 않은 경우에도 `Boolean`를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="e3ed1-185">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="e3ed1-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="e3ed1-186">@No__t_0, `Or`, `Not` 및 `Xor` 연산자는 Visual Basic에서 논리적 or 비트 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="e3ed1-187">그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우에는 비트 연산을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="e3ed1-188">@No__t_0 연산자는 `Operator` 문으로 직접 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="e3ed1-189">그러나 다음 조건을 충족 하는 경우 `AndAlso`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="e3ed1-190">@No__t_1에 사용 하려는 것과 동일한 피연산자 유형에 `And`를 정의 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="e3ed1-191">@No__t_0 정의는 사용자가 정의한 클래스 또는 구조체와 동일한 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="e3ed1-192">@No__t_1를 정의한 클래스 또는 구조체에 `IsFalse` 연산자를 정의 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="e3ed1-193">마찬가지로, 클래스 또는 구조체의 반환 형식을 사용 하 여 동일한 피연산자에 `Or`을 정의 하 고 클래스 또는 구조체에 `IsTrue`를 정의한 경우 `OrElse`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="e3ed1-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="e3ed1-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="e3ed1-195">*확대 변환은* 런타임에 항상 성공 하지만 *축소 변환은* 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="e3ed1-196">자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="e3ed1-197">@No__t_0 변환 프로시저를 선언 하는 경우 프로시저 코드에서 오류를 생성 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="e3ed1-198">이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-198">This means the following:</span></span>

- <span data-ttu-id="e3ed1-199">항상 `type` 형식의 유효한 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="e3ed1-200">가능한 모든 예외 및 기타 오류 조건을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="e3ed1-201">호출 하는 프로시저에서 반환 되는 모든 오류를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="e3ed1-202">변환 프로시저가 성공 하지 못할 수 있거나 처리 되지 않은 예외가 발생할 수 있는 경우 `Narrowing` 되도록 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="e3ed1-203">예제</span><span class="sxs-lookup"><span data-stu-id="e3ed1-203">Example</span></span>

<span data-ttu-id="e3ed1-204">다음 코드 예에서는 `Operator` 문을 사용 하 여 `And`, `Or`, `IsFalse` 및 `IsTrue` 연산자에 대 한 연산자 프로시저를 포함 하는 구조체의 개요를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="e3ed1-205">`And` 및 `Or`는 각각 `abc` 형식의 두 피연산자를 사용 하 고 `abc` 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="e3ed1-206">`IsFalse` 및 `IsTrue`는 `abc` 형식의 단일 피연산자를 사용 하 고 `Boolean`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="e3ed1-207">이러한 정의를 통해 호출 코드는 `abc` 형식의 피연산자를 사용 하 여 `And`, `AndAlso`, `Or` 및 `OrElse`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed1-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="e3ed1-208">참조</span><span class="sxs-lookup"><span data-stu-id="e3ed1-208">See also</span></span>

- [<span data-ttu-id="e3ed1-209">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="e3ed1-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="e3ed1-210">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="e3ed1-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="e3ed1-211">확장</span><span class="sxs-lookup"><span data-stu-id="e3ed1-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="e3ed1-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="e3ed1-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="e3ed1-213">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="e3ed1-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="e3ed1-214">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="e3ed1-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="e3ed1-215">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e3ed1-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e3ed1-216">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e3ed1-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="e3ed1-217">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="e3ed1-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="e3ed1-218">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="e3ed1-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
