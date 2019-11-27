---
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
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346753"
---
# <a name="property-statement"></a><span data-ttu-id="36c2b-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="36c2b-102">Property Statement</span></span>

<span data-ttu-id="36c2b-103">속성의 이름과 속성 값을 저장 하 고 검색 하는 데 사용 되는 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="36c2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="36c2b-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="36c2b-105">요소</span><span class="sxs-lookup"><span data-stu-id="36c2b-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="36c2b-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-106">Optional.</span></span> <span data-ttu-id="36c2b-107">이 속성 또는 `Get` 또는 `Set` 프로시저에 적용 되는 특성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="36c2b-108">[특성 목록](attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="36c2b-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="36c2b-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-109">Optional.</span></span> <span data-ttu-id="36c2b-110">이 속성이 정의 된 클래스 또는 구조체에 대 한 기본 속성 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="36c2b-111">기본 속성은 매개 변수를 허용 해야 하며 속성 이름을 지정 하지 않고 설정 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="36c2b-112">속성을 `Default`로 선언 하는 경우 속성 또는 속성 프로시저 중 하나에서 `Private`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="36c2b-113">`Property` 문과 `Get` 및 `Set` 문 중 하나 이상에 대 한 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="36c2b-114">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="36c2b-115">Public</span><span class="sxs-lookup"><span data-stu-id="36c2b-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="36c2b-116">Protected</span><span class="sxs-lookup"><span data-stu-id="36c2b-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="36c2b-117">Friend</span><span class="sxs-lookup"><span data-stu-id="36c2b-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="36c2b-118">Private</span><span class="sxs-lookup"><span data-stu-id="36c2b-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="36c2b-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="36c2b-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="36c2b-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="36c2b-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="36c2b-121">[Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="36c2b-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-122">Optional.</span></span> <span data-ttu-id="36c2b-123">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="36c2b-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="36c2b-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="36c2b-125">재정의</span><span class="sxs-lookup"><span data-stu-id="36c2b-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="36c2b-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="36c2b-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="36c2b-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="36c2b-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="36c2b-128">MyBase</span><span class="sxs-lookup"><span data-stu-id="36c2b-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="36c2b-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-129">Optional.</span></span> <span data-ttu-id="36c2b-130">[공유](../modifiers/shared.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="36c2b-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-131">Optional.</span></span> <span data-ttu-id="36c2b-132">[그림자](../modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="36c2b-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-133">Optional.</span></span> <span data-ttu-id="36c2b-134">[ReadOnly](../modifiers/readonly.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="36c2b-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-135">Optional.</span></span> <span data-ttu-id="36c2b-136">[WriteOnly](../modifiers/writeonly.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="36c2b-137">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-137">Optional.</span></span> <span data-ttu-id="36c2b-138">[반복기](../modifiers/iterator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="36c2b-139">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36c2b-139">Required.</span></span> <span data-ttu-id="36c2b-140">속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-140">Name of the property.</span></span> <span data-ttu-id="36c2b-141">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="36c2b-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-142">Optional.</span></span> <span data-ttu-id="36c2b-143">이 속성의 매개 변수를 나타내는 지역 변수 이름과 `Set` 프로시저의 가능한 추가 매개 변수를 나타내는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="36c2b-144">[매개 변수 목록](parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="36c2b-145">`Option Strict` `On`경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="36c2b-146">이 속성에서 반환 하는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="36c2b-147">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-147">Optional.</span></span> <span data-ttu-id="36c2b-148">이 속성이이 속성의 포함 클래스 또는 구조체에서 구현 하는 인터페이스에 각각 정의 된 하나 이상의 속성을 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="36c2b-149">[Implements 문](implements-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="36c2b-150">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="36c2b-151">구현 중인 속성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="36c2b-152">각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="36c2b-153">부분</span><span class="sxs-lookup"><span data-stu-id="36c2b-153">Part</span></span>|<span data-ttu-id="36c2b-154">설명</span><span class="sxs-lookup"><span data-stu-id="36c2b-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="36c2b-155">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36c2b-155">Required.</span></span> <span data-ttu-id="36c2b-156">이 속성에 포함 된 클래스 또는 구조체에 의해 구현 된 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="36c2b-157">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="36c2b-157">Required.</span></span> <span data-ttu-id="36c2b-158">`interface`에서 속성을 정의 하는 데 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="36c2b-159">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-159">Optional.</span></span> <span data-ttu-id="36c2b-160">속성이 `ReadOnly`표시 되는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="36c2b-161">속성의 값을 반환 하는 데 사용 되는 `Get` 속성 프로시저를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="36c2b-162">[자동 구현 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)에는 `Get` 문이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="36c2b-163">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-163">Optional.</span></span> <span data-ttu-id="36c2b-164">`Get` 또는 `Set` 프로시저 내에서 실행할 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="36c2b-165">`Get` 속성 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="36c2b-166">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-166">Optional.</span></span> <span data-ttu-id="36c2b-167">속성이 `WriteOnly`표시 되는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="36c2b-168">속성의 값을 저장 하는 데 사용 되는 `Set` 속성 프로시저를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="36c2b-169">[자동 구현 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)에는 `Set` 문이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="36c2b-170">`Set` 속성 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="36c2b-171">이 속성의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="36c2b-172">설명</span><span class="sxs-lookup"><span data-stu-id="36c2b-172">Remarks</span></span>

<span data-ttu-id="36c2b-173">`Property` 문은 속성의 선언을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="36c2b-174">속성에는 `Get` 프로시저 (읽기 전용), `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기/쓰기)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="36c2b-175">자동 구현 속성을 사용 하는 경우 `Get` 및 `Set` 프로시저를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="36c2b-176">자세한 내용은 [자동으로 구현된 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="36c2b-177">`Property`는 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="36c2b-178">즉, 속성에 대 한 *선언 컨텍스트* 는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="36c2b-179">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36c2b-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="36c2b-180">기본적으로 속성은 공용 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-180">By default, properties use public access.</span></span> <span data-ttu-id="36c2b-181">`Property` 문에서 액세스 한정자를 사용 하 여 속성의 액세스 수준을 조정 하 고 필요에 따라 속성 프로시저 중 하나를 더 제한적인 액세스 수준으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="36c2b-182">Visual Basic는 속성을 할당 하는 동안 매개 변수를 `Set` 프로시저에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="36c2b-183">`Set`에 대 한 매개 변수를 제공 하지 않으면 IDE (통합 개발 환경)에서 `value`라는 암시적 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="36c2b-184">이 매개 변수는 속성에 할당 되는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="36c2b-185">일반적으로이 값을 개인 지역 변수에 저장 하 고 `Get` 프로시저가 호출 될 때마다 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="36c2b-186">규칙</span><span class="sxs-lookup"><span data-stu-id="36c2b-186">Rules</span></span>

- <span data-ttu-id="36c2b-187">**혼합 액세스 수준.**</span><span class="sxs-lookup"><span data-stu-id="36c2b-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="36c2b-188">읽기/쓰기 속성을 정의 하는 경우 필요에 따라 `Get` 또는 `Set` 프로시저에 대해 다른 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="36c2b-189">이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="36c2b-190">예를 들어 속성을 `Friend`선언 하는 경우 `Set` 프로시저 `Private`선언할 수 있지만 `Public`는 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="36c2b-191">`ReadOnly` 또는 `WriteOnly` 속성을 정의 하는 경우에는 각각 단일 속성 프로시저 (`Get` 또는 `Set`)가 모든 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="36c2b-192">속성에 대해 두 개의 액세스 수준을 설정 하므로 프로시저에 대해 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="36c2b-193">**반환 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="36c2b-193">**Return Type.**</span></span> <span data-ttu-id="36c2b-194">`Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="36c2b-195">모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="36c2b-196">`returntype`지정 하지 않으면 속성은 `Object`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="36c2b-197">**구현이.**</span><span class="sxs-lookup"><span data-stu-id="36c2b-197">**Implementation.**</span></span> <span data-ttu-id="36c2b-198">이 속성이 `Implements` 키워드를 사용 하는 경우 포함 하는 클래스 또는 구조체에는 `Class` 또는 `Structure` 문 바로 다음에 `Implements` 문이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="36c2b-199">`Implements` 문은 `implementslist`에 지정 된 각 인터페이스를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="36c2b-200">그러나 인터페이스가 `Property`을 정의 하는 이름 (`definedname`)은이 속성의 이름과 같을 필요가 없습니다 (`name`).</span><span class="sxs-lookup"><span data-stu-id="36c2b-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="36c2b-201">동작</span><span class="sxs-lookup"><span data-stu-id="36c2b-201">Behavior</span></span>

- <span data-ttu-id="36c2b-202">**속성 프로시저에서 반환**</span><span class="sxs-lookup"><span data-stu-id="36c2b-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="36c2b-203">`Get` 또는 `Set` 프로시저가 호출 코드로 반환 되 면 호출 된 문 다음에 오는 문으로 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="36c2b-204">`Exit Property` 및 `Return` 문은 속성 프로시저에서 즉시 종료를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="36c2b-205">프로시저의 어디에 든 많은 `Exit Property` 및 `Return` 문이 표시 될 수 있으며 `Exit Property` 문과 `Return` 문을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="36c2b-206">**반환 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="36c2b-206">**Return Value.**</span></span> <span data-ttu-id="36c2b-207">`Get` 프로시저에서 값을 반환 하려면 속성 이름에 값을 할당 하거나 `Return` 문에 값을 포함 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="36c2b-208">다음 예에서는 `quoteForTheDay` 속성 이름에 반환 값을 할당 한 다음 `Exit Property` 문을 사용 하 여를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="36c2b-209">`name`에 값을 할당 하지 않고 `Exit Property`를 사용 하는 경우 `Get` 프로시저는 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="36c2b-210">`Return` 문은 `Get` 프로시저 반환 값을 할당 하 고 프로시저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="36c2b-211">다음 예제에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="36c2b-212">예제</span><span class="sxs-lookup"><span data-stu-id="36c2b-212">Example</span></span>

<span data-ttu-id="36c2b-213">다음 예제에서는 클래스의 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c2b-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="36c2b-214">참고자료</span><span class="sxs-lookup"><span data-stu-id="36c2b-214">See also</span></span>

- [<span data-ttu-id="36c2b-215">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="36c2b-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="36c2b-216">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="36c2b-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="36c2b-217">Get 문</span><span class="sxs-lookup"><span data-stu-id="36c2b-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="36c2b-218">Set 문</span><span class="sxs-lookup"><span data-stu-id="36c2b-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="36c2b-219">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="36c2b-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="36c2b-220">기본</span><span class="sxs-lookup"><span data-stu-id="36c2b-220">Default</span></span>](../modifiers/default.md)
