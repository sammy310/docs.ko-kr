---
title: readonly 키워드 - C# 참조
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 03b0aa63eda3e7a9d8745baaa33479fd5e85b01b
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389051"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="535c3-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="535c3-102">readonly (C# Reference)</span></span>

<span data-ttu-id="535c3-103">`readonly` 키워드는 다음 네 가지 컨텍스트에서 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="535c3-104">[필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="535c3-105">필드 선언과 생성자 내에서 읽기 전용 필드를 여러 번 할당 및 재할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="535c3-106">생성자가 종료된 후에는 `readonly` 필드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="535c3-107">이 규칙의 의미는 값 형식과 참조 형식에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="535c3-108">값 형식에는 해당 데이터가 직접 포함되므로, `readonly` 값 형식인 필드는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="535c3-109">참조 형식에는 해당 데이터에 대한 참조가 포함되므로, `readonly` 참조 형식인 필드는 항상 같은 개체를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="535c3-110">해당 개체는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-110">That object isn't immutable.</span></span> <span data-ttu-id="535c3-111">`readonly` 한정자는 필드가 참조 형식의 다른 인스턴스로 바뀌지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="535c3-112">그러나 이 한정자는 필드의 인스턴스 데이터가 읽기 전용 필드를 통해 수정되는 것을 방지하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="535c3-113">변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함된 외부에서 볼 수 있는 형식은 보안상 취약할 수 있으며 경고 [CA2104](/visualstudio/code-quality/ca2104) : “변경 가능한 읽기 전용 참조 형식을 선언하지 마세요.”를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="535c3-114">`readonly struct` 형식 정의에서 `readonly`는 구조체 형식을 변경할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="535c3-115">자세한 내용은 [구조체 형식](../builtin-types/struct.md) 문서의 [`readonly` 구조체](../builtin-types/struct.md#readonly-struct) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="535c3-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="535c3-116">구조체 형식 내 인스턴스 멤버 선언에서 `readonly`는 인스턴스 멤버가 구조체의 상태를 수정하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="535c3-117">자세한 내용은 [구조체 형식](../builtin-types/struct.md) 문서의 [`readonly` 인스턴스 멤버](../builtin-types/struct.md#readonly-instance-members) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="535c3-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="535c3-118">[`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 메서드가 참조를 반환하고 해당 참조에 쓰기가 허용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="535c3-119">`readonly struct` 및 `ref readonly` 컨텍스트는 C# 7.2에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="535c3-120">`readonly` 구조체 멤버는 C# 8.0에서 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="535c3-121">읽기 전용 필드 예제</span><span class="sxs-lookup"><span data-stu-id="535c3-121">Readonly field example</span></span>

<span data-ttu-id="535c3-122">이 예제에서 `year` 필드의 값은 클래스 생성자에서 할당되었지만 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="535c3-123">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="535c3-124">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="535c3-125">인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.</span><span class="sxs-lookup"><span data-stu-id="535c3-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="535c3-126">정적 필드 선언을 포함하는 클래스의 정적 생성자.</span><span class="sxs-lookup"><span data-stu-id="535c3-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="535c3-127">또한 이러한 생성자 컨텍스트에서는 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="535c3-128">`readonly` 키워드와 [const](const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="535c3-129">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="535c3-130">필드 선언과 임의 생성자에서 `readonly` 필드를 여러 번 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="535c3-131">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="535c3-132">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="535c3-133">위 예제에서 다음 예제와 같은 명령문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="535c3-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="535c3-134">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="535c3-135">**읽기 전용 필드에는 할당할 수 없습니다. 단 생성자 또는 변수 이니셜라이저에서는 예외입니다.**</span><span class="sxs-lookup"><span data-stu-id="535c3-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="535c3-136">참조 읽기 전용 반환 예</span><span class="sxs-lookup"><span data-stu-id="535c3-136">Ref readonly return example</span></span>

<span data-ttu-id="535c3-137">`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="535c3-138">다음 예제는 원점에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="535c3-139">예제에서는 `readonly` 한정자를 사용하여 호출자가 원본을 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="535c3-140">반환된 유형은 `readonly struct`일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="535c3-141">`ref readonly`를 통해 `ref`에서 반환될 수 있는 모든 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="535c3-142">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="535c3-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="535c3-143">언어 사양 제안도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535c3-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="535c3-144">readonly ref 및 readonly 구조체</span><span class="sxs-lookup"><span data-stu-id="535c3-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="535c3-145">readonly 구조체 멤버</span><span class="sxs-lookup"><span data-stu-id="535c3-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="535c3-146">참조</span><span class="sxs-lookup"><span data-stu-id="535c3-146">See also</span></span>

- [<span data-ttu-id="535c3-147">C# 참조</span><span class="sxs-lookup"><span data-stu-id="535c3-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="535c3-148">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="535c3-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="535c3-149">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="535c3-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="535c3-150">한정자</span><span class="sxs-lookup"><span data-stu-id="535c3-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="535c3-151">const</span><span class="sxs-lookup"><span data-stu-id="535c3-151">const</span></span>](const.md)
- [<span data-ttu-id="535c3-152">필드</span><span class="sxs-lookup"><span data-stu-id="535c3-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
