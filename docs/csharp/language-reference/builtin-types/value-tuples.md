---
title: 튜플 형식 - C# 참조
description: 'C# 튜플 알아보기: 관련 데이터 요소를 느슨하게 그룹화하는 데 사용할 수 있는 간단한 데이터 구조'
ms.date: 07/09/2020
helpviewer_keywords:
- value tuples [C#]
ms.openlocfilehash: 3d79ab19117847e2364b154db33a1521416bb3f4
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174978"
---
# <a name="tuple-types-c-reference"></a><span data-ttu-id="ce060-103">튜플 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ce060-103">Tuple types (C# reference)</span></span>

<span data-ttu-id="ce060-104">C# 7.0 이상에서 사용할 수 있는 ‘튜플’ 기능은 간단한 데이터 구조로 여러 데이터 요소를 그룹화하는 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-104">Available in C# 7.0 and later, the *tuples* feature provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="ce060-105">다음 예제에서는 튜플 변수를 선언하고 초기화하며 관련 데이터 멤버에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-105">The following example shows how you can declare a tuple variable, initialize it, and access its data members:</span></span>

[!code-csharp-interactive[tuple intro](snippets/ValueTuples.cs#Introduction)]

<span data-ttu-id="ce060-106">앞의 예제와 같이 튜플 형식을 정의하려면 모든 관련 데이터 멤버의 형식과 필요한 경우 [필드 이름](#tuple-field-names)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-106">As the preceding example shows, to define a tuple type, you specify types of all its data members and, optionally, the [field names](#tuple-field-names).</span></span> <span data-ttu-id="ce060-107">튜플 형식으로 메서드를 정의할 수는 없지만 다음 예제와 같이 .NET에서 제공하는 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-107">You cannot define methods in a tuple type, but you can use the methods provided by .NET, as the following example shows:</span></span>

[!code-csharp-interactive[tuple methods](snippets/ValueTuples.cs#MethodOnTuples)]

<span data-ttu-id="ce060-108">C# 7.3부터 튜플 형식은 [같음 연산자](../operators/equality-operators.md) `==` 및 `!=`을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-108">Beginning with C# 7.3, tuple types support [equality operators](../operators/equality-operators.md) `==` and `!=`.</span></span> <span data-ttu-id="ce060-109">자세한 내용은 [튜플 같음](#tuple-equality) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce060-109">For more information, see the [Tuple equality](#tuple-equality) section.</span></span>

<span data-ttu-id="ce060-110">튜플 형식은 [값 형식](value-types.md)이며 튜플 요소는 공용 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-110">Tuple types are [value types](value-types.md); tuple elements are public fields.</span></span> <span data-ttu-id="ce060-111">이에 따라 튜플은 ‘변경 가능한’ 값 형식으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-111">That makes tuples *mutable* value types.</span></span>

> [!NOTE]
> <span data-ttu-id="ce060-112">튜플 기능을 사용하려면 .NET Core 및 .NET Framework 4.7 이상에서 사용할 수 있는 <xref:System.ValueTuple?displayProperty=nameWithType> 형식 및 관련 제네릭 형식(예: <xref:System.ValueTuple%602?displayProperty=nameWithType>)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-112">The tuples feature requires the <xref:System.ValueTuple?displayProperty=nameWithType> type and related generic types (for example, <xref:System.ValueTuple%602?displayProperty=nameWithType>), which are available in .NET Core and .NET Framework 4.7 and later.</span></span> <span data-ttu-id="ce060-113">.NET Framework 4.6.2 이하를 대상으로 하는 프로젝트에서 튜플을 사용하려면 프로젝트에 NuGet 패키지 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-113">To use tuples in a project that targets .NET Framework 4.6.2 or earlier, add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) to the project.</span></span>

<span data-ttu-id="ce060-114">임의의 많은 요소를 포함하는 튜플을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-114">You can define tuples with an arbitrary large number of elements:</span></span>

[!code-csharp-interactive[large tuple](snippets/ValueTuples.cs#LargeTuple)]

## <a name="use-cases-of-tuples"></a><span data-ttu-id="ce060-115">튜플 사용 사례</span><span class="sxs-lookup"><span data-stu-id="ce060-115">Use cases of tuples</span></span>

<span data-ttu-id="ce060-116">튜플의 가장 일반적인 사용 사례 중 하나는 메서드 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-116">One of the most common use cases of tuples is as a method return type.</span></span> <span data-ttu-id="ce060-117">즉, [`out` 메서드 매개 변수](../keywords/out-parameter-modifier.md)를 정의하는 대신 다음 예제와 같이 메서드 결과를 튜플 반환 형식으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-117">That is, instead of defining [`out` method parameters](../keywords/out-parameter-modifier.md), you can group method results in a tuple return type, as the following example shows:</span></span>

[!code-csharp-interactive[multiple method outputs](snippets/ValueTuples.cs#MultipleReturns)]

<span data-ttu-id="ce060-118">앞의 예제와 같이 반환된 튜플 인스턴스를 직접 사용하거나 개별 변수로 [분해](#tuple-assignment-and-deconstruction)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-118">As the preceding example shows, you can work with the returned tuple instance directly or [deconstruct](#tuple-assignment-and-deconstruction) it in separate variables.</span></span>

<span data-ttu-id="ce060-119">[익명 형식](../../programming-guide/classes-and-structs/anonymous-types.md) 대신 튜플 형식을 사용할 수도 있습니다(예: LINQ 쿼리에서).</span><span class="sxs-lookup"><span data-stu-id="ce060-119">You can also use tuple types instead of [anonymous types](../../programming-guide/classes-and-structs/anonymous-types.md); for example, in LINQ queries.</span></span> <span data-ttu-id="ce060-120">자세한 내용은 [무명 형식과 튜플 형식 중에서 선택](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce060-120">For more information, see [Choosing between anonymous and tuple types](../../../standard/base-types/choosing-between-anonymous-and-tuple.md).</span></span>

<span data-ttu-id="ce060-121">일반적으로 튜플을 사용하여 관련 데이터 요소를 느슨하게 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-121">Typically, you use tuples to group loosely related data elements.</span></span> <span data-ttu-id="ce060-122">이 방법은 대개 프라이빗 및 내부 유틸리티 메서드 내에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-122">That is usually useful within private and internal utility methods.</span></span> <span data-ttu-id="ce060-123">공용 API의 경우 [클래스](../keywords/class.md) 또는 [구조체](struct.md) 형식을 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-123">In the case of public API, consider defining a [class](../keywords/class.md) or a [structure](struct.md) type.</span></span>

## <a name="tuple-field-names"></a><span data-ttu-id="ce060-124">튜플 필드 이름</span><span class="sxs-lookup"><span data-stu-id="ce060-124">Tuple field names</span></span>

<span data-ttu-id="ce060-125">다음 예제와 같이 튜플 초기화 식이나 튜플 형식 정의에 튜플 필드의 이름을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-125">You can explicitly specify the names of tuple fields either in a tuple initialization expression or in the definition of a tuple type, as the following example shows:</span></span>

[!code-csharp-interactive[explicit field names](snippets/ValueTuples.cs#ExplicitFieldNames)]

<span data-ttu-id="ce060-126">C# 7.1부터는 필드 이름을 지정하지 않으면 다음 예제와 같이 튜플 초기화 식의 해당 변수 이름에서 이름이 유추될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-126">Beginning with C# 7.1, if you don't specify a field name, it may be inferred from the name of the corresponding variable in a tuple initialization expression, as the following example shows:</span></span>

[!code-csharp-interactive[inferred field names](snippets/ValueTuples.cs#InferFieldNames)]

<span data-ttu-id="ce060-127">이를 튜플 프로젝션 이니셜라이저라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-127">That's known as tuple projection initializers.</span></span> <span data-ttu-id="ce060-128">다음과 같은 경우에 변수 이름은 튜플 필드 이름으로 프로젝션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-128">The name of a variable isn't projected onto a tuple field name in the following cases:</span></span>

- <span data-ttu-id="ce060-129">후보 이름이 튜플 형식의 멤버 이름인 경우(예: `Item3`, `ToString` 또는 `Rest`)</span><span class="sxs-lookup"><span data-stu-id="ce060-129">The candidate name is a member name of a tuple type, for example, `Item3`, `ToString`, or `Rest`.</span></span>
- <span data-ttu-id="ce060-130">후보 이름이 명시적이든 암시적이든 다른 튜플 필드 이름과 중복되는 경우</span><span class="sxs-lookup"><span data-stu-id="ce060-130">The candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="ce060-131">이 경우 명시적으로 필드 이름을 지정하거나 기본 이름으로 필드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-131">In those cases you either explicitly specify the name of a field or access a field by its default name.</span></span>

<span data-ttu-id="ce060-132">튜플 필드의 기본 이름은 `Item1`, `Item2`, `Item3` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-132">The default names of tuple fields are `Item1`, `Item2`, `Item3` and so on.</span></span> <span data-ttu-id="ce060-133">다음 예제와 같이 필드 이름이 명시적으로 지정되거나 유추되는 경우에도 언제든지 필드의 기본 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-133">You can always use the default name of a field, even when a field name is specified explicitly or inferred, as the following example shows:</span></span>

[!code-csharp-interactive[default field names](snippets/ValueTuples.cs#DefaultFieldNames)]

<span data-ttu-id="ce060-134">[튜플 할당](#tuple-assignment-and-deconstruction) 및 [튜플 같음 비교](#tuple-equality)에서는 필드 이름을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-134">[Tuple assignment](#tuple-assignment-and-deconstruction) and [tuple equality comparisons](#tuple-equality) don't take field names into account.</span></span>

<span data-ttu-id="ce060-135">컴파일 시간에 컴파일러는 기본값이 아닌 필드 이름을 해당하는 기본 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-135">At compile time, the compiler replaces non-default field names with the corresponding default names.</span></span> <span data-ttu-id="ce060-136">따라서 명시적으로 지정되거나 유추된 필드 이름을 런타임에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-136">As a result, explicitly specified or inferred field names aren't available at run time.</span></span>

## <a name="tuple-assignment-and-deconstruction"></a><span data-ttu-id="ce060-137">튜플 할당 및 분해</span><span class="sxs-lookup"><span data-stu-id="ce060-137">Tuple assignment and deconstruction</span></span>

<span data-ttu-id="ce060-138">C#은 다음 두 조건을 모두 충족하는 튜플 형식 간에 할당을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-138">C# supports assignment between tuple types that satisfy both of the following conditions:</span></span>

- <span data-ttu-id="ce060-139">두 튜플 형식의 요소 수가 동일함</span><span class="sxs-lookup"><span data-stu-id="ce060-139">both tuple types have the same number of elements</span></span>
- <span data-ttu-id="ce060-140">각 튜플 위치에서 오른쪽 튜플 요소의 형식이 해당하는 왼쪽 튜플 요소의 형식과 동일하거나 해당 형식으로 암시적으로 변환 가능함</span><span class="sxs-lookup"><span data-stu-id="ce060-140">for each tuple position, the type of the right-hand tuple element is the same as or implicitly convertible to the type of the corresponding left-hand tuple element</span></span>

<span data-ttu-id="ce060-141">튜플 요소 값은 튜플 요소의 순서에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-141">Tuple element values are assigned following the order of tuple elements.</span></span> <span data-ttu-id="ce060-142">다음 예제와 같이 튜플 필드의 이름은 무시되고 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-142">The names of tuple fields are ignored and not assigned, as the following example shows:</span></span>

[!code-csharp-interactive[tuple assignment](snippets/ValueTuples.cs#Assignment)]

<span data-ttu-id="ce060-143">`=` 대입 연산자를 사용하여 튜플 인스턴스를 개별 변수로 ‘분해’할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-143">You can also use the assignment operator `=` to *deconstruct* a tuple instance in separate variables.</span></span> <span data-ttu-id="ce060-144">다음 중 한 가지 방법으로 해당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-144">You can do that in one of the following ways:</span></span>

- <span data-ttu-id="ce060-145">괄호 안에 각 변수의 형식을 명시적으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-145">Explicitly declare the type of each variable inside parentheses:</span></span>

  [!code-csharp-interactive[specify types of variables](snippets/ValueTuples.cs#DeconstructExplicit)]

- <span data-ttu-id="ce060-146">괄호 밖에서 `var` 키워드를 사용하여 형식화된 변수를 암시적으로 선언하며 컴파일러가 해당 형식을 유추하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-146">Use the `var` keyword outside the parentheses to declare implicitly typed variables and let the compiler infer their types:</span></span>

  [!code-csharp-interactive[implicitly typed variables](snippets/ValueTuples.cs#DeconstructVar)]

- <span data-ttu-id="ce060-147">기존 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-147">Use existing variables:</span></span>

  [!code-csharp-interactive[existing variables](snippets/ValueTuples.cs#DeconstructExisting)]

<span data-ttu-id="ce060-148">튜플 및 기타 형식을 분해하는 방법에 관한 자세한 내용은 [튜플 및 기타 형식 분해](../../deconstruct.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce060-148">For more information about deconstruction of tuples and other types, see [Deconstructing tuples and other types](../../deconstruct.md).</span></span>

## <a name="tuple-equality"></a><span data-ttu-id="ce060-149">튜플 같음</span><span class="sxs-lookup"><span data-stu-id="ce060-149">Tuple equality</span></span>

<span data-ttu-id="ce060-150">C# 7.3부터 튜플 형식에서는 `==` 및 `!=` 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-150">Beginning with C# 7.3, tuple types support the `==` and `!=` operators.</span></span> <span data-ttu-id="ce060-151">해당 연산자는 튜플 요소 순서에 따라 왼쪽 피연산자의 멤버를 오른쪽 피연산자의 해당 멤버와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-151">These operators compare members of the left-hand operand with the corresponding members of the right-hand operand following the order of tuple elements.</span></span>

[!code-csharp-interactive[tuple equality](snippets/ValueTuples.cs#TupleEquality)]

<span data-ttu-id="ce060-152">앞의 예제와 같이 `==` 및 `!=` 연산에는 튜플 필드 이름이 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-152">As the preceding example shows, the `==` and `!=` operations don't take into account tuple field names.</span></span>

<span data-ttu-id="ce060-153">다음 조건이 둘 다 충족되면 두 튜플을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-153">Two tuples are comparable when both of the following conditions are satisfied:</span></span>

- <span data-ttu-id="ce060-154">두 튜플의 요소 수가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-154">Both tuples have the same number of elements.</span></span> <span data-ttu-id="ce060-155">예를 들어 `t1` 및 `t2`의 요소 수가 다른 경우 `t1 != t2`는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-155">For example, `t1 != t2` doesn't compile if `t1` and `t2` have different numbers of elements.</span></span>
- <span data-ttu-id="ce060-156">각 튜플 위치에서 왼쪽 및 오른쪽 튜플 피연산자의 해당 요소는 `==` 및 `!=` 연산자와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-156">For each tuple position, the corresponding elements from the left-hand and right-hand tuple operands are comparable with the `==` and `!=` operators.</span></span> <span data-ttu-id="ce060-157">예를 들어 `1`은 `(1, 2)`와 비교할 수 없기 때문에 `(1, (2, 3)) == ((1, 2), 3)`은 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-157">For example, `(1, (2, 3)) == ((1, 2), 3)` doesn't compile because `1` is not comparable with `(1, 2)`.</span></span>

<span data-ttu-id="ce060-158">`==` 및 `!=` 연산자는 단락(short-circuiting) 방식으로 튜플을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-158">The `==` and `!=` operators compare tuples in short-circuiting way.</span></span> <span data-ttu-id="ce060-159">즉, 같지 않은 요소 쌍을 충족하거나 튜플의 끝에 도달하는 즉시 연산이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-159">That is, an operation stops as soon as it meets a pair of non equal elements or reaches the ends of tuples.</span></span> <span data-ttu-id="ce060-160">그러나 다음 예제와 같이 비교하기 전에 ‘모든’ 튜플 요소가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-160">However, before any comparison, *all* tuple elements are evaluated, as the following example shows:</span></span>

[!code-csharp-interactive[tuple element evaluation](snippets/ValueTuples.cs#TupleEvaluationForEquality)]

## <a name="tuples-as-out-parameters"></a><span data-ttu-id="ce060-161">출력 매개 변수 튜플</span><span class="sxs-lookup"><span data-stu-id="ce060-161">Tuples as out parameters</span></span>

<span data-ttu-id="ce060-162">일반적으로 [`out` 매개 변수](../keywords/out-parameter-modifier.md)를 포함하는 메서드는 튜플을 반환하는 메서드로 리팩터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-162">Typically, you refactor a method that has [`out` parameters](../keywords/out-parameter-modifier.md) into a method that returns a tuple.</span></span> <span data-ttu-id="ce060-163">그러나 `out` 매개 변수가 튜플 형식일 수 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-163">However, there are cases in which an `out` parameter can be of a tuple type.</span></span> <span data-ttu-id="ce060-164">다음 예제에서는 튜플을 `out` 매개 변수로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-164">The following example shows how to work with tuples as `out` parameters:</span></span>

[!code-csharp-interactive[tuple as out parameter](snippets/ValueTuples.cs#TupleAsOutParameter)]

## <a name="tuples-vs-systemtuple"></a><span data-ttu-id="ce060-165">튜플과 `System.Tuple` 비교</span><span class="sxs-lookup"><span data-stu-id="ce060-165">Tuples vs `System.Tuple`</span></span>

<span data-ttu-id="ce060-166"><xref:System.ValueTuple?displayProperty=nameWithType> 형식으로 지원되는 C# 튜플은 <xref:System.Tuple?displayProperty=nameWithType> 형식으로 표현되는 튜플과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-166">C# tuples, which are backed by <xref:System.ValueTuple?displayProperty=nameWithType> types, are different from tuples that are represented by <xref:System.Tuple?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="ce060-167">주요 차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-167">The main differences are as follows:</span></span>

- <span data-ttu-id="ce060-168">`ValueTuple` 형식은 [값 형식](value-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-168">`ValueTuple` types are [value types](value-types.md).</span></span> <span data-ttu-id="ce060-169">`Tuple` 형식은 [참조 형식](../keywords/reference-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-169">`Tuple` types are [reference types](../keywords/reference-types.md).</span></span>
- <span data-ttu-id="ce060-170">`ValueTuple` 형식은 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-170">`ValueTuple` types are mutable.</span></span> <span data-ttu-id="ce060-171">`Tuple` 형식은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-171">`Tuple` types are immutable.</span></span>
- <span data-ttu-id="ce060-172">`ValueTuple` 형식의 데이터 멤버는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-172">Data members of `ValueTuple` types are fields.</span></span> <span data-ttu-id="ce060-173">`Tuple` 형식의 데이터 멤버는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ce060-173">Data members of `Tuple` types are properties.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ce060-174">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ce060-174">C# language specification</span></span>

<span data-ttu-id="ce060-175">자세한 내용은 다음 기능 제안 노트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce060-175">For more information, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="ce060-176">튜플 이름 유추(즉, 튜플 프로젝션 이니셜라이저)</span><span class="sxs-lookup"><span data-stu-id="ce060-176">Infer tuple names (aka. tuple projection initializers)</span></span>](~/_csharplang/proposals/csharp-7.1/infer-tuple-names.md)
- [<span data-ttu-id="ce060-177">튜플 형식에서 `==` 및 `!=` 지원</span><span class="sxs-lookup"><span data-stu-id="ce060-177">Support for `==` and `!=` on tuple types</span></span>](~/_csharplang/proposals/csharp-7.3/tuple-equality.md)

## <a name="see-also"></a><span data-ttu-id="ce060-178">참조</span><span class="sxs-lookup"><span data-stu-id="ce060-178">See also</span></span>

- [<span data-ttu-id="ce060-179">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ce060-179">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ce060-180">값 형식</span><span class="sxs-lookup"><span data-stu-id="ce060-180">Value types</span></span>](value-types.md)
- [<span data-ttu-id="ce060-181">무명 형식과 튜플 형식 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="ce060-181">Choosing between anonymous and tuple types</span></span>](../../../standard/base-types/choosing-between-anonymous-and-tuple.md)
- <xref:System.ValueTuple?displayProperty=nameWithType>
