---
title: Enum 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: be1780b00b4d58964e1de5ec199cb80dc0f9dba5
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583401"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="235a3-102">Enum 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="235a3-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="235a3-103">열거형을 선언 하 고 해당 멤버의 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="235a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="235a3-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="235a3-105">요소</span><span class="sxs-lookup"><span data-stu-id="235a3-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="235a3-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="235a3-106">Optional.</span></span> <span data-ttu-id="235a3-107">이 열거형에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="235a3-108">[특성 목록을](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호 ("`<`" 및 "`>`")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="235a3-109">@No__t_0 특성은 열거형의 인스턴스 값에 여러 열거형 멤버가 포함 될 수 있고 각 멤버가 열거형 값의 비트 필드를 나타내는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="235a3-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="235a3-110">Optional.</span></span> <span data-ttu-id="235a3-111">이 열거형에 액세스할 수 있는 코드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="235a3-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="235a3-113">Public</span><span class="sxs-lookup"><span data-stu-id="235a3-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="235a3-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="235a3-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="235a3-115">Friend</span><span class="sxs-lookup"><span data-stu-id="235a3-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="235a3-116">전용</span><span class="sxs-lookup"><span data-stu-id="235a3-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="235a3-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="235a3-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="235a3-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="235a3-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="235a3-119">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="235a3-119">Optional.</span></span> <span data-ttu-id="235a3-120">이 열거형이 기본 클래스에서 동일 하 게 명명 된 프로그래밍 요소 또는 오버 로드 된 요소 집합을 요소가 하 고 숨기도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="235a3-121">열거형은 해당 멤버가 아니라 열거형 자체 [에서만 지정할 수](../../../visual-basic/language-reference/modifiers/shadows.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="235a3-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="235a3-122">Required.</span></span> <span data-ttu-id="235a3-123">열거형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-123">Name of the enumeration.</span></span> <span data-ttu-id="235a3-124">올바른 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="235a3-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="235a3-125">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="235a3-125">Optional.</span></span> <span data-ttu-id="235a3-126">열거형 및 모든 해당 멤버의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="235a3-127">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="235a3-127">Required.</span></span> <span data-ttu-id="235a3-128">이 문에서 선언 되는 멤버 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="235a3-129">개별 소스 코드 줄에 여러 멤버가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="235a3-130">각 `member`에는 다음과 같은 구문과 파트가 있습니다. `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="235a3-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="235a3-131">파트</span><span class="sxs-lookup"><span data-stu-id="235a3-131">Part</span></span>|<span data-ttu-id="235a3-132">설명</span><span class="sxs-lookup"><span data-stu-id="235a3-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="235a3-133">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="235a3-133">Required.</span></span> <span data-ttu-id="235a3-134">이 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="235a3-135">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="235a3-135">Optional.</span></span> <span data-ttu-id="235a3-136">컴파일 시간에 평가 되 고이 멤버에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="235a3-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="235a3-137">`End` `Enum`</span></span>

  <span data-ttu-id="235a3-138">`Enum` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="235a3-139">주의</span><span class="sxs-lookup"><span data-stu-id="235a3-139">Remarks</span></span>

<span data-ttu-id="235a3-140">논리적으로 서로 관련 된 변경 되지 않은 값 집합이 있는 경우 열거형에서 함께 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="235a3-141">이는 열거형 및 해당 멤버에 대 한 의미 있는 이름을 제공 하며, 값 보다 쉽게 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="235a3-142">그런 다음 코드의 여러 위치에서 열거형 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="235a3-143">열거를 사용 하는 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="235a3-144">바꾸려면 또는 잘못 된 숫자로 인 한 오류를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="235a3-145">를 사용 하면 나중에 값을 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="235a3-146">코드를 더 쉽게 읽을 수 있습니다. 즉, 오류가 발생할 가능성이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="235a3-147">이전 버전과의 호환성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-147">Ensures forward compatibility.</span></span> <span data-ttu-id="235a3-148">열거를 사용 하는 경우 나중에 누군가가 멤버 이름에 해당 하는 값을 변경 하면 코드가 실패할 가능성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="235a3-149">열거형에는 이름, 기본 데이터 형식 및 멤버 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="235a3-150">각 멤버는 상수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-150">Each member represents a constant.</span></span>

<span data-ttu-id="235a3-151">프로시저 외부의 클래스, 구조체, 모듈 또는 인터페이스 수준에서 선언 된 열거형은 *멤버 열거형*입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="235a3-152">선언 하는 클래스, 구조체, 모듈 또는 인터페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="235a3-153">멤버 열거형은 클래스, 구조체, 모듈 또는 인터페이스 내의 어디에서 나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="235a3-154">클래스, 구조체 또는 모듈 외부의 코드는 해당 클래스, 구조체 또는 모듈의 이름을 사용 하 여 멤버 열거형의 이름을 한정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="235a3-155">소스 파일에 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 문을 추가 하 여 정규화 된 이름을 사용 하지 않아도 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="235a3-156">모든 클래스, 구조체, 모듈 또는 인터페이스 외부에서 네임 스페이스 수준에 선언 된 열거형은 해당 열거형이 표시 되는 네임 스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="235a3-157">열거형의 *선언 컨텍스트* 는 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="235a3-158">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="235a3-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="235a3-159">특성을 열거형 전체에 적용할 수 있지만 해당 멤버를 개별적으로 적용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="235a3-160">특성은 어셈블리의 메타 데이터에 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="235a3-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="235a3-161">Data Type</span></span>

<span data-ttu-id="235a3-162">@No__t_0 문은 열거형의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="235a3-163">각 멤버는 열거형의 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="235a3-164">@No__t_0, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong` 또는 `UShort` 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="235a3-165">열거형에 `datatype` 지정 하지 않으면 각 멤버가 해당 `initializer`의 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="235a3-166">@No__t_0와 `initializer`를 모두 지정 하는 경우 `initializer`의 데이터 형식을 `datatype`로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="235a3-167">@No__t_0 또는 `initializer` 모두 없는 경우에는 데이터 형식이 기본적으로 `Integer` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="235a3-168">멤버 초기화</span><span class="sxs-lookup"><span data-stu-id="235a3-168">Initializing Members</span></span>

<span data-ttu-id="235a3-169">@No__t_0 문은 `memberlist`에서 선택 된 멤버의 콘텐츠를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="235a3-170">@No__t_0를 사용 하 여 멤버에 할당할 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="235a3-171">멤버에 대 한 `initializer` 지정 하지 않으면 Visual Basic는 0 (`memberlist`의 첫 번째 `member`)으로 초기화 하거나 바로 앞의 `member` 보다 큰 값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="235a3-172">각 `initializer`에 제공 되는 식은 리터럴, 이미 정의 된 다른 상수 및이 열거형의 이전 멤버를 포함 하 여 이미 정의 된 열거형 멤버의 조합일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="235a3-173">산술 연산자와 논리 연산자를 사용 하 여 이러한 요소를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="235a3-174">@No__t_0 변수나 함수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="235a3-175">그러나 `CByte` 및 `CShort`와 같은 변환 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="235a3-176">상수 `String` 또는 `Char` 인수를 사용 하 여 호출 하는 경우 컴파일 시간에 계산할 수 있기 때문에 `AscW`를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="235a3-177">열거형에는 부동 소수점 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="235a3-178">멤버에 부동 소수점 값이 할당 되 고 `Option Strict`가 on으로 설정 된 경우 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="235a3-179">@No__t_0 해제 되어 있으면 값이 자동으로 `Enum` 형식으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="235a3-180">멤버의 값이 기본 데이터 형식에 대해 허용 가능한 범위를 초과 하거나 멤버를 기본 데이터 형식에서 허용 하는 최대 값으로 초기화 하는 경우 컴파일러에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="235a3-181">한정자</span><span class="sxs-lookup"><span data-stu-id="235a3-181">Modifiers</span></span>

<span data-ttu-id="235a3-182">클래스, 구조체, 모듈 및 인터페이스 멤버 열거형은 기본적으로 공용 액세스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="235a3-183">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="235a3-184">네임 스페이스 멤버 열거형은 기본적으로 friend 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="235a3-185">액세스 수준을 공용으로 조정할 수 있지만 비공개 또는 protected로는 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="235a3-186">자세한 내용은 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="235a3-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="235a3-187">모든 열거형 멤버는 공용 액세스 권한을 가지 며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="235a3-188">그러나 열거 자체의 액세스 수준이 더 제한적인 경우에는 지정 된 열거형 액세스 수준이 우선 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="235a3-189">기본적으로 모든 열거형은 형식이 고 해당 필드는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="235a3-190">따라서 열거형 또는 해당 멤버를 선언 하는 경우 `Shared`, `Static` 및 `ReadOnly` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="235a3-191">다중 값 할당</span><span class="sxs-lookup"><span data-stu-id="235a3-191">Assigning Multiple Values</span></span>

<span data-ttu-id="235a3-192">열거형은 일반적으로 상호 배타적인 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="235a3-193">@No__t_1 선언에 <xref:System.FlagsAttribute> 특성을 포함 하 여 대신 열거형의 인스턴스에 여러 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="235a3-194">@No__t_0 특성은 열거형을 비트 필드 즉, 플래그 집합으로 처리 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="235a3-195">이를 *비트* 열거형 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="235a3-196">@No__t_0 특성을 사용 하 여 열거형을 선언 하는 경우 값에 대해 1, 2, 4, 8, 16 등의 제곱을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="235a3-197">또한 값이 0 인 멤버의 이름을 "None"으로 지정할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="235a3-198">추가 지침은 <xref:System.FlagsAttribute> 및 <xref:System.Enum>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="235a3-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="235a3-199">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-199">Example</span></span>

<span data-ttu-id="235a3-200">다음 예제에서는 `Enum` 문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="235a3-201">멤버는 `Medium` 아닌 `EggSizeEnum.Medium` 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="235a3-202">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-202">Example</span></span>

<span data-ttu-id="235a3-203">다음 예제의 메서드는 `Egg` 클래스 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="235a3-204">따라서 `EggSizeEnum`은 `Egg.EggSizeEnum`으로 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="235a3-205">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-205">Example</span></span>

<span data-ttu-id="235a3-206">다음 예에서는 `Enum` 문을 사용 하 여 명명 된 상수 값의 관련 된 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="235a3-207">이 경우 값은 데이터베이스에 대 한 데이터 입력 양식을 디자인 하도록 선택할 수 있는 색입니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="235a3-208">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-208">Example</span></span>

<span data-ttu-id="235a3-209">다음 예에서는 양수 및 음수를 모두 포함 하는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="235a3-210">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-210">Example</span></span>

<span data-ttu-id="235a3-211">다음 예제에서는 `As` 절을 사용 하 여 열거형의 `datatype`를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="235a3-212">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-212">Example</span></span>

<span data-ttu-id="235a3-213">다음 예제에서는 비트 열거를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="235a3-214">비트 열거의 인스턴스에 여러 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="235a3-215">@No__t_0 선언에는 열거형을 플래그 집합으로 처리할 수 있음을 나타내는 <xref:System.FlagsAttribute> 특성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="235a3-216">예제</span><span class="sxs-lookup"><span data-stu-id="235a3-216">Example</span></span>

<span data-ttu-id="235a3-217">다음 예제에서는 열거형을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="235a3-218">@No__t_0 메서드를 사용 하 여 열거형에서 멤버 이름 배열을 검색 하 고 <xref:System.Enum.GetValues%2A> 멤버 값의 배열을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="235a3-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="235a3-219">참조</span><span class="sxs-lookup"><span data-stu-id="235a3-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="235a3-220">Const 문</span><span class="sxs-lookup"><span data-stu-id="235a3-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="235a3-221">Dim 문</span><span class="sxs-lookup"><span data-stu-id="235a3-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="235a3-222">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="235a3-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="235a3-223">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="235a3-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="235a3-224">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="235a3-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
