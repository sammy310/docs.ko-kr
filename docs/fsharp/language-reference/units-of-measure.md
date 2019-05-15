---
title: 측정 단위
description: 어떻게 부동 소수점을 알아보고 부호 있는 정수 값 F# , 측정 단위 길이, 볼륨 및 대용량을 나타내기 위해 일반적으로 사용 되는 연결 될 수 있습니다.
ms.date: 05/16/2016
ms.openlocfilehash: 217ef67912625c0a4b187a7ee13a739de811cfcb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641641"
---
# <a name="units-of-measure"></a><span data-ttu-id="36e11-103">측정 단위</span><span class="sxs-lookup"><span data-stu-id="36e11-103">Units of Measure</span></span>

<span data-ttu-id="36e11-104">부동 소수점 및 부호 있는 정수 값 F# , 측정 단위 길이, 볼륨, 질량 등 나타내며 일반적으로 사용 되는 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="36e11-105">한지 확인 하려면 산술 관계 올바른 단위를 방지할 수 있는 컴파일러를 사용 하면 수량 단위를 사용 하 여 오류를 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="36e11-106">구문</span><span class="sxs-lookup"><span data-stu-id="36e11-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="36e11-107">설명</span><span class="sxs-lookup"><span data-stu-id="36e11-107">Remarks</span></span>

<span data-ttu-id="36e11-108">이전 구문 정의 *단위 이름* 으로 측정 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="36e11-109">이전에 정의 된 단위를 기준으로 새 측정값을 정의 하는 선택적 부분 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="36e11-110">다음 줄에서는 측정값을 정의 하는 예를 들어 `cm` (센티미터).</span><span class="sxs-lookup"><span data-stu-id="36e11-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="36e11-111">다음 줄에서는 측정값 정의 `ml` (밀리 리터) 입방 형 3 센티미터도 (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="36e11-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="36e11-112">이전 구문에서 *측정값* 은 단위를 포함 하는 수식입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="36e11-113">단위를 포함 하는 수식에서 정수 거듭제곱 (긍정 및 부정) 지원 되는, 단위 사이 공백이 표시 단위 두 개를 곱한 `*` 단위의 제품을 나타내기도 및 `/` 단위 몫을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="36e11-114">역 단위에 대 한 음의 정수 power를 사용 하거나 또는 `/` 분자와 분모 단위 수식의 사이의 구분을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="36e11-115">분모의 여러 단위는 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="36e11-116">후 공백으로 구분 된 단위를 `/` 분모의 경우 다음 모든 단위의 일부인 것으로 해석 되는 `*` 분자의 일부로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="36e11-117">1 단위 식 수량을 나타내거나 단독으로 또는 분자와 같이 다른 단위를 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="36e11-118">으로 요금에 대해 단위는 작성 하는 예를 들어 `1/s`여기서 `s` 시간 (초)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="36e11-119">괄호 단위 수식에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="36e11-120">단위 수식의; 숫자 변환 상수를 지정 하지 않으면 그러나 단위를 사용 하 여 변환 상수를 개별적으로 정의할 수 있으며 단위 검사 계산에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="36e11-121">해당 하는 다양 한 방법으로 동일한 의미로 사용 하는 단위 수식은 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="36e11-122">따라서 컴파일러는 단위 수식 변환 음수 거듭제곱 평균은 그룹 단위를 단일 분자와 분모의 분자와 분모의 단위를 사전순으로 정렬 하며 일관 된 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="36e11-123">예를 들어, 단위 수식을 `kg m s^-2` 하 고 `m /s s * kg` 으로 변환 됩니다 `kg m/s^2`합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="36e11-124">측정 단위를 사용 하 여 부동 소수점 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="36e11-125">측정값의 관련된 단위와 함께 부동 소수점 숫자를 사용 하 여 다른 수준의 형식 안전성 더하고 약한 형식의 부동 소수점 숫자를 사용 하는 경우 수식에서 발생할 수 있는 단위 불일치 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="36e11-126">부동을 작성 하는 경우 단위를 사용 하는 지점 식, 식 단위와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="36e11-127">다음 예제와 같이 리터럴 꺾쇠 괄호 안에 단위 수식 사용 하 여 주석을 달 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="36e11-128">수 고 꺾쇠 괄호; 사이 공백을 넣지 않습니다. 와 같은 리터럴 접미사를 포함할 수는 있지만 `f`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="36e11-129">해당 기본 형식에서 리터럴 형식을 변경 하는 이러한 주석의 (같은 `float`) 차원이 지정 된 형식에 같은 `float<cm>` 또는 경우 `float<miles/hour>`합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="36e11-130">에 대 한 단위 주석을 `<1>` 되었음을 해당 유형과 수량을 나타내거나 단위 매개 변수 없이 기본 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="36e11-131">측정 단위의 유형의 부동 소수점 또는 부호 있는 정수 계열 형식 대괄호로 표시, 추가 단위 주석의 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="36e11-132">따라서 작성 하는 경우 변환 유형의 `g` (그램)를 `kg` (킬로그램) 다음과 같이 형식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="36e11-133">측정 단위를 확인 하는 컴파일 시간 단위에 대 한 사용 되지만 런타임 환경에서 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="36e11-134">따라서 성능을 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="36e11-135">측정 단위 형식일 뿐 아니라 부동 소수점 형식;에 적용할 수 있습니다. 그러나만 부동 소수점 형식은 정수 계열 형식 및 소수 형식 지원 차원이 수량에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="36e11-136">따라서 이러한 기본 형식을 포함 하는 집계 및 기본 형식에서 측정 단위를 사용 하는 것이 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="36e11-137">다음 예제에서는 측정 단위를 사용을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="36e11-138">다음 코드 예제에는 값을 가지는 부동 소수점 숫자에서 차원이 지정 된 부동 소수점 값으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="36e11-139">곱하기만 1.0에서 차원을 1.0을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="36e11-140">와 같은 함수에이 추상화할 수 있습니다 `degreesFahrenheit`합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="36e11-141">또한 부동 소수점 숫자 값을 가지는 함수에 차원이 지정 된 값을 전달할 때의 단위를 취소 하거나 해야 캐스팅할 `float` 를 사용 하 여는 `float` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="36e11-142">이 예에서 나누면 `1.0<degC>` 에 대 한 인수에 대 한 `printf` 때문에 `printf` 치수 수량을 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="36e11-143">다음 예제에서는 세션에서 출력 및 입력이이 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="36e11-144">일반 단위를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="36e11-144">Using Generic Units</span></span>

