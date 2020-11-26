---
description: is - C# 참조
title: is - C# 참조
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: d30ebfa2dc47265185a96514efbddc3e4937438c
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982396"
---
# <a name="is-c-reference"></a><span data-ttu-id="88ce3-103">is(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="88ce3-103">is (C# Reference)</span></span>

<span data-ttu-id="88ce3-104">`is` 연산자는 식의 결과가 지정된 형식과 호환되는지 확인하거나, (C# 7.0부터) 패턴에 대해 식을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-104">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="88ce3-105">형식 테스트 `is` 연산자에 대한 자세한 내용은 [형식 테스트 및 캐스트 연산자](../operators/type-testing-and-cast.md) 문서의 [is 연산자](../operators/type-testing-and-cast.md#is-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88ce3-105">For information about the type-testing `is` operator, see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="88ce3-106">`is`를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="88ce3-106">Pattern matching with `is`</span></span>

<span data-ttu-id="88ce3-107">C# 7.0부터는 `is` 및 [switch](switch.md) 문에서 패턴 일치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-107">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="88ce3-108">`is` 키워드는 다음과 같은 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-108">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="88ce3-109">[형식 패턴](#type-pattern) - 식을 지정된 형식으로 변환할 수 있는지를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 변수를 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-109">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts the variable to a variable of that type.</span></span>
- <span data-ttu-id="88ce3-110">[상수 패턴](#constant-pattern) - 식이 지정된 상수 값으로 평가되는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-110">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>
- <span data-ttu-id="88ce3-111">[var 패턴](#var-pattern) - 항상 성공하고 식의 값을 새 로컬 변수에 바인딩하는 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-111">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="88ce3-112">형식 패턴</span><span class="sxs-lookup"><span data-stu-id="88ce3-112">Type pattern</span></span>

<span data-ttu-id="88ce3-113">형식 패턴을 사용하여 패턴 일치를 수행하는 경우 `is`는 식을 지정된 형식으로 변환할 수 있는지 여부를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-113">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="88ce3-114">간결한 형식 평가 및 변환을 사용하는 `is` 문의 간단한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-114">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="88ce3-115">`is` 형식 패턴의 일반적인 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-115">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="88ce3-116">여기서 *expr* 은 일부 형식의 인스턴스로 평가되는 식이고 *type* 은 *expr* 의 결과가 변환될 형식의 이름이며 *varname* 은 `is` 테스트가 `true`인 경우 *expr* 의 결과변환가 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-116">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="88ce3-117">*expr* 이 `null`이 아니고 다음 조건 중 하나가 true일 경우 `is` 식은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-117">The `is` expression is `true` if *expr* isn't `null`, and any of the following conditions is true:</span></span>

- <span data-ttu-id="88ce3-118">*expr* 이 *type* 과 동일한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-118">*expr* is an instance of the same type as *type*.</span></span>
- <span data-ttu-id="88ce3-119">*expr* 이 *type* 에서 파생된 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-119">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="88ce3-120">즉, *expr* 의 결과를 *type* 의 인스턴스로 업캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-120">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>
- <span data-ttu-id="88ce3-121">*expr* 의 컴파일 시간 형식은 *type* 의 기본 클래스이고 *expr* 의 런타임 형식은 *type* 이거나 *type* 에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-121">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="88ce3-122">변수의 *컴파일 시간 형식* 은 해당 선언에 정의된 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-122">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="88ce3-123">변수의 *런타임 형식* 은 해당 변수에 할당된 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-123">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>
- <span data-ttu-id="88ce3-124">*expr* 이 *type* 인터페이스를 구현하는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-124">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="88ce3-125">C# 7.1부터 *expr* 은 제네릭 형식 매개 변수 및 해당 제약 조건을 통해 컴파일 시간 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-125">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="88ce3-126">*expr* 이 `true`이고 `is`가 `if` 문에서 사용되는 경우 *varname* 이 `if` 문 내에서만 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-126">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="88ce3-127">*varname* 의 범위는 `is` 식에서부터 `if` 문을 닫는 블록의 끝까지입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-127">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="88ce3-128">다른 위치에서 *varname* 을 사용하면 할당되지 않은 변수 사용에 대해 컴파일 시간 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-128">Using *varname* in any other location generates a compile-time error for use of a variable that hasn't been assigned.</span></span>

<span data-ttu-id="88ce3-129">다음 예제에서는 `is` 형식 패턴을 사용하여 형식의 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 메서드 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-129">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="88ce3-130">패턴 일치를 사용하지 않을 경우 이 코드를 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-130">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="88ce3-131">형식 패턴 일치를 사용하면 변환 결과가 `null`인지 여부를 테스트할 필요가 없으므로 보다 간결하고 읽기 쉬운 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-131">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="88ce3-132">또한 `is` 형식 패턴은 값 형식의 형식을 확인할 때 보다 간결한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-132">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="88ce3-133">다음 예제에서는 `is` 형식 패턴을 사용하여 개체가 `Person` 인스턴스인지 `Dog` 인스턴스인지를 확인한 후 적절한 속성의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-133">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="88ce3-134">패턴 일치를 사용하지 않는 동일한 코드에는 명시적 캐스트를 포함하는 별도의 할당이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-134">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="88ce3-135">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="88ce3-135">Constant pattern</span></span>

<span data-ttu-id="88ce3-136">상수 패턴을 사용한 패턴 일치를 수행하는 경우 `is`는 식이 지정된 상수와 같은지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-136">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="88ce3-137">C# 6 이전 버전에서는 상수 패턴이 [switch](switch.md) 문에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-137">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="88ce3-138">C# 7.0부터는 `is` 문에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-138">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="88ce3-139">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-139">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="88ce3-140">여기서 *expr* 은 평가할 식이고 *constant* 는 테스트할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-140">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="88ce3-141">*constant* 는 다음 상수 식 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-141">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="88ce3-142">리터럴 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-142">A literal value.</span></span>

- <span data-ttu-id="88ce3-143">선언된 `const` 변수의 이름</span><span class="sxs-lookup"><span data-stu-id="88ce3-143">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="88ce3-144">열거형 상수</span><span class="sxs-lookup"><span data-stu-id="88ce3-144">An enumeration constant.</span></span>

<span data-ttu-id="88ce3-145">상수 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-145">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="88ce3-146">*expr* 및 *constant* 가 정수 형식인 경우 C# 같음 연산자는 식에서 `true`를 반환하는지 여부 즉, `expr == constant`인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-146">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="88ce3-147">정수 형식이 아니면 static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 메서드 호출을 통해 식의 값이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-147">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="88ce3-148">다음 예제에서는 형식 패턴과 상수 패턴을 결합하여 개체가 `Dice` 인스턴스인지 여부를 테스트하고, 그럴 경우 주사위 굴리기 값이 6인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-148">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="88ce3-149">상수 패턴을 사용하여 `null`을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-149">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="88ce3-150">`null` 키워드는 `is` 문에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-150">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="88ce3-151">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-151">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="88ce3-152">다음 예제는 `null` 검사의 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-152">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

<span data-ttu-id="88ce3-153">`x is null` 식은 참조 형식 및 null 허용 값 형식에 대해 다르게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-153">The expression `x is null` is computed differently for reference types and nullable value types.</span></span> <span data-ttu-id="88ce3-154">null 허용 값 형식의 경우 <xref:System.Nullable%601.HasValue?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-154">For nullable value types, it uses <xref:System.Nullable%601.HasValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="88ce3-155">참조 형식의 경우 `(object)x == null`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-155">For reference types, it uses `(object)x == null`.</span></span>

### <a name="var-pattern"></a><span data-ttu-id="88ce3-156">var 패턴</span><span class="sxs-lookup"><span data-stu-id="88ce3-156">var pattern</span></span>

<span data-ttu-id="88ce3-157">`var` 패턴을 사용한 패턴 일치는 항상 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-157">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="88ce3-158">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-158">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="88ce3-159">여기서 *expr* 의 값은 항상 *varname* 이라는 지역 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-159">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="88ce3-160">*varname* 은 컴파일 시간 형식의 *expr* 과 동일한 형식의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-160">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="88ce3-161">*expr* 이 `null`로 평가되는 경우 `is` 식은 `true`를 생성하고 *varname* 에 `null`을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-161">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="88ce3-162">var 패턴은 `null` 값에 대해 `true`를 생성하는 흔치 않은 `is` 용도 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-162">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="88ce3-163">다음 예와 같이 `var` 패턴을 사용하여 부울 식 내에 임시 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-163">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="88ce3-164">앞의 예에서 임시 변수는 비용이 많이 드는 작업의 결과를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-164">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="88ce3-165">그런 다음 변수를 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ce3-165">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="88ce3-166">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="88ce3-166">C# language specification</span></span>
  
<span data-ttu-id="88ce3-167">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [s 연산자](~/_csharplang/spec/expressions.md#the-is-operator) 섹션과 다음 C# 언어 제안을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88ce3-167">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="88ce3-168">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="88ce3-168">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="88ce3-169">제네릭과 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="88ce3-169">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="88ce3-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88ce3-170">See also</span></span>

- [<span data-ttu-id="88ce3-171">C# 참조</span><span class="sxs-lookup"><span data-stu-id="88ce3-171">C# reference</span></span>](../index.md)
- [<span data-ttu-id="88ce3-172">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="88ce3-172">C# keywords</span></span>](index.md)
- [<span data-ttu-id="88ce3-173">형식 테스트 및 캐스트 연산자</span><span class="sxs-lookup"><span data-stu-id="88ce3-173">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
