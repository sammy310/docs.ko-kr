---
title: 추상 및 봉인 클래스와 클래스 멤버 - C# 프로그래밍 가이드
description: C#의 추상 키워드를 사용하여 불완전한 클래스와 클래스 멤버를 만듭니다. Sealed 키워드는 이전 가상 클래스 또는 클래스 멤버의 상속을 방지합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: 391a8ccbb1fbe6626d1cd5a4b6fcfd9ace3506e6
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474490"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="8144e-104">추상 및 봉인 클래스와 클래스 멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8144e-104">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="8144e-105">[abstract](../../language-reference/keywords/abstract.md) 키워드를 사용하면, 불완전하여 파생 클래스에서 구현해야 하는 클래스 및 [클래스](../../language-reference/keywords/class.md) 멤버를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-105">The [abstract](../../language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="8144e-106">[sealed](../../language-reference/keywords/sealed.md) 키워드를 사용하면, 이전에 [virtual](../../language-reference/keywords/virtual.md)로 표시되었던 클래스나 특정 클래스 멤버의 상속을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-106">The [sealed](../../language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="8144e-107">추상 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="8144e-107">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="8144e-108">클래스 정의 앞에 `abstract` 키워드를 배치하여 클래스를 추상으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-108">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="8144e-109">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="8144e-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 <span data-ttu-id="8144e-110">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-110">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="8144e-111">추상 클래스의 목적은 여러 파생 클래스에서 공유할 수 있는 기본 클래스의 공통적인 정의를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-111">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="8144e-112">예를 들어 클래스 라이브러리에서 여러 자체 함수에 매개 변수로 사용되는 추상 클래스를 정의한 다음 해당 라이브러리를 사용하는 프로그래머가 파생 클래스를 만들어 클래스의 고유 구현을 제공하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-112">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="8144e-113">추상 클래스에서는 추상 메서드도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-113">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="8144e-114">메서드의 반환 형식 앞에 `abstract` 키워드를 추가하면 추상 메서드가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-114">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="8144e-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="8144e-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 <span data-ttu-id="8144e-116">추상 메서드에는 구현이 없으므로 메서드 정의 다음에는 일반적인 메서드 블록 대신 세미콜론이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="8144e-117">추상 클래스의 파생 클래스에서는 모든 추상 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="8144e-118">추상 클래스에서 기본 클래스의 가상 메서드를 상속하는 경우 추상 클래스에서는 추상 메서드를 사용하여 가상 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="8144e-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="8144e-119">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 <span data-ttu-id="8144e-120">`virtual` 메서드는 `abstract`로 선언되어도 추상 클래스에서 상속된 모든 클래스에 대해 여전히 가상입니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-120">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="8144e-121">추상 메서드를 상속하는 클래스에서는 메서드의 원본 구현에 액세스할 수 없습니다. 앞의 예제에서 F 클래스의 `DoWork`에서는 D 클래스의 `DoWork`를 호출할 수 없습니다. 따라서 추상 클래스는 파생 클래스에서 가상 메서드에 대한 새 메서드 구현을 반드시 제공하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-121">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="8144e-122">봉인 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="8144e-122">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="8144e-123">클래스 정의 앞에 `sealed` 키워드를 배치하여 클래스를 [sealed](../../language-reference/keywords/sealed.md)로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-123">Classes can be declared as [sealed](../../language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="8144e-124">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="8144e-124">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 <span data-ttu-id="8144e-125">봉인 클래스는 기본 클래스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-125">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="8144e-126">그러므로 추상 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-126">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="8144e-127">봉인 클래스는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-127">Sealed classes prevent derivation.</span></span> <span data-ttu-id="8144e-128">봉인 클래스는 기본 클래스로 사용될 수 없으므로 일부 런타임 최적화에서는 봉인 클래스 멤버 호출이 약간 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-128">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="8144e-129">기본 클래스의 가상 멤버를 재정의하는 파생 클래스의 메서드, 인덱서, 속성 또는 이벤트는 해당 멤버를 봉인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-129">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="8144e-130">이렇게 하면 이후에 파생되는 클래스에서는 해당 멤버가 가상이 아니게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-130">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="8144e-131">클래스 멤버 선언에서 [override](../../language-reference/keywords/override.md) 키워드 앞에 `sealed` 키워드를 배치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-131">This is accomplished by putting the `sealed` keyword before the [override](../../language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="8144e-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8144e-132">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="8144e-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8144e-133">See also</span></span>

- [<span data-ttu-id="8144e-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8144e-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8144e-135">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="8144e-135">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="8144e-136">상속</span><span class="sxs-lookup"><span data-stu-id="8144e-136">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="8144e-137">메서드</span><span class="sxs-lookup"><span data-stu-id="8144e-137">Methods</span></span>](./methods.md)
- [<span data-ttu-id="8144e-138">필드</span><span class="sxs-lookup"><span data-stu-id="8144e-138">Fields</span></span>](./fields.md)
- [<span data-ttu-id="8144e-139">추상 속성 정의 방법</span><span class="sxs-lookup"><span data-stu-id="8144e-139">How to define abstract properties</span></span>](./how-to-define-abstract-properties.md)
