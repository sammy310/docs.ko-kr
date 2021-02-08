---
description: '자세히 알아보기: Module 문'
title: Module 문
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 2a19bcfa4521d34b5a91fbc9de412a6d8f6f39c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768872"
---
# <a name="module-statement"></a><span data-ttu-id="59d54-103">Module 문</span><span class="sxs-lookup"><span data-stu-id="59d54-103">Module Statement</span></span>

<span data-ttu-id="59d54-104">모듈 이름을 선언 하 고 모듈에서 구성 하는 변수, 속성, 이벤트 및 프로시저의 정의를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-104">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="59d54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="59d54-105">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="59d54-106">부분</span><span class="sxs-lookup"><span data-stu-id="59d54-106">Parts</span></span>

`attributelist`  
<span data-ttu-id="59d54-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-107">Optional.</span></span> <span data-ttu-id="59d54-108">[특성 목록](attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59d54-108">See [Attribute List](attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="59d54-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-109">Optional.</span></span> <span data-ttu-id="59d54-110">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-110">Can be one of the following:</span></span>

- [<span data-ttu-id="59d54-111">공용</span><span class="sxs-lookup"><span data-stu-id="59d54-111">Public</span></span>](../modifiers/public.md)

- [<span data-ttu-id="59d54-112">Friend</span><span class="sxs-lookup"><span data-stu-id="59d54-112">Friend</span></span>](../modifiers/friend.md)

<span data-ttu-id="59d54-113">[Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-113">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="59d54-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-114">Required.</span></span> <span data-ttu-id="59d54-115">이 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-115">Name of this module.</span></span> <span data-ttu-id="59d54-116">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-116">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="59d54-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-117">Optional.</span></span> <span data-ttu-id="59d54-118">이 모듈의 변수, 속성, 이벤트, 프로시저 및 중첩 형식을 정의 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-118">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="59d54-119">정의를 종료 `Module` 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-119">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="59d54-120">설명</span><span class="sxs-lookup"><span data-stu-id="59d54-120">Remarks</span></span>

<span data-ttu-id="59d54-121">`Module`문은 네임 스페이스 전체에서 사용할 수 있는 참조 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-121">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="59d54-122">*모듈* ( *표준 모듈이* 라고도 함)은 클래스와 비슷하지만 몇 가지 중요 한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-122">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="59d54-123">모든 모듈에는 정확히 하나의 인스턴스가 있으며 변수에 만들거나 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-123">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="59d54-124">모듈은 상속을 지원 하거나 인터페이스를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-124">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="59d54-125">모듈은 클래스 또는 구조체 라는 점에서 *형식이* 아닙니다. 프로그래밍 요소를 모듈의 데이터 형식으로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-125">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="59d54-126">는 `Module` 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-126">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="59d54-127">즉, 모듈의 *선언 컨텍스트* 는 소스 파일 또는 네임 스페이스 여야 하 고 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-127">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="59d54-128">모듈은 다른 모듈 또는 모든 형식 내에서 중첩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-128">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="59d54-129">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-129">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="59d54-130">모듈의 수명은 프로그램의 수명과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-130">A module has the same lifetime as your program.</span></span> <span data-ttu-id="59d54-131">해당 멤버는 모두 이므로 `Shared` 프로그램의 수명과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-131">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="59d54-132">모듈은 기본적으로 [Friend](../modifiers/friend.md) 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-132">Modules default to [Friend](../modifiers/friend.md) access.</span></span> <span data-ttu-id="59d54-133">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-133">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="59d54-134">자세한 내용은 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-134">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="59d54-135">모듈의 모든 멤버는 암시적으로 `Shared` 입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-135">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="59d54-136">클래스 및 모듈</span><span class="sxs-lookup"><span data-stu-id="59d54-136">Classes and Modules</span></span>

<span data-ttu-id="59d54-137">이러한 요소에는 여러 가지 유사점이 있지만 몇 가지 중요 한 차이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-137">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="59d54-138">**용어**</span><span class="sxs-lookup"><span data-stu-id="59d54-138">**Terminology.**</span></span> <span data-ttu-id="59d54-139">이전 버전의 Visual Basic에서는 *클래스 모듈* (cls 파일)과 *표준 모듈* (bas 파일)의 두 가지 모듈 형식을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-139">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="59d54-140">현재 버전은 이러한 *클래스* 및 *모듈* 을 각각 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-140">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="59d54-141">**공유 멤버.**</span><span class="sxs-lookup"><span data-stu-id="59d54-141">**Shared Members.**</span></span> <span data-ttu-id="59d54-142">클래스의 멤버가 공유 또는 인스턴스 멤버 인지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-142">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="59d54-143">**개체 방향입니다.**</span><span class="sxs-lookup"><span data-stu-id="59d54-143">**Object Orientation.**</span></span> <span data-ttu-id="59d54-144">클래스는 개체 지향적 이지만 모듈은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-144">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="59d54-145">따라서 클래스만 개체로 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-145">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="59d54-146">자세한 내용은 [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-146">For more information, see [Objects and Classes](../../programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="59d54-147">규칙</span><span class="sxs-lookup"><span data-stu-id="59d54-147">Rules</span></span>

- <span data-ttu-id="59d54-148">**수정자.**</span><span class="sxs-lookup"><span data-stu-id="59d54-148">**Modifiers.**</span></span> <span data-ttu-id="59d54-149">모든 모듈 멤버는 암시적으로 [공유](../modifiers/shared.md)됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-149">All module members are implicitly [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="59d54-150">멤버를 선언할 때 키워드를 사용할 수 없으며 `Shared` , 멤버의 공유 상태를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-150">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="59d54-151">**상.**</span><span class="sxs-lookup"><span data-stu-id="59d54-151">**Inheritance.**</span></span> <span data-ttu-id="59d54-152">모듈은 모든 모듈이 상속 하는 이외의 형식에서 상속할 수 없습니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="59d54-152">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="59d54-153">특히 한 모듈은 다른 모듈에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-153">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="59d54-154">을 지정 하는 경우에도 [Inherits 문을](inherits-statement.md) 모듈 정의에 사용할 수 없습니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="59d54-154">You cannot use the [Inherits Statement](inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="59d54-155">**기본 속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="59d54-155">**Default Property.**</span></span> <span data-ttu-id="59d54-156">모듈에서 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-156">You cannot define any default properties in a module.</span></span> <span data-ttu-id="59d54-157">자세한 내용은 [기본값](../modifiers/default.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-157">For more information, see [Default](../modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="59d54-158">동작</span><span class="sxs-lookup"><span data-stu-id="59d54-158">Behavior</span></span>

- <span data-ttu-id="59d54-159">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="59d54-159">**Access Level.**</span></span> <span data-ttu-id="59d54-160">모듈 내에서 각 멤버를 고유한 액세스 수준으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-160">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="59d54-161">모듈 멤버는 기본적으로 [Private](../modifiers/private.md) access로 기본 사용 되는 변수 및 상수를 제외 하 고 [공용](../modifiers/public.md) 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-161">Module members default to [Public](../modifiers/public.md) access, except variables and constants, which default to [Private](../modifiers/private.md) access.</span></span> <span data-ttu-id="59d54-162">모듈의 멤버 중 하나 보다 제한 된 액세스 권한이 있으면 지정 된 모듈 액세스 수준이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-162">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="59d54-163">**범위.**</span><span class="sxs-lookup"><span data-stu-id="59d54-163">**Scope.**</span></span> <span data-ttu-id="59d54-164">모듈은 전체 네임 스페이스 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-164">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="59d54-165">모든 모듈 멤버의 범위는 전체 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-165">The scope of every module member is the entire module.</span></span> <span data-ttu-id="59d54-166">모든 멤버가 *형식 승격* 을 거칩니다. 그러면 해당 범위가 모듈이 포함 된 네임 스페이스로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-166">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="59d54-167">자세한 내용은 [형식 승격](../../programming-guide/language-features/declared-elements/type-promotion.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-167">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="59d54-168">**조인의.**</span><span class="sxs-lookup"><span data-stu-id="59d54-168">**Qualification.**</span></span> <span data-ttu-id="59d54-169">프로젝트에 여러 모듈을 포함할 수 있으며, 둘 이상의 모듈에서 같은 이름을 사용 하 여 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-169">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="59d54-170">그러나 참조를 해당 모듈 외부에서 가져온 경우 적절 한 모듈 이름을 사용 하 여 이러한 멤버에 대 한 참조를 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d54-170">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="59d54-171">자세한 내용은 [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d54-171">For more information, see [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="59d54-172">예제</span><span class="sxs-lookup"><span data-stu-id="59d54-172">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="59d54-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59d54-173">See also</span></span>

- [<span data-ttu-id="59d54-174">Class 문</span><span class="sxs-lookup"><span data-stu-id="59d54-174">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="59d54-175">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="59d54-175">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="59d54-176">Structure 문</span><span class="sxs-lookup"><span data-stu-id="59d54-176">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="59d54-177">Interface 문</span><span class="sxs-lookup"><span data-stu-id="59d54-177">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="59d54-178">Property Statement</span><span class="sxs-lookup"><span data-stu-id="59d54-178">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="59d54-179">형식 승격</span><span class="sxs-lookup"><span data-stu-id="59d54-179">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
