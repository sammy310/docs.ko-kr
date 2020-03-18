---
title: 값 형식 - C# 참조
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 406e5b8bbe0802146a65bb4b9a053e753a7827ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398270"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="0b84e-102">값 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0b84e-102">Value types (C# reference)</span></span>

<span data-ttu-id="0b84e-103">*값 형식* 및 [참조 형식](../keywords/reference-types.md)은 C# 형식의 두 가지 주요 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="0b84e-104">값 형식의 변수에는 형식의 인스턴스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="0b84e-105">이는 형식 인스턴스에 대한 참조를 포함하는 참조 형식의 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="0b84e-106">기본적으로 변수 값은 [할당](../operators/assignment-operator.md) 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="0b84e-107">값 형식 변수의 경우 해당 형식 인스턴스가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="0b84e-108">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="0b84e-109">앞의 예제와 같이 값 형식 변수에 대한 작업은 변수에 저장된 값 형식의 인스턴스에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="0b84e-110">값 형식이 참조 형식의 데이터 구성원을 포함하는 경우에는 값 형식 인스턴스가 복사될 때 참조 형식의 인스턴스에 대한 참조만 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="0b84e-111">복사 및 원래 값 형식 인스턴스는 모두 동일한 참조 형식 인스턴스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="0b84e-112">다음 예제에서는 해당 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="0b84e-113">코드를 오류가 덜 발생하고 더 강력하게 만들려면 변경할 수 없는 값 형식을 정의 및 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="0b84e-114">이 문서에서는 데모용으로만 변경 가능한 값 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="0b84e-115">값 형식의 종류</span><span class="sxs-lookup"><span data-stu-id="0b84e-115">Kinds of value types</span></span>

<span data-ttu-id="0b84e-116">값 형식은 다음 두 가지 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="0b84e-117">데이터 및 관련 기능을 캡슐화하는[구조 형식](struct.md)</span><span class="sxs-lookup"><span data-stu-id="0b84e-117">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="0b84e-118">명명된 상수 집합으로 정의되고 선택 사항 또는 선택 사항의 조합을 나타내는 [열거 형식](enum.md)</span><span class="sxs-lookup"><span data-stu-id="0b84e-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="0b84e-119">기본 값 형식 `T`의 모든 값과 추가 [Null](../keywords/null.md) 값을 나타내는 [ 값 형식](nullable-value-types.md) `T?`</span><span class="sxs-lookup"><span data-stu-id="0b84e-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="0b84e-120">Null 허용 값 형식인 경우를 제외하고는 값 형식의 변수에 `null`을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="0b84e-121">기본 제공 값 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-121">Built-in value types</span></span>

<span data-ttu-id="0b84e-122">C#은 *단순 형식*이라고도 하는 다음과 같은 기본 제공 값 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="0b84e-123">정수 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="0b84e-124">부동 소수점 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="0b84e-125">부울 값을 나타내는 [bool](bool.md)</span><span class="sxs-lookup"><span data-stu-id="0b84e-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="0b84e-126">유니코드 UTF-16 문자를 나타내는 [문자](char.md)</span><span class="sxs-lookup"><span data-stu-id="0b84e-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="0b84e-127">모든 단순 형식은 구조체 형식이며, 특정 추가 작업을 허용한다는 점에서 다른 구조체 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="0b84e-128">리터럴을 사용하여 단순 형식의 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="0b84e-129">예를 들어 `'A'`는 `char` 형식의 리터럴이고, `2001`은 `int` 형식의 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="0b84e-130">[const](../keywords/const.md) 키워드를 사용하여 단순 형식의 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="0b84e-131">다른 구조체 형식의 상수는 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="0b84e-132">해당 피연산자가 모두 단순 형식의 상수인 상수 식은 컴파일 시간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="0b84e-133">C# 7.0부터는 C#에서 [값 튜플](../../tuples.md)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="0b84e-134">값 튜플은 단순 형식이 아닌 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b84e-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b84e-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0b84e-135">C# language specification</span></span>

<span data-ttu-id="0b84e-136">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b84e-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0b84e-137">값 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="0b84e-138">단순 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="0b84e-139">변수</span><span class="sxs-lookup"><span data-stu-id="0b84e-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="0b84e-140">참조</span><span class="sxs-lookup"><span data-stu-id="0b84e-140">See also</span></span>

- [<span data-ttu-id="0b84e-141">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0b84e-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="0b84e-142">참조 형식</span><span class="sxs-lookup"><span data-stu-id="0b84e-142">Reference types</span></span>](../keywords/reference-types.md)
