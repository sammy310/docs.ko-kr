---
title: ?? 및 ??= 연산자 - C# 참조
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 1e94038a41a6a6cc19be6c67bff2891397793fb3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924690"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="f645b-103">??</span><span class="sxs-lookup"><span data-stu-id="f645b-103">??</span></span> <span data-ttu-id="f645b-104">및 ??= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f645b-104">and ??= operators (C# reference)</span></span>

<span data-ttu-id="f645b-105">null 병합 연산자 `??`는 `null`이 아닌 경우 왼쪽 피연산자의 값을 반환합니다. 그렇지 않으면 오른쪽 피연자를 평가하고 그 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="f645b-106">왼쪽 피연산자가 null이 아닌 것으로 평가되면 `??` 연산자는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="f645b-107">C# 8.0 이상에서 사용할 수 있는 null 병합 할당 연산자 `??=`는 왼쪽 피연산자가 `null`로 계산되는 경우에만 오른쪽 피연산자의 값을 왼쪽 피연산자에 대입합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-107">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="f645b-108">왼쪽 피연산자가 null이 아닌 것으로 평가되면 `??=` 연산자는 오른쪽 피연산자를 평가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-108">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="f645b-109">`??=` 연산자의 왼쪽 피연산자는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 또는 [인덱서](../../programming-guide/indexers/index.md) 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-109">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span> <span data-ttu-id="f645b-110">null 병합 할당에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f645b-110">For more information about null-coalescing assignment, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

<span data-ttu-id="f645b-111">C# 7.3 이전 버전에서 `??` 연산자의 왼쪽 피연산자 형식은 참조 형식 또는 [null 허용 값 형식](../../programming-guide/nullable-types/index.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-111">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a reference type or a [nullable value type](../../programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="f645b-112">C# 8.0부터 이 요구 사항이 다음과 같이 바뀝니다. `??` 및 `??=` 연산자의 왼쪽 피연산자 형식은 null을 허용하지 않는 값 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-112">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="f645b-113">특히 C# 8.0 이상에서 비제한 형식 매개 변수와 함께 null 병합 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-113">In particular, you can use the null-coalescing operators with unconstrained type parameters in C# 8.0 and later:</span></span>

[!code-csharp[unconstrained type parameter](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="f645b-114">null 병합 연산자는 오른쪽 결합입니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-114">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="f645b-115">즉, 양식의 식이</span><span class="sxs-lookup"><span data-stu-id="f645b-115">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="f645b-116">다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-116">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="f645b-117">예제</span><span class="sxs-lookup"><span data-stu-id="f645b-117">Examples</span></span>

<span data-ttu-id="f645b-118">`??` 및 `??=` 연산자는 다음과 같은 시나리오에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-118">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="f645b-119">[null 병합 연산자 ?. 및 ?[]](member-access-operators.md#null-conditional-operators--and-)가 있는 식에서 null 병합 연산자를 사용하여 null 조건부 연산을 사용한 식의 결과가 `null`인 경우 평가하는 대체 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-119">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="f645b-120">[nullable 값 형식](../../programming-guide/nullable-types/index.md)을 사용하고 기본값 유형의 값을 제공해야 할 때 null 병합 연산자를 사용하여 nullable 값이 `null`인 경우 제공할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-120">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="f645b-121">nullable 형식 값이 `null`일 때 사용될 값이 기본 값 형식의 기본 값이어야 하는 경우 <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-121">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="f645b-122">C# 7.0부터 null 병합 연산자의 오른쪽 피연산자로 [`throw` 식](../keywords/throw.md#the-throw-expression)을 사용하여 인수 확인 코드를 보다 간결하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-122">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="f645b-123">앞의 예제에서는 [식 본문 멤버](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)를 사용하여 속성을 정의하는 방법도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-123">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="f645b-124">C# 8.0부터 `??=` 연산자를 사용하여 다음 양식의 코드를</span><span class="sxs-lookup"><span data-stu-id="f645b-124">Starting with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="f645b-125">다음 코드와 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-125">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="f645b-126">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="f645b-126">Operator overloadability</span></span>

<span data-ttu-id="f645b-127">`??` 및 `??=` 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f645b-127">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f645b-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f645b-128">C# language specification</span></span>

<span data-ttu-id="f645b-129">`??` 연산자에 대한 자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [null 병합 연산자](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f645b-129">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f645b-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f645b-130">See also</span></span>

- [<span data-ttu-id="f645b-131">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f645b-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f645b-132">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f645b-132">C# operators</span></span>](index.md)
- <span data-ttu-id="f645b-133">[?. 및 ?[] 연산자](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="f645b-133">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="f645b-134">?: 연산자</span><span class="sxs-lookup"><span data-stu-id="f645b-134">?: operator</span></span>](conditional-operator.md)
