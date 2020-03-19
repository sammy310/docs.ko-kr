---
title: 구별된 공용 구조체
description: F# 구분 된 공용 구조체를 사용 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401072"
---
# <a name="discriminated-unions"></a><span data-ttu-id="bfe26-103">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="bfe26-103">Discriminated Unions</span></span>

<span data-ttu-id="bfe26-104">구별된 공용 구조체는 서로 다른 값과 형식을 가진 여러 명명된 사례 중 하나일 수 있는 값을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="bfe26-105">구별된 공용 구조체는 이기종 데이터에 유용합니다. 유효 및 오류 사례를 포함하여 특별한 경우를 가질 수 있는 데이터; 한 인스턴스에서 다른 인스턴스로 유형이 다른 데이터; 작은 개체 계층 구조에 대한 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="bfe26-106">또한 재귀 구별 된 공용 구조체는 트리 데이터 구조를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfe26-107">구문</span><span class="sxs-lookup"><span data-stu-id="bfe26-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="bfe26-108">설명</span><span class="sxs-lookup"><span data-stu-id="bfe26-108">Remarks</span></span>

<span data-ttu-id="bfe26-109">구별된 공용 구조체는 다른 언어의 공용 구조체 유형과 유사하지만 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="bfe26-110">C++의 공용 구조체 유형 또는 Visual Basic의 변형 유형과 마찬가지로 값에 저장된 데이터는 고정되지 않습니다. 그것은 몇 가지 별개의 옵션 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="bfe26-111">그러나 이러한 다른 언어의 공용 구조체와 달리 가능한 각 옵션에는 *대/소문자 식별자가*제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="bfe26-112">대/소문자 식별자는 이 형식의 개체가 될 수 있는 다양한 가능한 유형의 값에 대한 이름입니다. 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="bfe26-113">값이 없는 경우 케이스는 열거형 사례와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="bfe26-114">값이 있는 경우 각 값은 지정된 형식의 단일 값이거나 동일하거나 다른 형식의 여러 필드를 집계하는 튜플일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="bfe26-115">개별 필드에 이름을 지정할 수 있지만 동일한 경우 다른 필드의 이름이 지정되더라도 이름은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="bfe26-116">구분된 공용 구조체에 `public`대한 액세스 기본값은 .</span><span class="sxs-lookup"><span data-stu-id="bfe26-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="bfe26-117">예를 들어 모양 형식의 다음 선언을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="bfe26-118">앞의 코드는 사각형, 원 및 프리즘의 세 가지 경우 중 어느 값도 가질 수 있는 구별된 공용 구조체 셰이프를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="bfe26-119">각 사례에는 서로 다른 필드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-119">Each case has a different set of fields.</span></span> <span data-ttu-id="bfe26-120">사각형 케이스에는 이름 너비와 길이가 `float`있는 두 개의 명명된 필드(형식)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="bfe26-121">Circle 케이스에는 명명된 필드인 반경이 하나뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="bfe26-122">프리즘 케이스에는 세 개의 필드가 있으며 그 중 두 필드(너비 및 높이)는 필드로 명명됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="bfe26-123">명명되지 않은 필드를 익명 필드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="bfe26-124">다음 예제에 따라 명명된 필드와 익명 필드에 대 한 값을 제공 하 여 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="bfe26-125">이 코드는 초기화에서 명명된 필드를 사용하거나 선언에서 필드의 순서를 기반으로 각 필드에 대한 값을 차례로 제공할 수 있음을 보여 주며, 이 에 따라 각 필드에 대한 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="bfe26-126">이전 `rect` 코드에서 생성자 호출은 명명된 필드를 사용하지만 생성자 호출은 순서지정을 `circ` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="bfe26-127">의 구성에서와 같이 정렬된 필드와 명명된 필드를 혼합할 수 `prism`있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="bfe26-128">형식은 `option` F# 코어 라이브러리에서 간단한 구별 된 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="bfe26-129">형식은 `option` 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="bfe26-130">이전 코드는 형식이 `Option` 두 가지 경우가 `Some` 있는 구별된 공용 `None`구조체및 .</span><span class="sxs-lookup"><span data-stu-id="bfe26-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="bfe26-131">`Some` 케이스에는 형식이 형식 매개 변수로 `'a`표시되는 하나의 익명 필드로 구성된 연결된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="bfe26-132">케이스에 `None` 연관된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-132">The `None` case has no associated value.</span></span> <span data-ttu-id="bfe26-133">따라서 `option` 형식은 일부 형식의 값이 있거나 값이 없는 제네릭 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="bfe26-134">또한 `Option` 이 형식에는 소문자 형식 `option`별칭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="bfe26-135">대/소문자 식별자는 구별된 공용 구조체 형식의 생성자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="bfe26-136">예를 들어 다음 코드는 `option` 형식의 값을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="bfe26-137">대/소문자 식별자는 패턴 일치 식에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="bfe26-138">패턴 일치 식에서 식별자는 개별 사례와 연결된 값에 대해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="bfe26-139">예를 들어 다음 코드에서는 `x` 형식의 `Some` 대/소문자와 연관된 값이 `option` 주어진 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="bfe26-140">패턴 일치 식에서 명명된 필드를 사용하여 구별된 공용 구조체 일치 항목을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="bfe26-141">이전에 선언된 Shape 형식의 경우 명명된 필드를 다음 코드와 같이 사용하여 필드의 값을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="bfe26-142">일반적으로 대/소문자 식별자는 공용 구조의 이름으로 한정하지 않고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="bfe26-143">이름이 항상 공용 구조체 이름으로 정규화하도록 하려면 [공용 구조체 액세스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) 특성을 공용 구조체 유형 정의에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="bfe26-144">차별된 공용 구조체의 래핑 해제</span><span class="sxs-lookup"><span data-stu-id="bfe26-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="bfe26-145">F# 구별 된 공용 구조체는 종종 단일 형식을 래핑하기 위한 도메인 모델링에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="bfe26-146">패턴 일치를 통해 기본 값을 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="bfe26-147">단일 케이스에 match 식을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="bfe26-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="bfe26-149">패턴 일치는 함수 매개 변수에서 직접 허용되므로 단일 케이스의 래핑을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="bfe26-150">구조체 차별 된 연합</span><span class="sxs-lookup"><span data-stu-id="bfe26-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="bfe26-151">구별된 공용 구조체를 구조체로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="bfe26-152">이 작업은 특성으로 `[<Struct>]` 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="bfe26-153">이러한 형식은 참조 형식이 아니라 값 형식이므로 참조 구별된 공용 구조체와 비교하여 추가 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="bfe26-154">값 유형으로 복사 되고 값 형식 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="bfe26-155">다중 대/소문자 구조 구별 유니온에서는 재귀 형식 정의를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="bfe26-156">다중 케이스 구조체 구별 유니온에 대해 고유한 사례 이름을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="bfe26-157">개체 계층 구조 대신 구분된 공용 구조체 사용</span><span class="sxs-lookup"><span data-stu-id="bfe26-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="bfe26-158">작은 개체 계층 구조에 대한 간단한 대안으로 구별된 공용 구조체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="bfe26-159">예를 들어, 원, 사각형 등에 `Shape` 대한 파생 형식이 있는 기본 클래스 대신 다음과 같은 구별된 공용 구조체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="bfe26-160">개체 지향 구현에서 사용하는 것처럼 영역이나 둘레를 계산하는 가상 메서드 대신 패턴 일치를 적절한 수식에 분기하여 이러한 수량을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="bfe26-161">다음 예제에서는 모양에 따라 영역을 계산하는 데 다른 수식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="bfe26-162">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="bfe26-163">트리 데이터 구조에 구별된 공용 구조 체 사용</span><span class="sxs-lookup"><span data-stu-id="bfe26-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="bfe26-164">구별된 공용 구조체는 재귀적일 수 있으므로 하나 이상의 사례 유형에 공용 구조체 자체가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="bfe26-165">재귀 구별 된 공용 구조체는 프로그래밍 언어에서 식을 모델링하는 데 사용되는 트리 구조를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="bfe26-166">다음 코드에서는 재귀 구별 된 공용 구조체가 이진 트리 데이터 구조를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="bfe26-167">공용 구조체는 정수 값과 왼쪽 및 오른쪽 하위 트리가 있는 노드와 `Node` `Tip`트리를 종료하는 노드인 두 가지 경우로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="bfe26-168">이전 코드에서는 `resultSumTree` 값 10이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="bfe26-169">다음 그림에서는 에 대한 `myTree`트리 구조를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-169">The following illustration shows the tree structure for `myTree`.</span></span>

