---
title: Override 및 New 키워드를 사용하여 버전 관리 - C# 프로그래밍 가이드
description: C#에서의 기본 및 파생 클래스에 대한 버전 관리와 메서드가 상속된 메서드를 재정의할지 숨길지 지정하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, versioning
- C# language, override and new
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
ms.openlocfilehash: 13321cdc83637105a2b981902ce984e6a90a25d9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181819"
---
# <a name="versioning-with-the-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="e1a05-103">Override 및 New 키워드를 사용하여 버전 관리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e1a05-103">Versioning with the Override and New Keywords (C# Programming Guide)</span></span>

<span data-ttu-id="e1a05-104">C# 언어는 서로 다른 라이브러리의 [기본](../../language-reference/keywords/base.md) 및 파생 클래스 간 버전 관리를 개발하고 이전 버전과의 호환성을 유지할 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-104">The C# language is designed so that versioning between [base](../../language-reference/keywords/base.md) and derived classes in different libraries can evolve and maintain backward compatibility.</span></span> <span data-ttu-id="e1a05-105">예를 들어 파생 클래스의 멤버와 동일한 이름을 가진 기본 [클래스](../../language-reference/keywords/class.md)에 새 멤버가 추가되면 C#이 완전히 지원되고 예기치 않은 동작이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-105">This means, for example, that the introduction of a new member in a base [class](../../language-reference/keywords/class.md) with the same name as a member in a derived class is completely supported by C# and does not lead to unexpected behavior.</span></span> <span data-ttu-id="e1a05-106">따라서 클래스는 메서드가 상속된 메서드를 재정의할지 아니면 메서드가 유사한 이름의 상속된 메서드를 숨기는 새 메서드인지를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-106">It also means that a class must explicitly state whether a method is intended to override an inherited method, or whether a method is a new method that hides a similarly named inherited method.</span></span>  
  
 <span data-ttu-id="e1a05-107">C#에서 파생 클래스는 기본 클래스 메서드와 동일한 이름 가진 메서드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-107">In C#, derived classes can contain methods with the same name as base class methods.</span></span>  

- <span data-ttu-id="e1a05-108">파생 클래스의 메서드 앞에 [new](../../language-reference/keywords/new-modifier.md) 또는 [override](../../language-reference/keywords/override.md) 키워드가 있으면 컴파일러는 경고를 표시하고 메서드는 `new` 키워드가 있는 것처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-108">If the method in the derived class is not preceded by [new](../../language-reference/keywords/new-modifier.md) or [override](../../language-reference/keywords/override.md) keywords, the compiler will issue a warning and the method will behave as if the `new` keyword were present.</span></span>  
  
- <span data-ttu-id="e1a05-109">파생 클래스의 메서드 앞에 `new` 키워드가 있는 경우 이 메서드는 기본 클래스의 메서드와 독립적으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-109">If the method in the derived class is preceded with the `new` keyword, the method is defined as being independent of the method in the base class.</span></span>  
  
- <span data-ttu-id="e1a05-110">파생 클래스의 메서드 앞에 `override` 키워드가 있는 경우 파생 클래스의 개체는 기본 클래스 메서드 대신 해당 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-110">If the method in the derived class is preceded with the `override` keyword, objects of the derived class will call that method instead of the base class method.</span></span>  

- <span data-ttu-id="e1a05-111">`override` 키워드를 파생 클래스의 메서드에 적용하려면 기본 클래스 메서드가 [가상](../../language-reference/keywords/virtual.md)으로 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-111">In order to apply the `override` keyword to the method in the derived class, the base class method must be defined [virtual](../../language-reference/keywords/virtual.md).</span></span>
  
- <span data-ttu-id="e1a05-112">기본 클래스 메서드는 `base` 키워드를 사용하여 파생 클래스 내에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-112">The base class method can be called from within the derived class using the `base` keyword.</span></span>  
  
