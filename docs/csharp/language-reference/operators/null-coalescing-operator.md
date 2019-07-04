---
title: ?? 연산자 - C# 참조
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: a19b5558da36ffb11dabd1b9bec419a3623a0f17
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67024995"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="00535-103">??</span><span class="sxs-lookup"><span data-stu-id="00535-103">??</span></span> <span data-ttu-id="00535-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="00535-104">operator (C# reference)</span></span>

<span data-ttu-id="00535-105">null 병합 연산자 `??`는 `null`이 아닌 경우 왼쪽 피연산자의 값을 반환합니다. 그렇지 않으면 오른쪽 피연자를 평가하고 그 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="00535-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="00535-106">왼쪽 피연산자가 null이 아닌 것으로 평가되면 `??` 연산자는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00535-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="00535-107">null 병합 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="00535-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="00535-108">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="00535-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="00535-109">`??` 연산자는 다음과 같은 시나리오에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00535-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="00535-110">[null 병합 연산자 ?. 및 ?[]](member-access-operators.md#null-conditional-operators--and-)가 있는 식에서 null 병합 연산자를 사용하여 null 조건부 연산을 사용한 식의 결과가 `null`인 경우 평가하는 대체 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00535-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="00535-111">[nullable 값 형식](../../programming-guide/nullable-types/index.md)을 사용하고 기본값 유형의 값을 제공해야 할 때 null 병합 연산자를 사용하여 nullable 값이 `null`인 경우 제공할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00535-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="00535-112">nullable 형식 값이 `null`일 때 사용될 값이 기본 값 형식의 기본 값이어야 하는 경우 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00535-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="00535-113">C# 7.0부터 null 병합 연산자의 오른쪽 피연산자로 [`throw` 식](../keywords/throw.md#the-throw-expression)을 사용하여 인수 확인 코드를 보다 간결하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00535-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="00535-114">앞의 예제에서는 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 사용하여 속성을 정의하는 방법도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="00535-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="00535-115">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="00535-115">Operator overloadability</span></span>

<span data-ttu-id="00535-116">null 병합 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00535-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="00535-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="00535-117">C# language specification</span></span>

<span data-ttu-id="00535-118">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [null 병합 연산자](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00535-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00535-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00535-119">See also</span></span>

- [<span data-ttu-id="00535-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="00535-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="00535-121">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="00535-121">C# operators</span></span>](index.md)
- <span data-ttu-id="00535-122">[?. 및 ?[] 연산자](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="00535-122">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="00535-123">?: 연산자</span><span class="sxs-lookup"><span data-stu-id="00535-123">?: operator</span></span>](conditional-operator.md)
