---
title: 속성
description: '개체와 연결 된 값을 나타내는 멤버인 F # 속성에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740200"
---
# <a name="properties"></a><span data-ttu-id="cee9b-103">속성</span><span class="sxs-lookup"><span data-stu-id="cee9b-103">Properties</span></span>

<span data-ttu-id="cee9b-104">*속성* 은 개체와 연결 된 값을 나타내는 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="cee9b-105">구문</span><span class="sxs-lookup"><span data-stu-id="cee9b-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="cee9b-106">설명</span><span class="sxs-lookup"><span data-stu-id="cee9b-106">Remarks</span></span>

<span data-ttu-id="cee9b-107">속성은 개체에 연결 된 데이터를 나타내는 개체 지향 프로그래밍의 "있음" 관계를 나타냅니다. 정적 속성의 경우에는 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="cee9b-108">속성에 대 한 기본 값 (백업 저장소 라고도 함)을 명시적으로 지정 하는지 아니면 컴파일러가 자동으로 백업 저장소를 생성할 수 있는지에 따라 두 가지 방법으로 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="cee9b-109">일반적으로 속성에 특수 한 구현이 있는 경우 보다 명시적인 방법을 사용 하 고 속성이 값 또는 변수에 대 한 간단한 래퍼 일 때 자동으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="cee9b-110">속성을 명시적으로 선언 하려면 키워드를 사용 `member` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="cee9b-111">이 선언적 구문 뒤에는 `get` 및 `set` 메서드 (명명 된 *접근자*)를 지정 하는 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="cee9b-112">구문 섹션에 표시 된 다양 한 형식의 명시적 구문은 읽기/쓰기, 읽기 전용 및 쓰기 전용 속성에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="cee9b-113">읽기 전용 속성의 경우 `get` 메서드만 정의 합니다. 쓰기 전용 속성의 경우 `set` 메서드만 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="cee9b-114">속성에 및 접근자가 모두 있는 `get` 경우 `set` 에는 다음 코드에 표시 된 것 처럼 대체 구문을 사용 하 여 각 접근자에 대해 다른 특성 및 액세스 가능성 한정자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="cee9b-115">및 메서드를 모두 포함 하는 읽기/쓰기 속성의 경우 `get` `set` 및의 순서 `get` 를 `set` 반대로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="cee9b-116">또는 `get` 결합 된 구문을 사용 하는 대신에 대해서만 표시 되는 구문 및에 대해 표시 된 구문도 제공할 수 있습니다 `set` .</span><span class="sxs-lookup"><span data-stu-id="cee9b-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="cee9b-117">이렇게 하면 개별 `get` 또는 메서드를 쉽게 주석으로 처리할 수 있습니다 `set` .</span><span class="sxs-lookup"><span data-stu-id="cee9b-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="cee9b-118">다음 코드에서는 조합 된 구문 사용에 대 한 대안을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="cee9b-119">속성의 데이터를 포함 하는 전용 값을 *백업 저장소* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="cee9b-120">컴파일러가 백업 저장소를 자동으로 만들도록 하려면 키워드를 사용 하 여 `member val` 자체 식별자를 생략 한 다음 속성을 초기화 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="cee9b-121">속성을 변경할 수 있으면를 포함 `with get, set` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="cee9b-122">예를 들어 다음 클래스 형식은 자동으로 구현 된 두 개의 속성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="cee9b-123">`Property1` 는 읽기 전용 이며 기본 생성자에 제공 된 인수로 초기화 되며, `Property2` 는 설정 가능한 속성은 빈 문자열로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="cee9b-124">자동으로 구현 된 속성은 형식 초기화의 일부 이므로 `let` 형식 정의에서 바인딩과 바인딩과 마찬가지로 다른 멤버 정의 앞에 포함 되어야 합니다 `do` .</span><span class="sxs-lookup"><span data-stu-id="cee9b-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="cee9b-125">자동으로 구현 된 속성을 초기화 하는 식은 초기화 시에만 계산 되며 속성에 액세스할 때마다 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="cee9b-126">이 동작은 명시적으로 구현 된 속성의 동작과는 대조적입니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="cee9b-127">이는 실제로 이러한 속성을 초기화 하는 코드가 클래스의 생성자에 추가 된다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="cee9b-128">이러한 차이를 표시 하는 다음 코드를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

