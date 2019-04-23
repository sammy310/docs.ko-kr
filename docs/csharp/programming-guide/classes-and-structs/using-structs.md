---
title: 구조체 사용 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: d2e89c842ae83a5be65c7500e47beb7f302e23be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427190"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="00ac9-102">구조체 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="00ac9-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="00ac9-103">`struct` 형식은 `Point`, `Rectangle`, `Color`등의 간단한 개체를 나타내는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="00ac9-104">점을 [자동으로 구현된 속성](../../../csharp/language-reference/keywords/class.md) 이 있는 [클래스](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)로 표현할 수도 있지만 일부 시나리오에서는 [구조체](../../../csharp/language-reference/keywords/struct.md) 를 사용하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="00ac9-105">예를 들어 1000개의 `Point` 개체가 있는 배열을 선언하는 경우에는 각 개체를 참조하기 위해 추가 메모리를 할당하게 되며, 이러한 경우 구조체가 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="00ac9-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]에 <xref:System.Drawing.Point>라는 개체가 포함되어 있으므로 이 예제의 구조체 이름은 "Coords"로 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "Coords" instead.</span></span>  
  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 <span data-ttu-id="00ac9-107">구조체에 대해 기본 생성자(매개 변수 없음)를 정의하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-107">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="00ac9-108">구조체 본문에서 인스턴스 필드를 초기화해도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="00ac9-109">외부에서 액세스할 수 있는 구조체 멤버는 매개 변수가 있는 생성자, 암시적 기본 생성자 또는 [개체 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 사용하거나 구조체가 선언된 후 멤버에 개별적으로 액세스하는 방법으로만 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, default constructor, an [object initializer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="00ac9-110">모든 전용 또는 달리 액세스할 수 없는 멤버를 사용하려면 단독으로 생성자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>
  
 <span data-ttu-id="00ac9-111">[new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 구조체 개체를 생성할 경우 [생성자 시그니처](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax)에 따라 구조체 개체가 생성된 후에 적절한 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-111">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax).</span></span> <span data-ttu-id="00ac9-112">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="00ac9-113">이런 경우에는 생성자를 호출하지 않으므로 할당이 더 효율적으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="00ac9-114">하지만 필드가 할당되지 않은 상태로 남아 있게 되며 개체를 사용하려면 모든 필드를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="00ac9-115">여기에는 속성을 통해 값을 가져오거나 설정할 수 없는 것도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-115">This includes the inability to get or set values through properties.</span></span>
 
 <span data-ttu-id="00ac9-116">매개 변수가 없는 기본 생성자를 사용하여 구조체 개체를 인스턴스화하는 경우 모든 멤버는 해당 [기본값](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-116">If you instantiate a struct object using the default, parameterless constructor, all members are assigned according to their [default values](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>
  
 <span data-ttu-id="00ac9-117">구조체에 대한 매개 변수를 사용하여 생성자를 작성할 때 모든 멤버를 명시적으로 초기화해야 합니다. 그렇지 않으면 하나 이상의 멤버가 할당되지 않은 상태로 유지되고 구조체를 사용할 수 없으므로 컴파일러 오류 CS0171이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error CS0171.</span></span>  
  
 <span data-ttu-id="00ac9-118">클래스의 경우와는 달리 구조체에 대한 상속은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="00ac9-119">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="00ac9-120">그러나 구조체는 기본 클래스 <xref:System.Object>에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="00ac9-121">구조체는 클래스에서 인터페이스를 구현하는 것과 동일한 방식으로 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="00ac9-122">`struct`키워드를 사용하여 클래스를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="00ac9-123">C#에서 클래스와 구조체는 구문적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="00ac9-124">구조체는 값 형식인 반면 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="00ac9-125">자세한 내용은 [값 형식](../../../csharp/language-reference/keywords/value-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00ac9-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="00ac9-126">참조 형식 구문이 필요한 경우가 아니라면 작은 클래스는 구조체로 대신 선언하면 시스템에서 보다 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="00ac9-127">예제 1</span><span class="sxs-lookup"><span data-stu-id="00ac9-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="00ac9-128">설명</span><span class="sxs-lookup"><span data-stu-id="00ac9-128">Description</span></span>  
 <span data-ttu-id="00ac9-129">이 예제에서는 기본 생성자와 매개 변수가 있는 생성자 둘 다를 사용하여 `struct` 를 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="00ac9-130">코드</span><span class="sxs-lookup"><span data-stu-id="00ac9-130">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="00ac9-131">예제 2</span><span class="sxs-lookup"><span data-stu-id="00ac9-131">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="00ac9-132">설명</span><span class="sxs-lookup"><span data-stu-id="00ac9-132">Description</span></span>  
 <span data-ttu-id="00ac9-133">이 예제에서는 구조체의 특징에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-133">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="00ac9-134">여기서는 `new` 연산자를 사용하지 않고 Coords 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-134">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="00ac9-135">`struct` 를 `class`로 바꾸면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00ac9-135">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="00ac9-136">코드</span><span class="sxs-lookup"><span data-stu-id="00ac9-136">Code</span></span>  
 [!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]  
  
 [!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="00ac9-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00ac9-137">See also</span></span>

- [<span data-ttu-id="00ac9-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="00ac9-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="00ac9-139">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="00ac9-139">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="00ac9-140">구조체</span><span class="sxs-lookup"><span data-stu-id="00ac9-140">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
