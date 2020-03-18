---
title: '- 및 -= 연산자 - C# 참조'
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 2017aade92e8d7ad2af7101a107122fa8d7b9e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847653"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="44d64-102">- 및 -= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="44d64-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="44d64-103">`-` 및 `-=` 연산자에는 기본 제공 [정수](../builtin-types/integral-numeric-types.md) 및 [부동 소수점](../builtin-types/floating-point-numeric-types.md) 숫자 형식, [대리자](../builtin-types/reference-types.md#the-delegate-type) 형식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="44d64-104">산술 `-` 연산자에 대한 자세한 내용은 [산술 연산자](arithmetic-operators.md#unary-plus-and-minus-operators) 문서의 [단항 더하기 및 빼기 연산자](arithmetic-operators.md#subtraction-operator--) 및 [빼기 연산자 -](arithmetic-operators.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d64-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="44d64-105">대리자 제거</span><span class="sxs-lookup"><span data-stu-id="44d64-105">Delegate removal</span></span>

<span data-ttu-id="44d64-106">동일한 [대리자](../builtin-types/reference-types.md#the-delegate-type) 형식의 피연산자에 대해 `-` 연산자는 다음과 같이 계산되는 대리자 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="44d64-107">두 피연산자가 모두 null이 아니고 오른쪽 피연산자의 호출 목록이 왼쪽 피연산자의 호출 목록에 적절한 연속 하위 목록인 경우, 이 연산의 결과는 왼쪽 피연산자의 호출 목록에서 오른쪽 피연산자의 항목을 제거하여 얻은 새로운 호출 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="44d64-108">오른쪽 피연산자의 목록이 왼쪽 피연산자 목록의 여러 개의 연속 하위 목록과 일치하는 경우 가장 오른쪽의 일치하는 하위 목록만 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="44d64-109">제거로 인해 빈 목록이 생성되면 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](snippets/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="44d64-110">오른쪽 피연산자의 호출 목록이 왼쪽 피연산자의 호출 목록의 적절한 연속 하위 목록이 아닌 경우, 해당 연산의 결과는 왼쪽 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="44d64-111">예를 들어 멀티 캐스트 대리자의 일부가 아닌 대리자를 제거하면 아무 작업도 수행되지 않고 변경되지 않은 멀티 캐스트 대리자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](snippets/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="44d64-112">또한 앞의 예제에서는 대리자 제거 중 대리자 인스턴스를 비교하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="44d64-113">예를 들어 동일한 [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md)의 평가에서 생성된 대리자는 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="44d64-114">대리자 같음에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/expressions.md#delegate-equality-operators)의 [대리자 같음 연산자](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d64-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="44d64-115">왼쪽 피연산자가 `null`이면, 연산 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="44d64-116">오른쪽 피연산자가 `null`이면, 연산 결과는 왼쪽 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](snippets/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="44d64-117">대리자를 결합하려면 [`+` 연산자](addition-operator.md#delegate-combination)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="44d64-118">대리자 형식에 대한 자세한 내용은 [대리자](../../programming-guide/delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d64-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="44d64-119">빼기 할당 연산자 -=</span><span class="sxs-lookup"><span data-stu-id="44d64-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="44d64-120">다음과 같은 `-=` 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="44d64-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="44d64-121">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="44d64-122">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="44d64-123">다음 예제에서는 `-=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](snippets/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="44d64-124">또한 `-=`이벤트[에서 구독 취소할 때 ](../keywords/event.md) 연산자를 사용하여 제거할 이벤트 처리기 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="44d64-125">자세한 내용은 [이벤트를 구독 및 구독 취소하는 방법](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d64-125">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="44d64-126">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="44d64-126">Operator overloadability</span></span>

<span data-ttu-id="44d64-127">사용자 정의 형식은 [ 연산자를 ](operator-overloading.md)오버로드`-`할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="44d64-128">이진 `-` 연산자가 오버로드되면 `-=` 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="44d64-129">사용자 정의 형식에는 `-=` 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44d64-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="44d64-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="44d64-130">C# language specification</span></span>

<span data-ttu-id="44d64-131">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/expressions.md#unary-minus-operator)의 [단항 빼기 연산자](~/_csharplang/spec/expressions.md#subtraction-operator) 및 [빼기 연산자](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d64-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44d64-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44d64-132">See also</span></span>

- [<span data-ttu-id="44d64-133">C# 참조</span><span class="sxs-lookup"><span data-stu-id="44d64-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="44d64-134">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="44d64-134">C# operators</span></span>](index.md)
- [<span data-ttu-id="44d64-135">이벤트</span><span class="sxs-lookup"><span data-stu-id="44d64-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="44d64-136">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="44d64-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="44d64-137">+ 및 += 연산자</span><span class="sxs-lookup"><span data-stu-id="44d64-137">+ and += operators</span></span>](addition-operator.md)
