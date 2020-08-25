---
title: 레코드
description: 'F # 레코드가 선택적으로 멤버와 함께 명명 된 값의 단순 집계를 나타내는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: a72c0f15b58407e7d759e2fb5a1b35a7fc0d29e3
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812356"
---
# <a name="records"></a><span data-ttu-id="3c61e-103">레코드</span><span class="sxs-lookup"><span data-stu-id="3c61e-103">Records</span></span>

<span data-ttu-id="3c61e-104">레코드는 명명된 값의 간단한 집계(경우에 따라 멤버가 포함된)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="3c61e-105">구조체 또는 참조 형식 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="3c61e-106">기본적으로 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c61e-107">구문</span><span class="sxs-lookup"><span data-stu-id="3c61e-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="3c61e-108">설명</span><span class="sxs-lookup"><span data-stu-id="3c61e-108">Remarks</span></span>

<span data-ttu-id="3c61e-109">위의 구문에서 *typename* 은 레코드 형식의 이름이 고, *label1* 및 *label2* 는 값의 이름이 며, *이름 이라고 하*고, *type1* 및 *type2* 는 이러한 값의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="3c61e-110">*멤버 목록은* 해당 형식에 대 한 멤버의 선택적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="3c61e-111">특성을 사용 하 여 `[<Struct>]` 참조 형식인 레코드가 아닌 구조체 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="3c61e-112">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="3c61e-113">각 레이블이 별도의 줄에 있으면 세미콜론은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="3c61e-114">*레코드 식*이라고 하는 식에서 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="3c61e-115">컴파일러는 사용 되는 레이블에서 형식을 유추 합니다 (레이블이 다른 레코드 형식과 충분히 다른 경우).</span><span class="sxs-lookup"><span data-stu-id="3c61e-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="3c61e-116">중괄호 ({})는 레코드 식을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="3c61e-117">다음 코드에서는 레이블이 인 세 개의 float 요소와로 레코드를 초기화 하는 레코드 식을 보여 줍니다 `x` `y` `z` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="3c61e-118">레이블이 같은 다른 형식이 있을 수 있는 경우에는 약식 형식을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3c61e-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="3c61e-119">가장 최근에 선언 된 형식의 레이블은 이전에 선언 된 형식 보다 우선적으로 적용 되므로 앞의 예제에서 `mypoint3D` 는로 유추 됩니다 `Point3D` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="3c61e-120">다음 코드와 같이 레코드 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="3c61e-121">클래스 형식과 마찬가지로 레코드 형식에 대해 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="3c61e-122">레코드 식을 사용 하 여 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="3c61e-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="3c61e-123">레코드에 정의 된 레이블을 사용 하 여 레코드를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="3c61e-124">이를 수행 하는 식을 *레코드 식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="3c61e-125">중괄호를 사용 하 여 레코드 식을 묶고 세미콜론을 구분 기호로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="3c61e-126">다음 예제에서는 레코드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="3c61e-127">레코드 식의 마지막 필드와 형식 정의에서 세미콜론은 모두 필드가 한 줄에 있는지 여부에 관계 없이 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="3c61e-128">레코드를 만들 때는 각 필드에 대 한 값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="3c61e-129">모든 필드에 대 한 초기화 식에서 다른 필드의 값을 참조할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="3c61e-130">다음 코드에서의 형식은 `myRecord2` 필드 이름에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="3c61e-131">필요에 따라 형식 이름을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="3c61e-132">다른 형태의 레코드 생성은 기존 레코드를 복사 하 고 일부 필드 값을 변경 해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="3c61e-133">다음 코드 줄에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="3c61e-134">레코드 식의 이러한 형태를 *복사 및 업데이트 레코드 식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="3c61e-135">기본적으로 레코드를 변경할 수 없습니다. 그러나 복사 및 업데이트 식을 사용 하 여 수정 된 레코드를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="3c61e-136">변경할 수 있는 필드를 명시적으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="3c61e-137">레코드 필드에 DefaultValue 특성을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3c61e-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="3c61e-138">기본 값으로 초기화 되는 필드를 사용 하 여 레코드의 기본 인스턴스를 정의한 다음, 복사 및 업데이트 레코드 식을 사용 하 여 기본값과 다른 필드를 설정 하는 것이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="3c61e-139">상호 재귀 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="3c61e-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="3c61e-140">언젠가는 레코드를 만들 때 나중에 정의 하려는 다른 형식에 종속 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="3c61e-141">이는 상호 재귀 되도록 레코드 형식을 정의 하지 않는 한 컴파일 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="3c61e-142">상호 재귀 레코드 정의는 키워드를 사용 하 여 수행 됩니다 `and` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="3c61e-143">이렇게 하면 2 개 이상의 레코드 형식을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="3c61e-144">예를 들어 다음 코드는 `Person` 및 `Address` 형식을 상호 재귀로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="3c61e-145">키워드를 사용 하지 않고 이전 예제를 정의 하는 경우에는 `and` 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="3c61e-146">`and`키워드는 상호 재귀 정의에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="3c61e-147">레코드와 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="3c61e-147">Pattern Matching with Records</span></span>

