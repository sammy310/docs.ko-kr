---
title: true 및 false 연산자 - C# 참조
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 869eeab6515340b2f1884ab7206979e83654a10b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328246"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="af493-102">true 및 false 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="af493-102">true and false operators (C# Reference)</span></span>

<span data-ttu-id="af493-103">`true` 연산자는 [부울](bool.md) 값을 반환하여 `true` 피연산자가 확실히 true임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af493-103">The `true` operator returns the [bool](bool.md) value `true` to indicate that an operand is definitely true.</span></span> <span data-ttu-id="af493-104">`false` 연산자는 `bool` 값을 반환하여 `true` 피연산자가 확실히 false임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af493-104">The `false` operator returns the `bool` value `true` to indicate that an operand is definitely false.</span></span> <span data-ttu-id="af493-105">`true` 및 `false` 연산자는 서로를 보완한다고 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="af493-106">즉, `true` 및 `false` 연산자는 모두 `bool` 값을 동일한 `false` 피연산자에 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="af493-107">형식이 두 연산자 중 하나를 정의하는 경우 나머지 연산자도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-107">If a type defines one of the two operators, it must also define another operator.</span></span>

<span data-ttu-id="af493-108">정의된 `true` 및 `false` 연산자가 있는 형식이 특정 방식으로 [논리적 OR 연산자](../operators/boolean-logical-operators.md#logical-or-operator-) `|` 또는 [논리적 AND 연산자](../operators/boolean-logical-operators.md#logical-and-operator-) `&`를 [오버로드](operator.md)하는 경우, [조건부 논리적 OR 연산자](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) `||` 또는 [조건부 논리적 AND 연산자](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) `&&`가 해당 형식의 피연산자에 대해 각각 계산될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-108">If a type with the defined `true` and `false` operators [overloads](operator.md) the [logical OR operator](../operators/boolean-logical-operators.md#logical-or-operator-) `|` or the [logical AND operator](../operators/boolean-logical-operators.md#logical-and-operator-) `&` in a certain way, the [conditional logical OR operator](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) `||` or [conditional logical AND operator](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="af493-109">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [사용자 정의 조건부 논리 연산자](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af493-109">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

<span data-ttu-id="af493-110">정의된 `true` 연산자가 있는 형식은 [if](if-else.md), [do](do.md), [while](while.md) 및 [for](for.md) 문과 [조건부 연산자`?:`](../operators/conditional-operator.md)에서 제어하는 조건식의 결과 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-110">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span> <span data-ttu-id="af493-111">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [부울 식](~/_csharplang/spec/expressions.md#boolean-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af493-111">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!TIP]
> <span data-ttu-id="af493-112">예를 들어 값이 세 개인 논리를 지원해야 하는 경우(예: 값이 세 개인 부울 형식을 지원하는 데이터베이스에서 작업하는 경우) `bool?` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-112">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="af493-113">C#은 `bool?` 피연산자를 사용하여 값이 세 개인 논리를 지원하는 `&` 및 `|` 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-113">C# provides the `&` and `|` operators that support the three-valued logic with the `bool?` operands.</span></span> <span data-ttu-id="af493-114">자세한 내용은 [부울 논리 연산자](../operators/boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af493-114">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="af493-115">다음 예제는 `true` 및 `false` 연산자를 둘 다 정의하는 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-115">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="af493-116">더욱이, `&&` 연산자도 해당 형식의 피연산자에 대해 계산될 수 있는 방식으로 논리적 AND 연산자 `&`를 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-116">Moreover, it overloads the logical AND operator `&` in such a way that the operator `&&` also can be evaluated for the operands of that type.</span></span>

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

<span data-ttu-id="af493-117">`&&` 연산자의 단락 동작을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af493-117">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="af493-118">`GetFuelLaunchStatus` 메서드가 `LaunchStatus.Red`를 반환하면 `&&` 연산자의 두 번째 피연산자는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-118">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the second operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="af493-119">`LaunchStatus.Red`가 확실히 false이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="af493-119">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="af493-120">따라서 논리적 AND의 결과가 두 번째 피연산자의 값에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-120">Then the result of the logical AND doesn't depend on the value of the second operand.</span></span> <span data-ttu-id="af493-121">예제 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af493-121">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="af493-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af493-122">See also</span></span>

- [<span data-ttu-id="af493-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="af493-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af493-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="af493-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af493-125">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="af493-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="af493-126">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="af493-126">C# Operators</span></span>](../operators/index.md)
- [<span data-ttu-id="af493-127">`true` 리터럴</span><span class="sxs-lookup"><span data-stu-id="af493-127">`true` literal</span></span>](true-literal.md)
- [<span data-ttu-id="af493-128">`false` 리터럴</span><span class="sxs-lookup"><span data-stu-id="af493-128">`false` literal</span></span>](false-literal.md)