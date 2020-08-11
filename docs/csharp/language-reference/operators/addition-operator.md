---
title: + 및 += 연산자 - C# 참조
ms.date: 04/23/2020
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: f1db0054ad2411bfe23f10b64bc2727a71ad7463
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916957"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="d1e66-102">+ 및 += 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d1e66-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="d1e66-103">`+` 및 `+=` 연산자에는 기본 제공 [정수](../builtin-types/integral-numeric-types.md) 및 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식, [문자열](../builtin-types/reference-types.md#the-string-type) 형식 및 [대리자](../builtin-types/reference-types.md#the-delegate-type) 형식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="d1e66-104">산술 `+` 연산자에 대한 자세한 내용은 [산술 연산자](arithmetic-operators.md) 문서의 [단항 더하기 및 빼기 연산자](arithmetic-operators.md#unary-plus-and-minus-operators) 및 [더하기 연산자 +](arithmetic-operators.md#addition-operator-) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e66-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="d1e66-105">문자열 연결</span><span class="sxs-lookup"><span data-stu-id="d1e66-105">String concatenation</span></span>

<span data-ttu-id="d1e66-106">피연산자 중 하나 또는 둘 다가 [문자열](../builtin-types/reference-types.md#the-string-type) 형식이면 `+` 연산자는 피연산자의 문자열 표현을 연결합니다(`null`의 문자열 표현은 빈 문자열임).</span><span class="sxs-lookup"><span data-stu-id="d1e66-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands (the string representation of `null` is an empty string):</span></span>

[!code-csharp-interactive[string concatenation](snippets/shared/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="d1e66-107">C# 6부터 [문자열 보간](../tokens/interpolated.md)은 문자열 형식을 지정하는 더욱 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](snippets/shared/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="d1e66-108">대리자 조합</span><span class="sxs-lookup"><span data-stu-id="d1e66-108">Delegate combination</span></span>

<span data-ttu-id="d1e66-109">동일한 [대리자](../builtin-types/reference-types.md#the-delegate-type) 형식의 피연산자의 경우 `+` 연산자는 호출될 때 왼쪽 피연산자를 호출한 다음, 오른쪽 피연산자를 호출하는 새 대리자 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="d1e66-110">피연산자 중 하나라도 `null`이면 `+` 연산자는 다른 피연산자(`null`일 수도 있음)의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="d1e66-111">다음 예제는 `+` 연산자를 사용하여 대리자를 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](snippets/shared/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="d1e66-112">대리자 제거를 수행하려면 [`-` 연산자](subtraction-operator.md#delegate-removal)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="d1e66-113">대리자 형식에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e66-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="d1e66-114">더하기 할당 연산자 +=</span><span class="sxs-lookup"><span data-stu-id="d1e66-114">Addition assignment operator +=</span></span>

<span data-ttu-id="d1e66-115">다음과 같은 `+=` 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="d1e66-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="d1e66-116">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="d1e66-117">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="d1e66-118">다음 예제에서는 `+=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](snippets/shared/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="d1e66-119">또한 [이벤트](../keywords/event.md)를 구독할 때 `+=` 연산자를 사용하여 이벤트 처리기 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="d1e66-120">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e66-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d1e66-121">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="d1e66-121">Operator overloadability</span></span>

<span data-ttu-id="d1e66-122">사용자 정의 형식은 `+` 연산자를 [오버로드](operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="d1e66-123">이진 `+` 연산자가 오버로드되면 `+=` 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="d1e66-124">사용자 정의 형식에는 `+=` 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e66-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d1e66-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d1e66-125">C# language specification</span></span>

<span data-ttu-id="d1e66-126">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [단항 더하기 연산자](~/_csharplang/spec/expressions.md#unary-plus-operator) 및 [더하기 연산자](~/_csharplang/spec/expressions.md#addition-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e66-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1e66-127">참조</span><span class="sxs-lookup"><span data-stu-id="d1e66-127">See also</span></span>

- [<span data-ttu-id="d1e66-128">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d1e66-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d1e66-129">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="d1e66-129">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="d1e66-130">여러 문자열 연결 방법</span><span class="sxs-lookup"><span data-stu-id="d1e66-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="d1e66-131">이벤트</span><span class="sxs-lookup"><span data-stu-id="d1e66-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="d1e66-132">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="d1e66-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="d1e66-133">- 및 -= 연산자</span><span class="sxs-lookup"><span data-stu-id="d1e66-133">- and -= operators</span></span>](subtraction-operator.md)
