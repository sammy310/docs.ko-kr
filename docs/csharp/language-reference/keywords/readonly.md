---
title: readonly 키워드 - C# 참조
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348017"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="27ef1-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="27ef1-102">readonly (C# Reference)</span></span>

<span data-ttu-id="27ef1-103">`readonly` 키워드는 세 가지 컨텍스트에서 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="27ef1-104">[필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="27ef1-105">필드 선언과 생성자 내에서 읽기 전용 필드를 여러 번 할당 및 재할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="27ef1-106">생성자가 종료된 후에는 `readonly` 필드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="27ef1-107">이 제한의 의미는 값 형식과 참조 형식에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="27ef1-108">값 형식에는 해당 데이터가 직접 포함되므로, `readonly` 값 형식인 필드는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="27ef1-109">참조 형식에는 해당 데이터에 대한 참조가 포함되므로, `readonly` 참조 형식인 필드는 항상 같은 개체를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="27ef1-110">해당 개체는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-110">That object is not immutable.</span></span> <span data-ttu-id="27ef1-111">`readonly` 한정자는 필드가 참조 형식의 다른 인스턴스로 바뀌지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="27ef1-112">그러나 한정자는 필드의 인스턴스 데이터가 읽기 전용 필드를 통해 수정되는 것을 방지하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="27ef1-113">변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함된 외부에서 볼 수 있는 형식은 보안상 취약할 수 있으며 경고 [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : “변경 가능한 읽기 전용 참조 형식을 선언하지 마세요.”를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="27ef1-114">[`readonly struct` 정의](#readonly-struct-example)에서 `readonly`는 `struct`가 불변임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="27ef1-115">[`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 해당 메서드가 참조를 반환하고 해당 참조에 쓰기를 허용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="27ef1-116">마지막 두 컨텍스트가 C# 7.2에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="27ef1-117">읽기 전용 필드 예제</span><span class="sxs-lookup"><span data-stu-id="27ef1-117">Readonly field example</span></span>

<span data-ttu-id="27ef1-118">이 예제에서는 클래스 생성자에서 값이 할당되지만, `year` 필드의 값을 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="27ef1-119">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="27ef1-120">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="27ef1-121">인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.</span><span class="sxs-lookup"><span data-stu-id="27ef1-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="27ef1-122">정적 필드 선언을 포함하는 클래스의 정적 생성자.</span><span class="sxs-lookup"><span data-stu-id="27ef1-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="27ef1-123">이러한 생성자 컨텍스트는 또한 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효한 유일한 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="27ef1-124">`readonly` 키워드와 [const](const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="27ef1-125">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="27ef1-126">필드 선언과 임의 생성자에서 `readonly` 필드를 여러 번 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="27ef1-127">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="27ef1-128">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="27ef1-129">위 예제에서 다음 예제와 같은 명령문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="27ef1-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="27ef1-130">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="27ef1-131">읽기 전용 구조체 예제</span><span class="sxs-lookup"><span data-stu-id="27ef1-131">Readonly struct example</span></span>

<span data-ttu-id="27ef1-132">`struct` 정의의 `readonly` 한정자는 구조체가 **불변**임을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="27ef1-133">다음 예제와 같이 `struct`의 모든 인스턴스 필드를 `readonly`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="27ef1-134">앞의 예제는 [읽기 전용 자동 속성](../../properties.md#read-only)을 사용하여 스토리지를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="27ef1-135">이는 컴파일러가 해당 속성의 `readonly` 백킹 필드를 만들도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="27ef1-136">`readonly` 필드를 직접 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="27ef1-137">`readonly`로 표시되지 않은 필드를 추가하면 컴파일러 오류 `CS8340`: "읽기 전용 구조체의 인스턴스 필드는 읽기 전용이어야 합니다."가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="27ef1-138">참조 읽기 전용 반환 예</span><span class="sxs-lookup"><span data-stu-id="27ef1-138">Ref readonly return example</span></span>

<span data-ttu-id="27ef1-139">`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="27ef1-140">다음 예제는 원점에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="27ef1-141">호출자가 원본을 수정할 수 없음을 나타내기 위해 `readonly` 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="27ef1-142">반환된 유형은 `readonly struct`일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="27ef1-143">`ref readonly`를 통해 `ref`에서 반환될 수 있는 모든 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27ef1-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="27ef1-144">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="27ef1-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="27ef1-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27ef1-145">See also</span></span>

- [<span data-ttu-id="27ef1-146">C# 참조</span><span class="sxs-lookup"><span data-stu-id="27ef1-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="27ef1-147">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="27ef1-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="27ef1-148">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="27ef1-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="27ef1-149">한정자</span><span class="sxs-lookup"><span data-stu-id="27ef1-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="27ef1-150">const</span><span class="sxs-lookup"><span data-stu-id="27ef1-150">const</span></span>](const.md)
- [<span data-ttu-id="27ef1-151">필드</span><span class="sxs-lookup"><span data-stu-id="27ef1-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
