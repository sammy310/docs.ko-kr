---
description: C#의 값 형식, 관련 종류 및 기본 제공 항목에 관한 자세한 정보
title: 값 형식 - C# 참조
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 64c9e9eba2495531cfef8a603d53fb21c95c87a4
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599397"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="37a7f-103">값 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="37a7f-103">Value types (C# reference)</span></span>

<span data-ttu-id="37a7f-104">*값 형식* 및 [참조 형식](../keywords/reference-types.md)은 C# 형식의 두 가지 주요 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-104">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="37a7f-105">값 형식의 변수에는 형식의 인스턴스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-105">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="37a7f-106">이는 형식 인스턴스에 대한 참조를 포함하는 참조 형식의 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-106">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="37a7f-107">기본적으로 변수 값은 [할당](../operators/assignment-operator.md) 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-107">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="37a7f-108">값 형식 변수의 경우 해당 형식 인스턴스가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-108">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="37a7f-109">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-109">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/shared/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="37a7f-110">앞의 예제와 같이 값 형식 변수에 대한 작업은 변수에 저장된 값 형식의 인스턴스에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-110">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="37a7f-111">값 형식이 참조 형식의 데이터 구성원을 포함하는 경우에는 값 형식 인스턴스가 복사될 때 참조 형식의 인스턴스에 대한 참조만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-111">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="37a7f-112">복사 및 원래 값 형식 인스턴스는 모두 동일한 참조 형식 인스턴스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-112">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="37a7f-113">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-113">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/shared/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="37a7f-114">코드를 오류가 덜 발생하고 더 강력하게 만들려면 변경할 수 없는 값 형식을 정의 및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-114">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="37a7f-115">이 문서에서는 데모용으로만 변경 가능한 값 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-115">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types-and-type-constraints"></a><span data-ttu-id="37a7f-116">값 형식 및 형식 제약 조건의 종류</span><span class="sxs-lookup"><span data-stu-id="37a7f-116">Kinds of value types and type constraints</span></span>

<span data-ttu-id="37a7f-117">값 형식은 다음 두 가지 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-117">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="37a7f-118">데이터 및 관련 기능을 캡슐화하는[구조 형식](struct.md)</span><span class="sxs-lookup"><span data-stu-id="37a7f-118">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="37a7f-119">명명된 상수 집합으로 정의되고 선택 사항 또는 선택 사항의 조합을 나타내는 [열거 형식](enum.md)</span><span class="sxs-lookup"><span data-stu-id="37a7f-119">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="37a7f-120">기본 값 형식 `T`의 모든 값과 추가 [Null](../keywords/null.md) 값을 나타내는 [ 값 형식](nullable-value-types.md) `T?`</span><span class="sxs-lookup"><span data-stu-id="37a7f-120">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="37a7f-121">Null 허용 값 형식인 경우를 제외하고는 값 형식의 변수에 `null`을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-121">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

<span data-ttu-id="37a7f-122">[`struct` 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 사용하여 형식 매개 변수가 null을 허용하지 않는 값 형식이라고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-122">You can use the [`struct` constraint](../../programming-guide/generics/constraints-on-type-parameters.md) to specify that a type parameter is a non-nullable value type.</span></span> <span data-ttu-id="37a7f-123">구조체 형식과 열거형 형식 모두 `struct` 제약 조건을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-123">Both structure and enumeration types satisfy the `struct` constraint.</span></span> <span data-ttu-id="37a7f-124">C# 7.3부터 기본 클래스 제약 조건([열거형 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)이라고 함)에서 `System.Enum`을 사용하여 형식 매개 변수가 열거형 형식이라고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-124">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="37a7f-125">기본 제공 값 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-125">Built-in value types</span></span>

<span data-ttu-id="37a7f-126">C#은 *단순 형식* 이라고도 하는 다음과 같은 기본 제공 값 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-126">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="37a7f-127">정수 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-127">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="37a7f-128">부동 소수점 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-128">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="37a7f-129">부울 값을 나타내는 [bool](bool.md)</span><span class="sxs-lookup"><span data-stu-id="37a7f-129">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="37a7f-130">유니코드 UTF-16 문자를 나타내는 [문자](char.md)</span><span class="sxs-lookup"><span data-stu-id="37a7f-130">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="37a7f-131">모든 단순 형식은 구조체 형식이며, 특정 추가 작업을 허용한다는 점에서 다른 구조체 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-131">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="37a7f-132">리터럴을 사용하여 단순 형식의 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-132">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="37a7f-133">예를 들어 `'A'`는 `char` 형식의 리터럴이고, `2001`은 `int` 형식의 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-133">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="37a7f-134">[const](../keywords/const.md) 키워드를 사용하여 단순 형식의 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-134">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="37a7f-135">다른 구조체 형식의 상수는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-135">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="37a7f-136">해당 피연산자가 모두 단순 형식의 상수인 상수 식은 컴파일 시간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-136">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="37a7f-137">C# 7.0부터는 C#에서 [값 튜플](value-tuples.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-137">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="37a7f-138">값 튜플은 단순 형식이 아닌 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="37a7f-138">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="37a7f-139">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="37a7f-139">C# language specification</span></span>

<span data-ttu-id="37a7f-140">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37a7f-140">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="37a7f-141">값 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-141">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="37a7f-142">단순 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-142">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="37a7f-143">변수</span><span class="sxs-lookup"><span data-stu-id="37a7f-143">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="37a7f-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37a7f-144">See also</span></span>

- [<span data-ttu-id="37a7f-145">C# 참조</span><span class="sxs-lookup"><span data-stu-id="37a7f-145">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="37a7f-146">참조 형식</span><span class="sxs-lookup"><span data-stu-id="37a7f-146">Reference types</span></span>](../keywords/reference-types.md)
