---
description: abstract - C# 참조
title: abstract - C# 참조
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 095c4dea838aff4f14833d78fb10a2f831cf5173
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127206"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="cbfdf-103">abstract(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cbfdf-103">abstract (C# Reference)</span></span>
<span data-ttu-id="cbfdf-104">`abstract` 한정자는 수정되는 항목에 누락되거나 불완전한 구현이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-104">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="cbfdf-105">abstract 한정자는 클래스, 메서드, 속성, 인덱서 및 이벤트와 함께 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-105">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="cbfdf-106">클래스 선언에서 `abstract` 한정자를 사용하여 클래스가 자체에서 인스턴스화되지 않고 다른 클래스의 기본 클래스로만 사용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-106">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="cbfdf-107">추상으로 표시된 멤버는 추상 클래스에서 파생된 비 추상 클래스에 의해 구현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-107">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="cbfdf-108">예제</span><span class="sxs-lookup"><span data-stu-id="cbfdf-108">Example</span></span>  
 <span data-ttu-id="cbfdf-109">이 예제에서 `Square` 클래스는 `Shape`에서 파생되므로 `GetArea` 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-109">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="cbfdf-110">다음 기능이 있는 추상 클래스:</span><span class="sxs-lookup"><span data-stu-id="cbfdf-110">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="cbfdf-111">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-111">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="cbfdf-112">추상 클래스에 추상 메서드 및 접근자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="cbfdf-113">[sealed](./sealed.md) 한정자를 사용하여 추상 클래스를 수정할 수는 없습니다. 두 한정자가 상반된 의미가 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-113">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="cbfdf-114">`sealed` 한정자를 사용하면 클래스가 상속되지 않고 `abstract` 한정자를 사용하려면 클래스가 상속되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="cbfdf-115">추상 클래스에서 추상이 아닌 파생 클래스에는 모든 상속된 메서드 및 접근자의 실제 구현이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="cbfdf-116">메서드 또는 속성 선언에서 `abstract` 한정자를 사용하여 메서드 또는 속성에 구현이 포함되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="cbfdf-117">추상 메서드에는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-117">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="cbfdf-118">추상 메서드는 암시적으로 가상 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-118">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="cbfdf-119">추상 메서드 선언은 추상 클래스에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="cbfdf-120">추상 메서드 선언은 실제 구현을 제공하지 않으므로 메서드 본문이 없습니다. 메서드 선언은 세미콜론으로 끝나고 시그니처 뒤에 중괄호({ })가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="cbfdf-121">예:</span><span class="sxs-lookup"><span data-stu-id="cbfdf-121">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="cbfdf-122">구현은 비추상 클래스의 멤버인 메서드 [override](./override.md)에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-122">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="cbfdf-123">추상 메서드 선언에서 [static](./static.md) 또는 [virtual](./virtual.md) 한정자를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-123">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="cbfdf-124">선언 및 호출 구문의 차이점을 제외하고 추상 속성은 추상 메서드처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="cbfdf-125">정적 속성에서 `abstract` 한정자를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="cbfdf-126">[override](./override.md) 한정자를 사용하는 속성 선언을 포함하여 상속된 추상 속성을 파생 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="cbfdf-127">추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="cbfdf-128">추상 클래스는 모든 인터페이스 멤버에 대한 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="cbfdf-129">인터페이스를 구현하는 추상 클래스는 인터페이스 메서드를 추상 메서드에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="cbfdf-130">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="cbfdf-130">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="cbfdf-131">예제</span><span class="sxs-lookup"><span data-stu-id="cbfdf-131">Example</span></span>  
 <span data-ttu-id="cbfdf-132">이 예제에서 `DerivedClass` 클래스는 추상 클래스 `BaseClass`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-132">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="cbfdf-133">추상 클래스에는 추상 메서드 `AbstractMethod` 및 두 개의 추상 속성 `X` 및 `Y`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-133">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="cbfdf-134">앞의 예제에서 다음과 같이 문을 사용하여 추상 클래스를 인스턴스화하려고 하면,</span><span class="sxs-lookup"><span data-stu-id="cbfdf-134">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="cbfdf-135">컴파일러가 추상 클래스 'BaseClass'의 인스턴스를 만들 수 없다는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfdf-135">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="cbfdf-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="cbfdf-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbfdf-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbfdf-137">See also</span></span>

- [<span data-ttu-id="cbfdf-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cbfdf-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cbfdf-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cbfdf-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cbfdf-140">한정자</span><span class="sxs-lookup"><span data-stu-id="cbfdf-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="cbfdf-141">virtual</span><span class="sxs-lookup"><span data-stu-id="cbfdf-141">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="cbfdf-142">override</span><span class="sxs-lookup"><span data-stu-id="cbfdf-142">override</span></span>](./override.md)
- [<span data-ttu-id="cbfdf-143">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="cbfdf-143">C# Keywords</span></span>](./index.md)
