---
title: 측정 단위
description: 'F #의 부동 소수점 및 부호 있는 정수 값에 일반적으로 길이, 볼륨 및 질량을 나타내는 데 사용 되는 연결 된 측정 단위가 있을 수 있는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811576"
---
# <a name="units-of-measure"></a><span data-ttu-id="c8d97-103">측정 단위</span><span class="sxs-lookup"><span data-stu-id="c8d97-103">Units of Measure</span></span>

<span data-ttu-id="c8d97-104">F #의 부동 소수점 및 부호 있는 정수 값에는 일반적으로 길이, 볼륨, 질량 등을 나타내는 데 사용 되는 관련 측정 단위가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="c8d97-105">단위가 포함 된 수량을 사용 하면 컴파일러에서 산술 관계의 단위가 올바른지 확인 하 여 프로그래밍 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8d97-106">구문</span><span class="sxs-lookup"><span data-stu-id="c8d97-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="c8d97-107">설명</span><span class="sxs-lookup"><span data-stu-id="c8d97-107">Remarks</span></span>

<span data-ttu-id="c8d97-108">위의 구문은 *단위 이름을* 측정 단위로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="c8d97-109">선택적 부분은 이전에 정의 된 단위를 기준으로 새 측정값을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="c8d97-110">예를 들어 다음 줄은 측정값 `cm` (센티미터)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="c8d97-111">다음 줄은 measure `ml` (milliliter)를 입방 센티미터 ()로 정의 합니다 `cm^3` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="c8d97-112">이전 구문에서 *측정값* 은 단위를 포함 하는 수식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="c8d97-113">단위를 포함 하는 수식에서 정수 거듭제곱이 지원 됩니다 (긍정 및 부정). 단위 사이의 공백은 두 단위의 곱을 나타내고 단위 곱을 나타내며 단위의 `*` `/` 몫을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="c8d97-114">역 단위의 경우 음의 정수 거듭제곱을 사용 하거나 `/` 단위 수식의 분자와 분모를 구분 하는을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="c8d97-115">분모의 여러 단위는 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="c8d97-116">뒤에 공백으로 구분 된 단위는 `/` 분모의 일부로 해석 되지만 뒤에 오는 단위는 `*` 분자의 일부로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="c8d97-117">단위 식에 1을 사용 하 여 dimensionless 수량을 나타내거나 분자와 같이 다른 단위를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="c8d97-118">예를 들어 rate의 단위는로 작성 됩니다 `1/s` . 여기서은 `s` 초를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="c8d97-119">단위 수식에는 괄호가 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="c8d97-120">단위 수식에는 숫자 변환 상수를 지정 하지 않습니다. 그러나 단위를 사용 하 여 변환 상수를 별도로 정의 하 고 단위 검사 계산에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="c8d97-121">동일한 항목을 의미 하는 단위 수식을 다양 한 방법으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="c8d97-122">따라서 컴파일러는 단위 수식을 일관 된 형식으로 변환 합니다. 그러면 음수 거듭제곱을 reciprocals로 변환 하 고, 단위를 단일 분자와 분모로 그룹화 하 고, 분자와 분모의 단위를 alphabetizes.</span><span class="sxs-lookup"><span data-stu-id="c8d97-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="c8d97-123">예를 들어 단위 수식 `kg m s^-2` 와는 `m /s s * kg` 모두로 변환 됩니다 `kg m/s^2` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="c8d97-124">부동 소수점 식에서는 측정 단위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="c8d97-125">관련 측정 단위와 부동 소수점 숫자를 함께 사용 하면 다른 수준의 형식 안전성이 추가 되 고 약한 형식의 부동 소수점 숫자를 사용 하는 경우 수식에서 발생할 수 있는 단위 불일치 오류가 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="c8d97-126">단위를 사용 하는 부동 소수점 식을 작성 하는 경우 식의 단위가 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="c8d97-127">다음 예제에 표시 된 것 처럼 꺾쇠 괄호 안의 단위 수식을 사용 하 여 리터럴에 주석을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="c8d97-128">숫자와 꺾쇠 괄호 사이에는 공백을 두지 않습니다. 그러나 다음 예제와 같이와 같은 리터럴 접미사를 포함할 수 있습니다 `f` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="c8d97-129">이러한 주석은 리터럴의 형식을 기본 형식 (예:)에서 또는 등의 치수화 된 `float` 형식 (이 경우)으로 변경 `float<cm>` `float<miles/hour>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="c8d97-130">의 단위 주석은 `<1>` dimensionless 수량을 나타내며, 해당 형식은 unit 매개 변수가 없는 기본 형식에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="c8d97-131">측정 단위 형식은 괄호 안에 표시 되는 추가 단위 주석과 함께 부동 소수점 또는 부호 있는 정수 계열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="c8d97-132">따라서 `g` (그램)에서 (킬로그램)로 변환 형식을 작성 하는 경우 `kg` 다음과 같이 형식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="c8d97-133">측정 단위는 컴파일 시간 단위 검사에 사용 되지만 런타임 환경에서는 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="c8d97-134">따라서 성능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="c8d97-135">측정 단위는 부동 소수점 형식이 아니라 모든 형식에 적용할 수 있습니다. 그러나 부동 소수점 형식, 부호 있는 정수 형식 및 decimal 형식만 차원을 지 원하는 수량을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="c8d97-136">따라서 기본 형식의 측정 단위와 이러한 기본 형식을 포함 하는 집계를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="c8d97-137">다음 예에서는 측정 단위를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="c8d97-138">다음 코드 예제에서는 dimensionless 부동 소수점 숫자에서 치수화 된 부동 소수점 값으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="c8d97-139">1.0에 곱하여 크기를 1.0에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="c8d97-140">이를와 같은 함수로 추상화할 수 있습니다 `degreesFahrenheit` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="c8d97-141">또한 dimensionless 부동 소수점 숫자가 필요한 함수에 치수화 된 값을 전달 하는 경우에는 연산자를 사용 하 여 단위를 취소 하거나로 캐스팅 해야 합니다 `float` `float` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="c8d97-142">이 예제에서는가 `1.0<degC>` dimensionless 수량을 예상 하기 때문에에 대 한 인수를로 나눕니다 `printf` `printf` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="c8d97-143">다음 예제 세션에서는에서의 출력과이 코드에 대 한 입력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-143">The following example session shows the outputs from and inputs to this code.</span></span>

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="c8d97-144">제네릭 단위 사용</span><span class="sxs-lookup"><span data-stu-id="c8d97-144">Using Generic Units</span></span>

