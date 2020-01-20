---
title: 구조체 사용 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 22d63465c534090a8918348ea5f050739c0cf01c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964751"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="a21c1-102">구조체 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a21c1-102">Using structs (C# Programming Guide)</span></span>

<span data-ttu-id="a21c1-103">`struct` 형식은 `Point`, `Rectangle`, `Color`등의 간단한 개체를 나타내는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="a21c1-104">점을 [자동으로 구현된 속성](../../language-reference/keywords/class.md) 이 있는 [클래스](./auto-implemented-properties.md)로 표현할 수도 있지만 일부 시나리오에서는 [구조체](../../language-reference/keywords/struct.md) 를 사용하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-104">Although it is just as convenient to represent a point as a [class](../../language-reference/keywords/class.md) with [Auto-Implemented Properties](./auto-implemented-properties.md), a [struct](../../language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="a21c1-105">예를 들어 1000개의 `Point` 개체가 있는 배열을 선언하는 경우에는 각 개체를 참조하기 위해 추가 메모리를 할당하게 되며, 이러한 경우 구조체가 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="a21c1-106">.NET에 <xref:System.Drawing.Point>라는 개체가 이미 포함되어 있으므로 이 예제의 구조체 이름은 `Coords`로 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-106">Because .NET already contains an object called <xref:System.Drawing.Point>, the struct in this example is named `Coords` instead.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

<span data-ttu-id="a21c1-107">구조체에 대해 매개 변수가 없는 생성자를 정의하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-107">It is an error to define a parameterless constructor for a struct.</span></span> <span data-ttu-id="a21c1-108">구조체 본문에서 인스턴스 필드를 초기화해도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="a21c1-109">외부에서 액세스할 수 있는 구조체 멤버는 매개 변수화된 생성자, 암시적 매개 변수 없는 생성자, [개체 이니셜라이저](object-and-collection-initializers.md)를 사용하거나 구조체가 선언된 후 멤버에 개별적으로 액세스하는 방법으로만 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, parameterless constructor, an [object initializer](object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="a21c1-110">모든 전용 또는 달리 액세스할 수 없는 멤버를 사용하려면 단독으로 생성자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>

<span data-ttu-id="a21c1-111">[new](../../language-reference/operators/new-operator.md) 연산자를 사용하여 구조체 개체를 생성할 경우 [생성자 시그니처](constructors.md#constructor-syntax)에 따라 구조체 개체가 생성된 후에 적절한 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-111">When you create a struct object using the [new](../../language-reference/operators/new-operator.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](constructors.md#constructor-syntax).</span></span> <span data-ttu-id="a21c1-112">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="a21c1-113">이런 경우에는 생성자를 호출하지 않으므로 할당이 더 효율적으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="a21c1-114">하지만 필드가 할당되지 않은 상태로 남아 있게 되며 개체를 사용하려면 모든 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="a21c1-115">여기에는 속성을 통해 값을 가져오거나 설정할 수 없는 것도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-115">This includes the inability to get or set values through properties.</span></span>

<span data-ttu-id="a21c1-116">매개 변수가 없는 생성자를 사용하여 구조체 개체를 인스턴스화하면 모든 멤버가 해당 [기본값](../../language-reference/builtin-types/default-values.md)에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-116">If you instantiate a struct object using the parameterless constructor, all members are assigned according to their [default values](../../language-reference/builtin-types/default-values.md).</span></span>

<span data-ttu-id="a21c1-117">구조체에 대해 매개 변수가 있는 생성자를 작성하는 경우, 모든 멤버를 명시적으로 초기화해야 합니다. 초기화하지 않으면 하나 이상의 멤버가 할당되지 않은 상태로 유지되고 구조체를 사용할 수 없으므로 컴파일러 오류 [CS0171](../../misc/cs0171.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error [CS0171](../../misc/cs0171.md).</span></span>

<span data-ttu-id="a21c1-118">클래스의 경우와는 달리 구조체에 대한 상속은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="a21c1-119">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="a21c1-120">그러나 구조체는 기본 클래스 <xref:System.Object>에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="a21c1-121">구조체는 클래스에서 인터페이스를 구현하는 것과 동일한 방식으로 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>

<span data-ttu-id="a21c1-122">`struct`키워드를 사용하여 클래스를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="a21c1-123">C#에서 클래스와 구조체는 구문적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="a21c1-124">구조체는 값 형식인 반면 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="a21c1-125">자세한 내용은 [값 형식](../../language-reference/keywords/value-types.md) 및 [참조 형식](../../language-reference/keywords/reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a21c1-125">For more information, see [Value types](../../language-reference/keywords/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>

<span data-ttu-id="a21c1-126">참조 형식 구문이 필요한 경우가 아니라면 작은 클래스는 구조체로 대신 선언하면 시스템에서 보다 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>

## <a name="example-1"></a><span data-ttu-id="a21c1-127">예제 1</span><span class="sxs-lookup"><span data-stu-id="a21c1-127">Example 1</span></span>

<span data-ttu-id="a21c1-128">이 예제에서는 매개 변수가 없는 생성자와 매개 변수가 있는 생성자를 사용한 `struct` 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-128">This example demonstrates `struct` initialization using both parameterless and parameterized constructors.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]

## <a name="example-2"></a><span data-ttu-id="a21c1-129">예제 2</span><span class="sxs-lookup"><span data-stu-id="a21c1-129">Example 2</span></span>

<span data-ttu-id="a21c1-130">이 예제에서는 구조체의 특징에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-130">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="a21c1-131">여기서는 `new` 연산자를 사용하지 않고 Coords 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-131">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="a21c1-132">`struct` 를 `class`로 바꾸면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a21c1-132">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]

## <a name="see-also"></a><span data-ttu-id="a21c1-133">참조</span><span class="sxs-lookup"><span data-stu-id="a21c1-133">See also</span></span>

- [<span data-ttu-id="a21c1-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a21c1-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a21c1-135">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="a21c1-135">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="a21c1-136">구조체</span><span class="sxs-lookup"><span data-stu-id="a21c1-136">Structs</span></span>](structs.md)
