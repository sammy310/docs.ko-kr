---
description: 대입 연산자 - C# 참조
title: 대입 연산자 - C# 참조
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 3df118143b692cc8655de31cce23af41f7da125c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117885"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="0e4a6-103">대입 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0e4a6-103">Assignment operators (C# reference)</span></span>

<span data-ttu-id="0e4a6-104">대입 연산자 `=`은 오른쪽 피연산자의 값을 왼쪽 피연산자가 제공하는 변수, [속성](../../programming-guide/classes-and-structs/properties.md) 또는 [인덱서](../../programming-guide/indexers/index.md) 요소에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-104">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="0e4a6-105">대입식의 결과는 왼쪽 피연산자에 할당된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-105">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="0e4a6-106">오른쪽 피연산자의 형식은 왼쪽 피연산자의 형식과 동일하거나 왼쪽 피연산자의 형식으로 암시적으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-106">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="0e4a6-107">`=` 대입 연산자는 오른쪽 결합성입니다. 즉, 다음 형식의 식을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-107">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="0e4a6-108">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-108">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="0e4a6-109">다음 예제에서는 로컬 변수, 속성 및 인덱서 요소를 왼쪽 피연산자로 포함해서 대입 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-109">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/shared/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="0e4a6-110">ref 대입 연산자</span><span class="sxs-lookup"><span data-stu-id="0e4a6-110">ref assignment operator</span></span>

<span data-ttu-id="0e4a6-111">C# 7.3부터 ref 대입 연산자 `= ref`를 사용하여 [ref 지역](../keywords/ref.md#ref-locals) 또는 [ref readonly 지역](../keywords/ref.md#ref-readonly-locals) 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-111">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="0e4a6-112">다음 예제에서는 ref 대입 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-112">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/shared/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="0e4a6-113">ref 대입 연산자의 경우 양쪽 피연산자의 형식이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-113">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="0e4a6-114">복합 할당</span><span class="sxs-lookup"><span data-stu-id="0e4a6-114">Compound assignment</span></span>

<span data-ttu-id="0e4a6-115">이진 연산자(`op`)의 경우 양식의 복합 할당 식</span><span class="sxs-lookup"><span data-stu-id="0e4a6-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="0e4a6-116">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="0e4a6-117">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="0e4a6-118">복합 할당은 [산술](arithmetic-operators.md#compound-assignment), [부울 논리](boolean-logical-operators.md#compound-assignment), [비트 논리 및 시프트](bitwise-and-shift-operators.md#compound-assignment) 연산자를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="0e4a6-119">null 병합 할당</span><span class="sxs-lookup"><span data-stu-id="0e4a6-119">Null-coalescing assignment</span></span>

<span data-ttu-id="0e4a6-120">C# 8.0부터 null 병합 할당 연산자 `??=`를 사용하여 왼쪽 피연산자가 `null`로 계산되는 경우에만 오른쪽 피연산자의 값을 왼쪽 피연산자에 대입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="0e4a6-121">자세한 내용은 [?? 및 ??= 연산자](null-coalescing-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0e4a6-122">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="0e4a6-122">Operator overloadability</span></span>

<span data-ttu-id="0e4a6-123">사용자 정의 형식은 대입 연산자를 [오버로드](operator-overloading.md)할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-123">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="0e4a6-124">그러나 사용자 정의 형식은 다른 형식으로 암시적 변환을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="0e4a6-125">이렇게 하면 사용자 정의 형식의 값을 다른 형식의 변수, 속성 또는 인덱서 요소에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="0e4a6-126">자세한 내용은 [사용자 정의 변환 연산자](user-defined-conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="0e4a6-127">사용자 정의 형식은 복합 대입 연산자를 명시적으로 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-127">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="0e4a6-128">그러나 사용자 정의 형식이 이항 연산자 `op`를 오버로드하는 경우에는 `op=` 연산자(있는 경우)도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-128">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0e4a6-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0e4a6-129">C# language specification</span></span>

<span data-ttu-id="0e4a6-130">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [대입 연산자](~/_csharplang/spec/expressions.md#assignment-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-130">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0e4a6-131">ref 대입 연산자 `= ref`에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4a6-131">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e4a6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e4a6-132">See also</span></span>

- [<span data-ttu-id="0e4a6-133">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0e4a6-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0e4a6-134">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="0e4a6-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="0e4a6-135">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="0e4a6-135">ref keyword</span></span>](../keywords/ref.md)
