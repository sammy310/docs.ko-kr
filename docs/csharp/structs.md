---
title: 구조체 - C# 가이드
description: 구조체 형식 및 만드는 방법을 알아봅니다.
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: cdfe2a763058b8f568ede2ff93c918c2dae874f7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346898"
---
# <a name="structs"></a><span data-ttu-id="c65c0-103">구조체</span><span class="sxs-lookup"><span data-stu-id="c65c0-103">Structs</span></span>

<span data-ttu-id="c65c0-104">*struct*가 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-104">A *struct* is a value type.</span></span> <span data-ttu-id="c65c0-105">구조체를 만드는 경우 구조체가 할당된 변수에 구조체의 실제 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-105">When a struct is created, the variable to which the struct is assigned holds the struct's actual data.</span></span> <span data-ttu-id="c65c0-106">구조체를 새 변수에 할당하면 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-106">When the struct is assigned to a new variable, it is copied.</span></span> <span data-ttu-id="c65c0-107">따라서 새 변수와 원래 변수에 동일한 데이터의 두 가지 별도 복사본이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-107">The new variable and the original variable therefore contain two separate copies of the same data.</span></span> <span data-ttu-id="c65c0-108">한 복사본의 변경 내용은 다른 복사본에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-108">Changes made to one copy do not affect the other copy.</span></span>

<span data-ttu-id="c65c0-109">값 형식 변수에는 해당 값이 직접 포함되므로, 변수가 선언된 컨텍스트에 관계없이 메모리가 인라인으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-109">Value type variables directly contain their values, which means that the memory is allocated inline in whatever context the variable is declared.</span></span> <span data-ttu-id="c65c0-110">값 형식 변수에 대한 별도 힙 할당이나 가비지 수집 오버헤드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-110">There is no separate heap allocation or garbage collection overhead for value-type variables.</span></span>

<span data-ttu-id="c65c0-111">값 형식에는 [struct](language-reference/keywords/struct.md) 및 [enum](language-reference/builtin-types/enum.md)의 두 가지 범주가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-111">There are two categories of value types: [struct](language-reference/keywords/struct.md) and [enum](language-reference/builtin-types/enum.md).</span></span>

<span data-ttu-id="c65c0-112">기본 제공 숫자 형식은 구조체이며, 액세스할 수 있는 속성과 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-112">The built-in numeric types are structs, and they have properties and methods that you can access:</span></span>

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

<span data-ttu-id="c65c0-113">하지만 단순 비집계 형식처럼 값을 선언하고 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-113">But you declare and assign values to them as if they were simple non-aggregate types:</span></span>

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

<span data-ttu-id="c65c0-114">값 형식은 *sealed*이므로, 예를 들어 <xref:System.Int32>에서 형식을 파생시킬 수 없으며 구조체는 <xref:System.ValueType>에서만 상속할 수 있기 때문에 사용자 정의 클래스 또는 구조체에서 상속하는 구조체를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-114">Value types are *sealed*, which means, for example, that you cannot derive a type from <xref:System.Int32>, and you cannot define a struct to inherit from any user-defined class or struct because a struct can only inherit from <xref:System.ValueType>.</span></span> <span data-ttu-id="c65c0-115">그러나 구조체는 하나 이상의 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-115">However, a struct can implement one or more interfaces.</span></span> <span data-ttu-id="c65c0-116">구조체 형식을 인터페이스 형식으로 캐스팅할 수 있습니다. 이 경우 *boxing* 작업은 관리되는 힙의 참조 형식 개체 내에 구조체를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-116">You can cast a struct type to an interface type; this causes a *boxing* operation to wrap the struct inside a reference type object on the managed heap.</span></span> <span data-ttu-id="c65c0-117">boxing 작업은 <xref:System.Object>를 입력 매개 변수로 사용하는 메서드에 값 형식을 전달할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-117">Boxing operations occur when you pass a value type to a method that takes an <xref:System.Object> as an input parameter.</span></span> <span data-ttu-id="c65c0-118">자세한 내용은 [boxing 및 unboxing](./programming-guide/types/boxing-and-unboxing.md )을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c65c0-118">For more information, see [Boxing and Unboxing](./programming-guide/types/boxing-and-unboxing.md ).</span></span>

<span data-ttu-id="c65c0-119">[struct](./language-reference/keywords/struct.md) 키워드를 사용하여 고유한 사용자 지정 값 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-119">You use the [struct](./language-reference/keywords/struct.md) keyword to create your own custom value types.</span></span> <span data-ttu-id="c65c0-120">일반적으로 구조체는 다음 예제와 같이 소규모 관련 변수 집합의 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-120">Typically, a struct is used as a container for a small set of related variables, as shown in the following example:</span></span>

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

