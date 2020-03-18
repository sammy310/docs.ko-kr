---
title: true 및 false 연산자 - C# 참조
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 5ccd08a348478902bbbac36e99acf7ffc1fc814b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846221"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="8e529-102">true 및 false 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8e529-102">true and false operators (C# reference)</span></span>

<span data-ttu-id="8e529-103">`true` 연산자는 [부울](../builtin-types/bool.md) 값을 반환하여 `true` 피연산자가 확실히 true임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-103">The `true` operator returns the [bool](../builtin-types/bool.md) value `true` to indicate that its operand is definitely true.</span></span> <span data-ttu-id="8e529-104">`false` 연산자는 `bool` 값을 반환하여 `true` 피연산자가 확실히 false임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-104">The `false` operator returns the `bool` value `true` to indicate that its operand is definitely false.</span></span> <span data-ttu-id="8e529-105">`true` 및 `false` 연산자는 서로를 보완한다고 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="8e529-106">즉, `true` 및 `false` 연산자는 모두 `bool` 값을 동일한 `false` 피연산자에 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="8e529-107">형식이 두 연산자 중 하나를 정의하는 경우 나머지 연산자도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-107">If a type defines one of the two operators, it must also define another operator.</span></span>

> [!TIP]
> <span data-ttu-id="8e529-108">예를 들어 값이 세 개인 논리를 지원해야 하는 경우(예: 값이 세 개인 부울 형식을 지원하는 데이터베이스에서 작업하는 경우) `bool?` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-108">Use the `bool?` type, if you need to support the three-valued logic (for example, when you work with databases that support a three-valued Boolean type).</span></span> <span data-ttu-id="8e529-109">C#은 `&` 피연산자를 사용하여 값이 세 개인 논리를 지원하는 `|` 및 `bool?` 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-109">C# provides the `&` and `|` operators that support the three-valued logic with the `bool?` operands.</span></span> <span data-ttu-id="8e529-110">자세한 내용은 [부울 논리 연산자](boolean-logical-operators.md#nullable-boolean-logical-operators) 문서의 [Nullable 부울 논리 연산자](boolean-logical-operators.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e529-110">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="8e529-111">부울 식</span><span class="sxs-lookup"><span data-stu-id="8e529-111">Boolean expressions</span></span>

<span data-ttu-id="8e529-112">정의된 `true` 연산자가 있는 형식은 [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) 및 [for](../keywords/for.md) 문과 [조건부 연산자`?:`](conditional-operator.md)에서 제어하는 조건식의 결과 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-112">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](conditional-operator.md).</span></span> <span data-ttu-id="8e529-113">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/expressions.md#boolean-expressions)의 [부울 식](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e529-113">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="user-defined-conditional-logical-operators"></a><span data-ttu-id="8e529-114">사용자 지정 조건부 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="8e529-114">User-defined conditional logical operators</span></span>

<span data-ttu-id="8e529-115">정의된 `true` 및 `false` 연산자가 있는 형식이 특정 방식으로 [논리적 OR 연산자](operator-overloading.md) [ 또는 ](boolean-logical-operators.md#logical-or-operator-)논리적 AND 연산자`|` [를 ](boolean-logical-operators.md#logical-and-operator-)오버로드`&`하는 경우, [조건부 논리적 OR 연산자](boolean-logical-operators.md#conditional-logical-or-operator-) `||` 또는 [조건부 논리적 AND 연산자](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`가 해당 형식의 피연산자에 대해 각각 계산될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-115">If a type with the defined `true` and `false` operators [overloads](operator-overloading.md) the [logical OR operator](boolean-logical-operators.md#logical-or-operator-) `|` or the [logical AND operator](boolean-logical-operators.md#logical-and-operator-) `&` in a certain way, the [conditional logical OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||` or [conditional logical AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="8e529-116">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)의 [사용자 정의 조건부 논리 연산자](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e529-116">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="example"></a><span data-ttu-id="8e529-117">예제</span><span class="sxs-lookup"><span data-stu-id="8e529-117">Example</span></span>

<span data-ttu-id="8e529-118">다음 예제는 `true` 및 `false` 연산자를 둘 다 정의하는 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-118">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="8e529-119">`&` 연산자도 해당 형식의 피연산자에 대해 계산될 수 있는 방식으로 논리적 AND 연산자 `&&`를 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-119">The type also overloads the logical AND operator `&` in such a way that the `&&` operator also can be evaluated for the operands of that type.</span></span>

[!code-csharp[true and false operators example](snippets/TrueFalseOperators.cs)]

<span data-ttu-id="8e529-120">`&&` 연산자의 단락 동작을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-120">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="8e529-121">`GetFuelLaunchStatus` 메서드가 `LaunchStatus.Red`를 반환하면 `&&` 연산자의 오른쪽 피연산자는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-121">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the right-hand operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="8e529-122">`LaunchStatus.Red`가 확실히 false이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-122">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="8e529-123">따라서 논리적 AND의 결과가 오른쪽 피연산자의 값에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-123">Then the result of the logical AND doesn't depend on the value of the right-hand operand.</span></span> <span data-ttu-id="8e529-124">예제 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e529-124">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="8e529-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e529-125">See also</span></span>

- [<span data-ttu-id="8e529-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8e529-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8e529-127">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8e529-127">C# operators</span></span>](index.md)
