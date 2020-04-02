---
title: 구조체 형식 - C# 참조
ms.date: 03/26/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6a2c97b93a8f6d1d62bd8a96865a4fe6587f55d3
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345136"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="8dc65-102">구조체 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8dc65-102">Structure types (C# reference)</span></span>

<span data-ttu-id="8dc65-103">‘구조체 형식’은 데이터와 관련 기능을 캡슐화할 수 있는 [값 형식](value-types.md)입니다.  </span><span class="sxs-lookup"><span data-stu-id="8dc65-103">A *structure type* (or *struct type*) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="8dc65-104">구조체 형식은 `struct` 키워드를 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-104">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

<span data-ttu-id="8dc65-105">구조체 형식은 ‘값 의미 체계’를 갖습니다. </span><span class="sxs-lookup"><span data-stu-id="8dc65-105">Structure types have *value semantics*.</span></span> <span data-ttu-id="8dc65-106">즉, 구조체 형식의 변수는 해당 형식의 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-106">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="8dc65-107">기본적으로 변수 값은 할당 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-107">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="8dc65-108">구조체 형식 변수의 경우, 해당 형식의 인스턴스가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-108">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="8dc65-109">자세한 내용은 [값 형식](value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc65-109">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="8dc65-110">구조체 형식은 일반적으로 동작을 거의 제공하지 않거나 전혀 제공하지 않는 작은 데이터 중심 형식을 설계하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-110">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="8dc65-111">예를 들어, .NET에서는 구조체 형식을 사용하여 숫자([정수](integral-numeric-types.md)와 [실수](floating-point-numeric-types.md)), [부울 값](bool.md), [유니코드 문자](char.md), [시간 인스턴스](xref:System.DateTime)를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-111">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="8dc65-112">형식의 동작이 중요한 경우에는 [클래스](../keywords/class.md)를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-112">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="8dc65-113">클래스 형식은 ‘참조 의미 체계’를 갖습니다. </span><span class="sxs-lookup"><span data-stu-id="8dc65-113">Class types have *reference semantics*.</span></span> <span data-ttu-id="8dc65-114">즉, 클래스 형식의 변수는 인스턴스 자체가 아닌 해당 형식의 인스턴스에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-114">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

<span data-ttu-id="8dc65-115">구조체 형식에는 값 의미 체계가 있기 때문에 *변경할 수* 없는 구조체 형식을 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-115">Because structure types have value semantics, we recommend you to define *immutable* structure types.</span></span>

## <a name="readonly-struct"></a><span data-ttu-id="8dc65-116">`readonly` 구조체</span><span class="sxs-lookup"><span data-stu-id="8dc65-116">`readonly` struct</span></span>

<span data-ttu-id="8dc65-117">C# 7.2부터 `readonly` 한정자를 사용하여 구조체 형식을 변경할 수 없도록 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-117">Beginning with C# 7.2, you use the `readonly` modifier to declare that a structure type is immutable:</span></span>

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

<span data-ttu-id="8dc65-118">`readonly` 구조체의 모든 데이터 멤버는 다음과 같이 읽기 전용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-118">All data members of a `readonly` struct must be read-only as follows:</span></span>

- <span data-ttu-id="8dc65-119">모든 필드 선언에는 [`readonly` 한정자](../keywords/readonly.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-119">Any field declaration must have the [`readonly` modifier](../keywords/readonly.md)</span></span>
- <span data-ttu-id="8dc65-120">자동 구현된 속성을 포함하여 모든 속성은 읽기 전용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-120">Any property, including auto-implemented ones, must be read-only</span></span>

<span data-ttu-id="8dc65-121">이렇게 하면 `readonly` 구조체의 멤버가 구조체의 상태를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-121">That guarantees that no member of a `readonly` struct modifies the state of the struct.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc65-122">`readonly` 구조체에서 변경 가능한 참조 형식의 데이터 멤버는 여전히 자체 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-122">In a `readonly` struct, a data member of a mutable reference type still can mutate its own state.</span></span> <span data-ttu-id="8dc65-123">예를 들어 <xref:System.Collections.Generic.List%601> 인스턴스를 바꿀 수는 없지만 여기에 새 요소를 추가할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-123">For example, you cannot replace a <xref:System.Collections.Generic.List%601> instance, but you can add new elements to it.</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="8dc65-124">구조체 형식 설계의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8dc65-124">Limitations with the design of a structure type</span></span>

<span data-ttu-id="8dc65-125">구조체 형식을 설계할 때는 [클래스](../keywords/class.md) 형식과 같은 기능을 사용할 수 있으나, 다음과 같은 예외가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-125">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="8dc65-126">매개 변수가 없는 생성자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-126">You cannot declare a parameterless constructor.</span></span> <span data-ttu-id="8dc65-127">모든 구조체 형식은 이미 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-127">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="8dc65-128">인스턴스 필드 또는 속성은 선언과 동시에 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-128">You cannot initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="8dc65-129">단, [static](../keywords/static.md) 또는 [const](../keywords/const.md) 필드 또는 정적 속성은 선언과 동시에 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-129">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="8dc65-130">구조체 형식의 생성자는 해당 형식의 모든 인스턴스 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-130">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="8dc65-131">구조체 형식은 다른 클래스 또는 구조체 형식에서 상속할 수 없으며, 클래스의 기본이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-131">A structure type cannot inherit from other class or structure type and it cannot be the base of a class.</span></span> <span data-ttu-id="8dc65-132">단, 구조체 형식은 [인터페이스](../keywords/interface.md)를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-132">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="8dc65-133">구조체 형식 내에서 [종료자](../../programming-guide/classes-and-structs/destructors.md)를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-133">You cannot declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="8dc65-134">구조체 형식의 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="8dc65-134">Instantiation of a structure type</span></span>

<span data-ttu-id="8dc65-135">C#에서는 선언된 변수를 사용하려면 먼저 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-135">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="8dc65-136">구조체 형식 변수는 `null`일 수 없으므로([nulla 허용 변수 값 형식](nullable-value-types.md)의 변수인 경우 제외), 해당 형식의 인스턴스를 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-136">Because a structure-type variable cannot be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="8dc65-137">이 작업은 몇 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-137">There are several ways to do that.</span></span>

<span data-ttu-id="8dc65-138">일반적으로, 구조체 형식은 [`new`](../operators/new-operator.md) 연산자를 사용하여 적절한 생성자를 호출함으로써 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-138">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="8dc65-139">모든 구조체 형식은 하나 이상의 생성자를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-139">Every structure type has at least one constructor.</span></span> <span data-ttu-id="8dc65-140">이는 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-140">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="8dc65-141">[기본값 식](../operators/default.md)을 사용하여 형식의 기본값을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-141">You can also use a [default value expression](../operators/default.md) to produce the default value of a type.</span></span>

<span data-ttu-id="8dc65-142">구조체 형식의 모든 인스턴스 필드가 액세스 가능한 경우, `new` 연산자 없이 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-142">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="8dc65-143">이 경우 인스턴스를 처음 사용하기 전에 모든 인스턴스 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-143">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="8dc65-144">다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-144">The following example shows how to do that:</span></span>

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

<span data-ttu-id="8dc65-145">[기본 제공 값 형식](value-types.md#built-in-value-types)의 경우, 해당 리터럴을 사용하여 해당 형식의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-145">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="8dc65-146">참조를 통해 구조체 형식 변수 전달</span><span class="sxs-lookup"><span data-stu-id="8dc65-146">Passing structure-type variables by reference</span></span>

<span data-ttu-id="8dc65-147">구조체 형식 변수를 메서드에 인수로 전달하거나 메서드에서 구조체 형식 값을 반환할 경우, 구조체 형식의 인스턴스 전체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-147">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="8dc65-148">이로 인해 구조체 형식이 많이 사용되는 고성능 시나리오에서 코드의 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-148">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="8dc65-149">구조체 형식 변수를 참조를 통해 전달하면 값이 복사되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-149">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="8dc65-150">참조를 통해 인수를 전달해야 한다는 사실을 나타내려면 [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) 또는 [`in`](../keywords/in-parameter-modifier.md) 메서드 매개 변수 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-150">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="8dc65-151">참조를 통해 메서드 결과를 반환하려면 [ref returns](../../programming-guide/classes-and-structs/ref-returns.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-151">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="8dc65-152">자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc65-152">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="8dc65-153">변환</span><span class="sxs-lookup"><span data-stu-id="8dc65-153">Conversions</span></span>

<span data-ttu-id="8dc65-154">모든 구조체 형식에는 <xref:System.ValueType?displayProperty=nameWithType> 및 <xref:System.Object?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-154">For any structure type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="8dc65-155">구조체 형식과 구조체 형식이 구현하는 인터페이스 간에도 boxing 및 unboxing 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc65-155">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8dc65-156">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8dc65-156">C# language specification</span></span>

<span data-ttu-id="8dc65-157">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [구조체](~/_csharplang/spec/structs.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc65-157">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="8dc65-158">`readonly` 구조체에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc65-158">For more information about `readonly` structs, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs).</span></span>

## <a name="see-also"></a><span data-ttu-id="8dc65-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dc65-159">See also</span></span>

- [<span data-ttu-id="8dc65-160">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8dc65-160">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8dc65-161">디자인 지침 - 클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="8dc65-161">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="8dc65-162">디자인 지침-구조체 디자인</span><span class="sxs-lookup"><span data-stu-id="8dc65-162">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="8dc65-163">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="8dc65-163">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
