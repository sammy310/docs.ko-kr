---
title: 'C# 예약된 특성: null 허용 정적 분석'
ms.date: 02/02/2021
description: null 허용 참조 형식 및 null을 허용하지 않는 참조 형식에 대한 더 나은 정적 분석을 제공하기 위해 컴파일러가 이 특성을 해석합니다.
ms.openlocfilehash: 50fb987ed5c8200e5418d2ea0211b32626538176
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104652687"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a><span data-ttu-id="f78f7-103">예약된 특성은 컴파일러의 null 상태 정적 분석에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-103">Reserved attributes contribute to the compiler's null state static analysis</span></span>

<span data-ttu-id="f78f7-104">null 허용 컨텍스트에서 컴파일러는 코드의 정적 분석을 수행하여 모든 참조 형식 변수의 null 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-104">In a nullable context, the compiler performs static analysis of code to determine the null state of all reference type variables:</span></span>

- <span data-ttu-id="f78f7-105">‘null이 아님’: 정적 분석을 통해 변수에 null이 아닌 값이 할당되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-105">*not null*: Static analysis determines that a variable is assigned a non-null value.</span></span>
- <span data-ttu-id="f78f7-106">‘null일 수 있음’: 정적 분석에서 변수에 null이 아닌 값이 할당되었는지 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-106">*maybe null*: Static analysis can't determine that a variable is assigned a non-null value.</span></span>

<span data-ttu-id="f78f7-107">API의 의미 체계에 대한 정보를 컴파일러에 제공하는 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-107">You can apply attributes that provide information to the compiler about the semantics of your APIs.</span></span> <span data-ttu-id="f78f7-108">이 정보는 컴파일러에서 정적 분석을 수행하고 변수가 null이 아닌 경우를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-108">That information helps the compiler perform static analysis and determine when a variable isn't null.</span></span> <span data-ttu-id="f78f7-109">이 문서에서는 각 특성 및 사용 방법에 대해 간단하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-109">This article provides a brief description of each of those attributes and how to use them.</span></span> <span data-ttu-id="f78f7-110">모든 예제에서는 C# 8.0 이상을 사용한다고 가정하며 코드는 null 허용 컨텍스트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-110">All the examples assume C# 8.0 or newer, and the code is in a nullable context.</span></span>

<span data-ttu-id="f78f7-111">친숙한 예제부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-111">Let's start with a familiar example.</span></span> <span data-ttu-id="f78f7-112">라이브러리에 리소스 문자열을 검색하는 다음 API가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-112">Imagine your library has the following API to retrieve a resource string:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="f78f7-113">앞의 예제는 .NET의 친숙한 `Try*` 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-113">The preceding example follows the familiar `Try*` pattern in .NET.</span></span> <span data-ttu-id="f78f7-114">이 API에 대한 두 개의 참조 인수인 `key` 및 `message` 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-114">There are two reference arguments for this API: the `key` and the `message` parameter.</span></span> <span data-ttu-id="f78f7-115">이 API에는 해당 인수의 nullness에 관련된 다음 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-115">This API has the following rules relating to the nullness of these arguments:</span></span>

- <span data-ttu-id="f78f7-116">호출자는 `null`을 `key`의 인수로 전달하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-116">Callers shouldn't pass `null` as the argument for `key`.</span></span>
- <span data-ttu-id="f78f7-117">호출자는 값이 `null`인 변수를 `message`의 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-117">Callers can pass a variable whose value is `null` as the argument for `message`.</span></span>
- <span data-ttu-id="f78f7-118">`TryGetMessage` 메서드가 `true`를 반환하면 `message` 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-118">If the `TryGetMessage` method returns `true`, the value of `message` isn't null.</span></span> <span data-ttu-id="f78f7-119">반환 값이 `false,`이면 `message`의 값과 해당 null 상태는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-119">If the return value is `false,` the value of `message` (and its null state) is null.</span></span>

<span data-ttu-id="f78f7-120">`key`에 대한 규칙은 변수 형식으로 표현될 수 있습니다. `key`는 null을 허용하지 않는 참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-120">The rule for `key` can be expressed by the variable type: `key` should be a non-nullable reference type.</span></span> <span data-ttu-id="f78f7-121">`message` 매개 변수는 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-121">The `message` parameter is more complex.</span></span> <span data-ttu-id="f78f7-122">`null`을 인수로 허용하지만, 성공 시 해당 `out` 인수가 null이 아님을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-122">It allows `null` as the argument, but guarantees that, on success, that `out` argument isn't null.</span></span> <span data-ttu-id="f78f7-123">이 시나리오의 경우 기대치를 설명하는 더 다양한 어휘가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-123">For these scenarios, you need a richer vocabulary to describe the expectations.</span></span>

