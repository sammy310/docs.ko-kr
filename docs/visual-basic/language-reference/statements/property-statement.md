---
title: Property 문 (Visual Basic)
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
ms.openlocfilehash: 7b2d388cbcd1995178adf4102520ecaa1c9b1889
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814192"
---
# <a name="property-statement"></a><span data-ttu-id="d08d3-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d08d3-102">Property Statement</span></span>
<span data-ttu-id="d08d3-103">이름 속성 및 저장 하 고 속성의 값을 검색 하는 데 속성 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="d08d3-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="d08d3-105">요소</span><span class="sxs-lookup"><span data-stu-id="d08d3-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="d08d3-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-106">Optional.</span></span> <span data-ttu-id="d08d3-107">이 속성에 적용 되는 특성의 목록 또는 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="d08d3-108">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="d08d3-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-109">Optional.</span></span> <span data-ttu-id="d08d3-110">이 속성은 클래스 또는 구조체 정의 된 기본 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="d08d3-111">기본 속성 매개 변수를 허용 해야 합니다 설정 및 속성 이름을 지정 하지 않고 검색 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="d08d3-112">속성으로 선언 하는 경우 `Default`를 사용할 수 없습니다 `Private` 속성 또는 해당 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="d08d3-113">선택적 요소를 `Property` 문 및 중 하나만 `Get` 및 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="d08d3-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="d08d3-114">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d08d3-115">공용</span><span class="sxs-lookup"><span data-stu-id="d08d3-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="d08d3-116">보호됨</span><span class="sxs-lookup"><span data-stu-id="d08d3-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="d08d3-117">Friend</span><span class="sxs-lookup"><span data-stu-id="d08d3-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="d08d3-118">전용</span><span class="sxs-lookup"><span data-stu-id="d08d3-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="d08d3-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d08d3-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md) 

    - [<span data-ttu-id="d08d3-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="d08d3-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="d08d3-121">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d08d3-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="d08d3-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-122">Optional.</span></span> <span data-ttu-id="d08d3-123">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-123">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d08d3-124">오버로드</span><span class="sxs-lookup"><span data-stu-id="d08d3-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="d08d3-125">재정의</span><span class="sxs-lookup"><span data-stu-id="d08d3-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="d08d3-126">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="d08d3-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="d08d3-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="d08d3-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="d08d3-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d08d3-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="d08d3-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-129">Optional.</span></span> <span data-ttu-id="d08d3-130">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="d08d3-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-131">Optional.</span></span> <span data-ttu-id="d08d3-132">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="d08d3-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-133">Optional.</span></span> <span data-ttu-id="d08d3-134">참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="d08d3-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-135">Optional.</span></span> <span data-ttu-id="d08d3-136">참조 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="d08d3-137">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-137">Optional.</span></span> <span data-ttu-id="d08d3-138">참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="d08d3-139">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d08d3-139">Required.</span></span> <span data-ttu-id="d08d3-140">속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-140">Name of the property.</span></span> <span data-ttu-id="d08d3-141">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d08d3-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="d08d3-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-142">Optional.</span></span> <span data-ttu-id="d08d3-143">이 속성의 매개 변수 및의 추가 매개 변수 수를 나타내는 지역 변수 이름의 목록을 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="d08d3-144">참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="d08d3-145">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="d08d3-146">이 속성에 의해 반환 되는 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-146">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="d08d3-147">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-147">Optional.</span></span> <span data-ttu-id="d08d3-148">하나 이상의 속성을이 속성의 포함 하는 클래스 또는 구조체에서 구현 된 인터페이스에 정의 된 각각이이 속성을 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="d08d3-149">참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="d08d3-150">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="d08d3-151">구현 되는 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-151">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="d08d3-152">각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-152">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="d08d3-153">파트</span><span class="sxs-lookup"><span data-stu-id="d08d3-153">Part</span></span>|<span data-ttu-id="d08d3-154">설명</span><span class="sxs-lookup"><span data-stu-id="d08d3-154">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="d08d3-155">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d08d3-155">Required.</span></span> <span data-ttu-id="d08d3-156">이 속성에 의해 구현 된 인터페이스의 이름을 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-156">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="d08d3-157">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d08d3-157">Required.</span></span> <span data-ttu-id="d08d3-158">속성에 정의 된 이름 `interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-158">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="d08d3-159">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-159">Optional.</span></span> <span data-ttu-id="d08d3-160">속성이 표시 하는 경우 필요한 `WriteOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="d08d3-161">시작을 `Get` 속성의 값을 반환 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="d08d3-162">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-162">Optional.</span></span> <span data-ttu-id="d08d3-163">내에 실행할 문 블록을 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="d08d3-164">종료는 `Get` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-164">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="d08d3-165">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-165">Optional.</span></span> <span data-ttu-id="d08d3-166">속성이 표시 하는 경우 필요한 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="d08d3-167">시작을 `Set` 속성의 값을 저장 하는 데 사용 되는 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="d08d3-168">종료는 `Set` 속성 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-168">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="d08d3-169">이 속성의 정의 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-169">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d08d3-170">설명</span><span class="sxs-lookup"><span data-stu-id="d08d3-170">Remarks</span></span>  
 <span data-ttu-id="d08d3-171">`Property` 문을 속성의 선언을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="d08d3-172">속성을 `Get` (읽기 전용), 프로시저를 `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기-쓰기).</span><span class="sxs-lookup"><span data-stu-id="d08d3-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="d08d3-173">생략할 수 있습니다 합니다 `Get` 및 `Set` 자동 구현 속성을 사용 하는 경우에 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="d08d3-174">자세한 내용은 [자동으로 구현된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d08d3-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="d08d3-175">사용할 수 있습니다 `Property` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="d08d3-176">즉, 합니다 *선언 컨텍스트* 속성 클래스, 구조체, 모듈 또는 인터페이스 여야 하 고 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="d08d3-177">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d08d3-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="d08d3-178">기본적으로 속성 공용 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-178">By default, properties use public access.</span></span> <span data-ttu-id="d08d3-179">액세스 한정자를 사용 하 여 속성의 액세스 수준을 조정할 수 있습니다는 `Property` 문 고 필요에 따라 조정할 수는 더 제한적인 액세스 수준에 해당 속성 프로시저 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="d08d3-180">Visual Basic에 매개 변수를 전달 합니다 `Set` 속성을 할당 하는 동안 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="d08d3-181">매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="d08d3-182">이 매개 변수 속성에 할당할 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="d08d3-183">일반적으로 개인 로컬 변수에이 값을 저장 하 고 반환할 때마다는 `Get` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d08d3-184">규칙</span><span class="sxs-lookup"><span data-stu-id="d08d3-184">Rules</span></span>  
  
-   <span data-ttu-id="d08d3-185">**혼합 된 액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="d08d3-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="d08d3-186">서로 다른 액세스 수준에 대 한 필요에 따라 지정할 수는 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 절차, 하지만 둘 다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="d08d3-187">이 작업을 수행 하는 경우 프로시저 액세스 수준 속성의 액세스 수준 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="d08d3-188">예를 들어, 속성 선언 되 면 `Friend`를 선언할 수 있습니다 합니다 `Set` 프로시저 `Private`, 아닌 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="d08d3-189">정의 하는 경우는 `ReadOnly` 또는 `WriteOnly` 속성을 단일 속성 프로시저 (`Get` 또는 `Set`각각) 모든 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="d08d3-190">속성에 대 한 액세스 수준은 다음 두 설정 되므로 이러한 프로시저에 대 한 다른 액세스 수준을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="d08d3-191">**형식을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d08d3-191">**Return Type.**</span></span> <span data-ttu-id="d08d3-192">`Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="d08d3-193">모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="d08d3-194">지정 하지 않는 경우 `returntype`에서 속성 반환 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-194">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="d08d3-195">**구현입니다.**</span><span class="sxs-lookup"><span data-stu-id="d08d3-195">**Implementation.**</span></span> <span data-ttu-id="d08d3-196">이 속성을 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스 또는 구조체 있어야를 `Implements` 문 바로 다음 해당 `Class` 또는 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="d08d3-197">합니다 `Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="d08d3-198">그러나 사용 되는 인터페이스는 다음과 같이 정의 됩니다. 이름을 합니다 `Property` (에서 `definedname`)이이 속성의 이름으로 동일할 필요가 없습니다 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="d08d3-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d08d3-199">동작</span><span class="sxs-lookup"><span data-stu-id="d08d3-199">Behavior</span></span>  
  
-   <span data-ttu-id="d08d3-200">**속성 프로시저에서 반환합니다.**</span><span class="sxs-lookup"><span data-stu-id="d08d3-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="d08d3-201">경우는 `Get` 또는 `Set` 프로시저가 호출 코드에 반환 되 면 실행이 문 다음에 호출한 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="d08d3-202">합니다 `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="d08d3-203">임의 개수의 `Exit Property` 하 고 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="d08d3-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="d08d3-204">**값을 반환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d08d3-204">**Return Value.**</span></span> <span data-ttu-id="d08d3-205">값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함을 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="d08d3-206">다음 예제에서는 속성 이름에 반환 값을 할당 `quoteForTheDay` 를 사용 하 여는 `Exit Property` 문을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     <span data-ttu-id="d08d3-207">사용 하는 경우 `Exit Property` 값을 할당 하지 않고 `name`는 `Get` 프로시저가 속성의 데이터 형식에 대 한 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="d08d3-208">`Return` 문은 한 번에 할당 된 `Get` 프로시저 반환 값 및 절차를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="d08d3-209">다음 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-209">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="d08d3-210">예제</span><span class="sxs-lookup"><span data-stu-id="d08d3-210">Example</span></span>  
 <span data-ttu-id="d08d3-211">다음 예제에서는 클래스에서 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d08d3-211">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]  
  
## <a name="see-also"></a><span data-ttu-id="d08d3-212">참고자료</span><span class="sxs-lookup"><span data-stu-id="d08d3-212">See also</span></span>

- [<span data-ttu-id="d08d3-213">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="d08d3-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="d08d3-214">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="d08d3-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="d08d3-215">Get 문</span><span class="sxs-lookup"><span data-stu-id="d08d3-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="d08d3-216">Set 문</span><span class="sxs-lookup"><span data-stu-id="d08d3-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="d08d3-217">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="d08d3-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="d08d3-218">기본</span><span class="sxs-lookup"><span data-stu-id="d08d3-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
