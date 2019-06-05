---
title: '- 및 -= 연산자 - C# 참조'
ms.custom: seodec18
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
ms.openlocfilehash: 9f43a863de69122e251204668af2ea989fcc993c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300084"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="f38c1-102">- 및 -= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f38c1-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="f38c1-103">`-` 연산자는 기본 제공 숫자 형식 및 [대리자](../keywords/delegate.md) 형식에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="f38c1-104">산술 `-` 연산자에 대한 자세한 내용은 [산술 연산자](arithmetic-operators.md) 문서의 [단항 더하기 및 빼기 연산자](arithmetic-operators.md#unary-plus-and-minus-operators) 및 [빼기 연산자 -](arithmetic-operators.md#subtraction-operator--) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f38c1-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="f38c1-105">대리자 제거</span><span class="sxs-lookup"><span data-stu-id="f38c1-105">Delegate removal</span></span>

<span data-ttu-id="f38c1-106">동일한 [대리자](../keywords/delegate.md) 형식의 피연산자에 대해 `-` 연산자는 다음과 같이 계산되는 대리자 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="f38c1-107">두 피연산자가 모두 null이 아니고 두 번째 피연산자의 호출 목록이 첫 번째 피연산자의 호출 목록에 적절한 연속 하위 목록인 경우, 이 작업의 결과는 첫 번째 피연산자의 호출 목록에서 두 번째 피연산자의 항목을 제거하여 얻은 새로운 호출 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="f38c1-108">두 번째 피연산자의 목록이 첫 번째 피연산자 목록의 여러 개의 연속 하위 목록과 일치하는 경우 가장 오른쪽에 일치하는 하위 목록만 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="f38c1-109">제거로 인해 빈 목록이 생성되면 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-109">If removal results in an empty list, the result is `null`.</span></span>
- <span data-ttu-id="f38c1-110">두 번째 피연산자의 호출 목록이 첫 번째 피연산자의 호출 목록의 적절한 연속 하위 목록이 아닌 경우, 해당 작업의 결과는 첫 번째 피연자입니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span>
- <span data-ttu-id="f38c1-111">첫 번째 피연산자가 `null`이면, 작업의 결과는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-111">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="f38c1-112">두 번째 피연산자가 `null`이면, 작업 결과는 첫 번째 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-112">If the second operand is `null`, the result of the operation is the first operand.</span></span>

<span data-ttu-id="f38c1-113">다음 예제에서는 `-` 작업에서 대리자 제거를 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-113">The following example shows how the `-` operation performs delegate removal:</span></span>

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="f38c1-114">빼기 할당 연산자 -=</span><span class="sxs-lookup"><span data-stu-id="f38c1-114">Subtraction assignment operator -=</span></span>

<span data-ttu-id="f38c1-115">다음과 같은 `-=` 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="f38c1-115">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="f38c1-116">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-116">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="f38c1-117">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="f38c1-118">다음 예제에서는 `-=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-118">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="f38c1-119">또한 [이벤트](../keywords/event.md)에서 구독 취소할 때 `-=` 연산자를 사용하여 제거할 이벤트 처리기 메서드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-119">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="f38c1-120">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f38c1-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f38c1-121">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="f38c1-121">Operator overloadability</span></span>

<span data-ttu-id="f38c1-122">사용자 정의 형식은 `-` 연산자를 [오버로드](../keywords/operator.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-122">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="f38c1-123">이진 `-` 연산자가 오버로드되면 `-=` 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-123">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="f38c1-124">사용자 정의 형식에는 `-=` 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f38c1-124">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f38c1-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f38c1-125">C# language specification</span></span>

<span data-ttu-id="f38c1-126">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [단항 빼기 연산자](~/_csharplang/spec/expressions.md#unary-minus-operator) 및 [빼기 연산자](~/_csharplang/spec/expressions.md#subtraction-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f38c1-126">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f38c1-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f38c1-127">See also</span></span>

- [<span data-ttu-id="f38c1-128">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f38c1-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f38c1-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f38c1-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f38c1-130">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f38c1-130">C# Operators</span></span>](index.md)
- [<span data-ttu-id="f38c1-131">대리자</span><span class="sxs-lookup"><span data-stu-id="f38c1-131">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="f38c1-132">이벤트</span><span class="sxs-lookup"><span data-stu-id="f38c1-132">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="f38c1-133">Checked 및 Unchecked</span><span class="sxs-lookup"><span data-stu-id="f38c1-133">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="f38c1-134">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="f38c1-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="f38c1-135">+ 및 += 연산자</span><span class="sxs-lookup"><span data-stu-id="f38c1-135">+ and += operators</span></span>](addition-operator.md)
