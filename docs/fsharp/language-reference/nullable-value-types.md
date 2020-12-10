---
title: Nullable 값 형식
description: 'F #에서 null 일 수 있는 값 형식을 나타내는 방법인 nullable 값 형식을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 11/19/2020
ms.openlocfilehash: e28cbfc57c5631573f46ac36462517cf011e96d2
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009640"
---
# <a name="nullable-value-types"></a><span data-ttu-id="6f804-103">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="6f804-103">Nullable value types</span></span>

<span data-ttu-id="6f804-104">_Nullable 값 형식은_ `Nullable<'T>` 일 수도 있는 모든 [구조체](structures.md) 형식을 나타냅니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="6f804-104">A _nullable value type_ `Nullable<'T>` represents any [struct](structures.md) type that could also be `null`.</span></span> <span data-ttu-id="6f804-105">이는 정수와 같은 이러한 종류의 유형을 효율성을 위해 값으로 표시 하도록 선택할 수 있는 라이브러리 및 구성 요소와 상호 작용 하는 경우에 유용 `null` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-105">This is helpful when interacting with libraries and components that may choose to represent these kinds of types, like integers, with a `null` value for efficiency reasons.</span></span> <span data-ttu-id="6f804-106">이 구문을 지 원하는 기본 형식은 <xref:System.Nullable%601?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-106">The underlying type that backs this construct is <xref:System.Nullable%601?displayProperty=nameWithType>.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f804-107">구문</span><span class="sxs-lookup"><span data-stu-id="6f804-107">Syntax</span></span>

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a><span data-ttu-id="6f804-108">값을 사용 하 여 선언 및 할당</span><span class="sxs-lookup"><span data-stu-id="6f804-108">Declare and assign with values</span></span>

<span data-ttu-id="6f804-109">Nullable 값 형식을 선언 하는 것은 F #에서 래퍼와 유사한 형식을 선언 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-109">Declaring a nullable value type is just like declaring any wrapper-like type in F#:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

<span data-ttu-id="6f804-110">제네릭 형식 매개 변수를 elide 하 고 형식 유추를 사용 하 여 문제를 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-110">You can also elide the generic type parameter and allow type inference to resolve it:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

<span data-ttu-id="6f804-111">Nullable 값 형식에 할당 하려면 명시적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-111">To assign to a nullable value type, you'll need to also be explicit.</span></span> <span data-ttu-id="6f804-112">F #에서 정의한 nullable 값 형식에 대 한 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-112">There is no implicit conversion for F#-defined nullable value types:</span></span>

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a><span data-ttu-id="6f804-113">Null 할당</span><span class="sxs-lookup"><span data-stu-id="6f804-113">Assign null</span></span>

<span data-ttu-id="6f804-114">`null`Nullable 값 형식에 직접 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-114">You cannot directly assign `null` to a nullable value type.</span></span> <span data-ttu-id="6f804-115">`Nullable()`대신를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-115">Use `Nullable()` instead:</span></span>

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

<span data-ttu-id="6f804-116">에 적절 한 값이 없기 때문입니다 `Nullable<'T>` `null` .</span><span class="sxs-lookup"><span data-stu-id="6f804-116">This is because `Nullable<'T>` does not have `null` as a proper value.</span></span>

## <a name="pass-and-assign-to-members"></a><span data-ttu-id="6f804-117">전달 및 멤버에 할당</span><span class="sxs-lookup"><span data-stu-id="6f804-117">Pass and assign to members</span></span>

<span data-ttu-id="6f804-118">멤버 작업과 F # 값을 사용 하는 경우의 주요 차이점은 멤버를 사용할 때 nullable 값 형식이 암시적으로 유추 될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-118">A key difference between working with members and F# values is that nullable value types can be implicitly inferred when you're working with members.</span></span> <span data-ttu-id="6f804-119">Nullable 값 형식을 입력으로 사용 하는 다음 메서드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-119">Consider the following method that takes a nullable value type as input:</span></span>

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

