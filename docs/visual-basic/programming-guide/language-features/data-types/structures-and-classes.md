---
title: 구조체와 클래스
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: d252d9216a9b825ad0663a5779d7ce7f81fa9011
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393574"
---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="3bd36-102">구조체와 클래스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bd36-102">Structures and Classes (Visual Basic)</span></span>
<span data-ttu-id="3bd36-103">Visual Basic는 구조체와 클래스에 대 한 구문을 통합 하며, 두 엔터티 모두 동일한 기능을 대부분 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-103">Visual Basic unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="3bd36-104">그러나 구조와 클래스 사이에는 중요 한 차이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="3bd36-105">클래스는 참조 형식이 될 수 있다는 장점이 있습니다. 참조를 전달 하는 것은 구조체 변수를 모든 데이터와 함께 전달 하는 것 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="3bd36-106">반면에 구조체는 전역 힙에서 메모리를 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="3bd36-107">구조체에서 상속할 수 없으므로 구조체는 확장 하지 않아도 되는 개체에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="3bd36-108">만들려는 개체의 인스턴스 크기가 작은 경우 구조체를 사용 하 고 클래스와 구조체의 성능 특성을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="3bd36-109">비슷하며</span><span class="sxs-lookup"><span data-stu-id="3bd36-109">Similarities</span></span>  
 <span data-ttu-id="3bd36-110">구조체와 클래스는 다음과 같은 점에서 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-110">Structures and classes are similar in the following respects:</span></span>  
  
- <span data-ttu-id="3bd36-111">둘 다 *컨테이너* 형식입니다. 즉, 다른 형식을 멤버로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
- <span data-ttu-id="3bd36-112">둘 다에는 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="3bd36-113">그러나 이러한 멤버를 구조체의 선언 된 *요소* 와 혼동 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
- <span data-ttu-id="3bd36-114">두 멤버 모두 개별화 된 액세스 수준을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="3bd36-115">예를 들어 한 멤버를 선언 하 고 다른 멤버를 선언할 수 있습니다 `Public` `Private` .</span><span class="sxs-lookup"><span data-stu-id="3bd36-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
- <span data-ttu-id="3bd36-116">둘 다 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-116">Both can implement interfaces.</span></span>  
  
- <span data-ttu-id="3bd36-117">둘 다 매개 변수를 포함 하거나 포함 하지 않는 공유 생성자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-117">Both can have shared constructors, with or without parameters.</span></span>  
  
- <span data-ttu-id="3bd36-118">속성에 하나 이상의 매개 변수가 사용 되는 경우 둘 다 *기본 속성*을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
- <span data-ttu-id="3bd36-119">둘 다 이벤트를 선언 하 고 발생 시킬 수 있으며 둘 다 대리자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="3bd36-120">차이점</span><span class="sxs-lookup"><span data-stu-id="3bd36-120">Differences</span></span>  
 <span data-ttu-id="3bd36-121">구조체와 클래스는 다음 인스턴스와 관련 사항을 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-121">Structures and classes differ in the following particulars:</span></span>  
  