- <span data-ttu-id="e1a05-113">`override`, `virtual`, 및 `new` 키워드는 속성, 인덱서 및 이벤트에도 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-113">The `override`, `virtual`, and `new` keywords can also be applied to properties, indexers, and events.</span></span>  
  
 <span data-ttu-id="e1a05-114">기본적으로 C# 메서드는 가상입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-114">By default, C# methods are not virtual.</span></span> <span data-ttu-id="e1a05-115">메서드가 가상으로 선언되면 이 메서드를 상속하는 클래스는 자체 버전을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-115">If a method is declared as virtual, any class inheriting the method can implement its own version.</span></span> <span data-ttu-id="e1a05-116">메서드를 가상으로 만들려면 기본 클래스의 메서드 선언에서 `virtual` 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-116">To make a method virtual, the `virtual` modifier is used in the method declaration of the base class.</span></span> <span data-ttu-id="e1a05-117">파생 클래스는 `override` 키워드를 사용하여 기본 가상 메서드를 재정의하거나 `new` 키워드를 사용하여 기본 클래스에서 가상 메서드를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-117">The derived class can then override the base virtual method by using the `override` keyword or hide the virtual method in the base class by using the `new` keyword.</span></span> <span data-ttu-id="e1a05-118">`override` 키워드와 `new` 키워드가 모두 지정되지 않은 경우 컴파일러는 경고를 표시하고 파생 클래스의 메서드는 기본 클래스의 메서드를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-118">If neither the `override` keyword nor the `new` keyword is specified, the compiler will issue a warning and the method in the derived class will hide the method in the base class.</span></span>  
  
 <span data-ttu-id="e1a05-119">이를 실증적으로 보여 주기 위해, A 회사가 프로그램에서 사용하는 `GraphicsClass`라는 클래스를 만들었다고 잠시 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-119">To demonstrate this in practice, assume for a moment that Company A has created a class named `GraphicsClass`, which your program uses.</span></span> <span data-ttu-id="e1a05-120">다음은 `GraphicsClass`입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-120">The following is `GraphicsClass`:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#27)]  
  
 <span data-ttu-id="e1a05-121">회사에서 이 클래스를 사용하며, 사용자는 이를 사용하여 고유한 클래스를 파생시키고 새 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-121">Your company uses this class, and you use it to derive your own class, adding a new method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#28)]  
  
 <span data-ttu-id="e1a05-122">회사 A에서 `GraphicsClass`의 새 버전을 출시할 때까지 애플리케이션은 문제없이 사용됩니다. 새 버전은 다음 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-122">Your application is used without problems, until Company A releases a new version of `GraphicsClass`, which resembles the following code:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#29)]  
  
 <span data-ttu-id="e1a05-123">`GraphicsClass`의 새 버전에는 이제 `DrawRectangle`이라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-123">The new version of `GraphicsClass` now contains a method named `DrawRectangle`.</span></span> <span data-ttu-id="e1a05-124">처음에는 아무것도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-124">Initially, nothing occurs.</span></span> <span data-ttu-id="e1a05-125">새 버전은 여전히 이전 버전과 호환되는 이진입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-125">The new version is still binary compatible with the old version.</span></span> <span data-ttu-id="e1a05-126">새 클래스가 해당 컴퓨터 시스템에 설치되어 있어도 사용자가 배포한 소프트웨어는 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-126">Any software that you have deployed will continue to work, even if the new class is installed on those computer systems.</span></span> <span data-ttu-id="e1a05-127">`DrawRectangle` 메서드에 대한 호출은 파생 클래스에서 계속 해당 버전을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-127">Any existing calls to the method `DrawRectangle` will continue to reference your version, in your derived class.</span></span>  
  
 <span data-ttu-id="e1a05-128">그러나 `GraphicsClass`의 새 버전을 사용하여 애플리케이션을 다시 컴파일하자마자 컴파일러에서 경고(CS0108)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-128">However, as soon as you recompile your application by using the new version of `GraphicsClass`, you will receive a warning from the compiler, CS0108.</span></span> <span data-ttu-id="e1a05-129">이 경고는 `DrawRectangle` 메서드가 애플리케이션에서 어떻게 작동할지를 고려해야 한다고 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-129">This warning informs you that you have to consider how you want your `DrawRectangle` method to behave in your application.</span></span>  
  
 <span data-ttu-id="e1a05-130">메서드가 새로운 기본 클래스 메서드를 재정의하도록 하려면 `override` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-130">If you want your method to override the new base class method, use the `override` keyword:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#30)]  
  
 <span data-ttu-id="e1a05-131">`override` 키워드는 `YourDerivedGraphicsClass`에서 파생된 개체가 `DrawRectangle`의 파생 클래스 버전을 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-131">The `override` keyword makes sure that any objects derived from `YourDerivedGraphicsClass` will use the derived class version of `DrawRectangle`.</span></span> <span data-ttu-id="e1a05-132">`YourDerivedGraphicsClass`에서 파생된 개체는 기본 키워드를 사용하여 여전히 `DrawRectangle`의 기본 클래스 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-132">Objects derived from `YourDerivedGraphicsClass` can still access the base class version of `DrawRectangle` by using the base keyword:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#44)]  
  
 <span data-ttu-id="e1a05-133">메서드가 새 기본 클래스 메서드를 재정의하도록 하지 않으려면 다음 고려 사항을 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a05-133">If you do not want your method to override the new base class method, the following considerations apply.</span></span> <span data-ttu-id="e1a05-134">두 메서드 간 혼동을 피하려면 메서드의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-134">To avoid confusion between the two methods, you can rename your method.</span></span> <span data-ttu-id="e1a05-135">이 방법은 시간이 오래 걸리고 오류가 발생하기 쉬우며 어떤 경우에는 실용적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-135">This can be time-consuming and error-prone, and just not practical in some cases.</span></span> <span data-ttu-id="e1a05-136">그러나 프로젝트 규모가 비교적 작으면 Visual Studio 리팩터링 옵션을 사용하여 메서드의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-136">However, if your project is relatively small, you can use Visual Studio's Refactoring options to rename the method.</span></span> <span data-ttu-id="e1a05-137">자세한 내용은 [클래스 및 형식 리팩터링(클래스 디자이너)](/visualstudio/ide/class-designer/refactoring-classes-and-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a05-137">For more information, see [Refactoring Classes and Types (Class Designer)](/visualstudio/ide/class-designer/refactoring-classes-and-types).</span></span>  
  
 <span data-ttu-id="e1a05-138">또는 파생 클래스 정의에서 `new` 키워드를 사용하여 경고를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-138">Alternatively, you can prevent the warning by using the keyword `new` in your derived class definition:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#31)]  
  
 <span data-ttu-id="e1a05-139">`new` 키워드는 사용자 정의가 기본 클래스에 포함된 정의를 숨긴다는 것을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-139">Using the `new` keyword tells the compiler that your definition hides the definition that is contained in the base class.</span></span> <span data-ttu-id="e1a05-140">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-140">This is the default behavior.</span></span>  
  
