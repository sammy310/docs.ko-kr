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
ms.openlocfilehash: 184970d33aae4af135153f9d6f6755770bdf84f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818594"
---
# <a name="operator-statement"></a><span data-ttu-id="1c074-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1c074-102">Operator Statement</span></span>
<span data-ttu-id="1c074-103">연산자 기호, 피연산자 및 클래스 또는 구조체에서 연산자 프로시저를 정의 하는 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c074-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c074-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="1c074-105">요소</span><span class="sxs-lookup"><span data-stu-id="1c074-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="1c074-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-106">Optional.</span></span> <span data-ttu-id="1c074-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="1c074-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-108">Required.</span></span> <span data-ttu-id="1c074-109">이 연산자 프로시저가 있음을 나타냅니다 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="1c074-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-110">Optional.</span></span> <span data-ttu-id="1c074-111">참조 [오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="1c074-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-112">Required.</span></span> <span data-ttu-id="1c074-113">이 연산자 프로시저 임을 나타냅니다는 [공유](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="1c074-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-114">Optional.</span></span> <span data-ttu-id="1c074-115">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="1c074-116">지정 하지 않으면 변환 연산자에 필요한 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="1c074-117">이 연산자 프로시저 정의 함을 나타냅니다는 [Widening](../../../visual-basic/language-reference/modifiers/widening.md) 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="1c074-118">이 도움말 페이지에 "확대 변환과 축소 변환"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c074-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="1c074-119">지정 하지 않으면 변환 연산자에 필요한 `Widening`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="1c074-120">이 연산자 프로시저 정의 함을 나타냅니다는 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="1c074-121">이 도움말 페이지에 "확대 변환과 축소 변환"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c074-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="1c074-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-122">Required.</span></span> <span data-ttu-id="1c074-123">기호 또는이 연산자 프로시저 정의 하는 연산자의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="1c074-124">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-124">Required.</span></span> <span data-ttu-id="1c074-125">이름과 (변환 연산자를 포함 하 여) 단항 연산자의 단일 피연산자는 이항 연산자의 왼쪽된 피연산자의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="1c074-126">이항 연산자에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-126">Required for binary operators.</span></span> <span data-ttu-id="1c074-127">이름과 이항 연산자의 오른쪽 피연산자의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="1c074-128">`operand1` 및 `operand2` 는 다음과 같은 구문 및 부분:</span><span class="sxs-lookup"><span data-stu-id="1c074-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="1c074-129">파트</span><span class="sxs-lookup"><span data-stu-id="1c074-129">Part</span></span>|<span data-ttu-id="1c074-130">설명</span><span class="sxs-lookup"><span data-stu-id="1c074-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="1c074-131">선택 사항 이지만 전달 메커니즘 이어야 합니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="1c074-132">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-132">Required.</span></span> <span data-ttu-id="1c074-133">이 피연산자를 나타내는 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="1c074-134">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c074-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="1c074-135">선택적 경우가 아니면 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="1c074-136">이 피연산자의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="1c074-137">선택적 경우가 아니면 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="1c074-138">연산자 프로시저 값의 데이터 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="1c074-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-139">Optional.</span></span> <span data-ttu-id="1c074-140">블록에서 연산자 프로시저를 실행 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="1c074-141">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-141">Required.</span></span> <span data-ttu-id="1c074-142">연산자 프로시저가 호출 코드에 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="1c074-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="1c074-143">`End` `Operator`</span></span>  
 <span data-ttu-id="1c074-144">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1c074-144">Required.</span></span> <span data-ttu-id="1c074-145">이 연산자 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c074-146">설명</span><span class="sxs-lookup"><span data-stu-id="1c074-146">Remarks</span></span>  
 <span data-ttu-id="1c074-147">사용할 수 있습니다 `Operator` 클래스 또는 구조체에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="1c074-148">즉, 합니다 *선언 컨텍스트* 연산자는 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="1c074-149">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c074-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="1c074-150">모든 연산자는 반드시 `Public Shared`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="1c074-151">지정할 수 없습니다 `ByRef`, `Optional`, 또는 `ParamArray` 두 피연산자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="1c074-152">반환 값을 저장 하는 연산자 기호 또는 식별자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="1c074-153">사용 해야는 `Return` 문 및 해당 값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="1c074-154">임의 개수의 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="1c074-155">연산자 정의 하는 이러한 방식으로 라고 *연산자 오버 로드*사용 여부는 `Overloads` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="1c074-156">다음 표에는 정의할 수 있는 연산자가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="1c074-157">형식</span><span class="sxs-lookup"><span data-stu-id="1c074-157">Type</span></span>|<span data-ttu-id="1c074-158">연산자</span><span class="sxs-lookup"><span data-stu-id="1c074-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="1c074-159">단항</span><span class="sxs-lookup"><span data-stu-id="1c074-159">Unary</span></span>|<span data-ttu-id="1c074-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="1c074-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="1c074-161">이항</span><span class="sxs-lookup"><span data-stu-id="1c074-161">Binary</span></span>|<span data-ttu-id="1c074-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="1c074-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="1c074-163">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="1c074-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="1c074-164">`=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="1c074-165">정의 하는 경우 `CType`를 지정 해야 `Widening` 또는 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="1c074-166">일치 하는 쌍</span><span class="sxs-lookup"><span data-stu-id="1c074-166">Matched Pairs</span></span>  
 <span data-ttu-id="1c074-167">일치 하는 쌍으로 특정 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="1c074-168">이러한 쌍의 두 연산자를 정의 하는 경우 다른도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="1c074-169">일치 하는 쌍 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="1c074-170">`=` 및 `<>`</span><span class="sxs-lookup"><span data-stu-id="1c074-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="1c074-171">`>` 및 `<`</span><span class="sxs-lookup"><span data-stu-id="1c074-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="1c074-172">`>=` 및 `<=`</span><span class="sxs-lookup"><span data-stu-id="1c074-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="1c074-173">`IsTrue` 및 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="1c074-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="1c074-174">데이터 형식 제한 사항</span><span class="sxs-lookup"><span data-stu-id="1c074-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="1c074-175">정의한 모든 연산자는 클래스 또는 구조체 정의를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="1c074-176">이 클래스 또는 구조체의 다음 데이터 형식으로 표시 되어야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="1c074-177">단항 연산자의 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="1c074-178">하나 이상의 이항 연산자의 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="1c074-179">피연산자 또는 변환 연산자의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="1c074-180">특정 연산자에는 제한 사항 다음과 같이 입력 하는 추가 데이터:</span><span class="sxs-lookup"><span data-stu-id="1c074-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="1c074-181">정의 하는 경우는 `IsTrue` 하 고 `IsFalse` 연산자를 모두 반환 해야 합니다 `Boolean` 형식.</span><span class="sxs-lookup"><span data-stu-id="1c074-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="1c074-182">정의 하는 경우는 `<<` 및 `>>` 연산자는 둘 다 지정 해야 합니다 `Integer` 에 대 한 입력을 `operandtype` 의 `operand2`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="1c074-183">두 피연산자의 형식에 해당 하는 반환 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="1c074-184">예를 들어, 비교 연산자와 같은 `=` 또는 `<>` 반환할 수 있습니다 `Boolean` 도 아닌 경우 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="1c074-185">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="1c074-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="1c074-186">합니다 `And`, `Or`를 `Not`, 및 `Xor` 연산자 Visual Basic의 논리 또는 비트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="1c074-187">그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우 해당 연산을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="1c074-188">정의할 수 없습니다는 `AndAlso` 연산자를 사용 하 여 직접는 `Operator` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="1c074-189">사용할 수 있습니다 `AndAlso` 다음 조건을 충족 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="1c074-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="1c074-190">정의한 `And` 에 대 한 사용 하려는 같은 피연산자 유형에 따라 `AndAlso`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="1c074-191">정의 `And` 클래스 또는 구조체를 정의한 것과 동일한 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="1c074-192">정의한 합니다 `IsFalse` 연산자를 정의한 클래스 또는 구조체에서 `And`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="1c074-193">마찬가지로, 사용할 수 있습니다 `OrElse` 정의 하는 경우 `Or` 동일한 피연산자에서 클래스 또는 구조체의 반환 형식을 사용 하 여 정의한 `IsTrue` 클래스 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="1c074-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="1c074-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="1c074-195">A *확대 변환은* 런타임 시 항상 성공 하는 동안를 *축소 변환* 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="1c074-196">자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c074-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="1c074-197">변환 프로시저를 선언 하는 경우 `Widening`, 프로시저 코드가 발생 한 모든 오류를 생성 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="1c074-198">이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-198">This means the following:</span></span>  
  
-   <span data-ttu-id="1c074-199">형식의 올바른 값을 반환 항상 해야 `type`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="1c074-200">모든 예외 및 다른 오류 조건을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="1c074-201">호출 하는 프로시저의 모든 오류 반환을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="1c074-202">되도록 선언 해야 변환 프로시저 성공 하지 않을 수 있는 가능성이 없거나는 처리 되지 않은 예외가 발생할 수 있습니다, `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c074-203">예제</span><span class="sxs-lookup"><span data-stu-id="1c074-203">Example</span></span>  
 <span data-ttu-id="1c074-204">다음 코드 예제에서는 합니다 `Operator` 연산자 프로시저를 포함 하는 구조체의 윤곽선을 정의 하는 문을 합니다 `And`, `Or`, `IsFalse`, 및 `IsTrue` 연산자.</span><span class="sxs-lookup"><span data-stu-id="1c074-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="1c074-205">`And` 및 `Or` 형식의 두 개의 피연산자 `abc` 반환 형식 및 `abc`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="1c074-206">`IsFalse` 및 `IsTrue` 형식의 단일 피연산자를 각각 사용 `abc` 돌아와 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="1c074-207">이러한 정의 사용 하도록 호출 코드를 사용 하면 `And`, `AndAlso`를 `Or`, 및 `OrElse` 형식의 피연산자를 사용 하 여 `abc`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]  
  
## <a name="see-also"></a><span data-ttu-id="1c074-208">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c074-208">See also</span></span>

- [<span data-ttu-id="1c074-209">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="1c074-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="1c074-210">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="1c074-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="1c074-211">확장</span><span class="sxs-lookup"><span data-stu-id="1c074-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="1c074-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="1c074-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="1c074-213">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="1c074-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1c074-214">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="1c074-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="1c074-215">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="1c074-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="1c074-216">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="1c074-217">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="1c074-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="1c074-218">방법: 연산자를 정의 하는 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c074-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