![myTree의 트리 구조를 보여 주는 다이어그램입니다.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="bfe26-171">트리의 노드가 이기종인 경우 구별된 공용 구조체가 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="bfe26-172">다음 코드에서 형식은 `Expression` 숫자와 변수의 추가 및 곱셈을 지원하는 간단한 프로그래밍 언어로 식의 추상 구문 트리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="bfe26-173">일부 공용 구조체 케이스는 재귀가 아니며`Number`숫자 ()`Variable`또는 변수()를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="bfe26-174">다른 경우는 재귀적이며, 발착식도 있는 작업(및)을`Add` `Multiply`나타낸다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="bfe26-175">함수는 `Evaluate` match 식을 사용하여 구문 트리를 재귀적으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="bfe26-176">이 코드가 실행되면 `result` 값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="bfe26-177">구성원</span><span class="sxs-lookup"><span data-stu-id="bfe26-177">Members</span></span>

<span data-ttu-id="bfe26-178">구별된 공용 구조체에서 멤버를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="bfe26-179">다음 예제에서는 속성을 정의 하고 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-179">The following example shows how to define a property and implement an interface:</span></span>

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

## <a name="common-attributes"></a><span data-ttu-id="bfe26-180">일반적인 특성</span><span class="sxs-lookup"><span data-stu-id="bfe26-180">Common attributes</span></span>

<span data-ttu-id="bfe26-181">다음 특성은 일반적으로 구별된 공용 구조체에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfe26-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="bfe26-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfe26-182">See also</span></span>

- [<span data-ttu-id="bfe26-183">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="bfe26-183">F# Language Reference</span></span>](index.md)
