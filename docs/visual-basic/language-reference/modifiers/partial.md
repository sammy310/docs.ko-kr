---
description: '자세한 정보: 부분 (Visual Basic)'
title: 부분
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: bf2d8b06b83f4a90ec2f4edd52405b58695c26e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701016"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="347d0-103">Partial(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="347d0-103">Partial (Visual Basic)</span></span>

<span data-ttu-id="347d0-104">형식 선언이 해당 형식에 대한 부분 정의임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-104">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="347d0-105">`Partial` 키워드를 사용하여 형식 정의를 다수의 선언으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-105">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="347d0-106">원하는 만큼 다양한 소스 파일에서 원하는 만큼 partial 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-106">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="347d0-107">그러나 모든 선언이 동일한 어셈블리와 동일한 네임스페이스에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-107">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="347d0-108">Visual Basic는 부분 클래스에서 일반적으로 구현 되는 *부분 메서드 (partial* method)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-108">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="347d0-109">자세한 내용은 [부분 메서드](../../programming-guide/language-features/procedures/partial-methods.md) 및 [Sub 문](../statements/sub-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-109">For more information, see [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347d0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="347d0-110">Syntax</span></span>  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="347d0-111">부분</span><span class="sxs-lookup"><span data-stu-id="347d0-111">Parts</span></span>  
  
|<span data-ttu-id="347d0-112">용어</span><span class="sxs-lookup"><span data-stu-id="347d0-112">Term</span></span>|<span data-ttu-id="347d0-113">정의</span><span class="sxs-lookup"><span data-stu-id="347d0-113">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="347d0-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-114">Optional.</span></span> <span data-ttu-id="347d0-115">이 형식에 적용되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-115">List of attributes that apply to this type.</span></span> <span data-ttu-id="347d0-116">[특성 목록을](../statements/attribute-list.md) 꺾쇠 괄호 ()로 묶어야 합니다 `< >` .</span><span class="sxs-lookup"><span data-stu-id="347d0-116">You must enclose the [Attribute List](../statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="347d0-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-117">Optional.</span></span> <span data-ttu-id="347d0-118">이 형식에 액세스할 수 있는 코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-118">Specifies what code can access this type.</span></span> <span data-ttu-id="347d0-119">[Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-119">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="347d0-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-120">Optional.</span></span> <span data-ttu-id="347d0-121">[그림자](shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-121">See [Shadows](shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="347d0-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-122">Optional.</span></span> <span data-ttu-id="347d0-123">[MustInherit](mustinherit.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="347d0-123">See [MustInherit](mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="347d0-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-124">Optional.</span></span> <span data-ttu-id="347d0-125">[NotInheritable](notinheritable.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-125">See [NotInheritable](notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="347d0-126">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-126">Required.</span></span> <span data-ttu-id="347d0-127">이 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-127">Name of this type.</span></span> <span data-ttu-id="347d0-128">동일한 형식의 다른 모든 partial 선언에 정의된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-128">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="347d0-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-129">Optional.</span></span> <span data-ttu-id="347d0-130">제네릭 형식임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-130">Specifies that this is a generic type.</span></span> <span data-ttu-id="347d0-131">[Visual Basic의 제네릭 형식을](../../programming-guide/language-features/data-types/generic-types.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-131">See [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="347d0-132">을 사용 하 [는](../statements/of-clause.md)경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-132">Required if you use [Of](../statements/of-clause.md).</span></span> <span data-ttu-id="347d0-133">[형식 목록](../statements/type-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="347d0-133">See [Type List](../statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="347d0-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-134">Optional.</span></span> <span data-ttu-id="347d0-135">[Inherits 문](../statements/inherits-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-135">See [Inherits Statement](../statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="347d0-136">`Inherits`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-136">Required if you use `Inherits`.</span></span> <span data-ttu-id="347d0-137">이 클래스가 파생되는 출처인 인터페이스 또는 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-137">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="347d0-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-138">Optional.</span></span> <span data-ttu-id="347d0-139">[Implements 문](../statements/implements-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-139">See [Implements Statement](../statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="347d0-140">`Implements`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-140">Required if you use `Implements`.</span></span> <span data-ttu-id="347d0-141">이 형식이 구현하는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-141">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="347d0-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-142">Optional.</span></span> <span data-ttu-id="347d0-143">형식에 대한 추가 변수 및 이벤트를 선언하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-143">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="347d0-144">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-144">Optional.</span></span> <span data-ttu-id="347d0-145">형식에 대한 추가 프로시저를 선언하고 정의하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-145">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="347d0-146">`End Class` 또는 `End Structure`</span><span class="sxs-lookup"><span data-stu-id="347d0-146">`End Class` or `End Structure`</span></span>|<span data-ttu-id="347d0-147">`Class` 또는 `Structure`에 대한 이 부분적 정의를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-147">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="347d0-148">설명</span><span class="sxs-lookup"><span data-stu-id="347d0-148">Remarks</span></span>  

 <span data-ttu-id="347d0-149">Visual Basic에서는 사용자가 별도의 소스 파일에서 작성한 코드에서 생성된 코드를 구분하는 데 partial 클래스 정의를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-149">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="347d0-150">예를 들어, **Windows Form 디자이너** 에서는 <xref:System.Windows.Forms.Form>과 같은 컨트롤에 대해 partial 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-150">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="347d0-151">이런 컨트롤에서 생성된 코드를 수정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-151">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="347d0-152">부분 형식(Partial Type)을 만들면 클래스, 구조체, 인터페이스 및 모듈 만들기에 대한 모든 규칙(예; 한정자 사용 및 상속에 대한 규칙)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-152">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="347d0-153">모범 사례</span><span class="sxs-lookup"><span data-stu-id="347d0-153">Best Practices</span></span>  
  
- <span data-ttu-id="347d0-154">일반적인 상황에서는 단일 형식의 개발을 두 개 이상의 선언으로 분할해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-154">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="347d0-155">따라서 대부분의 경우 `Partial` 키워드가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-155">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="347d0-156">가독성을 위해, 형식에 대한 모든 partial 선언에는 `Partial` 키워드를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-156">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="347d0-157">컴파일러는 최대 하나의 partial 선언에서 이 키워드가 생략되는 것을 허용합니다. 두 개 이상의 partial 선언에서 이를 생략하는 경우 컴파일러에서 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-157">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="347d0-158">동작</span><span class="sxs-lookup"><span data-stu-id="347d0-158">Behavior</span></span>  
  
- <span data-ttu-id="347d0-159">**선언의 공용 구조체입니다.**</span><span class="sxs-lookup"><span data-stu-id="347d0-159">**Union of Declarations.**</span></span> <span data-ttu-id="347d0-160">컴파일러는 이 형식을 모든 partial 선언의 공용 구조체로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-160">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="347d0-161">모든 부분 정의의 모든 한정자는 전체 형식에 적용되며, 모든 부분 정의의 모든 멤버를 전체 형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-161">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="347d0-162">**모듈에 있는 부분 형식(Partial Type)에 대한 형식 승격이 허용되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="347d0-162">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="347d0-163">모듈 내부에 부분 정의가 있는 경우 해당 형식의 형식 승격은 자동으로 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-163">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="347d0-164">이러한 경우 일련의 부분 정의로 인해 예기치 않은 결과뿐만 아니라 컴파일러 오류도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-164">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="347d0-165">자세한 내용은 [형식 승격](../../programming-guide/language-features/declared-elements/type-promotion.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="347d0-165">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="347d0-166">컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-166">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="347d0-167">`Partial` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-167">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="347d0-168">Class 문</span><span class="sxs-lookup"><span data-stu-id="347d0-168">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="347d0-169">Structure 문</span><span class="sxs-lookup"><span data-stu-id="347d0-169">Structure Statement</span></span>](../statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="347d0-170">예제</span><span class="sxs-lookup"><span data-stu-id="347d0-170">Example</span></span>  

 <span data-ttu-id="347d0-171">다음 예제에서는 클래스 `sampleClass`의 정의를 두 개의 선언으로 분할합니다(여기서 각 선언은 서로 다른 `Sub` 프로시저를 정의함).</span><span class="sxs-lookup"><span data-stu-id="347d0-171">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="347d0-172">앞의 예제에서 두 개의 부분 정의는 동일한 소스 파일에 있거나 두 개의 서로 다른 소스 파일에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347d0-172">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347d0-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="347d0-173">See also</span></span>

- [<span data-ttu-id="347d0-174">Class 문</span><span class="sxs-lookup"><span data-stu-id="347d0-174">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="347d0-175">Structure 문</span><span class="sxs-lookup"><span data-stu-id="347d0-175">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="347d0-176">형식 승격</span><span class="sxs-lookup"><span data-stu-id="347d0-176">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="347d0-177">Overloads</span><span class="sxs-lookup"><span data-stu-id="347d0-177">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="347d0-178">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="347d0-178">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="347d0-179">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="347d0-179">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
