---
title: 멤버 액세스 연산자 - C# 참조
description: 형식 멤버에 액세스하는 데 사용하는 C# 연산자에 대해 알아봅니다.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 921d69e3deb7e5bb5115eb723727462839af9b6b
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452895"
---
# <a name="member-access-operators"></a><span data-ttu-id="8e18d-103">멤버 액세스 연산자</span><span class="sxs-lookup"><span data-stu-id="8e18d-103">Member access operators</span></span>

<span data-ttu-id="8e18d-104">형식 멤버에 액세스할 때 다음과 같은 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="8e18d-105">[`.` (멤버 액세스)](#member-access-operator-): 네임스페이스 또는 형식의 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="8e18d-106">[`[]` (배열 요소 또는 인덱서 액세스)](#indexer-operator-): 배열 요소 또는 형식 인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="8e18d-107">[`?.` 및 `?[]`(null 조건부 연산자)](#null-conditional-operators--and-): 피연산자가 null이 아닌 경우에만 멤버 또는 요소 액세스 작업 수행</span><span class="sxs-lookup"><span data-stu-id="8e18d-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="8e18d-108">[`()` (호출)](#invocation-operator-): 액세스된 메서드나 대리자 호출</span><span class="sxs-lookup"><span data-stu-id="8e18d-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="8e18d-109">멤버 액세스 연산자</span><span class="sxs-lookup"><span data-stu-id="8e18d-109">Member access operator .</span></span>

<span data-ttu-id="8e18d-110">다음 예제와 같이 `.` 토큰을 사용하여 네임스페이스 또는 형식의 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="8e18d-111">[ `using` 지시문](../keywords/using-directive.md)의 다음 예제와 같이 `.`을 사용하여 네임스페이스 내에 중첩된 네임스페이스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="8e18d-112">다음 코드와 같이 `.`을 사용하여 ‘정규화된 이름’을 만들고 네임스페이스 내의 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="8e18d-113">[`using` 지시문](../keywords/using-directive.md)을 사용하여 정규화된 이름 사용을 선택 사항으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="8e18d-114">다음 코드와 같이 `.`을 사용하여 정적 및 비정적 [형식 멤버](../../programming-guide/classes-and-structs/index.md#members)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="8e18d-115">`.`을 사용하여 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="8e18d-116">인덱서 연산자 []</span><span class="sxs-lookup"><span data-stu-id="8e18d-116">Indexer operator []</span></span>

<span data-ttu-id="8e18d-117">대괄호 `[]`는 일반적으로 배열, 인덱서 또는 포인터 요소 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="8e18d-118">배열 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-118">Array access</span></span>

<span data-ttu-id="8e18d-119">다음 예제는 배열 요소에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="8e18d-120">배열 인덱스가 배열의 해당 차원 범위를 벗어난 경우 <xref:System.IndexOutOfRangeException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="8e18d-121">앞의 예제와 같이, 배열 형식을 선언하거나 배열 인스턴스를 인스턴스화할 때도 대괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="8e18d-122">배열에 대한 자세한 내용은 [배열](../../programming-guide/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="8e18d-123">인덱서 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-123">Indexer access</span></span>

<span data-ttu-id="8e18d-124">다음 예제는 .NET <xref:System.Collections.Generic.Dictionary%602> 형식을 사용하여 인덱서 액세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="8e18d-125">인덱서를 사용하면 배열 인덱싱과 비슷한 방법으로 사용자 정의 형식의 인스턴스를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="8e18d-126">정수여야 하는 배열 인덱스와 달리, 인덱서 인수는 임의 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="8e18d-127">인덱서에 대한 자세한 내용은 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="8e18d-128">다른 [] 용도</span><span class="sxs-lookup"><span data-stu-id="8e18d-128">Other usages of []</span></span>

<span data-ttu-id="8e18d-129">포인터 요소 액세스에 대한 자세한 내용은 [방법: 포인터를 사용하여 배열 요소 액세스](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-129">For information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="8e18d-130">또한 대괄호를 사용하여 [특성](../../programming-guide/concepts/attributes/index.md)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="8e18d-131">Null 조건부 연산자 ?.</span><span class="sxs-lookup"><span data-stu-id="8e18d-131">Null-conditional operators ?.</span></span> <span data-ttu-id="8e18d-132">및 ?[]</span><span class="sxs-lookup"><span data-stu-id="8e18d-132">and ?[]</span></span>

<span data-ttu-id="8e18d-133">C# 6 이상에서 사용할 수 있는 null 조건부 연산자는 피연산자가 null이 아닌 것으로 평가되었을 때만 멤버 액세스 `?.`, 또는 요소 액세스 `?[]` 연산을 피연산자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="8e18d-134">피연산자가 `null`로 평가되면 연산자 적용 결과가 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span>

<span data-ttu-id="8e18d-135">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-135">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="8e18d-136">즉 조건부 멤버나 요소 액세스 작업의 한 체인의 작업에서 `null`을 반환하면 나머지 체인은 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-136">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="8e18d-137">다음 예제에서 `A`가 `null`로 평가되면 `B`가 평가되지 않고, `A` 또는 `B`가 `null`로 평가되면 `C`가 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-137">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="8e18d-138">다음 예제에서는 `?.` 및 `?[]` 연산자의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-138">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="8e18d-139">위의 예제에서는 [null 병합 연산자](null-coalescing-operator.md)의 사용법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-139">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="8e18d-140">null 병합 연산자를 사용하여 null 조건부 연산 결과가 `null`인 경우 평가하는 대체 식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-140">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="8e18d-141">스레드로부터 안전한 대리자 호출</span><span class="sxs-lookup"><span data-stu-id="8e18d-141">Thread-safe delegate invocation</span></span>

<span data-ttu-id="8e18d-142">다음 코드에서처럼 `?.` 연산자를 사용하여 대리자가 null이 아닌지 확인하고 스레드로부터 안전한 방식으로 호출합니다(예: [이벤트 발생 시](../../../standard/events/how-to-raise-and-consume-events.md)).</span><span class="sxs-lookup"><span data-stu-id="8e18d-142">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="8e18d-143">이 코드는 C# 5 및 그 이전에서 사용하는 다음 코드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-143">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="8e18d-144">호출 연산자()</span><span class="sxs-lookup"><span data-stu-id="8e18d-144">Invocation operator ()</span></span>

<span data-ttu-id="8e18d-145">괄호(`()`)를 사용하여 [메서드](../../programming-guide/classes-and-structs/methods.md) 또는 [대리자](../../programming-guide/delegates/index.md)를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-145">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="8e18d-146">다음 예제는 인수를 사용하거나 사용하지 않고 메서드를 호출하는 방법과 대리자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-146">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="8e18d-147">[`new`](../keywords/new-operator.md) 연산자를 사용하여 [생성자](../../programming-guide/classes-and-structs/constructors.md)를 호출하는 경우에도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-147">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="8e18d-148">다른 () 용도</span><span class="sxs-lookup"><span data-stu-id="8e18d-148">Other usages of ()</span></span>

<span data-ttu-id="8e18d-149">또한 괄호를 사용하여 식에서 연산을 계산하는 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-149">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="8e18d-150">자세한 내용은 [연산자](../../programming-guide/statements-expressions-operators/operators.md) 문서의 [괄호 추가](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-150">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="8e18d-151">우선 순위 수준에 따라 정렬된 연산자 목록은 [C# 연산자](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-151">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="8e18d-152">전환 연산자를 호출하는 [캐스트 식](invocation-operator.md#cast-expression)도 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-152">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8e18d-153">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="8e18d-153">Operator overloadability</span></span>

<span data-ttu-id="8e18d-154">`.` 및 `()` 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-154">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="8e18d-155">`[]` 연산자도 오버로드할 수 없는 연산자로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-155">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="8e18d-156">[인덱서](../../programming-guide/indexers/index.md)를 사용하여 사용자 정의 형식의 인덱싱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8e18d-156">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8e18d-157">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8e18d-157">C# language specification</span></span>

<span data-ttu-id="8e18d-158">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e18d-158">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="8e18d-159">멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-159">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="8e18d-160">요소 액세스</span><span class="sxs-lookup"><span data-stu-id="8e18d-160">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="8e18d-161">Null 조건부 연산자</span><span class="sxs-lookup"><span data-stu-id="8e18d-161">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="8e18d-162">호출 식</span><span class="sxs-lookup"><span data-stu-id="8e18d-162">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="8e18d-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e18d-163">See also</span></span>

- [<span data-ttu-id="8e18d-164">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8e18d-164">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8e18d-165">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8e18d-165">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8e18d-166">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8e18d-166">C# Operators</span></span>](index.md)
- [<span data-ttu-id="8e18d-167">??(Null 병합 연산자)</span><span class="sxs-lookup"><span data-stu-id="8e18d-167">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
