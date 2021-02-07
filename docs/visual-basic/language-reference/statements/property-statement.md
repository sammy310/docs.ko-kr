---
description: '자세히 알아보기: Property 문'
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 95f2ac1f993fc8698d2033dfe50d925cd55a7dc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741395"
---
# <a name="property-statement"></a><span data-ttu-id="cccba-103">Property Statement</span><span class="sxs-lookup"><span data-stu-id="cccba-103">Property Statement</span></span>

<span data-ttu-id="cccba-104">속성의 이름과 속성 값을 저장 하 고 검색 하는 데 사용 되는 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-104">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="cccba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cccba-105">Syntax</span></span>

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a><span data-ttu-id="cccba-106">부분</span><span class="sxs-lookup"><span data-stu-id="cccba-106">Parts</span></span>

- `attributelist`

  <span data-ttu-id="cccba-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-107">Optional.</span></span> <span data-ttu-id="cccba-108">이 속성 또는 프로시저에 적용 되는 특성의 목록입니다 `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="cccba-108">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="cccba-109">[특성 목록](attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cccba-109">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="cccba-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-110">Optional.</span></span> <span data-ttu-id="cccba-111">이 속성이 정의 된 클래스 또는 구조체에 대 한 기본 속성 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-111">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="cccba-112">기본 속성은 매개 변수를 허용 해야 하며 속성 이름을 지정 하지 않고 설정 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-112">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="cccba-113">속성을로 선언 하는 경우 속성 `Default` 또는 속성 프로시저 중 하나에서을 사용할 수 없습니다 `Private` .</span><span class="sxs-lookup"><span data-stu-id="cccba-113">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="cccba-114">`Property`문과 및 문 중 하나 이상에 대 한 선택 사항 `Get` 입니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="cccba-114">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="cccba-115">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-115">Can be one of the following:</span></span>

  - [<span data-ttu-id="cccba-116">공용</span><span class="sxs-lookup"><span data-stu-id="cccba-116">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="cccba-117">보호됨</span><span class="sxs-lookup"><span data-stu-id="cccba-117">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="cccba-118">Friend</span><span class="sxs-lookup"><span data-stu-id="cccba-118">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="cccba-119">개인</span><span class="sxs-lookup"><span data-stu-id="cccba-119">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="cccba-120">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="cccba-120">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="cccba-121">비공개 보호</span><span class="sxs-lookup"><span data-stu-id="cccba-121">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="cccba-122">[Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-122">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="cccba-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-123">Optional.</span></span> <span data-ttu-id="cccba-124">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-124">Can be one of the following:</span></span>

  - [<span data-ttu-id="cccba-125">오버로드</span><span class="sxs-lookup"><span data-stu-id="cccba-125">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="cccba-126">재정의</span><span class="sxs-lookup"><span data-stu-id="cccba-126">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="cccba-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="cccba-127">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="cccba-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="cccba-128">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="cccba-129">New</span><span class="sxs-lookup"><span data-stu-id="cccba-129">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="cccba-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-130">Optional.</span></span> <span data-ttu-id="cccba-131">[공유](../modifiers/shared.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-131">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="cccba-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-132">Optional.</span></span> <span data-ttu-id="cccba-133">[그림자](../modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-133">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="cccba-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-134">Optional.</span></span> <span data-ttu-id="cccba-135">[ReadOnly](../modifiers/readonly.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-135">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="cccba-136">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-136">Optional.</span></span> <span data-ttu-id="cccba-137">[WriteOnly](../modifiers/writeonly.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-137">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="cccba-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-138">Optional.</span></span> <span data-ttu-id="cccba-139">[반복기](../modifiers/iterator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-139">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="cccba-140">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-140">Required.</span></span> <span data-ttu-id="cccba-141">속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-141">Name of the property.</span></span> <span data-ttu-id="cccba-142">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-142">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="cccba-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-143">Optional.</span></span> <span data-ttu-id="cccba-144">이 속성의 매개 변수를 나타내는 지역 변수 이름과 프로시저의 가능한 추가 매개 변수를 나타내는 목록입니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="cccba-144">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="cccba-145">[매개 변수 목록](parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-145">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="cccba-146">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-146">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="cccba-147">이 속성에서 반환 하는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-147">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="cccba-148">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-148">Optional.</span></span> <span data-ttu-id="cccba-149">이 속성이이 속성의 포함 클래스 또는 구조체에서 구현 하는 인터페이스에 각각 정의 된 하나 이상의 속성을 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-149">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="cccba-150">[Implements 문](implements-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-150">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="cccba-151">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-151">Required if `Implements` is supplied.</span></span> <span data-ttu-id="cccba-152">구현 중인 속성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-152">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="cccba-153">각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-153">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="cccba-154">파트</span><span class="sxs-lookup"><span data-stu-id="cccba-154">Part</span></span>|<span data-ttu-id="cccba-155">설명</span><span class="sxs-lookup"><span data-stu-id="cccba-155">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="cccba-156">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-156">Required.</span></span> <span data-ttu-id="cccba-157">이 속성에 포함 된 클래스 또는 구조체에 의해 구현 된 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-157">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="cccba-158">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-158">Required.</span></span> <span data-ttu-id="cccba-159">속성이에서 정의 되는 이름 `interface` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-159">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="cccba-160">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-160">Optional.</span></span> <span data-ttu-id="cccba-161">속성이로 표시 된 경우 필수 `ReadOnly` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-161">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="cccba-162">`Get`속성의 값을 반환 하는 데 사용 되는 속성 프로시저를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-162">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="cccba-163">`Get`문은 [자동으로 구현 된 속성과](../../programming-guide/language-features/procedures/auto-implemented-properties.md)함께 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-163">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="cccba-164">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-164">Optional.</span></span> <span data-ttu-id="cccba-165">또는 프로시저 내에서 실행할 문 블록 `Get` 입니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="cccba-165">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="cccba-166">`Get`속성 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-166">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="cccba-167">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-167">Optional.</span></span> <span data-ttu-id="cccba-168">속성이로 표시 된 경우 필수 `WriteOnly` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-168">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="cccba-169">`Set`속성의 값을 저장 하는 데 사용 되는 속성 프로시저를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-169">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="cccba-170">`Set`문은 [자동으로 구현 된 속성과](../../programming-guide/language-features/procedures/auto-implemented-properties.md)함께 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-170">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="cccba-171">`Set`속성 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-171">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="cccba-172">이 속성의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-172">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="cccba-173">설명</span><span class="sxs-lookup"><span data-stu-id="cccba-173">Remarks</span></span>

<span data-ttu-id="cccba-174">`Property`문은 속성의 선언을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-174">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="cccba-175">속성에는 `Get` 프로시저 (읽기 전용), `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기/쓰기)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-175">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="cccba-176">`Get` `Set` 자동 구현 속성을 사용 하는 경우 및 프로시저를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-176">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="cccba-177">자세한 내용은 [자동으로 구현된 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-177">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="cccba-178">는 `Property` 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-178">You can use `Property` only at class level.</span></span> <span data-ttu-id="cccba-179">즉, 속성에 대 한 *선언 컨텍스트* 는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-179">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="cccba-180">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cccba-180">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="cccba-181">기본적으로 속성은 공용 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-181">By default, properties use public access.</span></span> <span data-ttu-id="cccba-182">문의 액세스 한정자를 사용 하 여 속성의 액세스 수준을 조정 하 `Property` 고 필요에 따라 속성 프로시저 중 하나를 더 제한적인 액세스 수준으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-182">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="cccba-183">Visual Basic는 속성을 할당 하는 동안 매개 변수를 프로시저에 전달 `Set` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-183">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="cccba-184">에 대 한 매개 변수를 제공 하지 않으면 `Set` IDE (통합 개발 환경)에서 라는 암시적 매개 변수를 사용 합니다 `value` .</span><span class="sxs-lookup"><span data-stu-id="cccba-184">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="cccba-185">이 매개 변수는 속성에 할당 되는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-185">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="cccba-186">일반적으로이 값을 private 지역 변수에 저장 하 고 프로시저가 호출 될 때마다 반환 `Get` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-186">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="cccba-187">규칙</span><span class="sxs-lookup"><span data-stu-id="cccba-187">Rules</span></span>

- <span data-ttu-id="cccba-188">**혼합 액세스 수준.**</span><span class="sxs-lookup"><span data-stu-id="cccba-188">**Mixed Access Levels.**</span></span> <span data-ttu-id="cccba-189">읽기/쓰기 속성을 정의 하는 경우 필요에 따라 또는 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있습니다 `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="cccba-189">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="cccba-190">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-190">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="cccba-191">예를 들어 속성이 선언 된 경우 `Friend` 프로시저를 선언할 수 있지만는 선언할 수 `Set` `Private` 없습니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="cccba-191">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="cccba-192">또는 속성을 정의 하는 경우 `ReadOnly` `WriteOnly` 단일 속성 프로시저 ( `Get` 또는 `Set` 각각)는 속성을 모두 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-192">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="cccba-193">속성에 대해 두 개의 액세스 수준을 설정 하므로 프로시저에 대해 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-193">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="cccba-194">**반환 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="cccba-194">**Return Type.**</span></span> <span data-ttu-id="cccba-195">`Property`문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-195">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="cccba-196">모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-196">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="cccba-197">을 지정 하지 않으면 `returntype` 속성은을 반환 합니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="cccba-197">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="cccba-198">**구현이.**</span><span class="sxs-lookup"><span data-stu-id="cccba-198">**Implementation.**</span></span> <span data-ttu-id="cccba-199">이 속성이 키워드를 사용 하는 경우 `Implements` 포함 하는 클래스 또는 구조체에는 `Implements` 또는 문 바로 다음에 문이 있어야 합니다 `Class` `Structure` .</span><span class="sxs-lookup"><span data-stu-id="cccba-199">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="cccba-200">`Implements`문에는에 지정 된 각 인터페이스가 포함 되어야 합니다 `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="cccba-200">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="cccba-201">그러나 인터페이스에서 (의)를 정의 하는 이름은 `Property` `definedname` 이 속성의 이름과 같을 필요가 없습니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="cccba-201">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="cccba-202">동작</span><span class="sxs-lookup"><span data-stu-id="cccba-202">Behavior</span></span>

- <span data-ttu-id="cccba-203">**속성 프로시저에서 반환**</span><span class="sxs-lookup"><span data-stu-id="cccba-203">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="cccba-204">`Get`또는 `Set` 프로시저가 호출 코드에 반환 되 면 실행 되는 문 다음에 오는 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-204">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="cccba-205">`Exit Property`및 `Return` 문을 실행 하면 속성 프로시저에서 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-205">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="cccba-206">프로시저의 모든 위치에는 개수와 `Exit Property` `Return` 문이 모두 표시 될 수 있으며 `Exit Property` 문과 문을 혼합할 수 있습니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="cccba-206">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="cccba-207">**반환 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="cccba-207">**Return Value.**</span></span> <span data-ttu-id="cccba-208">프로시저에서 값을 반환 하려면 `Get` 속성 이름에 값을 할당 하거나 문에 해당 값을 포함 하면 됩니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="cccba-208">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="cccba-209">다음 예에서는 반환 값을 속성 이름에 할당 한 `quoteForTheDay` 다음 문을 사용 하 여를 `Exit Property` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-209">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="cccba-210">`Exit Property`에 값을 할당 하지 않고를 사용 하는 경우이 `name` `Get` 프로시저는 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-210">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="cccba-211">`Return`명령문은 `Get` 프로시저 반환 값을 할당 하 고 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-211">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="cccba-212">다음 예에서는 이러한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-212">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="cccba-213">예제</span><span class="sxs-lookup"><span data-stu-id="cccba-213">Example</span></span>

<span data-ttu-id="cccba-214">다음 예제에서는 클래스의 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cccba-214">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="cccba-215">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cccba-215">See also</span></span>

- [<span data-ttu-id="cccba-216">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="cccba-216">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="cccba-217">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="cccba-217">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="cccba-218">Get 문</span><span class="sxs-lookup"><span data-stu-id="cccba-218">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="cccba-219">Set 문</span><span class="sxs-lookup"><span data-stu-id="cccba-219">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="cccba-220">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="cccba-220">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="cccba-221">기본값</span><span class="sxs-lookup"><span data-stu-id="cccba-221">Default</span></span>](../modifiers/default.md)
