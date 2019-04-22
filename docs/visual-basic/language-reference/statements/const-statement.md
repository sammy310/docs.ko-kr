---
title: Const 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 089c2dca99373f379e1eff319cf8c41242e5f135
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835312"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="aba56-102">Const 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aba56-102">Const Statement (Visual Basic)</span></span>
<span data-ttu-id="aba56-103">선언 하 고 하나 이상의 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-103">Declares and defines one or more constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba56-104">구문</span><span class="sxs-lookup"><span data-stu-id="aba56-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a><span data-ttu-id="aba56-105">요소</span><span class="sxs-lookup"><span data-stu-id="aba56-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="aba56-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-106">Optional.</span></span> <span data-ttu-id="aba56-107">이 문에서 선언 된 모든 상수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="aba56-108">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="aba56-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="aba56-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-109">Optional.</span></span> <span data-ttu-id="aba56-110">이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="aba56-111">수 [공용](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [개인](../../../visual-basic/language-reference/modifiers/private.md), 또는 [Private Protected](../../language-reference/modifiers/private-protected.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>
  
 `Shadows`  
 <span data-ttu-id="aba56-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-112">Optional.</span></span> <span data-ttu-id="aba56-113">이 사용 하 여 다시 선언 하 고 기본 클래스의 프로그래밍 요소를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="aba56-114">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `constantlist`  
 <span data-ttu-id="aba56-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aba56-115">Required.</span></span> <span data-ttu-id="aba56-116">이 문에서 선언 되는 상수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-116">List of constants being declared in this statement.</span></span>  
  
 <span data-ttu-id="aba56-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="aba56-117">`constant` `[ ,` `constant` `... ]`</span></span>  
  
 <span data-ttu-id="aba56-118">각 `constant`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-118">Each `constant` has the following syntax and parts:</span></span>  
  
 <span data-ttu-id="aba56-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="aba56-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>  
  
|<span data-ttu-id="aba56-120">파트</span><span class="sxs-lookup"><span data-stu-id="aba56-120">Part</span></span>|<span data-ttu-id="aba56-121">설명</span><span class="sxs-lookup"><span data-stu-id="aba56-121">Description</span></span>|  
|----------|-----------------|  
|`constantname`|<span data-ttu-id="aba56-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aba56-122">Required.</span></span> <span data-ttu-id="aba56-123">상수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-123">Name of the constant.</span></span> <span data-ttu-id="aba56-124">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aba56-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`datatype`|<span data-ttu-id="aba56-125">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="aba56-126">데이터 형식 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-126">Data type of the constant.</span></span>|  
|`initializer`|<span data-ttu-id="aba56-127">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aba56-127">Required.</span></span> <span data-ttu-id="aba56-128">컴파일 시 계산 되 고 상수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba56-129">설명</span><span class="sxs-lookup"><span data-stu-id="aba56-129">Remarks</span></span>  
 <span data-ttu-id="aba56-130">응용 프로그램에서 변경 되지 않는 값을 해야 하는 경우에 명명 된 상수를 정의할 수 있으며 리터럴 값 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="aba56-131">이름 값에 비해 기억 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="aba56-132">상수를 한 번만 정의 하 고 코드에서이 여러 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="aba56-133">이후 버전에서는 값을 재정의 해야 하는 경우는 `Const` 문을 변경 해야 할 유일한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>  
  
 <span data-ttu-id="aba56-134">사용할 수 있습니다 `Const` 모듈 또는 프로시저 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="aba56-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="aba56-135">즉, 합니다 *선언 컨텍스트* 변수에 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 원본 파일, 네임 스페이스 또는 인터페이스 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="aba56-136">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aba56-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="aba56-137">공용 액세스를 기본 프로시저의 경우) (내의 로컬 상수에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="aba56-138">클래스와 모듈 멤버 (외부 프로시저) 상수 기본적으로 개인 액세스 및 구조체 멤버 상수는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="aba56-139">액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-139">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="aba56-140">규칙</span><span class="sxs-lookup"><span data-stu-id="aba56-140">Rules</span></span>  
  
-   <span data-ttu-id="aba56-141">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-141">**Declaration Context.**</span></span> <span data-ttu-id="aba56-142">모든 프로시저 외부 모듈 수준에서 선언 된 상수는 *멤버 상수*, 클래스, 구조체의 멤버인 또는 선언 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>  
  
     <span data-ttu-id="aba56-143">프로시저 수준에서 선언 된 상수는를 *지역 상수*; 프로시저 또는 블록을 선언한 로컬 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>  
  
-   <span data-ttu-id="aba56-144">**특성입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-144">**Attributes.**</span></span> <span data-ttu-id="aba56-145">지역 상수 아니라 멤버 상수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="aba56-146">특성 지역 상수와 같은 임시 저장소에 의미가 없는 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>  
  
-   <span data-ttu-id="aba56-147">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-147">**Modifiers.**</span></span> <span data-ttu-id="aba56-148">기본적으로 모든 상수는 `Shared`하십시오 `Static`, 및 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="aba56-149">상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-149">You cannot use any of these keywords when declaring a constant.</span></span>  
  
     <span data-ttu-id="aba56-150">프로시저 수준에서 사용할 수 없습니다 `Shadows` 또는 액세스 한정자를 지역 상수 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>  
  