<span data-ttu-id="3c61e-148">패턴 일치에 레코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="3c61e-149">일부 필드를 명시적으로 지정 하 고 일치가 발생할 때 할당 되는 다른 필드에 대 한 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="3c61e-150">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="3c61e-151">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a><span data-ttu-id="3c61e-152">레코드 및 멤버</span><span class="sxs-lookup"><span data-stu-id="3c61e-152">Records and members</span></span>

<span data-ttu-id="3c61e-153">클래스에서와 같이 레코드에 멤버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-153">You can specify members on records much like you can with classes.</span></span> <span data-ttu-id="3c61e-154">필드에 대 한 지원은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-154">There is no support for fields.</span></span> <span data-ttu-id="3c61e-155">일반적인 방법은 레코드 생성을 용이 하 게 하는 정적 멤버를 정의 하는 것입니다 `Default` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-155">A common approach is to define a `Default` static member for easy record construction:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

<span data-ttu-id="3c61e-156">자체 식별자를 사용 하는 경우 해당 식별자는 해당 멤버가 호출 된 레코드의 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-156">If you use a self identifier, that identifier refers to the instance of the record whose member is called:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123 }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="3c61e-157">레코드와 클래스의 차이점</span><span class="sxs-lookup"><span data-stu-id="3c61e-157">Differences Between Records and Classes</span></span>

<span data-ttu-id="3c61e-158">레코드 필드는 자동으로 속성으로 노출 되 고 레코드를 만들고 복사 하는 데 사용 된다는 점에서 클래스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-158">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="3c61e-159">또한 레코드 생성은 클래스 생성과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-159">Record construction also differs from class construction.</span></span> <span data-ttu-id="3c61e-160">레코드 형식에서 생성자를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-160">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="3c61e-161">대신이 항목에서 설명 하는 생성 구문이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-161">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="3c61e-162">클래스는 생성자 매개 변수, 필드 및 속성 간에 직접적인 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-162">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="3c61e-163">Union 및 구조체 형식과 마찬가지로 레코드는 구조적 같음 의미 체계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-163">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="3c61e-164">클래스에는 참조 같음 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-164">Classes have reference equality semantics.</span></span> <span data-ttu-id="3c61e-165">다음 코드 예제에서는 이 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-165">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="3c61e-166">이 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c61e-166">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="3c61e-167">클래스를 사용 하 여 동일한 코드를 작성 하는 경우 두 개의 값이 힙에 두 개의 개체를 나타내고 주소만 비교 되므로 (클래스 형식이 메서드를 재정의 하지 않는 경우) 두 클래스 개체는 같지 않습니다 `System.Object.Equals` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-167">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="3c61e-168">레코드에 대 한 참조 일치가 필요한 경우에는 레코드 위에 특성을 추가 합니다 `[<ReferenceEquality>]` .</span><span class="sxs-lookup"><span data-stu-id="3c61e-168">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c61e-169">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3c61e-169">See also</span></span>

- [<span data-ttu-id="3c61e-170">F# 형식</span><span class="sxs-lookup"><span data-stu-id="3c61e-170">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="3c61e-171">클래스</span><span class="sxs-lookup"><span data-stu-id="3c61e-171">Classes</span></span>](classes.md)
- [<span data-ttu-id="3c61e-172">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3c61e-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3c61e-173">참조-같음</span><span class="sxs-lookup"><span data-stu-id="3c61e-173">Reference-Equality</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-referenceequalityattribute.html)
- [<span data-ttu-id="3c61e-174">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="3c61e-174">Pattern Matching</span></span>](pattern-matching.md)