## <a name="override-and-method-selection"></a><span data-ttu-id="e1a05-141">재정의 및 메서드 선택</span><span class="sxs-lookup"><span data-stu-id="e1a05-141">Override and Method Selection</span></span>  

 <span data-ttu-id="e1a05-142">클래스에서 메서드 이름을 지정할 때, 동일한 이름을 가진 두 개의 메서드가 있고 전달된 매개 변수와 호환되는 매개 변수가 있는 경우와 같이 둘 이상의 메서드가 호출과 호환되는 경우, C# 컴파일러는 호출할 수 있는 최상의 메서드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-142">When a method is named on a class, the C# compiler selects the best method to call if more than one method is compatible with the call, such as when there are two methods with the same name, and parameters that are compatible with the parameter passed.</span></span> <span data-ttu-id="e1a05-143">다음 메서드는 호환 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-143">The following methods would be compatible:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#32)]  
  
 <span data-ttu-id="e1a05-144">`Derived`의 인스턴스에서 `DoWork`가 호출되면 C# 컴파일러는 호출이 원래 `Derived`에 선언된 `DoWork` 버전과 호환되도록 만들려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-144">When `DoWork` is called on an instance of `Derived`, the C# compiler will first try to make the call compatible with the versions of `DoWork` declared originally on `Derived`.</span></span> <span data-ttu-id="e1a05-145">재정의 메서드는 클래스에서 선언된 것으로 간주되지 않습니다. 재정의 메서드는 기본 클래스에서 선언된 메서드의 새로운 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-145">Override methods are not considered as declared on a class, they are new implementations of a method declared on a base class.</span></span> <span data-ttu-id="e1a05-146">C# 컴파일러는 메서드 호출을 `Derived`의 원래 메서드와 일치시킬 수 없는 경우에만, 재정의된 메서드에 대한 호출을 동일한 이름 및 호환되는 매개 변수와 일치시키려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-146">Only if the C# compiler cannot match the method call to an original method on `Derived` will it try to match the call to an overridden method with the same name and compatible parameters.</span></span> <span data-ttu-id="e1a05-147">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="e1a05-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#33)]  
  
 <span data-ttu-id="e1a05-148">`val` 변수를 double로 암시적으로 변환할 수 있으므로 C# 컴파일러는 `DoWork(int)` 대신 `DoWork(double)`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-148">Because the variable `val` can be converted to a double implicitly, the C# compiler calls `DoWork(double)` instead of `DoWork(int)`.</span></span> <span data-ttu-id="e1a05-149">이것을 방지할 수 있는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-149">There are two ways to avoid this.</span></span> <span data-ttu-id="e1a05-150">첫째, 가상 메서드와 동일한 이름을 가진 새 메서드를 선언하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-150">First, avoid declaring new methods with the same name as virtual methods.</span></span> <span data-ttu-id="e1a05-151">둘째, `Derived`의 인스턴스를 `Base`에 캐스팅하여 기본 클래스 메서드 목록을 검색하게 함으로써 가상 메서드를 호출하도록 C# 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-151">Second, you can instruct the C# compiler to call the virtual method by making it search the base class method list by casting the instance of `Derived` to `Base`.</span></span> <span data-ttu-id="e1a05-152">메서드는 가상이므로 `Derived`에서 `DoWork(int)`의 구현이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1a05-152">Because the method is virtual, the implementation of `DoWork(int)` on `Derived` will be called.</span></span> <span data-ttu-id="e1a05-153">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="e1a05-153">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#34)]  
  
 <span data-ttu-id="e1a05-154">`new` 및 `override`의 추가 예제는 [Override 및 New 키워드를 사용해야 하는 경우](./knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a05-154">For more examples of `new` and `override`, see [Knowing When to Use Override and New Keywords](./knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a05-155">참조</span><span class="sxs-lookup"><span data-stu-id="e1a05-155">See also</span></span>

- [<span data-ttu-id="e1a05-156">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e1a05-156">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e1a05-157">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="e1a05-157">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="e1a05-158">메서드</span><span class="sxs-lookup"><span data-stu-id="e1a05-158">Methods</span></span>](./methods.md)
- [<span data-ttu-id="e1a05-159">상속</span><span class="sxs-lookup"><span data-stu-id="e1a05-159">Inheritance</span></span>](./inheritance.md)
