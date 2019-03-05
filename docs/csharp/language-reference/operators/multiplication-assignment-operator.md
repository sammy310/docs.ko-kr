---
title: '*= 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967388"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5a8c1-102">\*= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5a8c1-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="5a8c1-103">곱하기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="5a8c1-104">다음과 같은 `*=` 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="5a8c1-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="5a8c1-105">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="5a8c1-106">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="5a8c1-107">숫자 형식의 경우 [\* 연산자](multiplication-operator.md)는 해당 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="5a8c1-108">다음 예제에서는 `*=` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="5a8c1-109">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="5a8c1-109">Operator overloadability</span></span>

<span data-ttu-id="5a8c1-110">사용자 정의 형식이 [곱하기 연산자](multiplication-operator.md) `*`를 [오버로드](../keywords/operator.md)하면 곱하기 대입 연산자 `*=`는 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="5a8c1-111">사용자 정의 형식은 곱하기 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5a8c1-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5a8c1-112">C# language specification</span></span>

<span data-ttu-id="5a8c1-113">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [복합 할당](~/_csharplang/spec/expressions.md#compound-assignment) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8c1-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a8c1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a8c1-114">See also</span></span>

- [<span data-ttu-id="5a8c1-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5a8c1-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a8c1-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5a8c1-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a8c1-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="5a8c1-117">C# Operators</span></span>](index.md)
