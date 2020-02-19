---
title: 구별된 공용 구조체
description: 구별 된 공용 구조체 F# 를 사용 하는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452645"
---
# <a name="discriminated-unions"></a><span data-ttu-id="4eb0b-103">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="4eb0b-103">Discriminated Unions</span></span>

<span data-ttu-id="4eb0b-104">구별 된 공용 구조체는 여러 개의 명명 된 사례 중 하나일 수 있는 값을 지원 합니다. 각각의 값과 형식이 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="4eb0b-105">구별 된 공용 구조체는 다른 유형의 데이터에 유용 합니다. 유효한 및 오류 사례를 포함 하 여 특수 한 경우를 포함 하는 데이터 한 인스턴스에서 다른 인스턴스로의 형식에 따라 달라 지는 데이터 및는 작은 개체 계층 구조에 대 한 대 안으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="4eb0b-106">또한 재귀적으로 구분 된 공용 구조체는 트리 데이터 구조를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="4eb0b-107">구문</span><span class="sxs-lookup"><span data-stu-id="4eb0b-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="4eb0b-108">설명</span><span class="sxs-lookup"><span data-stu-id="4eb0b-108">Remarks</span></span>

<span data-ttu-id="4eb0b-109">구별 된 공용 구조체는 다른 언어의 공용 구조체 형식과 비슷하지만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="4eb0b-110">의 C++ union 형식 또는 Visual Basic의 variant 형식과 마찬가지로 값에 저장 된 데이터는 수정 되지 않습니다. 여러 가지 다른 옵션 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="4eb0b-111">그러나 이러한 다른 언어의 공용 구조체와는 달리 각각의 가능한 옵션에는 *case 식별자*가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="4eb0b-112">Case 식별자는 이러한 형식의 개체가 가질 수 있는 다양 한 형식의 값에 대 한 이름입니다. 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="4eb0b-113">값이 없는 경우 대/소문자는 열거 사례와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="4eb0b-114">값이 있는 경우 각 값은 지정 된 형식의 단일 값 이거나 동일 하거나 다른 형식의 여러 필드를 집계 하는 튜플입니다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="4eb0b-115">개별 필드에 이름을 지정할 수 있지만 동일한 사례의 다른 필드가 명명 된 경우에도 이름은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="4eb0b-116">구분 된 공용 구조체에 대 한 접근성은 기본적으로 `public`입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="4eb0b-117">예를 들어 다음과 같은 모양 형식의 선언을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="4eb0b-118">위의 코드는 세 가지 경우 (사각형, 원 및 프리즘) 값을 가질 수 있는 구별 된 공용 구조체 셰이프를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="4eb0b-119">각 사례에는 서로 다른 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-119">Each case has a different set of fields.</span></span> <span data-ttu-id="4eb0b-120">사각형 케이스에는 두 개의 명명 된 필드가 있으며,이 두 필드는 모두 이름과 길이가 있는 `float`형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="4eb0b-121">원 케이스에는 하나의 명명 된 필드인 반지름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="4eb0b-122">프리즘 사례에는 세 개의 필드가 있으며,이 필드에는 두 개의 필드 (너비와 높이)가 명명 된 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="4eb0b-123">명명 되지 않은 필드를 익명 필드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="4eb0b-124">다음 예제에 따라 명명 된 필드 및 익명 필드에 값을 제공 하 여 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="4eb0b-125">이 코드에서는 초기화에 명명 된 필드를 사용 하거나, 선언의 필드 순서를 사용 하 고, 각 필드의 값을 차례로 제공 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="4eb0b-126">이전 코드의 `rect`에 대 한 생성자 호출은 명명 된 필드를 사용 하지만 `circ`의 생성자 호출은 정렬을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="4eb0b-127">`prism`생성에서와 같이 순서가 지정 된 필드와 명명 된 필드를 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="4eb0b-128">`option` 형식은 F# 핵심 라이브러리의 단순한 구별 된 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="4eb0b-129">`option` 형식은 다음과 같이 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="4eb0b-130">이전 코드는 `Option` 형식이 `Some` 및 `None`의 두 가지 경우를 포함 하는 구별 된 공용 구조체 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="4eb0b-131">`Some` case에는 형식이 형식 매개 변수 `'a`나타내는 익명 필드 하나로 구성 된 연결 된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="4eb0b-132">`None` 대/소문자에 연결 된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-132">The `None` case has no associated value.</span></span> <span data-ttu-id="4eb0b-133">따라서 `option` 형식은 일부 형식의 값 또는 값이 없는 제네릭 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="4eb0b-134">형식 `Option`에는 보다 일반적으로 사용 되는 소문자 형식 별칭 `option`있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="4eb0b-135">Case 식별자를 구별 된 공용 구조체 형식에 대 한 생성자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="4eb0b-136">예를 들어 다음 코드는 `option` 형식의 값을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="4eb0b-137">Case 식별자는 패턴 일치 식에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="4eb0b-138">패턴 일치 식에서 개별 사례와 관련 된 값에 대 한 식별자가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="4eb0b-139">예를 들어 다음 코드에서 `x`는 `option` 형식의 `Some` 대/소문자와 연결 된 값을 제공 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="4eb0b-140">패턴 일치 식에서 명명 된 필드를 사용 하 여 구별 된 공용 구조체 일치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="4eb0b-141">이전에 선언 된 셰이프 형식의 경우 다음 코드와 같이 명명 된 필드를 사용 하 여 필드 값을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="4eb0b-142">일반적으로 대/소문자 식별자는 공용 구조체의 이름으로 한정 하지 않고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="4eb0b-143">이름을 항상 공용 구조체의 이름으로 정규화 하려면 [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) 특성을 공용 구조체 형식 정의에 적용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="4eb0b-144">래핑 해제 구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="4eb0b-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="4eb0b-145">F# 구분 된 공용 구조체는 단일 형식을 래핑하는 도메인 모델링에 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="4eb0b-146">패턴 일치를 통해 내부 값을 추출 하는 것도 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="4eb0b-147">단일 사례에 대해 일치 식을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="4eb0b-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="4eb0b-149">또한 패턴 일치는 함수 매개 변수에서 직접 사용할 수 있으므로 단일 사례를 래핑을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="4eb0b-150">구별 된 공용 구조체 구조체</span><span class="sxs-lookup"><span data-stu-id="4eb0b-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="4eb0b-151">구별 된 공용 구조체를 구조체로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="4eb0b-152">`[<Struct>]` 특성을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="4eb0b-153">이러한 값 형식은 참조 형식이 아니라 값 형식 이므로 참조 구별 된 공용 구조체와 비교 하 여 추가로 고려해 야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="4eb0b-154">값 형식으로 복사 되 고 값 형식 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="4eb0b-155">Multicase 구조체와 구별 된 공용 구조체에는 재귀 형식 정의를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="4eb0b-156">Multicase 구조체 구별 된 공용 구조체에 대 한 고유한 대/소문자 이름을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="4eb0b-157">개체 계층 구조 대신 구별 된 공용 구조체 사용</span><span class="sxs-lookup"><span data-stu-id="4eb0b-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="4eb0b-158">종종 구별 된 공용 구조체를 작은 개체 계층에 대 한 보다 간단한 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="4eb0b-159">예를 들어 원, 사각형 등에 대해 파생 형식이 포함 된 `Shape` 기본 클래스 대신 다음과 같은 구별 된 공용 구조체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="4eb0b-160">영역 또는 둘레를 계산 하는 가상 메서드 대신 개체 지향 구현에서 사용 하는 것 처럼 패턴 일치를 사용 하 여 적절 한 수식으로 분기 하 고 이러한 수량을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="4eb0b-161">다음 예에서는 도형에 따라 서로 다른 수식을 사용 하 여 영역을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="4eb0b-162">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="4eb0b-163">트리 데이터 구조에 대해 구별 된 공용 구조체 사용</span><span class="sxs-lookup"><span data-stu-id="4eb0b-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="4eb0b-164">구분 된 공용 구조체는 재귀적 일 수 있습니다. 즉, union 자체는 하나 이상의 사례 형식에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="4eb0b-165">재귀 구별 된 공용 구조체를 사용 하 여 프로그래밍 언어로 식을 모델링 하는 데 사용 되는 트리 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="4eb0b-166">다음 코드에서 재귀적으로 구분 된 공용 구조체를 사용 하 여 이진 트리 데이터 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="4eb0b-167">Union은 정수 값과 왼쪽 및 오른쪽 하위 트리가 있는 노드인 `Node`와 트리를 종료 하는 `Tip`의 두 가지 사례로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="4eb0b-168">위의 코드에서 `resultSumTree` 값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="4eb0b-169">다음 그림에서는 `myTree`의 트리 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-169">The following illustration shows the tree structure for `myTree`.</span></span>