<span data-ttu-id="f78f7-124">변수의 null 상태에 대한 추가 정보를 표현하기 위해 여러 가지 특성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-124">Several attributes have been added to express additional information about the null state of variables.</span></span> <span data-ttu-id="f78f7-125">C# 8에 null 허용 참조 형식을 도입하기 전에 작성한 모든 코드는 ‘null 인식 불가능’이었습니다. </span><span class="sxs-lookup"><span data-stu-id="f78f7-125">All code you wrote before C# 8 introduced nullable reference types was *null oblivious*.</span></span> <span data-ttu-id="f78f7-126">즉, 모든 참조 형식 변수가 null일 수 있지만 null 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-126">That means any reference type variable may be null, but null checks aren't required.</span></span> <span data-ttu-id="f78f7-127">코드가 ‘null 허용 인식’이 되면 해당 규칙이 변경됩니다. </span><span class="sxs-lookup"><span data-stu-id="f78f7-127">Once your code is *nullable aware*, those rules change.</span></span> <span data-ttu-id="f78f7-128">참조 형식은 `null` 값이 아니어야 하며 null 허용 참조 형식은 참조되기 전에 `null`에 대해 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-128">Reference types should never be the `null` value, and nullable reference types must be checked against `null` before being dereferenced.</span></span>

<span data-ttu-id="f78f7-129">API에 대한 규칙은 `TryGetValue` API 시나리오에서 살펴본 것처럼 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-129">The rules for your APIs are likely more complicated, as you saw with the `TryGetValue` API scenario.</span></span> <span data-ttu-id="f78f7-130">대부분의 API에는 변수가 `null`일 수 있거나 없는 경우에 대한 더 복잡한 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-130">Many of your APIs have more complex rules for when variables can or can't be `null`.</span></span> <span data-ttu-id="f78f7-131">이 경우에는 다음 특성 중 하나를 사용하여 해당 규칙을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-131">In these cases, you'll use one of the following attributes to express those rules:</span></span>

