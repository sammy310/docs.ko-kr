---
description: '자세히 알아보기: Namespace 문'
title: Namespace 문
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 2c315947a26f72a90e03bc1f4bf1b5f647866b33
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768859"
---
# <a name="namespace-statement"></a><span data-ttu-id="4bd4c-103">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="4bd4c-103">Namespace Statement</span></span>

<span data-ttu-id="4bd4c-104">네임 스페이스의 이름을 선언 하 고이 선언 뒤에 오는 소스 코드가 해당 네임 스페이스 내에서 컴파일되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-104">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd4c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bd4c-105">Syntax</span></span>  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="4bd4c-106">부분</span><span class="sxs-lookup"><span data-stu-id="4bd4c-106">Parts</span></span>  

 <span data-ttu-id="4bd4c-107">전역</span><span class="sxs-lookup"><span data-stu-id="4bd4c-107">Global</span></span>  
 <span data-ttu-id="4bd4c-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-108">Optional.</span></span> <span data-ttu-id="4bd4c-109">프로젝트의 루트 네임 스페이스에서 네임 스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-109">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="4bd4c-110">[Visual Basic의 네임 스페이스를](../../programming-guide/program-structure/namespaces.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-110">See [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="4bd4c-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-111">Required.</span></span> <span data-ttu-id="4bd4c-112">네임 스페이스를 식별 하는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-112">A unique name that identifies the namespace.</span></span> <span data-ttu-id="4bd4c-113">유효한 Visual Basic 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-113">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="4bd4c-114">자세한 내용은 [선언 된 요소 이름](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-114">For more information, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="4bd4c-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-115">Optional.</span></span> <span data-ttu-id="4bd4c-116">네임 스페이스를 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-116">Elements that make up the namespace.</span></span> <span data-ttu-id="4bd4c-117">여기에는 열거형, 구조체, 인터페이스, 클래스, 모듈, 대리자 및 기타 네임 스페이스를 포함 하지만이에 국한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-117">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="4bd4c-118">블록을 종료 `Namespace` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-118">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bd4c-119">설명</span><span class="sxs-lookup"><span data-stu-id="4bd4c-119">Remarks</span></span>  

 <span data-ttu-id="4bd4c-120">네임 스페이스는 조직 시스템으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-120">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="4bd4c-121">다른 프로그램 및 응용 프로그램에 노출 되는 프로그래밍 요소를 분류 하 고 제공 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-121">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="4bd4c-122">네임 스페이스는 클래스 또는 구조체의 의미에서 *형식이* 아니므로 프로그래밍 요소를 선언 하 여 네임 스페이스의 데이터 형식을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-122">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="4bd4c-123">문 뒤에 선언 된 모든 프로그래밍 요소 `Namespace` 는 해당 네임 스페이스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-123">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="4bd4c-124">Visual Basic는 `End Namespace` 문 또는 다른 문이 나타날 때까지 요소를 마지막으로 선언 된 네임 스페이스로 계속 컴파일합니다 `Namespace` .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-124">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="4bd4c-125">프로젝트 외부에 있는 경우에도 네임 스페이스를 이미 정의한 경우에는 프로그래밍 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-125">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="4bd4c-126">이렇게 하려면 문을 사용 하 여 `Namespace` Visual Basic에서 요소를 해당 네임 스페이스로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-126">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="4bd4c-127">`Namespace`문은 파일이 나 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-127">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="4bd4c-128">즉, 네임 스페이스에 대 한 *선언 컨텍스트* 는 소스 파일 또는 다른 네임 스페이스 여야 하 고 클래스, 구조체, 모듈, 인터페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-128">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="4bd4c-129">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-129">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4bd4c-130">다른 네임 스페이스 내에서 하나의 네임 스페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-130">You can declare one namespace within another.</span></span> <span data-ttu-id="4bd4c-131">선언할 수 있는 중첩 수준에는 엄격한 제한이 없지만, 다른 코드에서 가장 안쪽 네임 스페이스에 선언 된 요소에 액세스 하는 경우에는 중첩 계층 구조에 있는 모든 네임 스페이스 이름을 포함 하는 한정 문자열을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-131">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="4bd4c-132">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4bd4c-132">Access Level</span></span>  

 <span data-ttu-id="4bd4c-133">네임 스페이스는 액세스 수준이 있는 것으로 처리 됩니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-133">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="4bd4c-134">네임 스페이스는 동일한 프로젝트의 모든 위치, 프로젝트를 참조 하는 다른 프로젝트 및 프로젝트에서 빌드된 모든 어셈블리에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-134">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="4bd4c-135">네임 스페이스에 선언 된 프로그래밍 요소는 네임 스페이스에서 선언 되지만 다른 요소 내부에는 포함 되지 않을 수 있습니다 `Public` `Friend` .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-135">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="4bd4c-136">지정 하지 않으면 이러한 요소의 액세스 수준이 기본적으로를 사용 합니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-136">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="4bd4c-137">네임 스페이스 수준에서 선언할 수 있는 요소에는 클래스, 구조체, 모듈, 인터페이스, 열거형 및 대리자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-137">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="4bd4c-138">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-138">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="4bd4c-139">루트 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="4bd4c-139">Root Namespace</span></span>  

 <span data-ttu-id="4bd4c-140">프로젝트의 모든 네임 스페이스 이름은 *루트 네임 스페이스* 를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-140">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="4bd4c-141">Visual Studio는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-141">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="4bd4c-142">예를 들어 프로젝트 이름이 `Payroll`이면 해당 프로그래밍 요소는 해당 네임스페이스 `Payroll`에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-142">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="4bd4c-143">을 선언 하는 경우 `Namespace funding` 해당 네임 스페이스의 전체 이름은 `Payroll.funding` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-143">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="4bd4c-144">`Namespace`제네릭 목록 클래스 예제와 같이 문에서 기존 네임 스페이스를 지정 하려는 경우 루트 네임 스페이스를 null 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-144">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="4bd4c-145">이렇게 하려면 **프로젝트** 메뉴에서 **프로젝트 속성** 을 클릭 한 다음, 상자가 비어 있도록 **루트 네임 스페이스** 항목의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-145">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="4bd4c-146">제네릭 목록 클래스 예제에서이 작업을 수행 하지 않은 경우 Visual Basic 컴파일러는 `System.Collections.Generic` `Payroll` 전체 이름을 사용 하 여 프로젝트 내에서 새 네임 스페이스를 사용 합니다 `Payroll.System.Collections.Generic` .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-146">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="4bd4c-147">또는 키워드를 사용 하 여 `Global` 프로젝트 외부에서 정의 된 네임 스페이스의 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-147">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="4bd4c-148">이렇게 하면 프로젝트 이름을 루트 네임 스페이스로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-148">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="4bd4c-149">이렇게 하면 프로그래밍 요소를 기존 네임 스페이스와 함께 실수로 병합할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-149">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="4bd4c-150">자세한 내용은 [Visual Basic의 네임 스페이스](../../programming-guide/program-structure/namespaces.md)에서 "정규화 된 이름의 전역 키워드" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-150">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="4bd4c-151">`Global`키워드는 네임 스페이스 문에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-151">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="4bd4c-152">이렇게 하면 프로젝트의 루트 네임스페이스에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-152">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="4bd4c-153">자세한 내용은 [Visual Basic 네임](../../programming-guide/program-structure/namespaces.md)스페이스의 "Namespace 문의 Global 키워드" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-153">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="4bd4c-154">**슈팅이.**</span><span class="sxs-lookup"><span data-stu-id="4bd4c-154">**Troubleshooting.**</span></span> <span data-ttu-id="4bd4c-155">루트 네임 스페이스는 예기치 않은 네임 스페이스 이름을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-155">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="4bd4c-156">프로젝트 외부에서 정의 된 네임 스페이스에 대 한 참조를 만드는 경우 Visual Basic 컴파일러는 루트 네임 스페이스에서 중첩 된 네임 스페이스로 construe 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-156">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="4bd4c-157">이 경우 컴파일러는 외부 네임 스페이스에 이미 정의 된 형식을 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-157">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="4bd4c-158">이를 방지 하려면 "루트 네임 스페이스"에 설명 된 대로 루트 네임 스페이스를 null 값으로 설정 하거나, 키워드를 사용 `Global` 하 여 외부 네임 스페이스의 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-158">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="4bd4c-159">특성 및 한정자</span><span class="sxs-lookup"><span data-stu-id="4bd4c-159">Attributes and Modifiers</span></span>  

 <span data-ttu-id="4bd4c-160">네임 스페이스에는 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-160">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="4bd4c-161">특성은 어셈블리의 메타 데이터에 정보를 제공 하며,이는 네임 스페이스와 같은 소스 분류자에는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-161">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="4bd4c-162">모든 액세스 또는 프로시저 한정자 나 다른 한정자는 네임 스페이스에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-162">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="4bd4c-163">형식이 아니므로 이러한 한정자는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-163">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bd4c-164">예제</span><span class="sxs-lookup"><span data-stu-id="4bd4c-164">Example</span></span>  

 <span data-ttu-id="4bd4c-165">다음 예제에서는 두 개의 네임 스페이스를 선언 합니다. 하나는 다른 네임 스페이스에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-165">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a><span data-ttu-id="4bd4c-166">예제</span><span class="sxs-lookup"><span data-stu-id="4bd4c-166">Example</span></span>  

 <span data-ttu-id="4bd4c-167">다음 예제에서는 여러 개의 중첩 된 네임 스페이스를 한 줄에 선언 하 고 이전 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-167">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="4bd4c-168">예제</span><span class="sxs-lookup"><span data-stu-id="4bd4c-168">Example</span></span>  

 <span data-ttu-id="4bd4c-169">다음 예제에서는 이전 예제에서 정의 된 클래스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd4c-169">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="4bd4c-170">예제</span><span class="sxs-lookup"><span data-stu-id="4bd4c-170">Example</span></span>  

 <span data-ttu-id="4bd4c-171">다음 예제에서는 새 제네릭 목록 클래스의 기본 구조를 정의 하 고 네임 스페이스에 추가 합니다 <xref:System.Collections.Generic?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4bd4c-171">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bd4c-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4bd4c-172">See also</span></span>

- [<span data-ttu-id="4bd4c-173">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="4bd4c-173">Imports Statement (.NET Namespace and Type)</span></span>](imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="4bd4c-174">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="4bd4c-174">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="4bd4c-175">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4bd4c-175">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