<span data-ttu-id="6f804-120">이전 예제에서는 메서드에를 전달할 수 있습니다 `12` `M` .</span><span class="sxs-lookup"><span data-stu-id="6f804-120">In the previous example, you can pass `12` to the method `M`.</span></span> <span data-ttu-id="6f804-121">Auto 속성에도 할당할 수 있습니다 `12` `NVT` .</span><span class="sxs-lookup"><span data-stu-id="6f804-121">You can also assign `12` to the auto property `NVT`.</span></span> <span data-ttu-id="6f804-122">입력이 nullable 값 형식으로 생성 될 수 있고 대상 형식과 일치 하면 F # 컴파일러는 이러한 호출 또는 할당을 암시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-122">If the input can be constructed as a nullable value type and it matches the target type, the F# compiler will implicitly convert such calls or assignments.</span></span>

## <a name="examine-a-nullable-value-type-instance"></a><span data-ttu-id="6f804-123">Nullable 값 형식 인스턴스를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-123">Examine a nullable value type instance</span></span>

<span data-ttu-id="6f804-124">가능한 값을 나타내기 위한 일반화 된 구문에 해당 하는 [옵션과](options.md)달리 nullable 값 형식은 패턴 일치에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-124">Unlike [Options](options.md), which are a generalized construct for representing a possible value, nullable value types are not used with pattern matching.</span></span> <span data-ttu-id="6f804-125">대신 식을 사용 하 [`if`](conditional-expressions-if-then-else.md) 고 속성을 확인 해야 `HasValue` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-125">Instead, you need to use an [`if`](conditional-expressions-if-then-else.md) expression and check the `HasValue` property.</span></span>

<span data-ttu-id="6f804-126">내부 값을 가져오려면 `Value` 다음과 같이 확인 후에 속성을 사용 합니다 `HasValue` .</span><span class="sxs-lookup"><span data-stu-id="6f804-126">To get the underlying value, use the `Value` property after a `HasValue` check, like so:</span></span>

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a><span data-ttu-id="6f804-127">Nullable 연산자</span><span class="sxs-lookup"><span data-stu-id="6f804-127">Nullable operators</span></span>

<span data-ttu-id="6f804-128">산술 또는 비교와 같은 nullable 값 형식에 대 한 연산은 [nullable 연산자](symbol-and-operator-reference/nullable-operators.md)를 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-128">Operations on nullable value types, such as arithmetic or comparison, can require the use of [nullable operators](symbol-and-operator-reference/nullable-operators.md).</span></span>

<span data-ttu-id="6f804-129">네임 스페이스의 변환 연산자를 사용 하 여 하나의 nullable 값 형식에서 다른 형식으로 변환할 수 있습니다 `FSharp.Linq` .</span><span class="sxs-lookup"><span data-stu-id="6f804-129">You can convert from one nullable value type to another using conversion operators from the `FSharp.Linq` namespace:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

<span data-ttu-id="6f804-130">또한 적절 한 null이 아닌 연산자를 사용 하 여 기본 형식으로 변환 하 고, 값이 없는 경우 예외를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-130">You can also use an appropriate non-nullable operator to convert to a primitive type, risking an exception if it has no value:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

<span data-ttu-id="6f804-131">및를 확인 하는 데 nullable 연산자를 짧은 방법으로 사용할 수도 있습니다 `HasValue` `Value` .</span><span class="sxs-lookup"><span data-stu-id="6f804-131">You can also use nullable operators as a short-hand for checking `HasValue` and `Value`:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

<span data-ttu-id="6f804-132">`?>`비교는 왼쪽이 null을 허용 하 고 값이 있는 경우에만 성공 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-132">The `?>` comparison checks if the left-hand side is nullable and only succeeds if it has a value.</span></span> <span data-ttu-id="6f804-133">뒤에 오는 줄과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f804-133">It is equivalent to the line that follows it.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f804-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f804-134">See also</span></span>

- [<span data-ttu-id="6f804-135">구조체</span><span class="sxs-lookup"><span data-stu-id="6f804-135">Structures</span></span>](structures.md)
- [<span data-ttu-id="6f804-136">F # 옵션</span><span class="sxs-lookup"><span data-stu-id="6f804-136">F# Options</span></span>](options.md)