<span data-ttu-id="cee9b-129">**출력**</span><span class="sxs-lookup"><span data-stu-id="cee9b-129">**Output**</span></span>

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="cee9b-130">이전 코드의 출력에서는 반복적으로 호출 될 때 AutoProperty 값이 변경 되지 않은 반면 ExplicitProperty가 호출 될 때마다 변경 되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="cee9b-131">이는 명시적 속성에 대 한 getter 메서드와 마찬가지로 자동으로 구현 된 속성에 대 한 식이 매번 계산 되지 않는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="cee9b-132">`System.Data.Entity`자동으로 구현 된 속성을 초기화 하는 경우 제대로 작동 하지 않는 기본 클래스 생성자에서 사용자 지정 작업을 수행 하는 Entity Framework ()와 같은 몇 가지 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="cee9b-133">이러한 경우에는 명시적 속성을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cee9b-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="cee9b-134">속성은 클래스, 구조체, 구분 된 공용 구조체, 레코드, 인터페이스 및 형식 확장의 멤버일 수 있으며 개체 식에 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="cee9b-135">속성에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="cee9b-136">속성에 특성을 적용 하려면 속성 앞에 별도의 줄에 특성을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="cee9b-137">자세한 내용은 [특성](../attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee9b-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="cee9b-138">기본적으로 속성은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-138">By default, properties are public.</span></span> <span data-ttu-id="cee9b-139">액세스 가능성 한정자는 속성에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="cee9b-140">액세스 가능성 한정자를 적용 하려면 및 메서드에 둘 다 적용 될 경우 속성 이름 바로 앞에 추가 하 고 `get` `set` `get` `set` 각 접근자에 대해 서로 다른 액세스 가능성이 필요한 경우 및 키워드 앞에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="cee9b-141">*액세스 가능성 한정자* 는 `public` ,, 중 하나일 수 있습니다. `private` `internal`</span><span class="sxs-lookup"><span data-stu-id="cee9b-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="cee9b-142">자세한 내용은 [Access Control](../access-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cee9b-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="cee9b-143">속성에 액세스할 때마다 속성 구현이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="cee9b-144">정적 및 인스턴스 속성</span><span class="sxs-lookup"><span data-stu-id="cee9b-144">Static and Instance Properties</span></span>

<span data-ttu-id="cee9b-145">속성은 정적 또는 인스턴스 속성 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="cee9b-146">정적 속성은 인스턴스 없이 호출할 수 있으며 개별 개체가 아닌 형식과 연결 된 값에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="cee9b-147">정적 속성의 경우 자체 식별자를 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="cee9b-148">인스턴스 속성에는 자체 식별자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="cee9b-149">다음 정적 속성 정의는 `myStaticValue` 속성의 백업 저장소 인 정적 필드가 있는 시나리오를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="cee9b-150">속성은 배열과 같을 수도 있으며,이 경우 *인덱싱된 속성* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="cee9b-151">자세한 내용은 [인덱싱된 속성](indexed-properties.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cee9b-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="cee9b-152">속성에 대 한 형식 주석</span><span class="sxs-lookup"><span data-stu-id="cee9b-152">Type Annotation for Properties</span></span>

<span data-ttu-id="cee9b-153">대부분의 경우 컴파일러는 백업 저장소의 형식에서 속성의 형식을 유추할 수 있는 충분 한 정보를 갖지만 형식 주석을 추가 하 여 명시적으로 형식을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="cee9b-154">속성 집합 접근자 사용</span><span class="sxs-lookup"><span data-stu-id="cee9b-154">Using Property set Accessors</span></span>

<span data-ttu-id="cee9b-155">연산자를 사용 하 여 접근자를 제공 하는 속성을 설정할 수 있습니다 `set` `<-` .</span><span class="sxs-lookup"><span data-stu-id="cee9b-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="cee9b-156">출력은 **20** 입니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="cee9b-157">추상 속성</span><span class="sxs-lookup"><span data-stu-id="cee9b-157">Abstract Properties</span></span>

<span data-ttu-id="cee9b-158">속성은 abstract 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-158">Properties can be abstract.</span></span> <span data-ttu-id="cee9b-159">메서드와 마찬가지로, `abstract` 속성에 연결 된 가상 디스패치가 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="cee9b-160">추상 속성은 실제로 추상 속성이 될 수 있습니다. 즉, 동일한 클래스에 정의가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="cee9b-161">따라서 이러한 속성을 포함 하는 클래스는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="cee9b-162">또는 abstract는 속성이 가상 임을 의미할 수 있으며,이 경우 정의가 동일한 클래스에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="cee9b-163">추상 속성은 private이 아니어야 하며 한 접근자가 abstract 인 경우 다른 접근자도 추상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cee9b-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="cee9b-164">추상 클래스에 대 한 자세한 내용은 [추상 클래스](../abstract-classes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cee9b-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="cee9b-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cee9b-165">See also</span></span>

- [<span data-ttu-id="cee9b-166">멤버</span><span class="sxs-lookup"><span data-stu-id="cee9b-166">Members</span></span>](index.md)
- [<span data-ttu-id="cee9b-167">메서드</span><span class="sxs-lookup"><span data-stu-id="cee9b-167">Methods</span></span>](methods.md)
