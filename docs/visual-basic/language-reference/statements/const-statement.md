---
title: Const 문
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 3b05d4067ef99e03df07d2c316c982051180d961
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382109"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="74aa1-102">Const 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74aa1-102">Const Statement (Visual Basic)</span></span>

<span data-ttu-id="74aa1-103">하나 이상의 상수를 선언 하 고 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-103">Declares and defines one or more constants.</span></span>

## <a name="syntax"></a><span data-ttu-id="74aa1-104">구문</span><span class="sxs-lookup"><span data-stu-id="74aa1-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a><span data-ttu-id="74aa1-105">부분</span><span class="sxs-lookup"><span data-stu-id="74aa1-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="74aa1-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-106">Optional.</span></span> <span data-ttu-id="74aa1-107">이 문에 선언 된 모든 상수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="74aa1-108">꺾쇠 [Attribute List](attribute-list.md) 괄호 (" `<` " 및 "")의 특성 목록을 참조 하십시오 `>` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-108">See [Attribute List](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`accessmodifier`  
<span data-ttu-id="74aa1-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-109">Optional.</span></span> <span data-ttu-id="74aa1-110">이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="74aa1-111">[Public](../modifiers/public.md), [protected](../modifiers/protected.md), [Friend](../modifiers/friend.md), [protected friend](../modifiers/protected-friend.md), [private](../modifiers/private.md)또는 [private Protected](../modifiers/private-protected.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-111">Can be [Public](../modifiers/public.md), [Protected](../modifiers/protected.md), [Friend](../modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../modifiers/private.md), or [Private Protected](../modifiers/private-protected.md).</span></span>

`Shadows`  
<span data-ttu-id="74aa1-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-112">Optional.</span></span> <span data-ttu-id="74aa1-113">기본 클래스에서 프로그래밍 요소를 다시 선언 하 고 숨기는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="74aa1-114">[그림자](../modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74aa1-114">See [Shadows](../modifiers/shadows.md).</span></span>

`constantlist`  
<span data-ttu-id="74aa1-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="74aa1-115">Required.</span></span> <span data-ttu-id="74aa1-116">이 문에서 선언 되는 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-116">List of constants being declared in this statement.</span></span>

<span data-ttu-id="74aa1-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="74aa1-117">`constant` `[ ,` `constant` `... ]`</span></span>

<span data-ttu-id="74aa1-118">각 `constant`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-118">Each `constant` has the following syntax and parts:</span></span>

<span data-ttu-id="74aa1-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="74aa1-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>

|<span data-ttu-id="74aa1-120">부분</span><span class="sxs-lookup"><span data-stu-id="74aa1-120">Part</span></span>|<span data-ttu-id="74aa1-121">Description</span><span class="sxs-lookup"><span data-stu-id="74aa1-121">Description</span></span>|
|----------|-----------------|
|`constantname`|<span data-ttu-id="74aa1-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="74aa1-122">Required.</span></span> <span data-ttu-id="74aa1-123">상수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-123">Name of the constant.</span></span> <span data-ttu-id="74aa1-124">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74aa1-124">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`datatype`|<span data-ttu-id="74aa1-125">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="74aa1-126">상수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-126">Data type of the constant.</span></span>|
|`initializer`|<span data-ttu-id="74aa1-127">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="74aa1-127">Required.</span></span> <span data-ttu-id="74aa1-128">컴파일 시간에 평가 되 고 상수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|

## <a name="remarks"></a><span data-ttu-id="74aa1-129">설명</span><span class="sxs-lookup"><span data-stu-id="74aa1-129">Remarks</span></span>

<span data-ttu-id="74aa1-130">응용 프로그램에서 변경 되지 않는 값이 있는 경우 명명 된 상수를 정의 하 고 리터럴 값 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="74aa1-131">이름은 값 보다 쉽게 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="74aa1-132">상수를 한 번만 정의 하 고 코드의 여러 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="74aa1-133">이후 버전에서 값을 다시 정의 해야 하는 경우에는 `Const` 문을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>

<span data-ttu-id="74aa1-134">는 `Const` 모듈 또는 프로시저 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="74aa1-135">즉, 변수에 대 한 *선언 컨텍스트* 는 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 소스 파일, 네임 스페이스 또는 인터페이스 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="74aa1-136">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74aa1-136">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="74aa1-137">지역 상수 (프로시저 내)는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="74aa1-138">클래스 및 모듈 멤버 상수 (프로시저 외부)는 기본적으로 private access로, 구조체 멤버 상수는 기본적으로 공용 액세스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="74aa1-139">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-139">You can adjust their access levels with the access modifiers.</span></span>

## <a name="rules"></a><span data-ttu-id="74aa1-140">규칙</span><span class="sxs-lookup"><span data-stu-id="74aa1-140">Rules</span></span>

- <span data-ttu-id="74aa1-141">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-141">**Declaration Context.**</span></span> <span data-ttu-id="74aa1-142">프로시저 외부에서 모듈 수준에 선언 된 상수는 *멤버 상수*입니다. 선언 하는 클래스, 구조체 또는 모듈의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>

  <span data-ttu-id="74aa1-143">프로시저 수준에서 선언 된 상수는 *지역 상수*입니다. 선언 하는 프로시저 또는 블록에 대해 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>

- <span data-ttu-id="74aa1-144">**특성.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-144">**Attributes.**</span></span> <span data-ttu-id="74aa1-145">로컬 상수가 아닌 멤버 상수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="74aa1-146">특성은 어셈블리의 메타 데이터에 정보를 제공 하며,이는 로컬 상수와 같은 임시 저장소에는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>

- <span data-ttu-id="74aa1-147">**수정자.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-147">**Modifiers.**</span></span> <span data-ttu-id="74aa1-148">기본적으로 모든 상수는 `Shared` , `Static` 및 `ReadOnly` 입니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="74aa1-149">상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-149">You cannot use any of these keywords when declaring a constant.</span></span>

  <span data-ttu-id="74aa1-150">프로시저 수준에서 `Shadows` 또는 액세스 한정자를 사용 하 여 지역 상수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>

- <span data-ttu-id="74aa1-151">**여러 상수.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-151">**Multiple Constants.**</span></span> <span data-ttu-id="74aa1-152">각 상수에 대해 파트를 지정 하 여 동일한 선언문에서 여러 상수를 선언할 수 있습니다 `constantname` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="74aa1-153">여러 상수를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-153">Multiple constants are separated by commas.</span></span>

## <a name="data-type-rules"></a><span data-ttu-id="74aa1-154">데이터 형식 규칙</span><span class="sxs-lookup"><span data-stu-id="74aa1-154">Data Type Rules</span></span>

- <span data-ttu-id="74aa1-155">**데이터 형식.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-155">**Data Types.**</span></span> <span data-ttu-id="74aa1-156">`Const`문은 변수의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="74aa1-157">모든 데이터 형식 또는 열거형의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-157">You can specify any data type or the name of an enumeration.</span></span>

- <span data-ttu-id="74aa1-158">**기본 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-158">**Default Type.**</span></span> <span data-ttu-id="74aa1-159">을 지정 하지 않으면 `datatype` 상수는의 데이터 형식을 사용 합니다 `initializer` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="74aa1-160">및를 둘 다 지정 하 `datatype` `initializer` 는 경우의 데이터 형식을 `initializer` 으로 변환할 수 있어야 합니다 `datatype` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="74aa1-161">`datatype`및가 모두 `initializer` 없는 경우에는 데이터 형식이 기본적으로로 설정 `Object` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>

- <span data-ttu-id="74aa1-162">**서로 다른 형식.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-162">**Different Types.**</span></span> <span data-ttu-id="74aa1-163">`As`선언 하는 각 변수에 대해 별도의 절을 사용 하 여 상수에 대해 서로 다른 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="74aa1-164">그러나 공통 절을 사용 하 여 여러 개의 상수를 동일한 형식으로 선언할 수 없습니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>

- <span data-ttu-id="74aa1-165">**초기.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-165">**Initialization.**</span></span> <span data-ttu-id="74aa1-166">에서 모든 상수의 값을 초기화 해야 합니다 `constantlist` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="74aa1-167">을 사용 하 여 `initializer` 상수에 할당할 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="74aa1-168">식에는 리터럴, 이미 정의 된 다른 상수 및 이미 정의 된 열거형 멤버가 모두 조합 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="74aa1-169">산술 연산자와 논리 연산자를 사용 하 여 이러한 요소를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-169">You can use arithmetic and logical operators to combine such elements.</span></span>

  <span data-ttu-id="74aa1-170">에서는 변수나 함수를 사용할 수 없습니다 `initializer` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="74aa1-171">그러나 및와 같은 변환 키워드를 사용할 수 `CByte` 있습니다 `CShort` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="74aa1-172">`AscW`상수 또는 인수를 사용 하 여 호출 하는 경우 `String` `Char` 컴파일 시간에 계산할 수 있으므로를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

## <a name="behavior"></a><span data-ttu-id="74aa1-173">동작</span><span class="sxs-lookup"><span data-stu-id="74aa1-173">Behavior</span></span>

- <span data-ttu-id="74aa1-174">**범위.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-174">**Scope.**</span></span> <span data-ttu-id="74aa1-175">로컬 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="74aa1-176">멤버 상수는 클래스, 구조체 또는 모듈 내의 어디에서 나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>

- <span data-ttu-id="74aa1-177">**조인의.**</span><span class="sxs-lookup"><span data-stu-id="74aa1-177">**Qualification.**</span></span> <span data-ttu-id="74aa1-178">클래스, 구조체 또는 모듈 외부의 코드는 해당 클래스, 구조체 또는 모듈의 이름으로 멤버 상수의 이름을 한 정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="74aa1-179">프로시저 또는 블록 외부의 코드는 해당 프로시저나 블록 내의 지역 상수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>

## <a name="example"></a><span data-ttu-id="74aa1-180">예제</span><span class="sxs-lookup"><span data-stu-id="74aa1-180">Example</span></span>

<span data-ttu-id="74aa1-181">다음 예제에서는 문을 사용 하 여 `Const` 리터럴 값 대신 사용할 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a><span data-ttu-id="74aa1-182">예제</span><span class="sxs-lookup"><span data-stu-id="74aa1-182">Example</span></span>

<span data-ttu-id="74aa1-183">데이터 형식을 사용 하 여 상수를 정의 하는 경우 `Object` Visual Basic 컴파일러는 대신의 형식을 제공 합니다 `initializer` `Object` .</span><span class="sxs-lookup"><span data-stu-id="74aa1-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="74aa1-184">다음 예제에서 상수에는 `naturalLogBase` 런타임 형식이 `Decimal` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

<span data-ttu-id="74aa1-185">이전 예제에서는 <xref:System.Type.ToString%2A> 를 사용 하 여로 <xref:System.Type> 변환할 수 없기 때문에 [GetType 연산자](../operators/gettype-operator.md)에 의해 반환 되는 개체에서 메서드를 사용 <xref:System.Type> `String` `CStr` 합니다.</span><span class="sxs-lookup"><span data-stu-id="74aa1-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74aa1-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74aa1-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="74aa1-187">Enum 문</span><span class="sxs-lookup"><span data-stu-id="74aa1-187">Enum Statement</span></span>](enum-statement.md)
- [<span data-ttu-id="74aa1-188">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="74aa1-188">#Const Directive</span></span>](../directives/const-directive.md)
- [<span data-ttu-id="74aa1-189">Dim 문</span><span class="sxs-lookup"><span data-stu-id="74aa1-189">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="74aa1-190">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="74aa1-190">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="74aa1-191">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="74aa1-191">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="74aa1-192">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="74aa1-192">Constants and Enumerations</span></span>](../../programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="74aa1-193">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="74aa1-193">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="74aa1-194">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="74aa1-194">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
