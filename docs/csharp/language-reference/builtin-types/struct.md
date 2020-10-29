---
title: 구조체 형식 - C# 참조
description: C#의 구조체 형식에 관한 자세한 정보
ms.date: 10/23/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: daf332dae483d75ef27e78dad5ee912734ccdb5f
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526598"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="de08d-103">구조체 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="de08d-103">Structure types (C# reference)</span></span>

<span data-ttu-id="de08d-104">‘구조체 형식’은 데이터와 관련 기능을 캡슐화할 수 있는 [값 형식](value-types.md)입니다.  </span><span class="sxs-lookup"><span data-stu-id="de08d-104">A *structure type* (or *struct type* ) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="de08d-105">구조체 형식은 `struct` 키워드를 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-105">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](snippets/shared/StructType.cs#StructExample)]

<span data-ttu-id="de08d-106">구조체 형식은 ‘값 의미 체계’를 갖습니다. </span><span class="sxs-lookup"><span data-stu-id="de08d-106">Structure types have *value semantics* .</span></span> <span data-ttu-id="de08d-107">즉, 구조체 형식의 변수는 해당 형식의 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-107">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="de08d-108">기본적으로 변수 값은 할당 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-108">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="de08d-109">구조체 형식 변수의 경우, 해당 형식의 인스턴스가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-109">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="de08d-110">자세한 내용은 [값 형식](value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de08d-110">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="de08d-111">구조체 형식은 일반적으로 동작을 거의 제공하지 않거나 전혀 제공하지 않는 작은 데이터 중심 형식을 설계하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-111">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="de08d-112">예를 들어, .NET에서는 구조체 형식을 사용하여 숫자([정수](integral-numeric-types.md)와 [실수](floating-point-numeric-types.md)), [부울 값](bool.md), [유니코드 문자](char.md), [시간 인스턴스](xref:System.DateTime)를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-112">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="de08d-113">형식의 동작이 중요한 경우에는 [클래스](../keywords/class.md)를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-113">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="de08d-114">클래스 형식은 ‘참조 의미 체계’를 갖습니다. </span><span class="sxs-lookup"><span data-stu-id="de08d-114">Class types have *reference semantics* .</span></span> <span data-ttu-id="de08d-115">즉, 클래스 형식의 변수는 인스턴스 자체가 아닌 해당 형식의 인스턴스에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-115">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

<span data-ttu-id="de08d-116">구조체 형식에는 값 의미 체계가 있기 때문에 *변경할 수* 없는 구조체 형식을 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-116">Because structure types have value semantics, we recommend you to define *immutable* structure types.</span></span>

## <a name="readonly-struct"></a><span data-ttu-id="de08d-117">`readonly` 구조체</span><span class="sxs-lookup"><span data-stu-id="de08d-117">`readonly` struct</span></span>

<span data-ttu-id="de08d-118">C# 7.2부터 `readonly` 한정자를 사용하여 구조체 형식을 변경할 수 없도록 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-118">Beginning with C# 7.2, you use the `readonly` modifier to declare that a structure type is immutable:</span></span>

