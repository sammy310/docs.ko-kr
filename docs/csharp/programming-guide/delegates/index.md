---
title: 대리자 - C# 프로그래밍 가이드
description: C#의 대리자는 매개 변수 목록 및 반환 형식이 있는 메서드를 나타내는 형식입니다. 대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.
ms.date: 02/02/2021
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 0da404146f09028754087c5e24bd05b9289a4220
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456928"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="e64eb-104">대리자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e64eb-104">Delegates (C# Programming Guide)</span></span>

<span data-ttu-id="e64eb-105">[대리자](../../language-reference/builtin-types/reference-types.md)는 특정 매개 변수 목록 및 반환 형식이 있는 메서드에 대한 참조를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-105">A [delegate](../../language-reference/builtin-types/reference-types.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="e64eb-106">대리자를 인스턴스화하면 모든 메서드가 있는 인스턴스를 호환되는 시그니처 및 반환 형식에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-106">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="e64eb-107">대리자 인스턴스를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-107">You can invoke (or call) the method through the delegate instance.</span></span>

<span data-ttu-id="e64eb-108">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-108">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="e64eb-109">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-109">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="e64eb-110">사용자 지정 메서드를 만들면 Windows 컨트롤 같은 클래스가 특정 이벤트가 발생했을 때 해당 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-110">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="e64eb-111">다음 예제에서는 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-111">The following example shows a delegate declaration:</span></span>

[!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]

<span data-ttu-id="e64eb-112">액세스 가능한 클래스 또는 대리자 형식과 일치하는 구조의 모든 메서드는 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-112">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="e64eb-113">메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-113">The method can be either static or an instance method.</span></span> <span data-ttu-id="e64eb-114">이러한 유연성은 프로그래밍 방식으로 메서드 호출을 변경하거나 기존 클래스에 새 코드를 삽입할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-114">This flexibility means you can programmatically change method calls, or plug new code into existing classes.</span></span>

> [!NOTE]
> <span data-ttu-id="e64eb-115">메서드 오버로드의 컨텍스트에서는 메서드 시그니처에 반환 값이 포함되지 않지만</span><span class="sxs-lookup"><span data-stu-id="e64eb-115">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="e64eb-116">대리자 컨텍스트에서는 시그니처에 반환 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-116">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="e64eb-117">즉 메서드의 반환 형식이 대리자의 반환 형식과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-117">In other words, a method must have the same return type as the delegate.</span></span>

<span data-ttu-id="e64eb-118">대리자에서는 이와 같이 메서드를 매개 변수로 취급할 수 있으므로 대리자는 콜백 메서드 정의에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-118">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="e64eb-119">애플리케이션에서 두 개체를 비교하는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-119">You can write a method that compares two objects in your application.</span></span> <span data-ttu-id="e64eb-120">이 메서드는 정렬 알고리즘의 대리자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-120">That method can be used in a delegate for a sort algorithm.</span></span> <span data-ttu-id="e64eb-121">비교 코드는 라이브러리와 별개이므로 정렬 메서드가 더욱 일반적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-121">Because the comparison code is separate from the library, the sort method can be more general.</span></span>

<span data-ttu-id="e64eb-122">[함수 포인터](~/_csharplang/proposals/csharp-9.0/function-pointers.md)는 호출 규칙을 더욱 세부적으로 제어해야 하는 유사한 시나리오용으로 C# 9에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-122">[Function pointers](~/_csharplang/proposals/csharp-9.0/function-pointers.md) were added to C# 9 for similar scenarios, where you need more control over the calling convention.</span></span> <span data-ttu-id="e64eb-123">대리자와 연결된 코드는 대리자 형식에 추가된 가상 메서드를 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-123">The code associated with a delegate is invoked using a virtual method added to a delegate type.</span></span> <span data-ttu-id="e64eb-124">함수 포인터를 사용하여 다른 규칙을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-124">Using function pointers, you can specify different conventions.</span></span>

## <a name="delegates-overview"></a><span data-ttu-id="e64eb-125">대리자 개요</span><span class="sxs-lookup"><span data-stu-id="e64eb-125">Delegates Overview</span></span>

<span data-ttu-id="e64eb-126">대리자에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-126">Delegates have the following properties:</span></span>

- <span data-ttu-id="e64eb-127">대리자는 C++ 함수 포인터와 유사하지만 C++ 함수 포인터와 달리 멤버 함수에 대해 완전히 개체 지향입니다. 대리자는 개체 인스턴스 및 메서드를 모두 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-127">Delegates are similar to C++ function pointers, but delegates are fully object-oriented, and unlike C++ pointers to member functions, delegates encapsulate both an object instance and a method.</span></span>
- <span data-ttu-id="e64eb-128">대리자를 통해 메서드를 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-128">Delegates allow methods to be passed as parameters.</span></span>
- <span data-ttu-id="e64eb-129">대리자를 사용하여 콜백 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-129">Delegates can be used to define callback methods.</span></span>
- <span data-ttu-id="e64eb-130">여러 대리자를 연결할 수 있습니다. 예를 들어 단일 이벤트에 대해 여러 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-130">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>
- <span data-ttu-id="e64eb-131">메서드는 대리자 형식과 정확히 일치하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-131">Methods don't have to match the delegate type exactly.</span></span> <span data-ttu-id="e64eb-132">자세한 내용은 [대리자의 가변성 사용](../concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e64eb-132">For more information, see [Using Variance in Delegates](../concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>
- <span data-ttu-id="e64eb-133">람다 식은 인라인 코드 블록을 작성하는 더욱 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-133">Lambda expressions are a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="e64eb-134">특정 컨텍스트에서는 람다 식이 대리자 형식으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-134">Lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="e64eb-135">람다 식에 대한 자세한 내용은 [람다 식](../../language-reference/operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e64eb-135">For more information about lambda expressions, see [Lambda expressions](../../language-reference/operators/lambda-expressions.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e64eb-136">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e64eb-136">In This Section</span></span>

- [<span data-ttu-id="e64eb-137">대리자 사용</span><span class="sxs-lookup"><span data-stu-id="e64eb-137">Using Delegates</span></span>](./using-delegates.md)
- <span data-ttu-id="e64eb-138">[인터페이스(C# 프로그래밍 가이드) 대신 대리자를 사용하는 경우](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e64eb-138">[When to Use Delegates Instead of Interfaces (C# Programming Guide)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))</span></span>
- [<span data-ttu-id="e64eb-139">명명된 메서드 및 무명 메서드가 있는 대리자</span><span class="sxs-lookup"><span data-stu-id="e64eb-139">Delegates with Named vs. Anonymous Methods</span></span>](./delegates-with-named-vs-anonymous-methods.md)
- [<span data-ttu-id="e64eb-140">대리자의 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="e64eb-140">Using Variance in Delegates</span></span>](../concepts/covariance-contravariance/using-variance-in-delegates.md)
- [<span data-ttu-id="e64eb-141">대리자를 결합하는 방법(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="e64eb-141">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="e64eb-142">대리자를 선언, 인스턴스화, 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e64eb-142">How to declare, instantiate, and use a delegate</span></span>](./how-to-declare-instantiate-and-use-a-delegate.md)

## <a name="c-language-specification"></a><span data-ttu-id="e64eb-143">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e64eb-143">C# Language Specification</span></span>

<span data-ttu-id="e64eb-144">자세한 내용은 [대리자](~/_csharplang/spec/delegates.md) 에 [ C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)합니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-144">For more information, see [Delegates](~/_csharplang/spec/delegates.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="e64eb-145">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e64eb-145">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="featured-book-chapters"></a><span data-ttu-id="e64eb-146">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="e64eb-146">Featured Book Chapters</span></span>

- <span data-ttu-id="e64eb-147">[대리자, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) 에 [ C# 3.0 Cookbook, Third Edition: 250 개 이상의 솔루션에 대 한 C# 3.0 프로그래머](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="e64eb-147">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>
- <span data-ttu-id="e64eb-148">[대리자 및 이벤트](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) 에 [학습 C# 3.0. 기본 사항 마스터 C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="e64eb-148">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="e64eb-149">참조</span><span class="sxs-lookup"><span data-stu-id="e64eb-149">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="e64eb-150">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e64eb-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e64eb-151">이벤트</span><span class="sxs-lookup"><span data-stu-id="e64eb-151">Events</span></span>](../events/index.md)