<span data-ttu-id="c65c0-121">.NET Framework의 값 형식에 대한 자세한 내용은 [CTS(공용 형식 시스템)](../standard/common-type-system.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c65c0-121">For more information about value types in the .NET Framework, see [Common Type System](../standard/common-type-system.md).</span></span>

<span data-ttu-id="c65c0-122">구조체가 클래스보다 더 제한적이지만 구조체는 클래스와 동일한 구문을 대부분 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-122">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>

- <span data-ttu-id="c65c0-123">구조체 선언 내에서 필드가 `const` 또는 `static`으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-123">Within a struct declaration, fields cannot be initialized unless they are declared as `const` or `static`.</span></span>

- <span data-ttu-id="c65c0-124">구조체는 매개 변수 없는 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-124">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>

- <span data-ttu-id="c65c0-125">할당 시 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-125">Structs are copied on assignment.</span></span> <span data-ttu-id="c65c0-126">구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-126">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="c65c0-127">Dictionary<string, myStruct> 등의 값 형식 컬렉션으로 작업하는 경우 이 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-127">This is important to remember when working with collections of value types such as Dictionary<string, myStruct>.</span></span>

- <span data-ttu-id="c65c0-128">구조체는 값 형식이고 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-128">Structs are value types and classes are reference types.</span></span>

- <span data-ttu-id="c65c0-129">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-129">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c65c0-130">.NET Core 2.1 이상에서 구조체 형식은 [new 연산자](language-reference/operators/new-operator.md) 또는 [기본 리터럴](language-reference/operators/default.md#default-literal)을 사용하거나 각 프라이빗 필드를 초기화하여 인스턴스화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-130">In .NET Core 2.1 and later, a struct type must be instantiated by using the [new operator](language-reference/operators/new-operator.md) or [default literal](language-reference/operators/default.md#default-literal), or by initializing each of its private fields.</span></span> <span data-ttu-id="c65c0-131">자세한 내용은 [버전 2.0에서 2.1로 마이그레이션 시 호환성이 손상되는 변경](../core/compatibility/2.0-2.1.md#corefx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c65c0-131">For more information, see [Breaking changes for migration from version 2.0 to 2.1](../core/compatibility/2.0-2.1.md#corefx).</span></span>

- <span data-ttu-id="c65c0-132">구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-132">Structs can declare constructors that have parameters.</span></span>

- <span data-ttu-id="c65c0-133">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-133">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="c65c0-134">모든 구조체는 <xref:System.Object>에서 상속하는 <xref:System.ValueType>에서 직접 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-134">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>

- <span data-ttu-id="c65c0-135">구조체는 클래스와 마찬가지로 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-135">A struct, like a class, can implement interfaces.</span></span>

## <a name="nullable-value-types"></a><span data-ttu-id="c65c0-136">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="c65c0-136">Nullable value types</span></span>

<span data-ttu-id="c65c0-137">일반적인 값 형식은 [null](language-reference/keywords/null.md) 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-137">Ordinary value types cannot have a value of [null](language-reference/keywords/null.md).</span></span> <span data-ttu-id="c65c0-138">그러나 형식 뒤에 `?`를 추가하면 null 허용 값 형식을</span><span class="sxs-lookup"><span data-stu-id="c65c0-138">However, you can create nullable value types by affixing a `?` after the type.</span></span> <span data-ttu-id="c65c0-139">예를 들어 `int?`는 [null](./language-reference/keywords/null.md) 값을 가질 수도 있는 `int` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-139">For example, `int?` is an `int` type that can also have the value [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="c65c0-140">nullable 값 형식은 제네릭 구조체 형식 <xref:System.Nullable%601>의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-140">Nullable value types are instances of the generic struct type <xref:System.Nullable%601>.</span></span> <span data-ttu-id="c65c0-141">nullable 값 형식은 특히 숫자 값이 null이거나 정의되지 않을 수 있는 데이터베이스에 데이터를 전달하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c65c0-141">Nullable value types are especially useful when you are passing data to and from databases in which numeric values might be null or undefined.</span></span> <span data-ttu-id="c65c0-142">자세한 내용은 [nullable 값 형식](language-reference/builtin-types/nullable-value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c65c0-142">For more information, see [Nullable value types](language-reference/builtin-types/nullable-value-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c65c0-143">참조</span><span class="sxs-lookup"><span data-stu-id="c65c0-143">See also</span></span>

- [<span data-ttu-id="c65c0-144">클래스</span><span class="sxs-lookup"><span data-stu-id="c65c0-144">Classes</span></span>](programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="c65c0-145">기본 형식</span><span class="sxs-lookup"><span data-stu-id="c65c0-145">Basic Types</span></span>](basic-types.md)
