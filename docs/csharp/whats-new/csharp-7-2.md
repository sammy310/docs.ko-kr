---
title: C# 7.2의 새로운 기능
description: C# 7.2의 새로운 기능에 대한 개요입니다.
ms.date: 08/16/2017
ms.openlocfilehash: b8b2be68aac3cba92e0dbd74dfe4ee3cbbef0e88
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185352"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="33d43-103">C# 7.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="33d43-103">What's new in C# 7.2</span></span>

<span data-ttu-id="33d43-104">C# 7.2는 다양한 유용한 기능을 추가하는 또 하나의 지점 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="33d43-105">이 릴리스의 한 테마는 불필요한 복사 또는 할당 없이 값 유형을 사용하여 보다 효율적으로 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span>

<span data-ttu-id="33d43-106">나머지 기능은 작지만 멋진 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="33d43-107">C# 7.2는 [언어 버전 선택](../language-reference/configure-language-version.md) 구성 요소를 사용하여 컴파일러 언어 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="33d43-108">이 릴리스의 새로운 언어 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="33d43-109">안전하고 효율적인 코드를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="33d43-109">Techniques for writing safe efficient code</span></span>](#safe-efficient-code-enhancements)
  - <span data-ttu-id="33d43-110">참조 의미 체계를 사용하는 값 유형으로 작동할 수 있는 구문 개선의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="33d43-111">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="33d43-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="33d43-112">명명된 인수 뒤에는 위치 인수가 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="33d43-113">숫자 리터럴의 선행 밑줄</span><span class="sxs-lookup"><span data-stu-id="33d43-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="33d43-114">숫자 리터럴은 이제 인쇄된 숫자 앞에 선행 밑줄이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="33d43-115">`private protected` 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="33d43-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="33d43-116">`private protected` 액세스 한정자는 동일한 어셈블리의 파생된 클래스에 대해 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
* [<span data-ttu-id="33d43-117">조건부 `ref` 식</span><span class="sxs-lookup"><span data-stu-id="33d43-117">Conditional `ref` expressions</span></span>](#conditional-ref-expressions)
  - <span data-ttu-id="33d43-118">이제 조건식(`?:`)의 결과가 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-118">The result of a conditional expression (`?:`) can now be a reference.</span></span>

## <a name="safe-efficient-code-enhancements"></a><span data-ttu-id="33d43-119">안전하고 효율적인 코드 개선 사항</span><span class="sxs-lookup"><span data-stu-id="33d43-119">Safe efficient code enhancements</span></span>

<span data-ttu-id="33d43-120">7.2에 도입된 언어 기능을 사용하면 참조 의미 체계를 사용하면서 값 형식을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-120">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="33d43-121">참조 유형 사용과 관련된 메모리를 할당하지 않으면서 값 형식 복사를 최소화하여 성능을 향상시키도록 설계되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-121">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="33d43-122">포함된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-122">The features include:</span></span>

- <span data-ttu-id="33d43-123">매개 변수의 `in` 한정자는 인수가 참조에 의해 전달되지만 호출된 메서드에 의해 수정되지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-123">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="33d43-124">`in` 한정자를 인수에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-124">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="33d43-125">메서드의 `ref readonly` 한정자는 메서드가 참조별 값을 반환하지만 해당 개체에 대한 쓰기를 허용하지 않음을 나타내기 위해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-125">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="33d43-126">반환이 값에 할당되는 경우 `ref readonly` 한정자를 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-126">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="33d43-127">기존 `ref` 반환 문에 `readonly` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-127">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="33d43-128">호출자가 `readonly` 한정자를 포함하도록 `ref` 지역 변수의 선언을 업데이트하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-128">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="33d43-129">`readonly struct` 선언은 구조체가 변경 가능하지 않으며 `in` 매개 변수로서 멤버 메서드로 전달되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-129">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="33d43-130">기존 구조체 선언에 `readonly` 한정자를 추가하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-130">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="33d43-131">`ref struct` 선언은 구조체 유형이 관리되는 메모리에 직접 액세스하고 항상 스택에 할당되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-131">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="33d43-132">기존 `struct` 선언에 `ref` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-132">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="33d43-133">`ref struct`는 클래스의 멤버가 되거나 힙에 할당될 수 있는 다른 위치에서 사용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-133">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="33d43-134">[안전하고 효율적인 코드 작성](../write-safe-efficient-code.md)에서 모든 변경 내용을 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-134">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="33d43-135">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="33d43-135">Non-trailing named arguments</span></span>

<span data-ttu-id="33d43-136">명명된 인수가 올바른 위치에 있을 때 메서드 호출은 이제 위치 인수보다 앞에 있는 명명된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-136">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="33d43-137">자세한 내용은 [명명된 인수 및 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33d43-137">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="33d43-138">숫자 리터럴의 선행 밑줄</span><span class="sxs-lookup"><span data-stu-id="33d43-138">Leading underscores in numeric literals</span></span>

<span data-ttu-id="33d43-139">C# 7.0에서는 자릿수 구분 기호에 대한 지원을 구현해도 `_`이 리터럴 값의 첫 번째 문자가 되는 것을 허용하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-139">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="33d43-140">16진수 및 이진 숫자 리터럴은 이제 `_`로 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-140">Hex and binary numeric literals may now begin with an `_`.</span></span>

<span data-ttu-id="33d43-141">예:</span><span class="sxs-lookup"><span data-stu-id="33d43-141">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="33d43-142">_private protected_ 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="33d43-142">_private protected_ access modifier</span></span>

<span data-ttu-id="33d43-143">새로운 복합 액세스 한정자인 `private protected`는 동일한 어셈블리에 선언된 클래스 또는 파생 클래스를 포함하여 멤버에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-143">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="33d43-144">`protected internal`은 동일한 어셈블리에 있는 파생 클래스나 클래스에 의한 액세스를 허용하지만 `private protected`는 동일한 어셈블리에서 선언된 파생 유형에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-144">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="33d43-145">자세한 내용은 언어 참조의 [액세스 한정자](../language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33d43-145">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="conditional-ref-expressions"></a><span data-ttu-id="33d43-146">조건부 `ref` 식</span><span class="sxs-lookup"><span data-stu-id="33d43-146">Conditional `ref` expressions</span></span>

<span data-ttu-id="33d43-147">마지막으로, 조건식은 값 결과 대신 참조 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-147">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="33d43-148">예를 들어 다음을 작성하여 두 배열 중 하나의 첫 번째 요소에 대한 참조를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-148">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="33d43-149">`r` 변수는 `arr` 또는 `otherArr`의 첫 번째 값에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="33d43-149">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="33d43-150">자세한 내용은 언어 참조에서 [조건부 연산자(?:)](../language-reference/operators/conditional-operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33d43-150">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>