-   <span data-ttu-id="aba56-151">**여러 상수입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-151">**Multiple Constants.**</span></span> <span data-ttu-id="aba56-152">동일한 선언문에서 여러 개의 상수를 선언할 수 있습니다 지정 하는 `constantname` 각각에 대 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="aba56-153">여러 상수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-153">Multiple constants are separated by commas.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="aba56-154">데이터 형식 규칙</span><span class="sxs-lookup"><span data-stu-id="aba56-154">Data Type Rules</span></span>  
  
-   <span data-ttu-id="aba56-155">**데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-155">**Data Types.**</span></span> <span data-ttu-id="aba56-156">`Const` 문은 데이터 형식의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="aba56-157">모든 데이터 형식이 나 열거형의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-157">You can specify any data type or the name of an enumeration.</span></span>  
  
-   <span data-ttu-id="aba56-158">**기본 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-158">**Default Type.**</span></span> <span data-ttu-id="aba56-159">지정 하지 않는 경우 `datatype`, 상수는 데이터 형식의 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="aba56-160">둘 다 지정 하는 경우 `datatype` 하 고 `initializer`, 데이터 형식 `initializer` 변환할 수 있어야 합니다 `datatype`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="aba56-161">모두 `datatype` 나 `initializer` 가 있는 경우 데이터 형식이 기본값으로 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>  
  
-   <span data-ttu-id="aba56-162">**다른 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-162">**Different Types.**</span></span> <span data-ttu-id="aba56-163">별도 사용 하 여 서로 다른 데이터 형식이 서로 다른 상수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대 한 절.</span><span class="sxs-lookup"><span data-stu-id="aba56-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="aba56-164">그러나 일반적인 사용 하 여 동일한 형식으로 여러 상수를 선언할 수 없습니다 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="aba56-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>  
  
-   <span data-ttu-id="aba56-165">**초기화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-165">**Initialization.**</span></span> <span data-ttu-id="aba56-166">모든 상수 값을 초기화 해야 `constantlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="aba56-167">사용할 `initializer` 상수에 할당할 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="aba56-168">식에는 리터럴, 이미 정의 되어 있는 다른 상수 및 이미 정의 된 열거형 멤버의 조합일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="aba56-169">이러한 요소를 결합 하 여 산술 및 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-169">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
     <span data-ttu-id="aba56-170">변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="aba56-171">와 같은 변환 키워드를 사용할 수는 있지만 `CByte` 고 `CShort`입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="aba56-172">사용할 수도 있습니다 `AscW` 상수를 사용 하 여 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 평가할 수 있는 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="aba56-173">동작</span><span class="sxs-lookup"><span data-stu-id="aba56-173">Behavior</span></span>  
  
-   <span data-ttu-id="aba56-174">**범위입니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-174">**Scope.**</span></span> <span data-ttu-id="aba56-175">지역 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="aba56-176">상수 멤버는 클래스, 구조체 또는 모듈 내의 모든 위치에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>  
  
-   <span data-ttu-id="aba56-177">**정규화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="aba56-177">**Qualification.**</span></span> <span data-ttu-id="aba56-178">코드 클래스 이외에 구조체 또는 모듈 이름을 한 정해야 멤버 상수의 해당 클래스, 구조체 또는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="aba56-179">코드 외부 프로시저 또는 블록을 해당 프로시저 또는 블록 내에 있는 로컬 상수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aba56-180">예제</span><span class="sxs-lookup"><span data-stu-id="aba56-180">Example</span></span>  
 <span data-ttu-id="aba56-181">다음 예제에서는 `Const` 문을 리터럴 값 대신 사용 하 여 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="aba56-182">예제</span><span class="sxs-lookup"><span data-stu-id="aba56-182">Example</span></span>  
 <span data-ttu-id="aba56-183">데이터 형식을 사용 하 여 상수를 정의 하는 경우 `Object`, Visual Basic 컴파일러의 형식을 제공 `initializer`를 대신 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="aba56-184">다음 예제에서는 상수 `naturalLogBase` 런타임 형식이 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 <span data-ttu-id="aba56-185">앞의 예제에서는 <xref:System.Type.ToString%2A> 메서드를 <xref:System.Type> 에서 반환 된 개체를 [GetType 연산자](../../../visual-basic/language-reference/operators/gettype-operator.md)이므로 <xref:System.Type> 변환할 수 없습니다 `String` 를 사용 하 여 `CStr`합니다.</span><span class="sxs-lookup"><span data-stu-id="aba56-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba56-186">참고자료</span><span class="sxs-lookup"><span data-stu-id="aba56-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="aba56-187">Enum 문</span><span class="sxs-lookup"><span data-stu-id="aba56-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="aba56-188">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="aba56-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="aba56-189">Dim 문</span><span class="sxs-lookup"><span data-stu-id="aba56-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="aba56-190">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="aba56-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="aba56-191">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="aba56-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="aba56-192">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="aba56-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="aba56-193">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="aba56-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="aba56-194">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="aba56-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
