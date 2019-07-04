---
title: = 연산자 - C# 참조
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: ef9c9bab5c1cebb06edf934254507180e2197349
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306563"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b688f-102">= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b688f-102">= operator (C# reference)</span></span>

<span data-ttu-id="b688f-103">대입 연산자 `=`은 오른쪽 피연산자의 값을 왼쪽 피연산자가 제공하는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 또는 [인덱서](../../../csharp/programming-guide/indexers/index.md) 요소에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="b688f-104">대입식의 결과는 왼쪽 피연산자에 할당된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="b688f-105">오른쪽 피연산자의 형식은 왼쪽 피연산자의 형식과 동일하거나 왼쪽 피연산자의 형식으로 암시적으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="b688f-106">대입 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b688f-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="b688f-107">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="b688f-108">다음 예제에서는 로컬 변수, 속성 및 인덱서 요소를 왼쪽 피연산자로 포함해서 대입 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="b688f-109">ref 대입 연산자</span><span class="sxs-lookup"><span data-stu-id="b688f-109">ref assignment operator</span></span>

<span data-ttu-id="b688f-110">C# 7.3부터 ref 대입 연산자 `= ref`를 사용하여 [ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="b688f-111">다음 예제에서는 ref 대입 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="b688f-112">ref 대입 연산자의 경우 양쪽 피연산자의 형식이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="b688f-113">자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b688f-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="b688f-114">복합 할당</span><span class="sxs-lookup"><span data-stu-id="b688f-114">Compound assignment</span></span>

<span data-ttu-id="b688f-115">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="b688f-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="b688f-116">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="b688f-117">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="b688f-118">복합 할당은 [산술](arithmetic-operators.md#compound-assignment), [부울 논리](boolean-logical-operators.md#compound-assignment), [비트 논리 및 시프트](bitwise-and-shift-operators.md#compound-assignment) 연산자를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b688f-119">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="b688f-119">Operator overloadability</span></span>

<span data-ttu-id="b688f-120">사용자 정의 형식은 대입 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-120">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="b688f-121">그러나 사용자 정의 형식은 다른 형식으로 암시적 변환을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-121">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="b688f-122">이렇게 하면 사용자 정의 형식의 값을 다른 형식의 변수, 속성 또는 인덱서 요소에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b688f-122">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="b688f-123">자세한 내용은 [implicit](../keywords/implicit.md) 키워드 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b688f-123">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b688f-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b688f-124">C# language specification</span></span>

<span data-ttu-id="b688f-125">자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [대입 연산자](~/_csharplang/spec/expressions.md#assignment-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b688f-125">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b688f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b688f-126">See also</span></span>

- [<span data-ttu-id="b688f-127">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b688f-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b688f-128">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b688f-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="b688f-129">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="b688f-129">ref keyword</span></span>](../keywords/ref.md)
