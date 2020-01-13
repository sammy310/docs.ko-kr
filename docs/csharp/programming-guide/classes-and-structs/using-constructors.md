---
title: 생성자 사용 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 7d027a67e533cb1ed7b2cea38112b4f585bf5fbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714634"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="9b2f4-102">생성자 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9b2f4-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="9b2f4-103">[class](../../language-reference/keywords/class.md) 또는 [struct](../../language-reference/keywords/struct.md)가 만들어지면 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="9b2f4-104">생성자는 클래스 또는 구조체와 이름이 같으며 일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="9b2f4-105">다음 예제에서는 간단한 생성자를 사용하여 `Taxi`란 이름의 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="9b2f4-106">그런 다음 [new](../../language-reference/operators/new-operator.md) 연산자를 사용하여 이 클래스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="9b2f4-107">새 개체에 메모리가 할당된 직후 `new` 연산자가 `Taxi` 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="9b2f4-108">매개 변수가 없는 생성자를 *매개 변수 없는 생성자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="9b2f4-109">`new` 연산자를 사용하여 개체가 인스턴스화되고 `new`에 제공된 인수가 없을 때마다 매개 변수가 없는 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="9b2f4-110">자세한 내용은 [인스턴스 생성자](./instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="9b2f4-111">클래스가 [정적](../../language-reference/keywords/static.md)이 아닌 경우 생성자가 없는 클래스에는 클래스 인스턴스화를 사용할 수 있도록 C# 컴파일러에서 공용 매개 변수 없는 생성자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="9b2f4-112">자세한 내용은 [static 클래스 및 static 클래스 멤버](./static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="9b2f4-113">다음과 같이 생성자를 비공개로 설정하여 클래스의 인스턴스화를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="9b2f4-114">자세한 내용은 [전용 생성자](./private-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="9b2f4-115">[struct](../../language-reference/keywords/struct.md) 형식의 생성자는 class 생성자와 비슷하지만, `structs`는 컴파일러에서 자동으로 제공되므로 명시적 매개 변수 없는 생성자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="9b2f4-116">이 생성자는 `struct`의 각 필드를 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="9b2f4-117">자세한 내용은 [기본값 표](../../language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-117">For more information, see [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="9b2f4-118">그러나 이 매개 변수 없는 생성자는 `struct`가 `new`로 인스턴스화될 경우에만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-118">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="9b2f4-119">예를 들어, 이 코드는 <xref:System.Int32>에 매개 변수 없는 생성자를 사용하므로 정수가 초기화되었음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-119">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="9b2f4-120">그러나 다음 코드는 `new`를 사용하지 않으므로, 그리고 초기화되지 않은 개체를 사용하려고 하므로 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="9b2f4-121">또는 `structs` 기반의 개체(모든 기본 제공 숫자 형식 포함)를 초기화하거나 할당한 후 다음 예제와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="9b2f4-122">따라서 값 형식에 대해 매개 변수 없는 생성자를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-122">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="9b2f4-123">클래스와 `structs` 모두 매개 변수를 사용하는 생성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="9b2f4-124">매개 변수를 사용하는 생성자는 `new` 문 또는 [base](../../language-reference/keywords/base.md) 문을 통해 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-124">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="9b2f4-125">클래스 및 `structs`는 여러 생성자를 정의할 수 있으며, 매개 변수 없는 생성자를 정의하는 데에는 둘 다 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-125">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="9b2f4-126">예:</span><span class="sxs-lookup"><span data-stu-id="9b2f4-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="9b2f4-127">다음 문 중 하나를 사용하여 이 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="9b2f4-128">생성자는 `base` 키워드를 사용하여 기본 클래스의 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="9b2f4-129">예:</span><span class="sxs-lookup"><span data-stu-id="9b2f4-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="9b2f4-130">이 예제에서는 생성자의 블록이 실행되기 전에 기본 클래스의 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="9b2f4-131">`base` 키워드는 매개 변수와 함께 또는 매개 변수 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="9b2f4-132">생성자에 대한 매개 변수는 `base`에 대한 매개 변수로 또는 식의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="9b2f4-133">자세한 내용은 [base](../../language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-133">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="9b2f4-134">파생 클래스에서는 `base` 키워드를 사용해 매개 변수 없는 클래스 생성자를 명시적으로 호출하지 않으면, 기본 생성자(있는 경우)가 암시적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="9b2f4-135">즉, 다음과 같은 생성자 선언은 실제로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="9b2f4-136">기본 클래스가 매개 변수 없는 생성자를 제공하지 않으면 파생 클래스는 `base`를 사용해 기본 생성자를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-136">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="9b2f4-137">생성자는 [this](../../language-reference/keywords/this.md) 키워드를 사용해 동일한 개체의 다른 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-137">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="9b2f4-138">`base`와 마찬가지로 `this`도 매개 변수 유무와 상관없이 사용할 수 있으며, 생성자에 대한 매개 변수는 `this`에 대한 매개 변수로 또는 식의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="9b2f4-139">예를 들어, 이전 예제의 두 번째 생성자는 `this`를 사용해 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="9b2f4-140">이전 예제에서 `this` 키워드를 사용하면 이 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="9b2f4-141">생성자는 [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-141">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="9b2f4-142">이러한 액세스 한정자는 클래스의 사용자가 클래스를 생성하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="9b2f4-143">자세한 내용은 [액세스 한정자](./access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-143">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="9b2f4-144">[static](../../language-reference/keywords/static.md) 키워드를 사용하여 생성자를 정적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-144">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="9b2f4-145">정적 생성자는 정적 필드에 액세스하기 직전에 자동으로 호출되며 일반적으로 정적 클래스 멤버를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="9b2f4-146">자세한 내용은 [정적 생성자](./static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-146">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9b2f4-147">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9b2f4-147">C# Language Specification</span></span>  

<span data-ttu-id="9b2f4-148">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [인스턴스 생성자](~/_csharplang/spec/classes.md#instance-constructors) 및 [정적 생성자](~/_csharplang/spec/classes.md#static-constructors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-148">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="9b2f4-149">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b2f4-149">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b2f4-150">참조</span><span class="sxs-lookup"><span data-stu-id="9b2f4-150">See also</span></span>

- [<span data-ttu-id="9b2f4-151">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9b2f4-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9b2f4-152">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="9b2f4-152">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="9b2f4-153">생성자</span><span class="sxs-lookup"><span data-stu-id="9b2f4-153">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="9b2f4-154">종료자</span><span class="sxs-lookup"><span data-stu-id="9b2f4-154">Finalizers</span></span>](./destructors.md)
