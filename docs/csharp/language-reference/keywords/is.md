---
title: is - C# 참조
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 1a1f539e80f8d843f40640fa798cf6122f316a9f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715235"
---
# <a name="is-c-reference"></a><span data-ttu-id="dcea7-102">is(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dcea7-102">is (C# Reference)</span></span>

<span data-ttu-id="dcea7-103">`is` 연산자는 식의 결과가 지정된 형식과 호환되는지 확인하거나, (C# 7.0부터) 패턴에 대해 식을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="dcea7-104">형식 테스트 `is` 연산자에 대한 자세한 내용은 [형식 테스트 및 캐스트 연산자](../operators/type-testing-and-cast.md) 문서의 [is 연산자](../operators/type-testing-and-cast.md#is-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcea7-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="dcea7-105">`is`를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="dcea7-105">Pattern matching with `is`</span></span>

<span data-ttu-id="dcea7-106">C# 7.0부터는 `is` 및 [switch](switch.md) 문에서 패턴 일치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="dcea7-107">`is` 키워드는 다음과 같은 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="dcea7-108">[형식 패턴](#type-pattern) - 식을 지정된 형식으로 변환할 수 있는지를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="dcea7-109">[상수 패턴](#constant-pattern) - 식이 지정된 상수 값으로 평가되는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="dcea7-110">[var 패턴](#var-pattern) - 항상 성공하고 식의 값을 새 로컬 변수에 바인딩하는 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="dcea7-111">형식 패턴</span><span class="sxs-lookup"><span data-stu-id="dcea7-111">Type pattern</span></span>

<span data-ttu-id="dcea7-112">형식 패턴을 사용하여 패턴 일치를 수행하는 경우 `is`는 식을 지정된 형식으로 변환할 수 있는지 여부를 테스트하고, 변환할 수 있으면 해당 형식의 변수로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="dcea7-113">간결한 형식 평가 및 변환을 사용하는 `is` 문의 간단한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="dcea7-114">`is` 형식 패턴의 일반적인 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="dcea7-115">여기서 *expr*은 일부 형식의 인스턴스로 평가되는 식이고 *type*은 *expr*의 결과가 변환될 형식의 이름이며 *varname*은 `is` 테스트가 `true`인 경우 *expr*의 결과가 변환되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-115">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="dcea7-116">*expr*이 `null`이 아니고 다음 중 하나가 true일 경우 `is` 식은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="dcea7-117">*expr*이 *type*과 동일한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="dcea7-118">*expr*이 *type*에서 파생된 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="dcea7-119">즉, *expr*의 결과를 *type*의 인스턴스로 업캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="dcea7-120">*expr*의 컴파일 시간 형식은 *type*의 기본 클래스이고 *expr*의 런타임 형식은 *type*이거나 *type*에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="dcea7-121">변수의 *컴파일 시간 형식*은 해당 선언에 정의된 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="dcea7-122">변수의 *런타임 형식*은 해당 변수에 할당된 인스턴스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="dcea7-123">*expr*이 *type* 인터페이스를 구현하는 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="dcea7-124">C# 7.1부터 *expr*은 제네릭 형식 매개 변수 및 해당 제약 조건을 통해 컴파일 시간 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="dcea7-125">*expr*이 `true`이고 `is`가 `if` 문에서 사용되는 경우 *varname*이 `if` 문 내에서만 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="dcea7-126">*varname*의 범위는 `is` 식에서부터 `if` 문을 닫는 블록의 끝까지입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="dcea7-127">다른 위치에서 *varname*을 사용하여 할당되지 않은 변수 사용에 대한 컴파일 시간 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="dcea7-128">다음 예제에서는 `is` 형식 패턴을 사용하여 형식의 <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> 메서드 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="dcea7-129">패턴 일치를 사용하지 않을 경우 이 코드를 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="dcea7-130">형식 패턴 일치를 사용하면 변환 결과가 `null`인지 여부를 테스트할 필요가 없으므로 보다 간결하고 읽기 쉬운 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="dcea7-131">또한 `is` 형식 패턴은 값 형식의 형식을 확인할 때 보다 간결한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="dcea7-132">다음 예제에서는 `is` 형식 패턴을 사용하여 개체가 `Person` 인스턴스인지 `Dog` 인스턴스인지를 확인한 후 적절한 속성의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="dcea7-133">패턴 일치를 사용하지 않는 동일한 코드에는 명시적 캐스트를 포함하는 별도의 할당이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="dcea7-134">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="dcea7-134">Constant pattern</span></span>

<span data-ttu-id="dcea7-135">상수 패턴을 사용한 패턴 일치를 수행하는 경우 `is`는 식이 지정된 상수와 같은지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="dcea7-136">C# 6 이전 버전에서는 상수 패턴이 [switch](switch.md) 문에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="dcea7-137">C# 7.0부터는 `is` 문에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="dcea7-138">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="dcea7-139">여기서 *expr*은 평가할 식이고 *constant*는 테스트할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="dcea7-140">*constant*는 다음 상수 식 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="dcea7-141">리터럴 값.</span><span class="sxs-lookup"><span data-stu-id="dcea7-141">A literal value.</span></span>

- <span data-ttu-id="dcea7-142">선언된 `const` 변수의 이름.</span><span class="sxs-lookup"><span data-stu-id="dcea7-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="dcea7-143">열거형 상수.</span><span class="sxs-lookup"><span data-stu-id="dcea7-143">An enumeration constant.</span></span>

<span data-ttu-id="dcea7-144">상수 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="dcea7-145">*expr* 및 *constant*가 정수 형식인 경우 C# 같음 연산자는 식에서 `true`를 반환하는지 여부 즉, `expr == constant`인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="dcea7-146">정수 형식이 아닌 경우 정적 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 메서드 호출을 통해 식의 값이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="dcea7-147">다음 예제에서는 형식 패턴과 상수 패턴을 결합하여 개체가 `Dice` 인스턴스인지 여부를 테스트하고, 그럴 경우 주사위 굴리기 값이 6인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="dcea7-148">상수 패턴을 사용하여 `null`을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="dcea7-149">`null` 키워드는 `is` 문에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="dcea7-150">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="dcea7-151">다음 예제는 `null` 검사의 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="dcea7-152">var 패턴</span><span class="sxs-lookup"><span data-stu-id="dcea7-152">var pattern</span></span>

<span data-ttu-id="dcea7-153">`var` 패턴은 모든 형식 또는 값에 대해 catch-all입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-153">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="dcea7-154">*expr*의 값은 항상 *expr*의 컴파일 시간 형식과 동일한 형식의 지역 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-154">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="dcea7-155">`is` 식의 결과는 항상 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-155">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="dcea7-156">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-156">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="dcea7-157">다음 예제에서는 var 패턴을 사용하여 `obj`라는 변수에 식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-157">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="dcea7-158">그런 다음 `obj`의 값과 형식을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dcea7-158">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="dcea7-159">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="dcea7-159">C# language specification</span></span>
  
<span data-ttu-id="dcea7-160">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [s 연산자](~/_csharplang/spec/expressions.md#the-is-operator) 섹션과 다음 C# 언어 제안을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcea7-160">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="dcea7-161">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="dcea7-161">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="dcea7-162">제네릭과 일치하는 패턴</span><span class="sxs-lookup"><span data-stu-id="dcea7-162">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="dcea7-163">참조</span><span class="sxs-lookup"><span data-stu-id="dcea7-163">See also</span></span>

- [<span data-ttu-id="dcea7-164">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dcea7-164">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dcea7-165">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="dcea7-165">C# keywords</span></span>](index.md)
- [<span data-ttu-id="dcea7-166">형식 테스트 및 캐스트 연산자</span><span class="sxs-lookup"><span data-stu-id="dcea7-166">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
