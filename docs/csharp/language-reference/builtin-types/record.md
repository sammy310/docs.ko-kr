---
title: 레코드 - C# 참조
description: C#의 레코드 형식에 대해 알아봅니다.
ms.date: 02/25/2021
f1_keywords:
- record_CSharpKeyword
helpviewer_keywords:
- record keyword [C#]
- record type [C#]
ms.openlocfilehash: 10fe7bcc1f3239b7a6bde0abcac41b177467cf0a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260031"
---
# <a name="records-c-reference"></a><span data-ttu-id="ae362-103">레코드(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ae362-103">Records (C# reference)</span></span>

<span data-ttu-id="ae362-104">C# 9부터 `record` 키워드를 사용하여 데이터를 캡슐화하는 기본 제공 기능을 제공하는 [참조 형식](reference-types.md)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-104">Beginning with C# 9, you use the `record` keyword to define a [reference type](reference-types.md) that provides built-in functionality for encapsulating data.</span></span> <span data-ttu-id="ae362-105">위치 매개 변수 또는 표준 속성 구문을 사용하여 변경할 수 없는 속성이 있는 레코드 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-105">You can create record types with immutable properties by using positional parameters or standard property syntax:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalRecord":::
:::code language="csharp" source="snippets/shared/RecordType.cs" id="ImmutableRecord":::

<span data-ttu-id="ae362-106">변경할 수 있는 속성 및 필드를 사용하여 레코드 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-106">You can also create record types with mutable properties and fields:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MutableRecord":::

<span data-ttu-id="ae362-107">레코드는 변경할 수 있지만 주로 변경할 수 없는 데이터 모델을 지원하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-107">While records can be mutable, they are primarily intended for supporting immutable data models.</span></span> <span data-ttu-id="ae362-108">레코드 형식은 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-108">The record type offers the following features:</span></span>

* [<span data-ttu-id="ae362-109">변경할 수 없는 속성을 사용하여 참조 형식을 만드는 간결한 구문</span><span class="sxs-lookup"><span data-stu-id="ae362-109">Concise syntax for creating a reference type with immutable properties</span></span>](#positional-syntax-for-property-definition)
* <span data-ttu-id="ae362-110">데이터 중심 참조 형식에 유용한 기본 제공 동작:</span><span class="sxs-lookup"><span data-stu-id="ae362-110">Built-in behavior useful for a data-centric reference type:</span></span>
  * [<span data-ttu-id="ae362-111">값 같음</span><span class="sxs-lookup"><span data-stu-id="ae362-111">Value equality</span></span>](#value-equality)
  * [<span data-ttu-id="ae362-112">비파괴적 변형을 위한 간결한 구문</span><span class="sxs-lookup"><span data-stu-id="ae362-112">Concise syntax for nondestructive mutation</span></span>](#nondestructive-mutation)
  * [<span data-ttu-id="ae362-113">표시를 위한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="ae362-113">Built-in formatting for display</span></span>](#built-in-formatting-for-display)
* [<span data-ttu-id="ae362-114">상속 계층 구조 지원</span><span class="sxs-lookup"><span data-stu-id="ae362-114">Support for inheritance hierarchies</span></span>](#inheritance)

<span data-ttu-id="ae362-115">[구조 형식](struct.md)을 사용하여 값 같음을 제공하고 동작이 거의 또는 전혀 발생하지 않는 데이터 중심 형식을 디자인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-115">You can also use [structure types](struct.md) to design data-centric types that provide value equality and little or no behavior.</span></span> <span data-ttu-id="ae362-116">그러나 비교적 규모가 큰 데이터 모델의 경우 구조체 형식에는 몇 가지 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-116">But for relatively large data models, structure types have some disadvantages:</span></span>

* <span data-ttu-id="ae362-117">상속을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-117">They don't support inheritance.</span></span>
* <span data-ttu-id="ae362-118">값 같음을 판별하는 효율성이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-118">They're less efficient at determining value equality.</span></span> <span data-ttu-id="ae362-119">값 형식의 경우 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 메서드는 리플렉션을 사용하여 모든 필드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-119">For value types, the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> method uses reflection to find all fields.</span></span> <span data-ttu-id="ae362-120">레코드의 경우 컴파일러가 `Equals` 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-120">For records, the compiler generates the `Equals` method.</span></span> <span data-ttu-id="ae362-121">실제로 레코드에서 값 같음을 구현하는 것이 어느 정도 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-121">In practice, the implementation of value equality in records is measurably faster.</span></span>
* <span data-ttu-id="ae362-122">모든 인스턴스는 모든 데이터의 전체 복사본을 포함하기 때문에 일부 시나리오에서는 더 많은 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-122">They use more memory in some scenarios, since every instance has a complete copy of all of the data.</span></span> <span data-ttu-id="ae362-123">레코드 형식은 [참조 형식](reference-types.md)이므로 레코드 인스턴스는 데이터에 대한 참조만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-123">Record types are [reference types](reference-types.md), so a record instance contains only a reference to the data.</span></span>

## <a name="positional-syntax-for-property-definition"></a><span data-ttu-id="ae362-124">속성 정의에 대한 위치 구문</span><span class="sxs-lookup"><span data-stu-id="ae362-124">Positional syntax for property definition</span></span>

<span data-ttu-id="ae362-125">위치 매개 변수를 사용하여 레코드의 속성을 선언하고 인스턴스를 만들 때 속성 값을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-125">You can use positional parameters to declare properties of a record and to initialize the property values when you create an instance:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InstantiatePositional":::

<span data-ttu-id="ae362-126">속성 정의에 위치 구문을 사용하는 경우 컴파일러가 다음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-126">When you use the positional syntax for property definition, the compiler creates:</span></span>

* <span data-ttu-id="ae362-127">레코드 선언에 제공된 각 위치 매개 변수에 대한 공용 초기화 전용 자동 구현 속성.</span><span class="sxs-lookup"><span data-stu-id="ae362-127">A public init-only auto-implemented property for each positional parameter provided in the record declaration.</span></span> <span data-ttu-id="ae362-128">[초기화 전용](../../whats-new/csharp-9.md#init-only-setters) 속성은 생성자에서만 또는 속성 이니셜라이저를 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-128">An [init-only](../../whats-new/csharp-9.md#init-only-setters) property can only be set in the constructor or by using a property initializer.</span></span>
* <span data-ttu-id="ae362-129">매개 변수가 레코드 선언의 위치 매개 변수와 일치하는 기본 생성자.</span><span class="sxs-lookup"><span data-stu-id="ae362-129">A primary constructor whose parameters match the positional parameters on the record declaration.</span></span>
* <span data-ttu-id="ae362-130">레코드 선언에 제공된 각 위치 매개 변수에 대한 `out` 매개 변수를 사용하는 `Deconstruct` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ae362-130">A `Deconstruct` method with an `out` parameter for each positional parameter provided in the record declaration.</span></span> <span data-ttu-id="ae362-131">이 메서드는 둘 이상의 위치 매개 변수가 있는 경우에만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-131">This method is provided only if there are two or more positional parameters.</span></span> <span data-ttu-id="ae362-132">메서드는 위치 구문을 사용하여 정의된 속성을 분해합니다. 표준 속성 구문을 사용하여 정의된 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-132">The method deconstructs properties defined by using positional syntax; it ignores properties that are defined by using standard property syntax.</span></span>

<span data-ttu-id="ae362-133">생성된 자동 구현 속성 정의가 원하는 내용이 아니면 동일한 이름의 속성을 직접 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-133">If the generated auto-implemented property definition isn't what you want, you can define your own property of the same name.</span></span> <span data-ttu-id="ae362-134">그러면 생성된 생성자 및 분해자에서 이 속성 정의를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-134">If you do that, the generated constructor and deconstructor will use your property definition.</span></span> <span data-ttu-id="ae362-135">예를 들어 다음 예제에서는 `FirstName` 위치 속성 `internal`을 `public` 대신 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-135">For instance, the following example makes the `FirstName` positional property `internal` instead of `public`.</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalWithManualProperty":::

<span data-ttu-id="ae362-136">레코드 형식은 위치 속성을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-136">A record type doesn't have to declare any positional properties.</span></span> <span data-ttu-id="ae362-137">다음 예제와 같이 위치 속성 없이 레코드를 선언하고 추가 필드 및 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-137">You can declare a record without any positional properties, and you can declare additional fields and properties, as in the following example:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MixedSyntax":::

<span data-ttu-id="ae362-138">표준 속성 구문을 사용하여 속성을 정의하지만 액세스 한정자를 생략하면 속성은 암시적으로 `public`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-138">If you define properties by using standard property syntax but omit the access modifier, the properties are implicitly `public`.</span></span>
<!-- Todo -- Explain issues surrounding use of attributes on positional properties. -->

## <a name="immutability"></a><span data-ttu-id="ae362-139">불변성</span><span class="sxs-lookup"><span data-stu-id="ae362-139">Immutability</span></span>

<span data-ttu-id="ae362-140">레코드 형식이 반드시 변경 불가능해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-140">A record type is not necessarily immutable.</span></span> <span data-ttu-id="ae362-141">`readonly`가 아닌 `set` 접근자 및 필드를 사용하여 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-141">You can declare properties with `set` accessors and fields that aren't `readonly`.</span></span> <span data-ttu-id="ae362-142">그러나 레코드는 변경할 수 있지만 이를 통해 변경할 수 없는 데이터 모델을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-142">But while records can be mutable, they make it easier to create immutable data models.</span></span>

<span data-ttu-id="ae362-143">불변성은 데이터 중심 형식이 스레드로부터 안전해야 하거나 해시 테이블에서 동일하게 남아 있는 해시 코드를 사용하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-143">Immutability can be useful when you need a data-centric type to be thread-safe or you're depending on a hash code remaining the same in a hash table.</span></span> <span data-ttu-id="ae362-144">하지만 불변성이 모든 데이터 시나리오에 적합한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-144">Immutability isn't appropriate for all data scenarios, however.</span></span> <span data-ttu-id="ae362-145">예를 들어, [Entity Framework Core](/ef/core/)는 변경할 수 없는 엔터티 형식을 사용한 업데이트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-145">[Entity Framework Core](/ef/core/), for example, doesn't support updating with immutable entity types.</span></span>

<span data-ttu-id="ae362-146">위치 매개 변수에서 생성되든 또는 `init` 접근자를 지정하여 생성되든 상관없이 초기화 전용 속성에는 ‘단순 불변성’이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-146">Init-only properties, whether created from positional parameters or by specifying `init` accessors, have *shallow immutability*.</span></span> <span data-ttu-id="ae362-147">초기화 후에는 값 형식 속성의 값 또는 참조 형식 속성의 참조를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-147">After initialization, you can't change the value of value-type properties or the reference of reference-type properties.</span></span> <span data-ttu-id="ae362-148">그러나 참조 형식 속성이 참조하는 데이터는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-148">However, the data that a reference-type property refers to can be changed.</span></span> <span data-ttu-id="ae362-149">다음 예제에서는 참조 형식 변경 불가능 속성의 콘텐츠(이 경우에는 배열)를 변경할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-149">The following example shows that the content of a reference-type immutable property (an array in this case) is mutable:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ShallowImmutability":::

<span data-ttu-id="ae362-150">레코드 형식에 고유한 기능이 컴파일러 합성 메서드로 구현되고, 이러한 메서드는 개체 상태를 수정하여 불변성을 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-150">The features unique to record types are implemented by compiler-synthesized methods, and none of these methods compromises immutability by modifying object state.</span></span>

## <a name="value-equality"></a><span data-ttu-id="ae362-151">값 같음</span><span class="sxs-lookup"><span data-stu-id="ae362-151">Value equality</span></span>

<span data-ttu-id="ae362-152">값 같음은 형식이 일치하고 모든 속성 및 필드 값이 일치하는 경우 레코드 형식의 두 변수가 같다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-152">Value equality means that two variables of a record type are equal if the types match and all property and field values match.</span></span> <span data-ttu-id="ae362-153">다른 참조 형식의 경우 같음은 ID를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-153">For other reference types, equality means identity.</span></span> <span data-ttu-id="ae362-154">즉, 참조 형식의 두 변수는 같은 개체를 참조하는 경우 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-154">That is, two variables of a reference type are equal if they refer to the same object.</span></span>

<span data-ttu-id="ae362-155">일부 데이터 모델에서는 참조 같음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-155">Reference equality is required for some data models.</span></span> <span data-ttu-id="ae362-156">예를 들어, [Entity Framework Core](/ef/core/)는 참조 같음을 사용하여 개념적으로 하나의 엔터티에 해당하는 엔터티 형식의 인스턴스를 하나만 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-156">For example, [Entity Framework Core](/ef/core/) depends on reference equality to ensure that it uses only one instance of an entity type for what is conceptually one entity.</span></span> <span data-ttu-id="ae362-157">이러한 이유로 레코드 형식은 Entity Framework Core에서 엔터티 형식으로 사용하기에 적절하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-157">For this reason, record types aren't appropriate for use as entity types in Entity Framework Core.</span></span>

<span data-ttu-id="ae362-158">다음 예제에서는 레코드 형식의 값 같음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-158">The following example illustrates value equality of record types:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="Equality":::

<span data-ttu-id="ae362-159">값 같음을 구현하기 위해 컴파일러는 다음 메서드를 합성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-159">To implement value equality, the compiler synthesizes the following methods:</span></span>

* <span data-ttu-id="ae362-160"><xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>의 재정의.</span><span class="sxs-lookup"><span data-stu-id="ae362-160">An override of <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>.</span></span>

  <span data-ttu-id="ae362-161">두 매개 변수가 모두 Null이 아닌 경우 이 메서드가 <xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType> 정적 메서드의 기본으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-161">This method is used as the basis for the <xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType> static method when both parameters are non-null.</span></span>

* <span data-ttu-id="ae362-162">매개 변수가 레코드 종류인 가상 `Equals` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ae362-162">A virtual `Equals` method whose parameter is the record type.</span></span> <span data-ttu-id="ae362-163">이 메서드는 <xref:System.IEquatable%601>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-163">This method implements <xref:System.IEquatable%601>.</span></span>

* <span data-ttu-id="ae362-164"><xref:System.Object.GetHashCode?displayProperty=nameWithType>의 재정의.</span><span class="sxs-lookup"><span data-stu-id="ae362-164">An override of <xref:System.Object.GetHashCode?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="ae362-165">연산자 `==` 및 `!=`의 재정의.</span><span class="sxs-lookup"><span data-stu-id="ae362-165">Overrides of operators `==` and `!=`.</span></span>

<span data-ttu-id="ae362-166">`class` 형식에서 같음 메서드 및 연산자를 수동으로 재정의하여 값 같음을 얻을 수 있지만, 해당 코드를 개발하고 테스트하는 데는 시간이 많이 걸리고 오류가 발생하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-166">In `class` types, you could manually override equality methods and operators to achieve value equality, but developing and testing that code would be time-consuming and error-prone.</span></span> <span data-ttu-id="ae362-167">이 기능을 기본 제공하면 속성 또는 필드가 추가되거나 변경될 때 사용자 지정 재정의 코드를 업데이트하지 않는 버그가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-167">Having this functionality built-in prevents bugs that would result from forgetting to update custom override code when properties or fields are added or changed.</span></span>

<span data-ttu-id="ae362-168">사용자 고유의 구현을 작성하여 이러한 합성된 메서드를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-168">You can write your own implementations to replace any of these synthesized methods.</span></span> <span data-ttu-id="ae362-169">레코드 종류에 합성 메서드의 시그니처와 일치하는 메서드가 있는 경우 해당 메서드는 컴파일러에서 합성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-169">If a record type has a method that matches the signature of any synthesized method, the compiler doesn't synthesize that method.</span></span>

<span data-ttu-id="ae362-170">레코드 형식에서 `Equals`의 고유한 구현을 제공하는 경우 `GetHashCode`의 구현도 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="ae362-170">If you provide your own implementation of `Equals` in a record type, provide an implementation of `GetHashCode` also.</span></span>

## <a name="nondestructive-mutation"></a><span data-ttu-id="ae362-171">비파괴적 변경</span><span class="sxs-lookup"><span data-stu-id="ae362-171">Nondestructive mutation</span></span>

<span data-ttu-id="ae362-172">레코드 인스턴스의 변경 불가능한 속성을 변경해야 하는 경우에는 `with` 식을 사용하여 ‘비파괴적 변형’을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-172">If you need to mutate immutable properties of a record instance, you can use a `with` expression to achieve *nondestructive mutation*.</span></span> <span data-ttu-id="ae362-173">`with` 식은 기존 레코드 인스턴스의 지정된 속성 및 필드가 수정된 복사본인 새 레코드 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-173">A `with` expression makes a new record instance that is a copy of an existing record instance, with specified properties and fields modified.</span></span> <span data-ttu-id="ae362-174">다음 예제와 같이 [개체 이니셜라이저](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) 구문을 사용하여 변경할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-174">You use [object initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) syntax to specify the values to be changed, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressions":::

<span data-ttu-id="ae362-175">`with` 식은 위치 속성 또는 표준 속성 구문을 사용하여 만든 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-175">The `with` expression can set positional properties or properties created by using standard property syntax.</span></span> <span data-ttu-id="ae362-176">비위치 속성에는 `with` 식에서 변경할 `init` 또는 `set` 접근자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-176">Non-positional properties must have an `init` or `set` accessor to be changed in a `with` expression.</span></span>

<span data-ttu-id="ae362-177">`with` 식의 결과는 ‘단순 복사본’입니다. 즉, 참조 속성의 경우 인스턴스에 대한 참조만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-177">The result of a `with` expression is a *shallow copy*, which means that for a reference property, only the reference to an instance is copied.</span></span> <span data-ttu-id="ae362-178">원본 레코드와 복사본은 모두 동일한 인스턴스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-178">Both the original record and the copy end up with a reference to the same instance.</span></span>

<span data-ttu-id="ae362-179">이 기능을 구현하기 위해 컴파일러는 clone 메서드와 복사 생성자를 합성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-179">To implement this feature, the compiler synthesizes a clone method and a copy constructor.</span></span> <span data-ttu-id="ae362-180">생성자는 복사할 레코드의 인스턴스를 사용하여 clone 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-180">The constructor takes an instance of the record to be copied and calls the clone method.</span></span> <span data-ttu-id="ae362-181">`with` 식을 사용하는 경우 컴파일러는 복사 생성자를 호출하는 코드를 만든 다음 `with` 식에 지정된 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-181">When you use a `with` expression, the compiler creates code that calls the copy constructor and then sets the properties that are specified in the `with` expression.</span></span>

<span data-ttu-id="ae362-182">다른 복사 동작이 필요한 경우 사용자 고유의 복사 생성자를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-182">If you need different copying behavior, you can write your own copy constructor.</span></span> <span data-ttu-id="ae362-183">이렇게 하면 컴파일러는 생성자를 합성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-183">If you do that, the compiler won't synthesize one.</span></span> <span data-ttu-id="ae362-184">레코드가 `sealed`면 생성자를 `private`로 설정하고 그렇지 않으면 `protected`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-184">Make your constructor `private` if the record is `sealed`, otherwise make it `protected`.</span></span>

<span data-ttu-id="ae362-185">Clone 메서드는 재정의할 수 없으며 `Clone`이라는 멤버는 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-185">You can't override the clone method, and you can't create a member named `Clone`.</span></span> <span data-ttu-id="ae362-186">Clone 메서드의 실제 이름은 컴파일러에서 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-186">The actual name of the clone method is compiler-generated.</span></span>

## <a name="built-in-formatting-for-display"></a><span data-ttu-id="ae362-187">표시를 위한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="ae362-187">Built-in formatting for display</span></span>

<span data-ttu-id="ae362-188">레코드 형식에는 공용 속성 및 필드의 이름과 값을 표시하는 컴파일러 생성 <xref:System.Object.ToString%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-188">Record types have a compiler-generated <xref:System.Object.ToString%2A> method that displays the names and values of public properties and fields.</span></span> <span data-ttu-id="ae362-189">`ToString` 메서드는 다음 형식의 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-189">The `ToString` method returns a string of the following format:</span></span>

> <span data-ttu-id="ae362-190">\<record type name> { \<property name> = \<value>, \<property name> = \<value>, ...}</span><span class="sxs-lookup"><span data-stu-id="ae362-190">\<record type name> { \<property name> = \<value>, \<property name> = \<value>, ...}</span></span>

<span data-ttu-id="ae362-191">참조 형식의 경우 속성이 참조하는 개체의 형식 이름이 속성 값 대신 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-191">For reference types, the type name of the object that the property refers to is displayed instead of the property value.</span></span> <span data-ttu-id="ae362-192">다음 예제에서는 배열이 참조 형식이므로 `System.String[]`이 실제 배열 요소 값 대신 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-192">In the following example, the array is a reference type, so `System.String[]` is displayed instead of the actual array element values:</span></span>

```
Person { FirstName = Nancy, LastName = Davolio, ChildNames = System.String[] } 
```

<span data-ttu-id="ae362-193">이 기능을 구현하기 위해 컴파일러는 가상 `PrintMembers` 메서드와 <xref:System.Object.ToString%2A> 재정의를 합성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-193">To implement this feature, the compiler synthesizes a virtual `PrintMembers` method and a <xref:System.Object.ToString%2A> override.</span></span>
<span data-ttu-id="ae362-194">`ToString` 재정의는 형식 이름과 그 뒤의 여는 괄호를 사용하여 <xref:System.Text.StringBuilder> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-194">The `ToString` override creates a <xref:System.Text.StringBuilder> object with the type name followed by an opening bracket.</span></span> <span data-ttu-id="ae362-195">`PrintMembers`를 호출하여 속성 이름 및 값을 추가한 다음 닫는 괄호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-195">It calls `PrintMembers` to add property names and values, then adds the closing bracket.</span></span> <span data-ttu-id="ae362-196">다음 예제에서는 합성된 재정의에 포함된 것과 유사한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-196">The following example shows code similar to what the synthesized override contains:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringOverrideDefault":::

<span data-ttu-id="ae362-197">`PrintMembers` 또는 `ToString` 재정의의 고유한 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-197">You can provide your own implementation of `PrintMembers` or the `ToString` override.</span></span> <span data-ttu-id="ae362-198">예제는 이 문서의 뒷부분에 나오는 [파생 레코드의 `PrintMembers` 형식](#printmembers-formatting-in-derived-records) 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-198">Examples are provided in the [`PrintMembers` formatting in derived records](#printmembers-formatting-in-derived-records) section later in this article.</span></span>

## <a name="inheritance"></a><span data-ttu-id="ae362-199">상속</span><span class="sxs-lookup"><span data-stu-id="ae362-199">Inheritance</span></span>

<span data-ttu-id="ae362-200">레코드는 다른 레코드에서 상속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-200">A record can inherit from another record.</span></span> <span data-ttu-id="ae362-201">그러나 레코드는 클래스에서 상속될 수 없고 클래스는 레코드에서 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-201">However, a record can't inherit from a class, and a class can't inherit from a record.</span></span>

### <a name="positional-parameters-in-derived-record-types"></a><span data-ttu-id="ae362-202">파생 레코드 형식의 위치 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae362-202">Positional parameters in derived record types</span></span>

<span data-ttu-id="ae362-203">파생 레코드는 기본 레코드 기본 생성자의 모든 매개 변수에 대한 위치 매개 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-203">The derived record declares positional parameters for all the parameters in the base record primary constructor.</span></span> <span data-ttu-id="ae362-204">기본 레코드는 이러한 속성을 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-204">The base record declares and initializes those properties.</span></span> <span data-ttu-id="ae362-205">파생 레코드는 이러한 속성을 숨기지는 않지만 기본 레코드에 선언되지 않은 매개 변수의 속성만 만들고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-205">The derived record doesn't hide them, but only creates and initializes properties for parameters that aren't declared in its base record.</span></span>

<span data-ttu-id="ae362-206">다음 예제에서는 위치 속성 구문을 사용한 상속을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-206">The following example illustrates inheritance with positional property syntax:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalInheritance":::

### <a name="equality-in-inheritance-hierarchies"></a><span data-ttu-id="ae362-207">상속 계층 구조에서의 같음</span><span class="sxs-lookup"><span data-stu-id="ae362-207">Equality in inheritance hierarchies</span></span>

<span data-ttu-id="ae362-208">두 레코드 변수가 같으려면 런타임 형식이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-208">For two record variables to be equal, the run-time type must be equal.</span></span> <span data-ttu-id="ae362-209">포함하는 변수의 형식은 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-209">The types of the containing variables might be different.</span></span> <span data-ttu-id="ae362-210">다음 코드 예제가 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-210">This is illustrated in the following code example:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InheritanceEquality":::

<span data-ttu-id="ae362-211">예제에서 모든 인스턴스에는 동일한 속성 및 동일한 속성 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-211">In the example, all instances have the same properties and the same property values.</span></span> <span data-ttu-id="ae362-212">그러나 모두 `Person` 형식 변수이지만 `student == teacher`는 `False`를 반환하고, 하나는 `Person` 변수이고 하나는 `Student` 변수이지만 `student == student2`는 `True`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-212">But `student == teacher` returns `False` although both are `Person`-type variables, and `student == student2` returns `True` although one is a `Person` variable and one is a `Student` variable.</span></span>

<span data-ttu-id="ae362-213">이 동작을 구현하기 위해 컴파일러는 레코드 형식과 일치하는 <xref:System.Type> 개체를 반환하는 `EqualityContract` 속성을 합성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-213">To implement this behavior, the compiler synthesizes an `EqualityContract` property that returns a <xref:System.Type> object that matches the type of the record.</span></span> <span data-ttu-id="ae362-214">이렇게 하면 같음 메서드가 같음을 확인할 때 개체의 런타임 형식을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-214">This enables the equality methods to compare the runtime type of objects when they are checking for equality.</span></span> <span data-ttu-id="ae362-215">레코드의 기본 형식이 `object`이면 이 속성은 `virtual`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-215">If the base type of a record is `object`, this property is `virtual`.</span></span> <span data-ttu-id="ae362-216">기본 형식이 또 다른 레코드 형식이면 이 속성은 재정의입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-216">If the base type is another record type, this property is an override.</span></span> <span data-ttu-id="ae362-217">레코드 형식이 `sealed`이면 이 속성은 `sealed`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-217">If the record type is `sealed`, this property is `sealed`.</span></span>

<span data-ttu-id="ae362-218">파생 형식의 두 인스턴스를 비교하는 경우 합성된 같음 메서드는 기본 및 파생 형식의 모든 속성에 서 같음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-218">When comparing two instances of a derived type, the synthesized equality methods check all properties of the base and derived types for equality.</span></span> <span data-ttu-id="ae362-219">합성된 `GetHashCode` 메서드는 기본 형식 및 파생 레코드 형식에 선언된 모든 속성과 필드의 `GetHashCode` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-219">The synthesized `GetHashCode` method uses the `GetHashCode` method from all properties and fields declared in the base type and the derived record type.</span></span>

### <a name="with-expressions-in-derived-records"></a><span data-ttu-id="ae362-220">파생 레코드의 `with` 식</span><span class="sxs-lookup"><span data-stu-id="ae362-220">`with` expressions in derived records</span></span>

<span data-ttu-id="ae362-221">합성된 clone 메서드는 [공변 반환 형식](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)을 사용하므로 `with` 식의 결과는 식의 피연산자와 동일한 런타임 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-221">Because the synthesized clone method uses a [covariant return type](~/_csharplang/proposals/csharp-9.0/covariant-returns.md), the result of a `with` expression has the same run-time type as the expression's operand.</span></span> <span data-ttu-id="ae362-222">런타임 형식의 속성은 모두 복사되지만 다음 예제와 같이 컴파일 시간 형식의 속성만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-222">All properties of the run-time type get copied, but you can only set properties of the compile-time type, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressionInheritance":::

### <a name="printmembers-formatting-in-derived-records"></a><span data-ttu-id="ae362-223">파생 레코드의 `PrintMembers` 형식</span><span class="sxs-lookup"><span data-stu-id="ae362-223">`PrintMembers` formatting in derived records</span></span>

<span data-ttu-id="ae362-224">파생 레코드 형식의 합성된 `PrintMembers` 메서드는 기본 구현을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-224">The synthesized `PrintMembers` method of a derived record type calls the base implementation.</span></span> <span data-ttu-id="ae362-225">그러면 다음 예제와 같이 파생된 형식과 기본 형식의 모든 공용 속성 및 필드가 `ToString` 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-225">The result is that all public properties and fields of both derived and base types are included in the `ToString` output, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringInheritance":::

<span data-ttu-id="ae362-226">`PrintMembers` 메서드의 고유한 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-226">You can provide your own implementation of the `PrintMembers` method.</span></span> <span data-ttu-id="ae362-227">이렇게 하려면 다음 서명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-227">If you do that, use the following signature:</span></span>

* <span data-ttu-id="ae362-228">`object`에서 파생되는 `sealed` 레코드(기본 레코드를 선언하지 않음): `private bool PrintMembers(StringBuilder builder)`</span><span class="sxs-lookup"><span data-stu-id="ae362-228">For a `sealed` record that derives from `object` (doesn't declare a base record): `private bool PrintMembers(StringBuilder builder)`;</span></span>
* <span data-ttu-id="ae362-229">다른 레코드에서 파생되는 `sealed` 레코드: `protected sealed override bool PrintMembers(StringBuilder builder)`</span><span class="sxs-lookup"><span data-stu-id="ae362-229">For a `sealed` record that derives from another record: `protected sealed override bool PrintMembers(StringBuilder builder)`;</span></span>
* <span data-ttu-id="ae362-230">`sealed`가 아니고 개체에서 파생된 레코드: `protected virtual bool PrintMembers(StringBuilder builder);`</span><span class="sxs-lookup"><span data-stu-id="ae362-230">For a record that isn't `sealed` and derives from object: `protected virtual bool PrintMembers(StringBuilder builder);`</span></span>
* <span data-ttu-id="ae362-231">`sealed`가 아니고 다른 레코드에서 파생된 레코드: `protected override bool PrintMembers(StringBuilder builder);`</span><span class="sxs-lookup"><span data-stu-id="ae362-231">For a record that isn't `sealed` and derives from another record: `protected override bool PrintMembers(StringBuilder builder);`</span></span>

<span data-ttu-id="ae362-232">다음은 합성된 `PrintMembers` 메서드를 대체하는 코드의 예제입니다. 하나는 개체에서 파생되는 레코드 형식이고 다른 하나는 다른 레코드에서 파생되는 레코드 형식에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-232">Here is an example of code that replaces the synthesized `PrintMembers` methods, one for a record type that derives from object, and one for a record type that derives from another record:</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PrintMembersImplementation":::

### <a name="deconstructor-behavior-in-derived-records"></a><span data-ttu-id="ae362-233">파생 레코드의 분해자 동작</span><span class="sxs-lookup"><span data-stu-id="ae362-233">Deconstructor behavior in derived records</span></span>

<span data-ttu-id="ae362-234">파생 레코드의 `Deconstruct` 메서드는 컴파일 시간 형식의 모든 위치 속성 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-234">The `Deconstruct` method of a derived record returns the values of all positional properties of the compile-time type.</span></span> <span data-ttu-id="ae362-235">변수 형식이 기본 레코드인 경우 개체가 파생 형식으로 캐스팅되는 경우를 제외하고는 기본 레코드 속성만 분해됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-235">If the variable type is a base record, only the base record properties are deconstructed unless the object is cast to the derived type.</span></span> <span data-ttu-id="ae362-236">다음 예제에서는 파생 레코드에 대해 분해자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-236">The following example demonstrates calling a deconstructor on a derived record.</span></span>

:::code language="csharp" source="snippets/shared/RecordType.cs" id="DeconstructorInheritance":::

## <a name="generic-constraints"></a><span data-ttu-id="ae362-237">제네릭 제약 조건</span><span class="sxs-lookup"><span data-stu-id="ae362-237">Generic constraints</span></span>

<span data-ttu-id="ae362-238">형식이 레코드가 되어야 하는 제네릭 제약 조건은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-238">There is no generic constraint that requires a type to be a record.</span></span> <span data-ttu-id="ae362-239">레코드는 `class` 제약 조건을 만족합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-239">Records satisfy the `class` constraint.</span></span> <span data-ttu-id="ae362-240">레코드 형식의 특정 계층 구조에 대한 제약 조건을 만들려면 기본 클래스와 동일한 방식으로 기본 레코드에 제약 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae362-240">To make a constraint on a specific hierarchy of record types, put the constraint on the base record as you would a base class.</span></span> <span data-ttu-id="ae362-241">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae362-241">For more information, see [Constraints on type parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ae362-242">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ae362-242">C# language specification</span></span>

<span data-ttu-id="ae362-243">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [클래스](~/_csharplang/spec/classes.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae362-243">For more information, see the [Classes](~/_csharplang/spec/classes.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="ae362-244">C# 9 이상에 도입된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae362-244">For more information about features introduced in C# 9 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="ae362-245">레코드</span><span class="sxs-lookup"><span data-stu-id="ae362-245">Records</span></span>](~/_csharplang/proposals/csharp-9.0/records.md)
- [<span data-ttu-id="ae362-246">초기화 전용 setter</span><span class="sxs-lookup"><span data-stu-id="ae362-246">Init-only setters</span></span>](~/_csharplang/proposals/csharp-9.0/init.md)
- [<span data-ttu-id="ae362-247">공변 반환</span><span class="sxs-lookup"><span data-stu-id="ae362-247">Covariant returns</span></span>](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)

## <a name="see-also"></a><span data-ttu-id="ae362-248">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae362-248">See also</span></span>

- [<span data-ttu-id="ae362-249">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ae362-249">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ae362-250">디자인 지침 - 클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="ae362-250">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="ae362-251">디자인 지침-구조체 디자인</span><span class="sxs-lookup"><span data-stu-id="ae362-251">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="ae362-252">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="ae362-252">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="ae362-253">`with` 식</span><span class="sxs-lookup"><span data-stu-id="ae362-253">`with` expression</span></span>](../operators/with-expression.md)