<span data-ttu-id="c8d97-145">연결 된 측정 단위가 있는 데이터에 대해 작동 하는 제네릭 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="c8d97-146">이 작업을 수행 하려면 다음 코드 예제와 같이 제네릭 단위와 함께 형식을 형식 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="c8d97-147">제네릭 단위를 사용 하 여 집계 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="c8d97-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="c8d97-148">다음 코드에서는 일반적인 단위가 있는 개별 부동 소수점 값으로 구성 된 집계 형식을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="c8d97-149">이렇게 하면 다양 한 단위에서 작동 하는 단일 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="c8d97-150">또한 제네릭 단위는 한 단위의 집합을 포함 하는 제네릭 형식이 다른 단위 집합을 가진 동일한 제네릭 형식과 다른 형식 인지 확인 하 여 형식 안전성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="c8d97-151">이 기술의 기본은 `Measure` 형식 매개 변수에 특성을 적용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="c8d97-152">런타임에 단위</span><span class="sxs-lookup"><span data-stu-id="c8d97-152">Units at Runtime</span></span>

<span data-ttu-id="c8d97-153">측정 단위는 정적 형식 검사에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="c8d97-154">부동 소수점 값이 컴파일되면 측정 단위가 제거 되므로 단위는 런타임에 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="c8d97-155">따라서 런타임에 단위를 확인 하는 데 종속 된 기능을 구현 하려는 시도는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="c8d97-156">예를 들어 단위를 출력 하는 함수를 구현 하는 `ToString` 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="c8d97-157">변환</span><span class="sxs-lookup"><span data-stu-id="c8d97-157">Conversions</span></span>

<span data-ttu-id="c8d97-158">단위가 있는 형식 (예:)을 단위가 없는 형식으로 변환 하려면 `float<'u>` 표준 변환 함수를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="c8d97-159">예를 들어 `float` 다음 코드와 같이를 사용 하 여 단위가 없는 값으로 변환할 수 있습니다 `float` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="c8d97-160">단위 없는 값을 단위가 있는 값으로 변환 하려면 적절 한 단위로 주석이 지정 된 값 1 또는 1.0을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="c8d97-161">그러나 상호 운용성 계층을 작성 하는 데 사용할 수 있는 몇 가지 명시적인 함수도 있습니다. 단위 값을 단위 값으로 변환 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="c8d97-162">이러한 [요소는 languageprimitives.physicalhash](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) 모듈에 fsharp.core.</span><span class="sxs-lookup"><span data-stu-id="c8d97-162">These are in the [FSharp.Core.LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) module.</span></span> <span data-ttu-id="c8d97-163">예를 들어 단위를에서로 변환 하려면 `float` `float<cm>` 다음 코드와 같이 [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="c8d97-164">F # 핵심 라이브러리의 측정 단위</span><span class="sxs-lookup"><span data-stu-id="c8d97-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="c8d97-165">단위 라이브러리는 네임 스페이스에서 사용할 수 있습니다 `FSharp.Data.UnitSystems.SI` .</span><span class="sxs-lookup"><span data-stu-id="c8d97-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="c8d97-166">하위 네임 스페이스의 기호 형식 ( `m` 예: 미터) `UnitSymbols` 과 하위 네임 스페이스의 전체 이름 (예: 미터)에 SI 단위를 포함 `meter` `UnitNames` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d97-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d97-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8d97-167">See also</span></span>

- [<span data-ttu-id="c8d97-168">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c8d97-168">F# Language Reference</span></span>](index.md)
