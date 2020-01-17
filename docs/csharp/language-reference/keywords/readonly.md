---
title: readonly 키워드 - C# 참조
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: f9fa6f893e7f999564c4dcb43d40755547d3c793
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713120"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="0393b-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0393b-102">readonly (C# Reference)</span></span>

<span data-ttu-id="0393b-103">`readonly` 키워드는 다음 네 가지 컨텍스트에서 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="0393b-104">[필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="0393b-105">필드 선언과 생성자 내에서 읽기 전용 필드를 여러 번 할당 및 재할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="0393b-106">생성자가 종료된 후에는 `readonly` 필드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="0393b-107">이 규칙의 의미는 값 형식과 참조 형식에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="0393b-108">값 형식에는 해당 데이터가 직접 포함되므로, `readonly` 값 형식인 필드는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="0393b-109">참조 형식에는 해당 데이터에 대한 참조가 포함되므로, `readonly` 참조 형식인 필드는 항상 같은 개체를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="0393b-110">해당 개체는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-110">That object isn't immutable.</span></span> <span data-ttu-id="0393b-111">`readonly` 한정자는 필드가 참조 형식의 다른 인스턴스로 바뀌지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="0393b-112">그러나 이 한정자는 필드의 인스턴스 데이터가 읽기 전용 필드를 통해 수정되는 것을 방지하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="0393b-113">변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함된 외부에서 볼 수 있는 형식은 보안상 취약할 수 있으며 경고 [CA2104](/visualstudio/code-quality/ca2104) : “변경 가능한 읽기 전용 참조 형식을 선언하지 마세요.”를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="0393b-114">[`readonly struct` 정의](#readonly-struct-example)에서 `readonly`는 `struct`가 불변임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="0393b-115">[`readonly` 멤버 정의](#readonly-member-examples)에서 `readonly`는 `struct`의 멤버가 구조체의 내부 상태를 변경하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="0393b-116">[`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 메서드가 참조를 반환하고 해당 참조에 쓰기가 허용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="0393b-117">`readonly struct` 및 `ref readonly` 컨텍스트는 C# 7.2에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="0393b-118">`readonly` 구조체 멤버는 C# 8.0에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="0393b-119">읽기 전용 필드 예제</span><span class="sxs-lookup"><span data-stu-id="0393b-119">Readonly field example</span></span>

<span data-ttu-id="0393b-120">이 예제에서 `year` 필드의 값은 클래스 생성자에서 할당되었지만 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="0393b-121">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="0393b-122">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="0393b-123">인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.</span><span class="sxs-lookup"><span data-stu-id="0393b-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="0393b-124">정적 필드 선언을 포함하는 클래스의 정적 생성자.</span><span class="sxs-lookup"><span data-stu-id="0393b-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="0393b-125">또한 이러한 생성자 컨텍스트에서는 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="0393b-126">`readonly` 키워드와 [const](const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="0393b-127">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="0393b-128">필드 선언과 임의 생성자에서 `readonly` 필드를 여러 번 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="0393b-129">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="0393b-130">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="0393b-131">위 예제에서 다음 예제와 같은 명령문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="0393b-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="0393b-132">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-132">you'll get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="0393b-133">읽기 전용 구조체 예제</span><span class="sxs-lookup"><span data-stu-id="0393b-133">Readonly struct example</span></span>

<span data-ttu-id="0393b-134">`struct` 정의의 `readonly` 한정자는 구조체가 **불변**임을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-134">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="0393b-135">다음 예제와 같이 `struct`의 모든 인스턴스 필드를 `readonly`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-135">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="0393b-136">앞의 예제는 [읽기 전용 자동 속성](../../properties.md#read-only)을 사용하여 스토리지를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-136">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="0393b-137">이는 컴파일러가 해당 속성의 `readonly` 백킹 필드를 만들도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-137">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="0393b-138">`readonly` 필드를 직접 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-138">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="0393b-139">`readonly`로 표시되지 않은 필드를 추가하면 컴파일러 오류 `CS8340`: "읽기 전용 구조체의 인스턴스 필드는 읽기 전용이어야 합니다."가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-139">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="0393b-140">Readonly 멤버 예제</span><span class="sxs-lookup"><span data-stu-id="0393b-140">Readonly member examples</span></span>

<span data-ttu-id="0393b-141">변경을 지원하는 구조체를 만들 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-141">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="0393b-142">이러한 경우 몇 개의 인스턴스 멤버는 구조체의 내부 상태를 수정하지 않을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-142">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="0393b-143">`readonly` 한정자를 사용하여 해당 인스턴스 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-143">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="0393b-144">컴파일러에서 의도를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-144">The compiler enforces your intent.</span></span> <span data-ttu-id="0393b-145">해당 멤버가 상태를 직접 수정하거나 `readonly` 한정자로 선언되지 않은 멤버에 액세스하는 경우 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-145">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="0393b-146">`readonly` 한정자는 `struct` 멤버에서 유효하지만, `class` 또는 `interface` 멤버 선언에서는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-146">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="0393b-147">해당하는 `struct` 메서드에 `readonly` 한정자를 적용하면 두 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-147">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="0393b-148">가장 중요한 이점은 컴파일러에서 의도를 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-148">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="0393b-149">상태를 수정하는 코드는 `readonly` 메서드에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-149">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="0393b-150">컴파일러는 `readonly` 한정자를 사용하여 성능을 최적화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-150">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="0393b-151">큰 `struct` 형식을 `in` 참조로 전달할 때, 구조체의 상태를 수정할 수 있는 경우 컴파일러에서 방어형 복사본을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-151">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="0393b-152">`readonly` 멤버에만 액세스하는 경우에는 컴파일러에서 방어형 복사본을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-152">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="0393b-153">`readonly` 한정자는 <xref:System.Object?displayProperty=nameWithType>에 선언된 메서드를 재정의하는 메서드를 포함하여 대부분의 `struct` 멤버에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-153">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0393b-154">단, 다음과 같은 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-154">There are some restrictions:</span></span>

- <span data-ttu-id="0393b-155">`readonly` 정적 메서드 또는 속성을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-155">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="0393b-156">`readonly` 생성자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-156">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="0393b-157">속성 또는 인덱서 선언에 `readonly` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-157">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="0393b-158">속성 또는 인덱서의 개별 `get` 또는 `set` 접근자에 `readonly` 한정자를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-158">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="0393b-159">속성과 해당 속성의 접근자 중 하나 이상에 `readonly` 한정자를 모두 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-159">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="0393b-160">동일한 제한이 인덱서에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-160">That same restriction applies to indexers.</span></span>

<span data-ttu-id="0393b-161">컴파일러는 컴파일러 구현 코드에서 상태를 수정하지 않는 자동 구현 속성에 `readonly` 한정자를 암시적으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-161">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="0393b-162">다음 선언과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-162">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

<span data-ttu-id="0393b-163">해당 위치에 `readonly` 한정자를 추가할 수도 있지만 아무 의미도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-163">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="0393b-164">자동 구현 속성 setter 또는 읽기/쓰기 자동 구현 속성에 `readonly` 한정자를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-164">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="0393b-165">참조 읽기 전용 반환 예</span><span class="sxs-lookup"><span data-stu-id="0393b-165">Ref readonly return example</span></span>

<span data-ttu-id="0393b-166">`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-166">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="0393b-167">다음 예제는 원점에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-167">The following example returns a reference to the origin.</span></span> <span data-ttu-id="0393b-168">예제에서는 `readonly` 한정자를 사용하여 호출자가 원본을 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-168">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="0393b-169">반환된 유형은 `readonly struct`일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-169">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="0393b-170">`ref readonly`를 통해 `ref`에서 반환될 수 있는 모든 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-170">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0393b-171">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0393b-171">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="0393b-172">언어 사양 제안도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0393b-172">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="0393b-173">readonly ref 및 readonly 구조체</span><span class="sxs-lookup"><span data-stu-id="0393b-173">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="0393b-174">readonly 구조체 멤버</span><span class="sxs-lookup"><span data-stu-id="0393b-174">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="0393b-175">참조</span><span class="sxs-lookup"><span data-stu-id="0393b-175">See also</span></span>

- [<span data-ttu-id="0393b-176">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0393b-176">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0393b-177">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0393b-177">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0393b-178">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="0393b-178">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0393b-179">한정자</span><span class="sxs-lookup"><span data-stu-id="0393b-179">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0393b-180">const</span><span class="sxs-lookup"><span data-stu-id="0393b-180">const</span></span>](const.md)
- [<span data-ttu-id="0393b-181">필드</span><span class="sxs-lookup"><span data-stu-id="0393b-181">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