- <span data-ttu-id="f78f7-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-132">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable argument may be null.</span></span>
- <span data-ttu-id="f78f7-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 인수는 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-133">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable argument should never be null.</span></span>
- <span data-ttu-id="f78f7-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-134">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="f78f7-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-135">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="f78f7-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-136">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 인수는 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-137">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable argument won't be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-138">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="f78f7-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): 메서드는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-139">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="f78f7-140">즉, 항상 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-140">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="f78f7-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): 연결된 `bool` 매개 변수에 지정된 값이 있는 경우 이 메서드는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-141">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>
- <span data-ttu-id="f78f7-142">[MemberNotNull](xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute): 메서드가 반환하는 경우 나열된 멤버는 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-142">[MemberNotNull](xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute): The listed member won't be null when the method returns.</span></span>
- <span data-ttu-id="f78f7-143">[MemberNotNullWhen](xref:System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 나열된 멤버는 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-143">[MemberNotNullWhen](xref:System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute): The listed member won't be null when the method returns the specified `bool` value.</span></span>

<span data-ttu-id="f78f7-144">앞의 설명은 각 특성이 수행하는 작업에 대한 빠른 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-144">The preceding descriptions are a quick reference to what each attribute does.</span></span> <span data-ttu-id="f78f7-145">다음 각 섹션에서는 동작과 의미에 대해 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-145">Each following section describes the behavior and meaning more thoroughly.</span></span>

<span data-ttu-id="f78f7-146">이 특성을 추가하면 API 규칙에 대한 자세한 정보가 컴파일러에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-146">Adding these attributes gives the compiler more information about the rules for your API.</span></span> <span data-ttu-id="f78f7-147">호출 코드가 null 허용 사용 가능 컨텍스트에서 컴파일되는 경우 컴파일러는 해당 규칙을 위반할 때 호출자에게 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-147">When calling code is compiled in a nullable enabled context, the compiler will warn callers when they violate those rules.</span></span> <span data-ttu-id="f78f7-148">이러한 특성은 구현에 대한 더 많은 검사를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-148">These attributes don't enable more checks on your implementation.</span></span>

## <a name="specify-preconditions-allownull-and-disallownull"></a><span data-ttu-id="f78f7-149">전제 조건 지정: `AllowNull` 및 `DisallowNull`</span><span class="sxs-lookup"><span data-stu-id="f78f7-149">Specify preconditions: `AllowNull` and `DisallowNull`</span></span>

<span data-ttu-id="f78f7-150">읽기/쓰기 속성에는 적절한 기본값이 있으므로 `null`을 반환하지 않는 읽기/쓰기 속성을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-150">Consider a read/write property that never returns `null` because it has a reasonable default value.</span></span> <span data-ttu-id="f78f7-151">호출자는 속성을 해당 기본값으로 설정할 때 set 접근자에 `null`을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-151">Callers pass `null` to the set accessor when setting it to that default value.</span></span> <span data-ttu-id="f78f7-152">예를 들어 대화방에서 화면 이름을 요청하는 메시지 시스템을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-152">For example, consider a messaging system that asks for a screen name in a chat room.</span></span> <span data-ttu-id="f78f7-153">아무것도 제공되지 않으면 시스템은 임의 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-153">If none is provided, the system generates a random name:</span></span>

```csharp
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName;
```

<span data-ttu-id="f78f7-154">null 허용 인식 불가능 컨텍스트에서 이전 코드를 컴파일하면 정상적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-154">When you compile the preceding code in a nullable oblivious context, everything is fine.</span></span> <span data-ttu-id="f78f7-155">null 허용 참조 형식을 사용하도록 설정하면 `ScreenName` 속성이 null을 허용하지 않는 참조가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-155">Once you enable nullable reference types, the `ScreenName` property becomes a non-nullable reference.</span></span> <span data-ttu-id="f78f7-156">`get` 접근자의 경우도 마찬가지입니다. 이 접근자는 `null`을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-156">That's correct for the `get` accessor: it never returns `null`.</span></span> <span data-ttu-id="f78f7-157">호출자는 `null`에 대해 반환된 속성을 검사할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-157">Callers don't need to check the returned property for `null`.</span></span> <span data-ttu-id="f78f7-158">그러나 지금 속성을 `null`로 설정하면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-158">But now setting the property to `null` generates a warning.</span></span> <span data-ttu-id="f78f7-159">이 형식의 코드를 지원하려면 다음 코드와 같이 속성에 <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-159">To support this type of code, you add the <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> attribute to the property, as shown in the following code:</span></span>

```csharp
[AllowNull]
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName = GenerateRandomScreenName();
```

<span data-ttu-id="f78f7-160">이 특성과 이 문서에 설명된 다른 특성을 사용하려면 <xref:System.Diagnostics.CodeAnalysis>에 대한 `using` 지시문을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-160">You may need to add a `using` directive for <xref:System.Diagnostics.CodeAnalysis> to use this and other attributes discussed in this article.</span></span> <span data-ttu-id="f78f7-161">이 특성은 `set` 접근자가 아니라 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-161">The attribute is applied to the property, not the `set` accessor.</span></span> <span data-ttu-id="f78f7-162">`AllowNull` 특성은 사전 조건을 지정하며 인수에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-162">The `AllowNull` attribute specifies *pre-conditions*, and only applies to arguments.</span></span> <span data-ttu-id="f78f7-163">`get` 접근자에는 반환 값이 있지만 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-163">The `get` accessor has a return value, but no parameters.</span></span> <span data-ttu-id="f78f7-164">따라서 `AllowNull` 특성은 `set` 접근자에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-164">Therefore, the `AllowNull` attribute only applies to the `set` accessor.</span></span>

<span data-ttu-id="f78f7-165">앞의 예제에서는 인수에 대한 `AllowNull` 특성을 추가할 때 검색할 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-165">The preceding example demonstrates what to look for when adding the `AllowNull` attribute on an argument:</span></span>

1. <span data-ttu-id="f78f7-166">해당 변수에 대한 일반 계약은 `null`이 아니어야 하므로 null을 허용하지 않는 참조 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-166">The general contract for that variable is that it shouldn't be `null`, so you want a non-nullable reference type.</span></span>
1. <span data-ttu-id="f78f7-167">가장 일반적인 사용은 아니지만 매개 변수가 `null`이 되는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-167">There are scenarios for the parameter to be `null`, though they aren't the most common usage.</span></span>

<span data-ttu-id="f78f7-168">일반적으로 속성이나 `in`, `out` 및 `ref` 인수의 경우 이 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-168">Most often you'll need this attribute for properties, or `in`, `out`, and `ref` arguments.</span></span> <span data-ttu-id="f78f7-169">`AllowNull` 특성은 일반적으로 변수가 null이 아닌 경우에 가장 적합하지만, `null`을 전제 조건으로 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-169">The `AllowNull` attribute is the best choice when a variable is typically non-null, but you need to allow `null` as a precondition.</span></span>

<span data-ttu-id="f78f7-170">`DisallowNull` 사용에 대한 시나리오와 비교해 보세요. 이 특성을 사용하여 null 허용 참조 형식의 인수가 `null`이 아니도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-170">Contrast that with scenarios for using `DisallowNull`: You use this attribute to specify that an argument of a nullable reference type shouldn't be `null`.</span></span> <span data-ttu-id="f78f7-171">기본값이 `null`이지만 클라이언트에서 null이 아닌 값으로만 설정할 수 있는 속성을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-171">Consider a property where `null` is the default value, but clients can only set it to a non-null value.</span></span> <span data-ttu-id="f78f7-172">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="f78f7-172">Consider the following code:</span></span>

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

<span data-ttu-id="f78f7-173">이전 코드는 `ReviewComment`가 `null`일 수 있지만 `null`로 설정될 수 없는 의도를 표현하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-173">The preceding code is the best way to express your design that the `ReviewComment` could be `null`, but can't be set to `null`.</span></span> <span data-ttu-id="f78f7-174">이 코드가 null 허용 인식이 되면 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>를 사용하여 호출자에게 이 개념을 보다 명확하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-174">Once this code is nullable aware, you can express this concept more clearly to callers using the <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>:</span></span>

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

<span data-ttu-id="f78f7-175">null 허용 컨텍스트에서 `ReviewComment` `get` 접근자는 `null`의 기본값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-175">In a nullable context, the `ReviewComment` `get` accessor could return the default value of `null`.</span></span> <span data-ttu-id="f78f7-176">컴파일러는 액세스하기 전에 검사해야 한다는 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-176">The compiler warns that it must be checked before access.</span></span> <span data-ttu-id="f78f7-177">또한 `null`일 수 있는 경우에도 호출자가 명시적으로 `null`로 설정하지 않아야 한다는 경고를 호출자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-177">Furthermore, it warns callers that, even though it could be `null`, callers shouldn't explicitly set it to `null`.</span></span> <span data-ttu-id="f78f7-178">또한 `DisallowNull` 특성은 전제 조건을 지정하며 `get` 접근자에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-178">The `DisallowNull` attribute also specifies a *pre-condition*, it doesn't affect the `get` accessor.</span></span> <span data-ttu-id="f78f7-179">다음에 대해 이 특성을 관찰할 때 `DisallowNull` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-179">You use the `DisallowNull` attribute when you observe these characteristics about:</span></span>

1. <span data-ttu-id="f78f7-180">변수는 처음 인스턴스화될 때 주로 핵심 시나리오에서 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-180">The variable could be `null` in core scenarios, often when first instantiated.</span></span>
1. <span data-ttu-id="f78f7-181">변수를 명시적으로 `null`로 설정하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-181">The variable shouldn't be explicitly set to `null`.</span></span>

<span data-ttu-id="f78f7-182">이 상황은 원래 ‘null 인식 불가능’이었던 코드에서 일반적입니다. </span><span class="sxs-lookup"><span data-stu-id="f78f7-182">These situations are common in code that was originally *null oblivious*.</span></span> <span data-ttu-id="f78f7-183">개체 속성은 두 개의 개별 초기화 작업에서 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-183">It may be that object properties are set in two distinct initialization operations.</span></span> <span data-ttu-id="f78f7-184">일부 속성은 일부 비동기 작업이 완료된 후에만 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-184">It may be that some properties are set only after some asynchronous work has completed.</span></span>

<span data-ttu-id="f78f7-185">`AllowNull` 및 `DisallowNull` 특성을 사용하여 변수에 대한 전제 조건이 해당 변수의 null 허용 주석과 일치하지 않을 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-185">The `AllowNull` and `DisallowNull` attributes enable you to specify that preconditions on variables may not match the nullable annotations on those variables.</span></span> <span data-ttu-id="f78f7-186">이 특성은 API의 특징에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-186">These provide more detail about the characteristics of your API.</span></span> <span data-ttu-id="f78f7-187">이 추가 정보는 호출자가 API를 올바르게 사용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-187">This additional information helps callers use your API correctly.</span></span> <span data-ttu-id="f78f7-188">다음 특성을 사용하여 전제 조건을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-188">Remember you specify preconditions using the following attributes:</span></span>

- <span data-ttu-id="f78f7-189">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-189">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable argument may be null.</span></span>
- <span data-ttu-id="f78f7-190">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 인수는 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-190">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable argument should never be null.</span></span>

## <a name="specify-post-conditions-maybenull-and-notnull"></a><span data-ttu-id="f78f7-191">사후 조건 지정: `MaybeNull` 및 `NotNull`</span><span class="sxs-lookup"><span data-stu-id="f78f7-191">Specify post-conditions: `MaybeNull` and `NotNull`</span></span>

<span data-ttu-id="f78f7-192">다음 시그니처를 사용하는 메서드가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-192">Suppose you have a method with the following signature:</span></span>

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

<span data-ttu-id="f78f7-193">검색한 이름을 찾을 수 없는 경우 `null`을 반환하도록 이 메서드를 작성했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-193">You've likely written a method like this to return `null` when the name sought wasn't found.</span></span> <span data-ttu-id="f78f7-194">`null`은 분명히 레코드를 찾을 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-194">The `null` clearly indicates that the record wasn't found.</span></span> <span data-ttu-id="f78f7-195">이 예제에서는 반환 형식을 `Customer`에서 `Customer?`로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-195">In this example, you'd likely change the return type from `Customer` to `Customer?`.</span></span> <span data-ttu-id="f78f7-196">반환 값을 null 허용 참조 형식으로 선언하면 이 API의 의도가 분명하게 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-196">Declaring the return value as a nullable reference type specifies the intent of this API clearly.</span></span>

<span data-ttu-id="f78f7-197">[제네릭 정의 및 null 허용 여부](../../nullable-migration-strategies.md#generic-definitions-and-nullability)에서 설명하는 이유로 해당 기술은 제네릭 메서드에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-197">For reasons covered under [Generic definitions and nullability](../../nullable-migration-strategies.md#generic-definitions-and-nullability) that technique doesn't work with generic methods.</span></span> <span data-ttu-id="f78f7-198">비슷한 패턴을 따르는 제네릭 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-198">You may have a generic method that follows a similar pattern:</span></span>

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

<span data-ttu-id="f78f7-199">반환 값이 `T?`이도록 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-199">You can't specify that the return value is `T?`.</span></span> <span data-ttu-id="f78f7-200">검색한 항목을 찾을 수 없는 경우 메서드는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-200">The method returns `null` when the sought item isn't found.</span></span> <span data-ttu-id="f78f7-201">`T?` 반환 형식을 선언할 수 없으므로 `MaybeNull` 주석을 메서드 반환에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-201">Since you can't declare a `T?` return type, you add the `MaybeNull` annotation to the method return:</span></span>

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

<span data-ttu-id="f78f7-202">이전 코드는 계약이 null을 허용하지 않는 형식을 의미한다는 것을 호출자에게 알리지만, 반환 값은 실제로 null’일 수 있습니다’. </span><span class="sxs-lookup"><span data-stu-id="f78f7-202">The preceding code informs callers that the contract implies a non-nullable type, but the return value *may* actually be null.</span></span>  <span data-ttu-id="f78f7-203">API가 null을 허용하지 않는 형식(일반적으로 제네릭 형식 매개 변수)이어야 하지만 `null`이 반환되는 인스턴스가 있을 수 있는 경우 `MaybeNull` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-203">Use the `MaybeNull` attribute when your API should be a non-nullable type, typically a generic type parameter, but there may be instances where `null` would be returned.</span></span>

<span data-ttu-id="f78f7-204">형식이 null 허용 참조 형식인 경우에도 반환 값이나 `out` 또는 `ref` 인수가 null이 아니도록 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-204">You can also specify that a return value or an `out` or `ref` argument isn't null even though the type is a nullable reference type.</span></span> <span data-ttu-id="f78f7-205">배열이 많은 요소를 포함할 만큼 충분히 큰지 확인하는 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-205">Consider a method that ensures an array is large enough to hold a number of elements.</span></span> <span data-ttu-id="f78f7-206">인수에 용량이 없으면 루틴은 새 배열을 할당하고 기존 요소를 모두 새 배열로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-206">If the argument doesn't have capacity, the routine would allocate a new array and copy all the existing elements into it.</span></span> <span data-ttu-id="f78f7-207">인수가 `null`이면 루틴은 새 스토리지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-207">If the argument is `null`, the routine would allocate new storage.</span></span> <span data-ttu-id="f78f7-208">충분한 용량이 있는 경우 루틴은 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-208">If there's sufficient capacity, the routine does nothing:</span></span>

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

<span data-ttu-id="f78f7-209">다음과 같이 이 루틴을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-209">You could call this routine as follows:</span></span>

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

<span data-ttu-id="f78f7-210">null 참조 형식을 사용하도록 설정한 후 이전 코드가 경고 없이 컴파일되는지 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-210">After enabling null reference types, you want to ensure that the preceding code compiles without warnings.</span></span> <span data-ttu-id="f78f7-211">메서드가 반환하는 경우 `storage` 인수는 null이 아님이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-211">When the method returns, the `storage` argument is guaranteed to be not null.</span></span> <span data-ttu-id="f78f7-212">그러나 null 참조를 사용하여 `EnsureCapacity`를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-212">However, it's acceptable to call `EnsureCapacity` with a null reference.</span></span> <span data-ttu-id="f78f7-213">`storage`를 null 허용 참조 형식으로 만들고 `NotNull` 사후 조건을 매개 변수 선언에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-213">You can make `storage` a nullable reference type, and add the `NotNull` post-condition to the parameter declaration:</span></span>

```csharp
public void EnsureCapacity<T>([NotNull] ref T[]? storage, int size)
```

<span data-ttu-id="f78f7-214">이전 코드는 기존 계약을 명확하게 표현합니다. 호출자는 `null` 값과 함께 변수를 전달할 수 있지만 반환 값은 null이 아님이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-214">The preceding code expresses the existing contract clearly: Callers can pass a variable with the `null` value, but the return value is guaranteed to never be null.</span></span> <span data-ttu-id="f78f7-215">`null`이 인수로 전달될 수 있지만 메서드가 반환할 때 해당 인수가 null이 아님이 보장되는 경우 `NotNull` 특성은 `ref` 및 `out` 인수에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-215">The `NotNull` attribute is most useful for `ref` and `out` arguments where `null` may be passed as an argument, but that argument is guaranteed to be not null when the method returns.</span></span>

<span data-ttu-id="f78f7-216">다음 특성을 사용하여 무조건 사후 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-216">You specify unconditional postconditions using the following attributes:</span></span>

- <span data-ttu-id="f78f7-217">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-217">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="f78f7-218">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-218">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a><span data-ttu-id="f78f7-219">조건부 사후 조건 지정: `NotNullWhen`, `MaybeNullWhen` 및 `NotNullIfNotNull`</span><span class="sxs-lookup"><span data-stu-id="f78f7-219">Specify conditional post-conditions: `NotNullWhen`, `MaybeNullWhen`, and `NotNullIfNotNull`</span></span>

<span data-ttu-id="f78f7-220">`string` 메서드 <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>에 대해 잘 알고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-220">You're likely familiar with the `string` method <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>.</span></span> <span data-ttu-id="f78f7-221">인수가 null이거나 빈 문자열인 경우 이 메서드는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-221">This method returns `true` when the argument is null or an empty string.</span></span> <span data-ttu-id="f78f7-222">이는 null 검사의 한 가지 형태입니다. 메서드가 `false`를 반환하는 경우 호출자는 인수를 null 검사할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-222">It's a form of null-check: Callers don't need to null-check the argument if the method returns `false`.</span></span> <span data-ttu-id="f78f7-223">메서드를 이 null 허용 인식처럼 만들려면 인수를 null 허용 참조 형식으로 설정하고 `NotNullWhen` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-223">To make a method like this nullable aware, you'd set the argument to a nullable reference type, and add the `NotNullWhen` attribute:</span></span>

```csharp
bool IsNullOrEmpty([NotNullWhen(false)] string? value);
```

<span data-ttu-id="f78f7-224">이를 통해 반환 값이 `false`인 코드는 null 검사가 필요하지 않음을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-224">That informs the compiler that any code where the return value is `false` doesn't need null checks.</span></span> <span data-ttu-id="f78f7-225">특성을 추가하여 `IsNullOrEmpty`가 필요한 null 검사를 수행한다는 것을 컴파일러의 정적 분석에 알립니다. `false`를 반환하는 경우 인수는 `null`이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-225">The addition of the attribute informs the compiler's static analysis that `IsNullOrEmpty` performs the necessary null check: when it returns `false`, the argument isn't `null`.</span></span>

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

<span data-ttu-id="f78f7-226">.NET Core 3.0의 경우 위에 표시된 대로 <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> 메서드가 주석으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-226">The <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> method will be annotated as shown above for .NET Core 3.0.</span></span> <span data-ttu-id="f78f7-227">null 값에 대한 개체의 상태를 확인하는 비슷한 메서드가 코드베이스에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-227">You may have similar methods in your codebase that check the state of objects for null values.</span></span> <span data-ttu-id="f78f7-228">컴파일러는 사용자 지정 null 검사 메서드를 인식하지 않으며 주석을 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-228">The compiler won't recognize custom null check methods, and you'll need to add the annotations yourself.</span></span> <span data-ttu-id="f78f7-229">특성을 추가하면 컴파일러의 정적 분석은 테스트된 변수가 null 검사된 시기를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-229">When you add the attribute, the compiler's static analysis knows when the tested variable has been null checked.</span></span>

<span data-ttu-id="f78f7-230">또한 이 특성은 `Try*` 패턴에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-230">Another use for these attributes is the `Try*` pattern.</span></span> <span data-ttu-id="f78f7-231">`ref` 및 `out` 변수에 대한 사후 조건은 반환 값을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-231">The postconditions for `ref` and `out` variables are communicated through the return value.</span></span> <span data-ttu-id="f78f7-232">앞에서 설명한 이 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-232">Consider this method shown earlier:</span></span>

```csharp
bool TryGetMessage(string key, out string message)
```

<span data-ttu-id="f78f7-233">이전 메서드는 일반적인 .NET 관용구를 따릅니다. 반환 값은 `message`가 발견된 값으로 설정되었는지 또는 메시지가 없는 경우 기본값으로 설정되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-233">The preceding method follows a typical .NET idiom: the return value indicates if `message` was set to the found value or, if no message is found, to the default value.</span></span> <span data-ttu-id="f78f7-234">메서드가 `true`를 반환하는 경우 `message`의 값은 null이 아닙니다. 이 값을 반환하지 않는 경우 메서드는 `message`를 null로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-234">If the method returns `true`, the value of `message` isn't null; otherwise, the method sets `message` to null.</span></span>

<span data-ttu-id="f78f7-235">`NotNullWhen` 특성을 사용하여 해당 관용구를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-235">You can communicate that idiom using the `NotNullWhen` attribute.</span></span> <span data-ttu-id="f78f7-236">null 허용 참조 형식의 시그니처를 업데이트하는 경우 `string?`을 `message`로 만들고 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-236">When you update the signature for nullable reference types, make `message` a `string?` and add an attribute:</span></span>

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

<span data-ttu-id="f78f7-237">이전 예제에서 `TryGetMessage`가 `true`를 반환하는 경우 `message` 값은 null이 아닌 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-237">In the preceding example, the value of `message` is known to be not null when `TryGetMessage` returns `true`.</span></span> <span data-ttu-id="f78f7-238">동일한 방식으로 코드베이스에서 비슷한 메서드를 주석으로 처리해야 합니다. 인수는 `null`일 수 있으며 메서드가 `true`를 반환하는 경우 null이 아닌 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-238">You should annotate similar methods in your codebase in the same way: the arguments could be `null`, and are known to be not null when the method returns `true`.</span></span>

<span data-ttu-id="f78f7-239">한 가지 마지막 특성이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-239">There's one final attribute you may also need.</span></span> <span data-ttu-id="f78f7-240">경우에 따라 반환 값의 null 상태는 하나 이상의 인수의 null 상태에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-240">Sometimes the null state of a return value depends on the null state of one or more arguments.</span></span> <span data-ttu-id="f78f7-241">해당 메서드는 특정 인수가 `null`이 아닐 때마다 null이 아닌 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-241">These methods will return a non-null value whenever certain arguments aren't `null`.</span></span> <span data-ttu-id="f78f7-242">해당 메서드를 주석으로 올바르게 처리하려면 `NotNullIfNotNull` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-242">To correctly annotate these methods, you use the `NotNullIfNotNull` attribute.</span></span> <span data-ttu-id="f78f7-243">다음 태그를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-243">Consider the following method:</span></span>

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

<span data-ttu-id="f78f7-244">`url` 인수가 null이 아니면 출력은 `null`이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-244">If the `url` argument isn't null, the output isn't `null`.</span></span> <span data-ttu-id="f78f7-245">null 허용 참조가 사용하도록 설정되면 API에서 null 인수를 허용하지 않는 경우 해당 시그니처가 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-245">Once nullable references are enabled, that signature works correctly, provided your API never accepts a null argument.</span></span> <span data-ttu-id="f78f7-246">그러나 인수가 null일 수 있는 경우에는 반환 값도 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-246">However, if the argument could be null, then return value could also be null.</span></span> <span data-ttu-id="f78f7-247">시그니처를 다음 코드로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-247">You could change the signature to the following code:</span></span>

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="f78f7-248">또한 시그니처가 작동하지만 호출자가 추가 `null` 검사를 강제로 구현하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-248">That also works, but will often force callers to implement extra `null` checks.</span></span> <span data-ttu-id="f78f7-249">계약은 인수 `url`이 `null`인 경우에만 반환 값이 `null`이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-249">The contract is that the return value would be `null` only when the argument `url` is `null`.</span></span> <span data-ttu-id="f78f7-250">해당 계약을 표현하려면 다음 코드와 같이 이 메서드를 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-250">To express that contract, you would annotate this method as shown in the following code:</span></span>

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

<span data-ttu-id="f78f7-251">반환 값 및 인수 중 하나가 `null`일 수 있음을 나타내는 `?`를 사용하여 두 항목을 모두 주석으로 처리했습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-251">The return value and the argument have both been annotated with the `?` indicating that either could be `null`.</span></span> <span data-ttu-id="f78f7-252">특성은 `url` 인수가 `null`이 아닌 경우 반환 값이 null이 아님을 명확하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-252">The attribute further clarifies that the return value won't be null when the `url` argument isn't `null`.</span></span>

<span data-ttu-id="f78f7-253">해당 특성을 사용하여 조건부 사후 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-253">You specify conditional postconditions using these attributes:</span></span>

- <span data-ttu-id="f78f7-254">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-254">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-255">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 인수는 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-255">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable argument won't be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-256">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-256">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the argument for the specified parameter isn't null.</span></span>

## <a name="constructor-helper-methods-membernotnull-and-membernotnullwhen"></a><span data-ttu-id="f78f7-257">생성자 도우미 메서드: `MemberNotNull` 및 `MemberNotNullWhen`</span><span class="sxs-lookup"><span data-stu-id="f78f7-257">Constructor helper methods: `MemberNotNull` and `MemberNotNullWhen`</span></span>

<span data-ttu-id="f78f7-258">이러한 특성은 생성자에서 공용 코드를 도우미 메서드로 리팩터링할 때 의도를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-258">These attributes specify your intent when you've refactored common code from constructors into helper methods.</span></span> <span data-ttu-id="f78f7-259">C# 컴파일러는 생성자 및 필드 이니셜라이저를 분석하여 각 생성자를 반환하기 전에 null을 허용하지 않는 모든 참조 필드가 초기화되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-259">The C# compiler analyzes constructors and field initializers to make sure that all non-nullable reference fields have been initialized before each constructor returns.</span></span> <span data-ttu-id="f78f7-260">그러나 C# 컴파일러가 모든 도우미 메서드에서 필드 할당을 추적하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-260">However, the C# compiler doesn't track field assignments through all helper methods.</span></span> <span data-ttu-id="f78f7-261">컴파일러는 필드가 생성자에서 직접 초기화되지 않고 도우미 메서드에서 초기화되는 경우 `CS8618` 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-261">The compiler issues warning `CS8618` when fields aren't initialized directly in the constructor, but rather in a helper method.</span></span> <span data-ttu-id="f78f7-262">메서드 선언에 <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute>를 추가하고 메서드에서 Null이 아닌 값으로 초기화되는 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-262">You add the <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute> to a method declaration and specify the fields that are initialized to a non-null value in the method.</span></span> <span data-ttu-id="f78f7-263">예를 들어 다음 예제를 고려해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-263">For example, consider the following example:</span></span>

:::code language="csharp" source="snippets/InitializeMembers.cs" ID="MemberNotNullExample":::

<span data-ttu-id="f78f7-264">`MemberNotNull` 특성 생성자에 대한 인수로 여러 필드 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-264">You can specify multiple field names as arguments to the `MemberNotNull` attribute constructor.</span></span>

<span data-ttu-id="f78f7-265"><xref:System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute>에는 `bool` 인수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-265">The <xref:System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute> has a `bool` argument.</span></span> <span data-ttu-id="f78f7-266">도우미 메서드가 도우미 메서드에서 필드를 초기화했는지 여부를 나타내는 `bool`을 반환하는 경우 `MemberNotNullWhen`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-266">You use `MemberNotNullWhen` in situations where your helper method returns a `bool` indicating whether your helper method initialized fields.</span></span>

## <a name="verify-unreachable-code"></a><span data-ttu-id="f78f7-267">접근할 수 없는 코드 확인</span><span class="sxs-lookup"><span data-stu-id="f78f7-267">Verify unreachable code</span></span>

<span data-ttu-id="f78f7-268">일반적으로 예외 도우미 또는 기타 유틸리티 메서드와 같은 일부 메서드는 항상 예외를 throw하여 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-268">Some methods, typically exception helpers or other utility methods, always exit by throwing an exception.</span></span> <span data-ttu-id="f78f7-269">또는 도우미는 부울 인수 값을 기반으로 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-269">Or, a helper may throw an exception based on the value of a Boolean argument.</span></span>

<span data-ttu-id="f78f7-270">첫 번째 경우에 `DoesNotReturn` 특성을 메서드 선언에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-270">In the first case, you can add the `DoesNotReturn` attribute to the method declaration.</span></span> <span data-ttu-id="f78f7-271">컴파일러는 세 가지 방법으로 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-271">The compiler helps you in three ways.</span></span> <span data-ttu-id="f78f7-272">첫째, 예외를 throw하지 않고 메서드가 종료될 수 있는 경로가 있는 경우 컴파일러는 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-272">First, the compiler issues a warning if there's a path where the method can exit without throwing an exception.</span></span> <span data-ttu-id="f78f7-273">둘째, 컴파일러는 해당 메서드를 호출한 후 적절한 `catch` 절이 나타날 때까지 코드를 접근할 수 없음으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-273">Second, the compiler marks any code after a call to that method as *unreachable*, until an appropriate `catch` clause is found.</span></span> <span data-ttu-id="f78f7-274">셋째, 접근할 수 없는 코드는 null 상태에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-274">Third, the unreachable code won't affect any null states.</span></span> <span data-ttu-id="f78f7-275">이 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-275">Consider this method:</span></span>

```csharp
[DoesNotReturn]
private void FailFast()
{
    throw new InvalidOperationException();
}

public void SetState(object containedField)
{
    if (!isInitialized)
    {
        FailFast();
    }

    // unreachable code:
    _field = containedField;
}
```

<span data-ttu-id="f78f7-276">두 번째 경우에는 메서드의 부울 매개 변수에 `DoesNotReturnIf` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-276">In the second case, you add the `DoesNotReturnIf` attribute to a Boolean parameter of the method.</span></span> <span data-ttu-id="f78f7-277">이전 예제를 다음과 같이 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-277">You can modify the previous example as follows:</span></span>

```csharp
private void FailFast([DoesNotReturnIf(false)] bool isValid)
{
    if (!isValid)
    {
        throw new InvalidOperationException();
    }
}

public void SetState(object containedField)
{
    FailFast(isInitialized);

    // unreachable code when "isInitialized" is false:
    _field = containedField;
}
```

## <a name="summary"></a><span data-ttu-id="f78f7-278">요약</span><span class="sxs-lookup"><span data-stu-id="f78f7-278">Summary</span></span>

[!INCLUDE [C# version alert](../../includes/csharp-version-alert.md)]

<span data-ttu-id="f78f7-279">null 허용 참조 형식을 추가하면 `null`일 수 있는 변수의 API 기대치를 설명하는 초기 어휘가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-279">Adding nullable reference types provides an initial vocabulary to describe your APIs expectations for variables that could be `null`.</span></span> <span data-ttu-id="f78f7-280">특성은 변수의 null 상태를 전제 조건 및 사후 조건으로 설명하는 다양한 어휘를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-280">The attributes provide a richer vocabulary to describe the null state of variables as preconditions and postconditions.</span></span> <span data-ttu-id="f78f7-281">해당 특성은 기대치를 명확하게 설명하며 API를 사용하는 개발자에게 더 나은 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-281">These attributes more clearly describe your expectations and provide a better experience for the developers using your APIs.</span></span>

<span data-ttu-id="f78f7-282">null 허용 컨텍스트의 라이브러리를 업데이트할 때 해당 특성을 추가하여 API 사용자가 올바르게 사용하도록 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-282">As you update libraries for a nullable context, add these attributes to guide users of your APIs to the correct usage.</span></span> <span data-ttu-id="f78f7-283">해당 특성을 통해 인수 및 반환 값의 null 상태를 완벽하게 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-283">These attributes help you fully describe the null-state of arguments and return values:</span></span>

- <span data-ttu-id="f78f7-284">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-284">[AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): A non-nullable argument may be null.</span></span>
- <span data-ttu-id="f78f7-285">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 인수는 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-285">[DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): A nullable argument should never be null.</span></span>
- <span data-ttu-id="f78f7-286">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-286">[MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): A non-nullable return value may be null.</span></span>
- <span data-ttu-id="f78f7-287">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-287">[NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): A nullable return value will never be null.</span></span>
- <span data-ttu-id="f78f7-288">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 인수는 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-288">[MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): A non-nullable argument may be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-289">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 인수는 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-289">[NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): A nullable argument won't be null when the method returns the specified `bool` value.</span></span>
- <span data-ttu-id="f78f7-290">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-290">[NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): A return value isn't null if the argument for the specified parameter isn't null.</span></span>
- <span data-ttu-id="f78f7-291">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): 메서드는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-291">[DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): A method never returns.</span></span> <span data-ttu-id="f78f7-292">즉, 항상 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-292">In other words, it always throws an exception.</span></span>
- <span data-ttu-id="f78f7-293">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): 연결된 `bool` 매개 변수에 지정된 값이 있는 경우 이 메서드는 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f78f7-293">[DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): This method never returns if the associated `bool` parameter has the specified value.</span></span>