<span data-ttu-id="36e11-145">데이터에서 연결 된 단위에 대해 작동 하는 제네릭 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="36e11-146">이렇게 하면 형식 매개 변수와 함께 제네릭 단위 형식을 지정 하 여 다음 코드 예제에 표시 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="36e11-147">집합체 형식은 제네릭 단위를 사용 하 여 만들기</span><span class="sxs-lookup"><span data-stu-id="36e11-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="36e11-148">다음 코드에는 제네릭 단위가 있는 개별 부동 소수점 값으로 이루어진 집합체 형식을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="36e11-149">따라서 다양 한 단위를 사용 하 여 작동 하는 단일 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="36e11-150">또한 제네릭 단위 단위 집합을 가진 제네릭 형식을 다른 형식 보다 다양 한 단위를 사용 하 여 동일한 제네릭 형식 인지 확인 하 여 형식 안전성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="36e11-151">이 기법으로 `Measure` 특성 형식 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="36e11-152">런타임 시 단위</span><span class="sxs-lookup"><span data-stu-id="36e11-152">Units at Runtime</span></span>

<span data-ttu-id="36e11-153">측정 단위는 정적 형식 확인에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="36e11-154">부동 소수점 값을 컴파일하면 단위 런타임 시 손실 되므로 측정 단위를 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="36e11-155">따라서 런타임에 단위 확인에 의존 하는 기능을 구현 하려고 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="36e11-156">예를 들어, 구현를 `ToString` 단위를 인쇄 하는 함수 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="36e11-157">변환</span><span class="sxs-lookup"><span data-stu-id="36e11-157">Conversions</span></span>

<span data-ttu-id="36e11-158">단위에 있는 형식을 변환 하려면 (예를 들어 `float<'u>`) 단위 없는 형식으로 표준 변환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="36e11-159">예를 들어 사용할 수 있습니다 `float` 변환할는 `float` 다음 코드 에서처럼 단위에 있지 않은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="36e11-160">단위 값 단위 값으로 변환 하려면 적절 한 단위를 사용 하 여 주석이 추가 되는 1 또는 1.0 값으로 곱하면 하는 것이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="36e11-161">그러나 상호 운용성 레이어를 작성 하는 것에 대 한 가지도 단위 값 단위를 사용 하 여 값으로 변환 하는 데 사용할 수 있는 몇 가지 명시적 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="36e11-162">이러한 합니다 [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="36e11-163">예를 들어 단위를 변환할 `float` 에 `float<cm>`를 사용 하 여 [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)다음 코드에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="36e11-164">측정 단위는 F# 핵심 라이브러리</span><span class="sxs-lookup"><span data-stu-id="36e11-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="36e11-165">단위 라이브러리에서 사용할 수는 `FSharp.Data.UnitSystems.SI` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="36e11-166">기호 형식으로 모두의 SI 단위를 포함 (같은 `m` 미터에 대 한)에 `UnitSymbols` 하위 네임 스페이스와 전체 이름 (같은 `meter` 미터에 대 한)에서 `UnitNames` 하위 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="36e11-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="36e11-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="36e11-167">See also</span></span>

- [<span data-ttu-id="36e11-168">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="36e11-168">F# Language Reference</span></span>](index.md)
