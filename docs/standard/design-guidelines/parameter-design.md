---
description: '자세한 정보: 매개 변수 디자인'
title: 매개 변수 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 9663ef8146054985374fdb3e2974fcd996fd1402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731827"
---
# <a name="parameter-design"></a><span data-ttu-id="d9d8c-103">매개 변수 디자인</span><span class="sxs-lookup"><span data-stu-id="d9d8c-103">Parameter Design</span></span>

<span data-ttu-id="d9d8c-104">이 섹션에서는 인수 확인 지침이 포함된 섹션을 포함하여 매개 변수 디자인에 대한 광범위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-104">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="d9d8c-105">또한 [매개 변수 이름 지정](naming-parameters.md)에 설명된 지침도 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-105">In addition, you should refer to the guidelines described in [Naming Parameters](naming-parameters.md).</span></span>

 <span data-ttu-id="d9d8c-106">✔️ 멤버에 필요한 기능을 제공하는 최소 파생 매개 변수 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-106">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="d9d8c-107">예를 들어 컬렉션을 열거하고 각 항목을 콘솔에 출력하는 메서드를 디자인하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-107">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="d9d8c-108">이러한 메서드는 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.IList>가 아닌 <xref:System.Collections.IEnumerable>을 매개 변수로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-108">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="d9d8c-109">❌ 예약된 매개 변수를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-109">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="d9d8c-110">일부 이후 버전에서 멤버에 대한 추가 입력이 필요한 경우 새 오버로드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-110">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="d9d8c-111">❌ 포인터, 포인터 배열 또는 다차원 배열을 매개 변수로 사용하는 공개적으로 노출된 메서드가 없도록 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-111">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="d9d8c-112">포인터 및 다차원 배열은 제대로 사용하기가 비교적 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-112">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="d9d8c-113">거의 모든 경우에 API는 이러한 형식을 매개 변수로 사용하지 않도록 다시 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-113">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="d9d8c-114">✔️ 오버로드([멤버 오버로드](member-overloading.md) 참조) 간에 매개 변수 순서가 일치하지 않게 되더라도 모든 by-value 및 `ref` 매개 변수(매개 변수 배열 제외) 다음에 모든 `out` 매개 변수를 배치하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-114">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](member-overloading.md)).</span></span>

 <span data-ttu-id="d9d8c-115">`out` 매개 변수는 추가 반환 값으로 확인할 수 있으며, 이러한 매개 변수를 그룹화하면 메서드 시그니처를 더 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-115">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="d9d8c-116">✔️ 멤버를 재정의하거나 인터페이스 멤버를 구현할 때 매개 변수 이름을 일관되게 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-116">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="d9d8c-117">그러면 메서드 간의 관계가 더 잘 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-117">This better communicates the relationship between the methods.</span></span>

### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="d9d8c-118">열거형 및 부울 매개 변수 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="d9d8c-118">Choosing Between Enum and Boolean Parameters</span></span>  

 <span data-ttu-id="d9d8c-119">✔️ 멤버에 둘 이상의 부울 매개 변수가 있는 경우 열거형을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-119">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="d9d8c-120">❌ 셋 이상의 값이 필요하지 않다고 확신할 수 있는 경우에만 부울을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-120">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="d9d8c-121">열거형을 사용하면 나중에 값을 추가할 수 있지만 열거형에 값을 추가할 경우 미칠 수 있는 모든 영향을 알고 있어야 합니다. 자세한 내용은 [열거형 디자인](enum.md)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-121">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](enum.md).</span></span>

 <span data-ttu-id="d9d8c-122">✔️ 실제로 두 가지 상태 값이며 부울 속성을 초기화하는 데만 사용되는 생성자 매개 변수에는 부울을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-122">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validating-arguments"></a><span data-ttu-id="d9d8c-123">인수 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d9d8c-123">Validating Arguments</span></span>

 <span data-ttu-id="d9d8c-124">✔️ 퍼블릭 멤버, 보호된 멤버 또는 명시적으로 구현된 멤버에 전달된 인수의 유효성을 검사하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-124">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="d9d8c-125">유효성 검사가 실패하는 경우 <xref:System.ArgumentException?displayProperty=nameWithType> 또는 해당 서브클래스 중 하나가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-125">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="d9d8c-126">퍼블릭 또는 보호된 멤버 자체에서 실제 유효성 검사가 수행될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-126">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="d9d8c-127">일부 프라이빗 또는 내부 루틴의 하위 수준에서 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-127">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="d9d8c-128">중요한 점은 최종 사용자에게 노출되는 전체 노출 영역에서 인수를 확인한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-128">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="d9d8c-129">✔️ null 인수가 전달된 경우 멤버에서 null 인수를 지원하지 않으면 <xref:System.ArgumentNullException>을 throw하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-129">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="d9d8c-130">✔️ 열거형 매개 변수의 유효성을 검사하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-130">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="d9d8c-131">열거형 인수가 열거형에 의해 정의된 범위 내에 있다고 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-131">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="d9d8c-132">CLR에서는 값이 열거형에 정의되지 않은 경우에도 정수 값을 열거형 값으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-132">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="d9d8c-133">❌ 열거형 범위 확인에 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-133">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="d9d8c-134">✔️ 변경 가능한 인수는 유효성이 검사된 후 변경될 수 있음을 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-134">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="d9d8c-135">보안이 중요한 멤버인 경우 복사본을 만든 다음 인수의 유효성을 검사하고 처리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-135">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="parameter-passing"></a><span data-ttu-id="d9d8c-136">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="d9d8c-136">Parameter Passing</span></span>

 <span data-ttu-id="d9d8c-137">프레임워크 디자이너의 관점에서 by-value 매개 변수, `ref` 매개 변수, `out` 매개 변수의 세 가지 기본 매개 변수 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-137">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="d9d8c-138">by-value 매개 변수를 통해 인수를 전달하면 멤버는 전달된 실제 인수의 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-138">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="d9d8c-139">인수가 값 형식인 경우 인수의 복사본이 스택에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-139">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="d9d8c-140">인수가 참조 형식이면 참조의 복사본이 스택에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-140">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="d9d8c-141">C#, VB.NET, C++ 등 가장 널리 사용되는 CLR 언어는 기본적으로 매개 변수를 값으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-141">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="d9d8c-142">`ref` 매개 변수를 통해 인수를 전달하면 멤버는 전달된 실제 인수에 대한 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-142">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="d9d8c-143">인수가 값 형식인 경우 인수에 대한 참조가 스택에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-143">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="d9d8c-144">인수가 참조 형식이면 참조에 대한 참조가 스택에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-144">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="d9d8c-145">`Ref` 매개 변수를 사용하면 호출자가 전달한 인수를 멤버가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-145">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="d9d8c-146">`Out` 매개 변수는 `ref` 매개 변수와 유사하며, 약간의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-146">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="d9d8c-147">처음에 이 매개 변수는 할당되지 않은 것으로 간주되며, 일부 값이 할당된 다음에야 멤버 본문에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-147">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="d9d8c-148">또한 멤버에서 반환하기 전에 일부 값을 매개 변수에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-148">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="d9d8c-149">❌ `out` 또는 `ref` 매개 변수를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-149">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="d9d8c-150">`out` 또는 `ref` 매개 변수를 사용하려면 포인터 사용 방법을 알고 있어야 하고, 값 형식과 참조 형식이 어떻게 다른지 알고 있어야 하며, 반환 값이 여러 개인 메서드를 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-150">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="d9d8c-151">또한 `out` 매개 변수와 `ref` 매개 변수의 차이점은 잘 알려져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-151">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="d9d8c-152">일반 사용자를 대상으로 디자인하는 프레임워크 설계자는 사용자가 `out` 또는 `ref` 매개 변수를 사용하는 작업에 능숙할 것이라고 기대해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-152">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="d9d8c-153">❌ 참조로 참조 형식을 전달하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-153">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="d9d8c-154">참조를 교환하는 데 사용할 수 있는 메서드와 같이 규칙에는 몇 가지 제한된 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-154">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="d9d8c-155">매개 변수 개수가 가변적인 멤버</span><span class="sxs-lookup"><span data-stu-id="d9d8c-155">Members with Variable Number of Parameters</span></span>

 <span data-ttu-id="d9d8c-156">가변적인 개수의 인수를 사용하는 멤버는 배열 매개 변수를 제공하여 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-156">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="d9d8c-157">예를 들어 <xref:System.String>은 다음과 같은 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-157">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="d9d8c-158">사용자는 다음과 같이 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-158">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="d9d8c-159">C# params 키워드를 배열 매개 변수에 추가하면 매개 변수가 소위 params 배열 매개 변수로 변경되고 임시 배열을 만드는 바로 가기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-159">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="d9d8c-160">이렇게 하면 사용자가 인수 목록에서 직접 배열 요소를 전달하여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-160">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="d9d8c-161">params 키워드는 매개 변수 목록의 마지막 매개 변수에만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-161">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="d9d8c-162">✔️ 최종 사용자가 적은 수의 요소로 배열을 전달할 것으로 예상되는 경우 배열 매개 변수에 params 키워드를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-162">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="d9d8c-163">일반적인 시나리오에서 많은 요소가 전달될 것으로 예상되는 경우 사용자는 이러한 요소를 인라인으로 전달할 수 없으므로 params 키워드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-163">If it's expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="d9d8c-164">❌ 호출자가 거의 항상 배열에 미리 입력하는 경우에는 params 배열을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-164">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="d9d8c-165">예를 들어 바이트 배열 매개 변수를 사용하는 멤버는 개별 바이트를 전달하여 거의 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-165">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="d9d8c-166">따라서 .NET Framework의 바이트 배열 매개 변수는 params 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-166">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="d9d8c-167">❌ 배열이 params 배열 매개 변수를 사용하는 멤버에 의해 수정되는 경우 params 배열을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-167">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="d9d8c-168">대부분의 컴파일러는 멤버에 대한 인수를 호출 사이트에서 임시 배열로 변환하기 때문에 배열이 임시 개체가 되어 배열에 대한 수정 내용이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-168">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="d9d8c-169">✔️ 더 복잡한 오버로드에서 사용할 수 없는 경우 간단한 오버로드에서 params 키워드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-169">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="d9d8c-170">모든 오버로드에 포함되지 않은 경우에도 사용자가 하나의 오버로드에 params 배열을 포함하고 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-170">Ask yourself if users would value having the params array in one overload even if it wasn't in all overloads.</span></span>

 <span data-ttu-id="d9d8c-171">✔️ params 키워드를 사용할 수 있도록 매개 변수의 순서를 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-171">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="d9d8c-172">✔️ 성능이 매우 중요한 API에서는 적은 수의 인수를 사용하는 호출에 대해 특별한 오버로드 및 코드 경로를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-172">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="d9d8c-173">그러면 적은 수의 인수를 사용하여 API를 호출할 때 배열 개체가 생성되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-173">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="d9d8c-174">단수 형태의 배열 매개 변수를 사용하고 숫자 접미사를 추가하여 매개 변수의 이름을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-174">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="d9d8c-175">배열을 만들고 더욱 일반적인 메서드를 호출하는 것만이 아니라 전체 코드 경로를 특별히 처리하려는 경우에만 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-175">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="d9d8c-176">✔️ params 배열 인수로 null을 전달할 수 있음을 인식하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-176">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="d9d8c-177">처리하기 전에 배열이 null이 아닌지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-177">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="d9d8c-178">❌ 줄임표로도 알려져 있는 `varargs` 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-178">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="d9d8c-179">C++과 같은 일부 CLR 언어에서는 `varargs` 메서드라는 변수 매개 변수 목록을 전달하는 대체 규칙을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-179">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="d9d8c-180">규칙은 CLS 규격이 아니기 때문에 프레임워크에서 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-180">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="d9d8c-181">포인터 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9d8c-181">Pointer Parameters</span></span>

 <span data-ttu-id="d9d8c-182">일반적으로 포인터는 잘 디자인된 관리 코드 프레임워크의 퍼블릭 노출 영역에 표시되면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-182">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="d9d8c-183">대부분의 경우 포인터를 캡슐화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-183">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="d9d8c-184">그러나 상호 운용성을 위해 포인터가 필요한 경우가 있으며 이런 경우 포인터를 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-184">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="d9d8c-185">✔️ 포인터는 CLS 규격이 아니므로 포인터 인수를 사용하는 모든 멤버의 대안을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-185">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="d9d8c-186">❌ 포인터 인수에 대해서는 비용이 많이 드는 인수 확인을 수행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-186">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="d9d8c-187">✔️ 포인터를 사용하여 멤버를 디자인할 때는 일반적인 포인터 관련 규칙을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-187">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="d9d8c-188">예를 들어 간단한 포인터 산술을 사용하여 동일한 결과를 얻을 수 있으므로 시작 인덱스를 전달할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9d8c-188">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="d9d8c-189">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="d9d8c-189">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d9d8c-190">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d9d8c-190">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d9d8c-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9d8c-191">See also</span></span>

- [<span data-ttu-id="d9d8c-192">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d9d8c-192">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="d9d8c-193">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d9d8c-193">Framework Design Guidelines</span></span>](index.md)
