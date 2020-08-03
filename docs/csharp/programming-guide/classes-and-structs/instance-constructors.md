---
title: 인스턴스 생성자 - C# 프로그래밍 가이드
description: C#의 인스턴스 생성자는 new 식을 사용하여 class의 개체를 만들 때 인스턴스 멤버 변수를 만들고 초기화합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: d70e786446fb198afb4e0311757cacb65b706f47
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864204"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="3db7c-103">인스턴스 생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3db7c-103">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="3db7c-104">인스턴스 생성자는 [new](../../language-reference/operators/new-operator.md) 식을 사용하여 [class](../../language-reference/keywords/class.md)의 개체를 만들 때 인스턴스 멤버 변수를 만들고 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-104">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="3db7c-105">[정적](../../language-reference/keywords/static.md) 클래스 또는 비정적 클래스의 정적 변수를 초기화하려면 정적 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-105">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="3db7c-106">자세한 내용은 [정적 생성자](./static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3db7c-106">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="3db7c-107">다음 예제에서는 인스턴스 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-107">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> <span data-ttu-id="3db7c-108">이해를 돕기 위해 이 클래스에는 public 필드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="3db7c-109">public 필드를 사용하면 어디에 있든 프로그램 내의 모든 메서드가 확인되지 않고 개체의 내부 작업에 무제한 액세스할 수 있으므로 프로그래밍 시 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="3db7c-110">데이터 멤버는 일반적으로 private여야 하며, 클래스 메서드 및 속성을 통해서만 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="3db7c-111">`Coords` 클래스를 기반으로 하는 개체를 만들 때마다 이 인스턴스 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-111">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="3db7c-112">인수를 사용하지 않는 이러한 생성자를 *매개 변수 없는 생성자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-112">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="3db7c-113">그러나 추가 생성자를 제공하는 것이 유용한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="3db7c-114">예를 들어 데이터 멤버에 대한 초기 값을 지정할 수 있는 생성자를 `Coords` 클래스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-114">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 <span data-ttu-id="3db7c-115">이렇게 하면 기본 또는 특정 초기 값으로 `Coords` 개체를 다음과 같이 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-115">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 <span data-ttu-id="3db7c-116">클래스에 생성자가 없는 경우 매개 변수 없는 생성자가 자동으로 생성되고 개체 필드를 초기화하는 데 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-116">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="3db7c-117">예를 들어 [int](../../language-reference/builtin-types/integral-numeric-types.md)가 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-117">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="3db7c-118">형식 기본값에 대한 자세한 내용은 [C# 형식의 기본값](../../language-reference/builtin-types/default-values.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3db7c-118">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="3db7c-119">따라서 `Coords` 클래스 매개 변수 없는 생성자는 모든 데이터 멤버를 0으로 초기화하기 때문에 클래스의 작동 방식을 변경하지 않고 완전히 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-119">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="3db7c-120">여러 생성자를 사용하는 전체 예제는 이 항목의 뒷부분에 있는 예제 1에서 제공되고, 자동으로 생성된 생성자의 예는 예제 2에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-120">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="3db7c-121">인스턴스 생성자를 사용하여 기본 클래스의 인스턴스 생성자를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-121">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="3db7c-122">클래스 생성자는 다음과 같이 이니셜라이저를 통해 기본 클래스의 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-122">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 <span data-ttu-id="3db7c-123">이 예제에서 `Circle` 클래스는 `Circle`이 파생되는 `Shape`에서 제공하는 생성자에 반경과 높이를 나타내는 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-123">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="3db7c-124">`Shape` 및 `Circle`을 사용하는 전체 예제는 이 항목에서 예제 3으로 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-124">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="3db7c-125">예제 1</span><span class="sxs-lookup"><span data-stu-id="3db7c-125">Example 1</span></span>  
 <span data-ttu-id="3db7c-126">다음 예제에서는 인수 없는 클래스 생성자와 두 개의 인수를 사용하는 클래스 생성자가 있는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-126">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a><span data-ttu-id="3db7c-127">예제 2</span><span class="sxs-lookup"><span data-stu-id="3db7c-127">Example 2</span></span>  
 <span data-ttu-id="3db7c-128">이 예제에서 `Person` 클래스에는 생성자가 없으며, 매개 변수 없는 생성자가 자동으로 제공되고 필드는 해당 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-128">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 <span data-ttu-id="3db7c-129">`age`의 기본값은 `0`이고, `name`의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-129">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="3db7c-130">예제 3</span><span class="sxs-lookup"><span data-stu-id="3db7c-130">Example 3</span></span>  
 <span data-ttu-id="3db7c-131">다음 예제에서는 기본 클래스 이니셜라이저를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="3db7c-132">`Circle` 클래스는 제네릭 클래스 `Shape`에서 파생되고, `Cylinder` 클래스는 `Circle` 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="3db7c-133">각 파생 클래스의 생성자는 해당 기본 클래스 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3db7c-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 <span data-ttu-id="3db7c-134">기본 클래스 생성자 호출에 대한 추가 예제는 [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), [base](../../language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3db7c-134">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db7c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3db7c-135">See also</span></span>

- [<span data-ttu-id="3db7c-136">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3db7c-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3db7c-137">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="3db7c-137">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="3db7c-138">생성자</span><span class="sxs-lookup"><span data-stu-id="3db7c-138">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="3db7c-139">종료자</span><span class="sxs-lookup"><span data-stu-id="3db7c-139">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="3db7c-140">static</span><span class="sxs-lookup"><span data-stu-id="3db7c-140">static</span></span>](../../language-reference/keywords/static.md)