![MyTree의 트리 구조를 표시 하는 다이어그램입니다.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="4eb0b-171">구별 된 공용 구조체는 트리의 노드가 다른 유형이 면 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="4eb0b-172">다음 코드에서 `Expression` 형식은 숫자 및 변수의 더하기와 곱셈을 지 원하는 간단한 프로그래밍 언어의 식에 대 한 추상 구문 트리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="4eb0b-173">일부 공용 구조체 케이스는 재귀적이 아니고 숫자 (`Number`) 또는 변수 (`Variable`)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="4eb0b-174">다른 경우는 재귀이 고 연산자 (`Add` 및 `Multiply`)를 나타내지만 피연산자도 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="4eb0b-175">`Evaluate` 함수는 match 식을 사용 하 여 구문 트리를 재귀적으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="4eb0b-176">이 코드가 실행 되 면 `result`의 값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="4eb0b-177">구성원</span><span class="sxs-lookup"><span data-stu-id="4eb0b-177">Members</span></span>

<span data-ttu-id="4eb0b-178">구별 된 공용 구조체에 멤버를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="4eb0b-179">다음 예제에서는 속성을 정의 하 고 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-179">The following example shows how to define a property and implement an interface:</span></span>

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a><span data-ttu-id="4eb0b-180">공통 특성</span><span class="sxs-lookup"><span data-stu-id="4eb0b-180">Common attributes</span></span>

<span data-ttu-id="4eb0b-181">다음 특성은 일반적으로 구분 된 공용 구조체에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb0b-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="4eb0b-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4eb0b-182">See also</span></span>

- [<span data-ttu-id="4eb0b-183">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="4eb0b-183">F# Language Reference</span></span>](index.md)
