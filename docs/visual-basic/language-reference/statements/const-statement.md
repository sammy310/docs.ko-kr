---
title: Const 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 993c46f36b3c7e1479204df361983380bd33f7d1
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72578860"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="2165a-102">Const 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2165a-102">Const Statement (Visual Basic)</span></span>

<span data-ttu-id="2165a-103">하나 이상의 상수를 선언 하 고 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-103">Declares and defines one or more constants.</span></span>

## <a name="syntax"></a><span data-ttu-id="2165a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2165a-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a><span data-ttu-id="2165a-105">요소</span><span class="sxs-lookup"><span data-stu-id="2165a-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="2165a-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2165a-106">Optional.</span></span> <span data-ttu-id="2165a-107">이 문에 선언 된 모든 상수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="2165a-108">꺾쇠 괄호 ("`<`" 및 "`>`")의 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2165a-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`accessmodifier`  
<span data-ttu-id="2165a-109">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2165a-109">Optional.</span></span> <span data-ttu-id="2165a-110">이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="2165a-111">[Public](../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [protected friend](../modifiers/protected-friend.md), [private](../../../visual-basic/language-reference/modifiers/private.md)또는 [private Protected](../../language-reference/modifiers/private-protected.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>

`Shadows`  
<span data-ttu-id="2165a-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2165a-112">Optional.</span></span> <span data-ttu-id="2165a-113">기본 클래스에서 프로그래밍 요소를 다시 선언 하 고 숨기는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="2165a-114">[그림자](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2165a-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`constantlist`  
<span data-ttu-id="2165a-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2165a-115">Required.</span></span> <span data-ttu-id="2165a-116">이 문에서 선언 되는 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-116">List of constants being declared in this statement.</span></span>

<span data-ttu-id="2165a-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="2165a-117">`constant` `[ ,` `constant` `... ]`</span></span>

<span data-ttu-id="2165a-118">각 `constant`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-118">Each `constant` has the following syntax and parts:</span></span>

<span data-ttu-id="2165a-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="2165a-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>

|<span data-ttu-id="2165a-120">파트</span><span class="sxs-lookup"><span data-stu-id="2165a-120">Part</span></span>|<span data-ttu-id="2165a-121">설명</span><span class="sxs-lookup"><span data-stu-id="2165a-121">Description</span></span>|
|----------|-----------------|
|`constantname`|<span data-ttu-id="2165a-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2165a-122">Required.</span></span> <span data-ttu-id="2165a-123">상수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-123">Name of the constant.</span></span> <span data-ttu-id="2165a-124">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2165a-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`datatype`|<span data-ttu-id="2165a-125">@No__t_0 `On` 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="2165a-126">상수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-126">Data type of the constant.</span></span>|
|`initializer`|<span data-ttu-id="2165a-127">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2165a-127">Required.</span></span> <span data-ttu-id="2165a-128">컴파일 시간에 평가 되 고 상수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2165a-129">주의</span><span class="sxs-lookup"><span data-stu-id="2165a-129">Remarks</span></span>

<span data-ttu-id="2165a-130">응용 프로그램에서 변경 되지 않는 값이 있는 경우 명명 된 상수를 정의 하 고 리터럴 값 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="2165a-131">이름은 값 보다 쉽게 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="2165a-132">상수를 한 번만 정의 하 고 코드의 여러 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="2165a-133">이후 버전에서 값을 다시 정의 해야 하는 경우에는 `Const` 문만 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>

<span data-ttu-id="2165a-134">모듈 또는 프로시저 수준 에서만 `Const`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="2165a-135">즉, 변수에 대 한 *선언 컨텍스트* 는 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 소스 파일, 네임 스페이스 또는 인터페이스 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="2165a-136">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2165a-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="2165a-137">지역 상수 (프로시저 내)는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="2165a-138">클래스 및 모듈 멤버 상수 (프로시저 외부)는 기본적으로 private access로, 구조체 멤버 상수는 기본적으로 공용 액세스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="2165a-139">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-139">You can adjust their access levels with the access modifiers.</span></span>

## <a name="rules"></a><span data-ttu-id="2165a-140">규칙</span><span class="sxs-lookup"><span data-stu-id="2165a-140">Rules</span></span>

- <span data-ttu-id="2165a-141">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="2165a-141">**Declaration Context.**</span></span> <span data-ttu-id="2165a-142">프로시저 외부에서 모듈 수준에 선언 된 상수는 *멤버 상수*입니다. 선언 하는 클래스, 구조체 또는 모듈의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>

  <span data-ttu-id="2165a-143">프로시저 수준에서 선언 된 상수는 *지역 상수*입니다. 선언 하는 프로시저 또는 블록에 대해 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>

- <span data-ttu-id="2165a-144">**특성.**</span><span class="sxs-lookup"><span data-stu-id="2165a-144">**Attributes.**</span></span> <span data-ttu-id="2165a-145">로컬 상수가 아닌 멤버 상수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="2165a-146">특성은 어셈블리의 메타 데이터에 정보를 제공 하며,이는 로컬 상수와 같은 임시 저장소에는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>

- <span data-ttu-id="2165a-147">**수정자.**</span><span class="sxs-lookup"><span data-stu-id="2165a-147">**Modifiers.**</span></span> <span data-ttu-id="2165a-148">기본적으로 모든 상수는 `Shared`, `Static` 및 `ReadOnly`입니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="2165a-149">상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-149">You cannot use any of these keywords when declaring a constant.</span></span>

  <span data-ttu-id="2165a-150">프로시저 수준에서 `Shadows` 또는 액세스 한정자를 사용 하 여 지역 상수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>

- <span data-ttu-id="2165a-151">**여러 상수.**</span><span class="sxs-lookup"><span data-stu-id="2165a-151">**Multiple Constants.**</span></span> <span data-ttu-id="2165a-152">동일한 선언문에서 여러 상수를 선언 하 여 각 상수에 대 한 `constantname` 부분을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="2165a-153">여러 상수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-153">Multiple constants are separated by commas.</span></span>

## <a name="data-type-rules"></a><span data-ttu-id="2165a-154">데이터 형식 규칙</span><span class="sxs-lookup"><span data-stu-id="2165a-154">Data Type Rules</span></span>

- <span data-ttu-id="2165a-155">**데이터 형식.**</span><span class="sxs-lookup"><span data-stu-id="2165a-155">**Data Types.**</span></span> <span data-ttu-id="2165a-156">@No__t_0 문은 변수의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="2165a-157">모든 데이터 형식 또는 열거형의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-157">You can specify any data type or the name of an enumeration.</span></span>

- <span data-ttu-id="2165a-158">**기본 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="2165a-158">**Default Type.**</span></span> <span data-ttu-id="2165a-159">@No__t_0 지정 하지 않으면 상수는 `initializer` 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="2165a-160">@No__t_0와 `initializer`를 모두 지정 하는 경우 `initializer`의 데이터 형식을 `datatype`로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="2165a-161">@No__t_0 또는 `initializer` 모두 없는 경우에는 데이터 형식이 기본적으로 `Object` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>

- <span data-ttu-id="2165a-162">**서로 다른 형식.**</span><span class="sxs-lookup"><span data-stu-id="2165a-162">**Different Types.**</span></span> <span data-ttu-id="2165a-163">선언 하는 각 변수에 대해 별도의 `As` 절을 사용 하 여 상수에 대해 서로 다른 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="2165a-164">그러나 일반적인 `As` 절을 사용 하 여 여러 개의 상수를 동일한 형식으로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>

- <span data-ttu-id="2165a-165">**초기.**</span><span class="sxs-lookup"><span data-stu-id="2165a-165">**Initialization.**</span></span> <span data-ttu-id="2165a-166">@No__t_0의 모든 상수 값을 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="2165a-167">@No__t_0 사용 하 여 상수에 할당할 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="2165a-168">식에는 리터럴, 이미 정의 된 다른 상수 및 이미 정의 된 열거형 멤버가 모두 조합 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="2165a-169">산술 연산자와 논리 연산자를 사용 하 여 이러한 요소를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-169">You can use arithmetic and logical operators to combine such elements.</span></span>

  <span data-ttu-id="2165a-170">@No__t_0 변수나 함수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="2165a-171">그러나 `CByte` 및 `CShort`와 같은 변환 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="2165a-172">상수 `String` 또는 `Char` 인수를 사용 하 여 호출 하는 경우 컴파일 시간에 계산할 수 있기 때문에 `AscW`를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

## <a name="behavior"></a><span data-ttu-id="2165a-173">동작</span><span class="sxs-lookup"><span data-stu-id="2165a-173">Behavior</span></span>

- <span data-ttu-id="2165a-174">**범위.**</span><span class="sxs-lookup"><span data-stu-id="2165a-174">**Scope.**</span></span> <span data-ttu-id="2165a-175">로컬 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="2165a-176">멤버 상수는 클래스, 구조체 또는 모듈 내의 어디에서 나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>

- <span data-ttu-id="2165a-177">**조인의.**</span><span class="sxs-lookup"><span data-stu-id="2165a-177">**Qualification.**</span></span> <span data-ttu-id="2165a-178">클래스, 구조체 또는 모듈 외부의 코드는 해당 클래스, 구조체 또는 모듈의 이름으로 멤버 상수의 이름을 한 정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="2165a-179">프로시저 또는 블록 외부의 코드는 해당 프로시저나 블록 내의 지역 상수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>

## <a name="example"></a><span data-ttu-id="2165a-180">예제</span><span class="sxs-lookup"><span data-stu-id="2165a-180">Example</span></span>

<span data-ttu-id="2165a-181">다음 예제에서는 `Const` 문을 사용 하 여 리터럴 값 대신 사용할 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a><span data-ttu-id="2165a-182">예제</span><span class="sxs-lookup"><span data-stu-id="2165a-182">Example</span></span>

<span data-ttu-id="2165a-183">@No__t_0 데이터 형식을 사용 하 여 상수를 정의 하는 경우 Visual Basic 컴파일러는 `Object` 대신 `initializer` 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="2165a-184">다음 예제에서는 상수 `naturalLogBase`에 `Decimal` 런타임 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

<span data-ttu-id="2165a-185">이전 예제에서는 `CStr`를 사용 하 여 `String`로 변환할 수 <xref:System.Type> 없기 때문에 [GetType 연산자](../../../visual-basic/language-reference/operators/gettype-operator.md)에서 반환 하는 <xref:System.Type> 개체에 대해 <xref:System.Type.ToString%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2165a-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2165a-186">참조</span><span class="sxs-lookup"><span data-stu-id="2165a-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="2165a-187">Enum 문</span><span class="sxs-lookup"><span data-stu-id="2165a-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="2165a-188">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="2165a-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="2165a-189">Dim 문</span><span class="sxs-lookup"><span data-stu-id="2165a-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="2165a-190">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="2165a-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="2165a-191">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="2165a-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="2165a-192">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="2165a-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="2165a-193">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="2165a-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="2165a-194">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="2165a-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