[!code-csharp[readonly struct](snippets/shared/StructType.cs#ReadonlyStruct)]

<span data-ttu-id="de08d-119">`readonly` 구조체의 모든 데이터 멤버는 다음과 같이 읽기 전용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-119">All data members of a `readonly` struct must be read-only as follows:</span></span>

- <span data-ttu-id="de08d-120">모든 필드 선언에는 [`readonly` 한정자](../keywords/readonly.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-120">Any field declaration must have the [`readonly` modifier](../keywords/readonly.md)</span></span>
- <span data-ttu-id="de08d-121">자동 구현된 속성을 포함하여 모든 속성은 읽기 전용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-121">Any property, including auto-implemented ones, must be read-only.</span></span> <span data-ttu-id="de08d-122">C# 9.0 이상에서는 속성에 [`init` 접근자](../../whats-new/csharp-9.md#init-only-setters)가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-122">In C# 9.0 and later, a property may have an [`init` accessor](../../whats-new/csharp-9.md#init-only-setters).</span></span>

<span data-ttu-id="de08d-123">이렇게 하면 `readonly` 구조체의 멤버가 구조체의 상태를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-123">That guarantees that no member of a `readonly` struct modifies the state of the struct.</span></span> <span data-ttu-id="de08d-124">C# 8.0 이상에서는 생성자를 제외한 다른 인스턴스 멤버는 암시적으로 [`readonly`](#readonly-instance-members)임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-124">In C# 8.0 and later, that means that other instance members except constructors are implicitly [`readonly`](#readonly-instance-members).</span></span>

> [!NOTE]
> <span data-ttu-id="de08d-125">`readonly` 구조체에서 변경 가능한 참조 형식의 데이터 멤버는 여전히 자체 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-125">In a `readonly` struct, a data member of a mutable reference type still can mutate its own state.</span></span> <span data-ttu-id="de08d-126">예를 들어 <xref:System.Collections.Generic.List%601> 인스턴스를 바꿀 수는 없지만 새 요소를 추가할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-126">For example, you can't replace a <xref:System.Collections.Generic.List%601> instance, but you can add new elements to it.</span></span>

## <a name="readonly-instance-members"></a><span data-ttu-id="de08d-127">`readonly` 인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="de08d-127">`readonly` instance members</span></span>

<span data-ttu-id="de08d-128">C# 8.0부터 `readonly` 한정자를 사용하여 인스턴스 멤버가 구조체의 상태를 수정하지 않도록 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-128">Beginning with C# 8.0, you can also use the `readonly` modifier to declare that an instance member doesn't modify the state of a struct.</span></span> <span data-ttu-id="de08d-129">전체 구조체 형식을 `readonly`로 선언할 수 없는 경우 `readonly` 한정자를 사용하여 구조체의 상태를 수정하지 않는 인스턴스 멤버를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-129">If you can't declare the whole structure type as `readonly`, use the `readonly` modifier to mark the instance members that don't modify the state of the struct.</span></span>

<span data-ttu-id="de08d-130">`readonly` 인스턴스 멤버 내에서 구조체의 인스턴스 필드에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-130">Within a `readonly` instance member, you can't assign to structure's instance fields.</span></span> <span data-ttu-id="de08d-131">그러나 `readonly` 멤버는`readonly`가 아닌 멤버를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-131">However, a `readonly` member can call a non-`readonly` member.</span></span> <span data-ttu-id="de08d-132">이 경우 컴파일러는 구조체 인스턴스의 복사본을 만들고 해당 복사본에서 `readonly`가 아닌 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-132">In that case the compiler creates a copy of the structure instance and calls the non-`readonly` member on that copy.</span></span> <span data-ttu-id="de08d-133">따라서 원래 구조체 인스턴스는 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-133">As a result, the original structure instance is not modified.</span></span>

<span data-ttu-id="de08d-134">일반적으로 다음 종류의 인스턴스 멤버에 `readonly` 한정자를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-134">Typically, you apply the `readonly` modifier to the following kinds of instance members:</span></span>

- <span data-ttu-id="de08d-135">메서드:</span><span class="sxs-lookup"><span data-stu-id="de08d-135">methods:</span></span>

  [!code-csharp[readonly method](snippets/shared/StructType.cs#ReadonlyMethod)]

  <span data-ttu-id="de08d-136"><xref:System.Object?displayProperty=nameWithType>에 선언된 메서드를 재정의하는 메서드에 `readonly` 한정자를 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-136">You can also apply the `readonly` modifier to methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>:</span></span>

  [!code-csharp[readonly override](snippets/shared/StructType.cs#ReadonlyOverride)]

- <span data-ttu-id="de08d-137">속성 및 인덱서:</span><span class="sxs-lookup"><span data-stu-id="de08d-137">properties and indexers:</span></span>

  [!code-csharp[readonly property get](snippets/shared/StructType.cs#ReadonlyProperty)]

  <span data-ttu-id="de08d-138">속성 또는 인덱서의 두 접근자에 모두 `readonly` 한정자를 적용해야 하는 경우 속성 또는 인덱서의 선언에 해당 한정자를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-138">If you need to apply the `readonly` modifier to both accessors of a property or indexer, apply it in the declaration of the property or indexer.</span></span>

  > [!NOTE]
  > <span data-ttu-id="de08d-139">컴파일러는 속성 선언에 `readonly` 한정자가 있는지 여부와 관계없이 [자동 구현 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md)의 `get` 접근자를 `readonly`로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-139">The compiler declares a `get` accessor of an [auto-implemented property](../../programming-guide/classes-and-structs/auto-implemented-properties.md) as `readonly`, regardless of presence of the `readonly` modifier in a property declaration.</span></span>

  <span data-ttu-id="de08d-140">C# 9.0 이상에서는 `init` 접근자를 사용하여 속성 또는 인덱서에 `readonly` 한정자를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-140">In C# 9.0 and later, you may apply the `readonly` modifier to a property or indexer with an `init` accessor:</span></span>

  :::code language="csharp" source="snippets/shared/StructType.cs" id="ReadonlyWithInit":::

<span data-ttu-id="de08d-141">구조체 형식의 정적 멤버에는 `readonly` 한정자를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-141">You can't apply the `readonly` modifier to static members of a structure type.</span></span>

<span data-ttu-id="de08d-142">컴파일러는 성능 최적화를 위해 `readonly` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-142">The compiler may make use of the `readonly` modifier for performance optimizations.</span></span> <span data-ttu-id="de08d-143">자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de08d-143">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="de08d-144">구조체 형식 설계의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="de08d-144">Limitations with the design of a structure type</span></span>

<span data-ttu-id="de08d-145">구조체 형식을 설계할 때는 [클래스](../keywords/class.md) 형식과 같은 기능을 사용할 수 있으나, 다음과 같은 예외가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-145">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="de08d-146">매개 변수가 없는 생성자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-146">You can't declare a parameterless constructor.</span></span> <span data-ttu-id="de08d-147">모든 구조체 형식은 이미 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-147">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="de08d-148">인스턴스 필드 또는 속성은 선언과 동시에 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-148">You can't initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="de08d-149">단, [static](../keywords/static.md) 또는 [const](../keywords/const.md) 필드 또는 정적 속성은 선언과 동시에 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-149">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="de08d-150">구조체 형식의 생성자는 해당 형식의 모든 인스턴스 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-150">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="de08d-151">구조체 형식은 다른 클래스 또는 구조체 형식에서 상속할 수 없으며, 클래스의 기본이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-151">A structure type can't inherit from other class or structure type and it can't be the base of a class.</span></span> <span data-ttu-id="de08d-152">단, 구조체 형식은 [인터페이스](../keywords/interface.md)를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-152">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="de08d-153">구조체 형식 내에서 [종료자](../../programming-guide/classes-and-structs/destructors.md)를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-153">You can't declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="de08d-154">구조체 형식의 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="de08d-154">Instantiation of a structure type</span></span>

<span data-ttu-id="de08d-155">C#에서는 선언된 변수를 사용하려면 먼저 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-155">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="de08d-156">구조체 형식 변수는 `null`일 수 없으므로([null 허용 값 형식](nullable-value-types.md)의 변수인 경우 제외), 해당 형식의 인스턴스를 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-156">Because a structure-type variable can't be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="de08d-157">이 작업은 몇 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-157">There are several ways to do that.</span></span>

<span data-ttu-id="de08d-158">일반적으로, 구조체 형식은 [`new`](../operators/new-operator.md) 연산자를 사용하여 적절한 생성자를 호출함으로써 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-158">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="de08d-159">모든 구조체 형식은 하나 이상의 생성자를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-159">Every structure type has at least one constructor.</span></span> <span data-ttu-id="de08d-160">이는 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-160">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="de08d-161">[기본값 식](../operators/default.md)을 사용하여 형식의 기본값을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-161">You can also use a [default value expression](../operators/default.md) to produce the default value of a type.</span></span>

<span data-ttu-id="de08d-162">구조체 형식의 모든 인스턴스 필드가 액세스 가능한 경우, `new` 연산자 없이 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-162">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="de08d-163">이 경우 인스턴스를 처음 사용하기 전에 모든 인스턴스 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-163">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="de08d-164">다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-164">The following example shows how to do that:</span></span>

[!code-csharp[without new](snippets/shared/StructType.cs#WithoutNew)]

<span data-ttu-id="de08d-165">[기본 제공 값 형식](value-types.md#built-in-value-types)의 경우, 해당 리터럴을 사용하여 해당 형식의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-165">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="de08d-166">참조를 통해 구조체 형식 변수 전달</span><span class="sxs-lookup"><span data-stu-id="de08d-166">Passing structure-type variables by reference</span></span>

<span data-ttu-id="de08d-167">구조체 형식 변수를 메서드에 인수로 전달하거나 메서드에서 구조체 형식 값을 반환할 경우, 구조체 형식의 인스턴스 전체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-167">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="de08d-168">이로 인해 구조체 형식이 많이 사용되는 고성능 시나리오에서 코드의 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-168">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="de08d-169">구조체 형식 변수를 참조를 통해 전달하면 값이 복사되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-169">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="de08d-170">참조를 통해 인수를 전달해야 한다는 사실을 나타내려면 [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) 또는 [`in`](../keywords/in-parameter-modifier.md) 메서드 매개 변수 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-170">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="de08d-171">참조를 통해 메서드 결과를 반환하려면 [ref returns](../../programming-guide/classes-and-structs/ref-returns.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-171">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="de08d-172">자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de08d-172">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="ref-struct"></a><span data-ttu-id="de08d-173">`ref` 구조체</span><span class="sxs-lookup"><span data-stu-id="de08d-173">`ref` struct</span></span>

<span data-ttu-id="de08d-174">C# 7.2부터 구조체 형식 선언에 `ref` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-174">Beginning with C# 7.2, you can use the `ref` modifier in the declaration of a structure type.</span></span> <span data-ttu-id="de08d-175">`ref` 구조체 형식의 인스턴스는 스택에 할당되며 관리되는 힙으로 이스케이프할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-175">Instances of a `ref` struct type are allocated on the stack and can't escape to the managed heap.</span></span> <span data-ttu-id="de08d-176">이를 위해 컴파일러는 다음과 같이 `ref` 구조체 형식의 사용을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-176">To ensure that, the compiler limits the usage of `ref` struct types as follows:</span></span>

- <span data-ttu-id="de08d-177">`ref` 구조체는 배열의 요소 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-177">A `ref` struct can't be the element type of an array.</span></span>
- <span data-ttu-id="de08d-178">`ref` 구조체는 클래스의 필드 또는 비 `ref` 구조체의 선언된 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-178">A `ref` struct can't be a declared type of a field of a class or a non-`ref` struct.</span></span>
- <span data-ttu-id="de08d-179">`ref` 구조체는 인터페이스를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-179">A `ref` struct can't implement interfaces.</span></span>
- <span data-ttu-id="de08d-180">`ref` 구조체는 <xref:System.ValueType?displayProperty=nameWithType> 또는 <xref:System.Object?displayProperty=nameWithType>에 boxing할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-180">A `ref` struct can't be boxed to <xref:System.ValueType?displayProperty=nameWithType> or <xref:System.Object?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="de08d-181">`ref` 구조체는 형식 인수일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-181">A `ref` struct can't be a type argument.</span></span>
- <span data-ttu-id="de08d-182">[람다 식](../operators/lambda-expressions.md) 또는 [로컬 함수](../../programming-guide/classes-and-structs/local-functions.md)에서 `ref` 구조체 변수를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-182">A `ref` struct variable can't be captured by a [lambda expression](../operators/lambda-expressions.md) or a [local function](../../programming-guide/classes-and-structs/local-functions.md).</span></span>
- <span data-ttu-id="de08d-183">[`async`](../keywords/async.md) 메서드에서는 `ref` 구조체 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-183">A `ref` struct variable can't be used in an [`async`](../keywords/async.md) method.</span></span> <span data-ttu-id="de08d-184">그러나 동기 메서드에서는 `ref` 구조체 변수(예: <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환하는 변수)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-184">However, you can use `ref` struct variables in synchronous methods, for example, in those that return <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="de08d-185">[반복기](../../iterators.md)에서는 `ref` 구조체 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-185">A `ref` struct variable can't be used in [iterators](../../iterators.md).</span></span>

<span data-ttu-id="de08d-186">일반적으로 `ref` 구조체 형식의 데이터 멤버도 포함하는 형식이 필요한 경우 `ref` 구조체 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-186">Typically, you define a `ref` struct type when you need a type that also includes data members of `ref` struct types:</span></span>

[!code-csharp[ref struct](snippets/shared/StructType.cs#RefStruct)]

<span data-ttu-id="de08d-187">`ref` 구조체를 [`readonly`](#readonly-struct)로 선언하려면 형식 선언에서 `readonly` 및 `ref` 한정자를 결합합니다(`readonly` 한정자는 `ref` 한정자 앞에 와야함).</span><span class="sxs-lookup"><span data-stu-id="de08d-187">To declare a `ref` struct as [`readonly`](#readonly-struct), combine the `readonly` and `ref` modifiers in the type declaration (the `readonly` modifier must come before the `ref` modifier):</span></span>

[!code-csharp[readonly ref struct](snippets/shared/StructType.cs#ReadonlyRef)]

<span data-ttu-id="de08d-188">.NET에서 `ref` 구조체의 예는 <xref:System.Span%601?displayProperty=nameWithType> 및 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-188">In .NET, examples of a `ref` struct are <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span></span>

## <a name="conversions"></a><span data-ttu-id="de08d-189">변환</span><span class="sxs-lookup"><span data-stu-id="de08d-189">Conversions</span></span>

<span data-ttu-id="de08d-190">모든 구조체 형식([`ref` 구조체](#ref-struct) 형식 제외)에는 <xref:System.ValueType?displayProperty=nameWithType> 및 <xref:System.Object?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-190">For any structure type (except [`ref` struct](#ref-struct) types), there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="de08d-191">구조체 형식과 구조체 형식이 구현하는 인터페이스 간에도 boxing 및 unboxing 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de08d-191">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="de08d-192">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="de08d-192">C# language specification</span></span>

<span data-ttu-id="de08d-193">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [구조체](~/_csharplang/spec/structs.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de08d-193">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="de08d-194">C# 7.2 이상에 도입된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de08d-194">For more information about features introduced in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="de08d-195">읽기 전용 구조체</span><span class="sxs-lookup"><span data-stu-id="de08d-195">Readonly structs</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)
- [<span data-ttu-id="de08d-196">읽기 전용 인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="de08d-196">Readonly instance members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)
- [<span data-ttu-id="de08d-197">ref 유사 형식에 대한 컴파일 시간 안전성</span><span class="sxs-lookup"><span data-stu-id="de08d-197">Compile-time safety for ref-like types</span></span>](~/_csharplang/proposals/csharp-7.2/span-safety.md)

## <a name="see-also"></a><span data-ttu-id="de08d-198">참조</span><span class="sxs-lookup"><span data-stu-id="de08d-198">See also</span></span>

- [<span data-ttu-id="de08d-199">C# 참조</span><span class="sxs-lookup"><span data-stu-id="de08d-199">C# reference</span></span>](../index.md)
- [<span data-ttu-id="de08d-200">디자인 지침 - 클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="de08d-200">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="de08d-201">디자인 지침-구조체 디자인</span><span class="sxs-lookup"><span data-stu-id="de08d-201">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="de08d-202">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="de08d-202">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