- <span data-ttu-id="3bd36-122">구조체는 *값 형식*입니다. 클래스는 *참조 형식*입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="3bd36-123">구조체 형식의 변수에는 클래스 형식의 데이터에 대 한 참조를 포함 하는 대신 구조체의 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
- <span data-ttu-id="3bd36-124">구조체는 스택 할당을 사용 합니다. 클래스는 힙 할당을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
- <span data-ttu-id="3bd36-125">모든 구조체 요소는 `Public` 기본적으로입니다. 클래스 변수와 상수는 기본적으로 이며 `Private` 다른 클래스 멤버는 `Public` 기본적으로입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="3bd36-126">클래스 멤버에 대 한이 동작은 기본값 Visual Basic 6.0 시스템과의 호환성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
- <span data-ttu-id="3bd36-127">구조체에는 하나 이상의 비공유 변수나 비공유 noncustom event 요소가 있어야 합니다. 클래스는 완전히 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
- <span data-ttu-id="3bd36-128">구조체 요소는로 선언할 수 없습니다. `Protected` 클래스 멤버는 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
- <span data-ttu-id="3bd36-129">구조 프로시저는 [공유](../../../language-reference/modifiers/shared.md) 프로시저인 경우에만 이벤트를 처리할 수 있으며, AddHandler 문을 통해서만 이벤트를 처리할 수 있습니다 `Sub` . 모든 클래스 프로시저는 [Handles](../../../language-reference/statements/handles-clause.md) 키워드 또는 문을 사용 하 여 이벤트를 처리할 수 있습니다 [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="3bd36-129">A structure procedure can handle events only if it is a [Shared](../../../language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="3bd36-130">자세한 내용은 [이벤트](../events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bd36-130">For more information, see [Events](../events/index.md).</span></span>  
  
- <span data-ttu-id="3bd36-131">구조체 변수 선언에서 배열의 초기값 또는 초기 크기를 지정할 수 없습니다. 클래스 변수 선언에는를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
- <span data-ttu-id="3bd36-132">구조체는 클래스에서 암시적으로 상속 <xref:System.ValueType?displayProperty=nameWithType> 되며 다른 형식에서 상속할 수 없습니다. 클래스는 이외의 클래스 또는 클래스에서 상속할 수 있습니다 <xref:System.ValueType?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3bd36-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=nameWithType> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="3bd36-133">구조체는 상속할 수 없습니다. 클래스는입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-133">Structures are not inheritable; classes are.</span></span>  
  
- <span data-ttu-id="3bd36-134">구조체는 절대 끝나지 않으므로 CLR (공용 언어 런타임)은 모든 구조에서 메서드를 호출 하지 않습니다. <xref:System.Object.Finalize%2A> 클래스는 GC (가비지 수집기)에 의해 종료 됩니다 .이는 <xref:System.Object.Finalize%2A> 남아 있는 활성 참조가 없는 경우 클래스에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
- <span data-ttu-id="3bd36-135">구조체에는 생성자가 필요 하지 않습니다. 클래스는입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-135">A structure does not require a constructor; a class does.</span></span>  
  
- <span data-ttu-id="3bd36-136">구조체는 매개 변수를 사용 하는 경우에만 비공유 생성자를 포함할 수 있습니다. 클래스는 매개 변수를 포함 하거나 포함 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="3bd36-137">모든 구조체에는 매개 변수가 없는 암시적 public 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="3bd36-138">이 생성자는 모든 구조체의 데이터 요소를 기본값으로 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="3bd36-139">이 동작은 다시 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="3bd36-140">인스턴스 및 변수</span><span class="sxs-lookup"><span data-stu-id="3bd36-140">Instances and Variables</span></span>  
 <span data-ttu-id="3bd36-141">구조체는 값 형식 이므로 각 구조체 변수는 개별 구조체 인스턴스에 영구적으로 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="3bd36-142">그러나 클래스는 참조 형식이 며 개체 변수는 다양 한 시간에 다양 한 클래스 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="3bd36-143">이러한 차이는 다음과 같은 방법으로 구조 및 클래스 사용에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
- <span data-ttu-id="3bd36-144">**초기.**</span><span class="sxs-lookup"><span data-stu-id="3bd36-144">**Initialization.**</span></span> <span data-ttu-id="3bd36-145">구조체 변수에는 구조체의 매개 변수가 없는 생성자를 사용 하 여 요소를 초기화 하는 작업이 암시적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="3bd36-146">따라서 `Dim s As struct1` 는와 동일 `Dim s As struct1 = New struct1()` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
- <span data-ttu-id="3bd36-147">**변수 할당.**</span><span class="sxs-lookup"><span data-stu-id="3bd36-147">**Assigning Variables.**</span></span> <span data-ttu-id="3bd36-148">구조체 변수 하나를 다른 구조체 변수에 할당 하거나 구조 인스턴스를 프로시저 인수에 전달 하는 경우 모든 변수 요소의 현재 값이 새 구조체로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="3bd36-149">한 개체 변수를 다른 변수에 할당 하거나 개체 변수를 프로시저에 전달 하면 참조 포인터만 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
- <span data-ttu-id="3bd36-150">**아무 것도 할당 하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="3bd36-150">**Assigning Nothing.**</span></span> <span data-ttu-id="3bd36-151">구조체 변수에 [Nothing](../../../language-reference/nothing.md) 값을 할당할 수 있지만 인스턴스는 변수와 계속 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-151">You can assign the value [Nothing](../../../language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="3bd36-152">변수 요소는 할당에 의해 다시 초기화 되지만 여전히 해당 메서드를 호출 하 고 해당 데이터 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="3bd36-153">반면, 개체 변수를로 설정 하는 경우 `Nothing` 클래스 인스턴스로부터 분리 하 고 다른 인스턴스를 할당할 때까지 변수를 통해 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
- <span data-ttu-id="3bd36-154">**여러 인스턴스.**</span><span class="sxs-lookup"><span data-stu-id="3bd36-154">**Multiple Instances.**</span></span> <span data-ttu-id="3bd36-155">개체 변수에는 서로 다른 클래스 인스턴스가 할당 될 수 있으며, 여러 개체 변수가 동시에 동일한 클래스 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="3bd36-156">클래스 멤버의 값에 대 한 변경 내용은 동일한 인스턴스를 가리키는 다른 변수를 통해 액세스할 때 해당 멤버에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="3bd36-157">그러나 구조체 요소는 자체 인스턴스 내에서 격리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="3bd36-158">해당 값에 대 한 변경 내용은 다른 구조체 변수에는 적용 되지 않습니다. 동일한 선언의 다른 인스턴스에서도 마찬가지 `Structure` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
- <span data-ttu-id="3bd36-159">**연산.**</span><span class="sxs-lookup"><span data-stu-id="3bd36-159">**Equality.**</span></span> <span data-ttu-id="3bd36-160">두 구조체의 같음 테스트는 요소 및 요소 테스트를 사용 하 여 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="3bd36-161">메서드를 사용 하 여 두 개체 변수를 비교할 수 있습니다 <xref:System.Object.Equals%2A> .</span><span class="sxs-lookup"><span data-stu-id="3bd36-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="3bd36-162"><xref:System.Object.Equals%2A>두 변수가 동일한 인스턴스를 가리키도록 할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bd36-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd36-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bd36-163">See also</span></span>

- [<span data-ttu-id="3bd36-164">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3bd36-164">Data Types</span></span>](index.md)
- [<span data-ttu-id="3bd36-165">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3bd36-165">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="3bd36-166">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="3bd36-166">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="3bd36-167">구조체</span><span class="sxs-lookup"><span data-stu-id="3bd36-167">Structures</span></span>](structures.md)
- [<span data-ttu-id="3bd36-168">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3bd36-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="3bd36-169">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="3bd36-169">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="3bd36-170">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="3bd36-170">Objects and Classes</span></span>](../objects-and-classes/index.md)
