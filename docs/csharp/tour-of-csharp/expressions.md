---
title: C# 식 - C# 언어 둘러보기
description: 식, 피연산자 및 연산자는 C# 언어의 블록을 빌드합니다.
ms.date: 02/27/2020
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 209b5da01cd7539f2bd97023f40fd149910b6f1d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159158"
---
# <a name="expressions"></a><span data-ttu-id="6d125-103">표현식</span><span class="sxs-lookup"><span data-stu-id="6d125-103">Expressions</span></span>

<span data-ttu-id="6d125-104">*식*은 *피연산자* 및 *연산자*로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="6d125-105">식의 연산자는 피연산자에 적용할 연산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="6d125-106">연산자의 예로 `+`, `-`, `*`, `/` 및 `new`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="6d125-107">피연산자의 예로는 리터럴, 필드, 지역 변수 및 식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="6d125-108">식에 여러 연산자가 포함되어 있으면 연산자의 *우선 순위*에 따라 개별 연산자가 계산되는 순서가 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="6d125-109">예를 들어 `*` 연산자는 `+` 연산자보다 우선 순위가 더 높기 때문에 식 `x + y * z`는 `x + (y * z)`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="6d125-110">피연산자는 동일한 우선 순위를 가진 두 연산자 사이에 나올 경우 연산자의 *결합성*에 따라 연산이 수행되는 순서가 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="6d125-111">대입 및 Null 병합 연산자를 제외하고 모든 이항 연산자는 *왼쪽 결합성*을 갖습니다. 즉, 연산이 왼쪽에서 오른쪽으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-111">Except for the assignment and null-coalescing operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="6d125-112">예를 들어, `x + y + z`는 `(x + y) + z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="6d125-113">대입 연산자, Null 병합 `??` 및 `??=` 연산자, 조건부 연산자(`?:`)는 *오른쪽 결합성*을 갖습니다. 즉, 연산이 오른쪽에서 왼쪽으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-113">The assignment operators, the null-coalescing `??` and `??=` operators, and the conditional operator `?:` are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="6d125-114">예를 들어, `x = y = z`는 `x = (y = z)`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="6d125-115">우선 순위 및 결합성은 괄호를 사용하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="6d125-116">예를 들어 `x + y * z`는 먼저 `y`와 `z`를 곱한 다음 그 결과를 `x`와 더하지만 `(x + y) * z`는 먼저 `x`와 `y`를 더한 다음 그 결과에 `z`를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="6d125-117">대부분의 연산자는 [*오버로드*](../language-reference/operators/operator-overloading.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-117">Most operators can be [*overloaded*](../language-reference/operators/operator-overloading.md).</span></span> <span data-ttu-id="6d125-118">연산자 오버로드는 피연산자 중 하나 또는 둘 다가 사용자 정의 클래스 또는 구조체 형식인 연산에 대해 사용자 정의 연산자 구현을 지정할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="6d125-119">C#은 [산술](../language-reference/operators/arithmetic-operators.md), [논리](../language-reference/operators/boolean-logical-operators.md), [비트 및 시프트](../language-reference/operators/bitwise-and-shift-operators.md) 연산과 [같음](../language-reference/operators/equality-operators.md) 및 [순서](../language-reference/operators/comparison-operators.md) 비교를 수행하는 여러 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6d125-119">C# provides a number of operators to perform [arithmetic](../language-reference/operators/arithmetic-operators.md), [logical](../language-reference/operators/boolean-logical-operators.md), [bitwise and shift](../language-reference/operators/bitwise-and-shift-operators.md) operations and [equality](../language-reference/operators/equality-operators.md) and [order](../language-reference/operators/comparison-operators.md) comparisons.</span></span>

<span data-ttu-id="6d125-120">우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](../language-reference/operators/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d125-120">For the complete list of C# operators ordered by precedence level, see [C# operators](../language-reference/operators/index.md).</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="6d125-121">[이전](types-and-variables.md)
> [다음](statements.md)</span><span class="sxs-lookup"><span data-stu-id="6d125-121">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
