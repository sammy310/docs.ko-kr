---
title: 제네릭 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 330aa74538ab15d1de19d80b0f57b3d0921c5c55
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712158"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="b3184-102">제네릭(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b3184-102">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="b3184-103">제네릭에서 .NET Framework에 도입한 형식 매개 변수 개념은 클라이언트 코드에서 클래스 또는 메서드를 선언하고 인스턴스화할 때까지 하나 이상의 형식 사양을 따르는 클래스 및 메서드를 디자인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-103">Generics introduce the concept of type parameters to the .NET Framework, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="b3184-104">예를 들어 제네릭 형식 매개 변수 `T`를 사용하여 여기에 표시된 것처럼, 다른 클라이언트 코드에서 런타임 캐스팅 또는 boxing 작업에 대한 비용이나 위험을 발생하지 않고 사용할 수 있는 단일 클래스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-104">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="b3184-105">제네릭 클래스 및 메서드는 제네릭이 아닌 클래스 및 메서드에서는 결합할 수 없는 방식으로 재사용성, 형식 안전성 및 효율성을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-105">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="b3184-106">제네릭은 컬렉션 및 해당 컬렉션에서 작동하는 메서드에서 가장 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-106">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="b3184-107"><xref:System.Collections.Generic> 네임스페이스에는 몇 가지 제네릭 기반 컬렉션 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-107">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="b3184-108"><xref:System.Collections.ArrayList>와 같은 제네릭이 아닌 컬렉션은 권장되지 않으며 호환성을 위해 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-108">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="b3184-109">자세한 내용은 [.NET의 제네릭](../../../standard/generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3184-109">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="b3184-110">물론, 사용자 지정 제네릭 형식 및 메서드를 만들어 형식이 안전하고 효율적인 일반화된 솔루션 및 디자인 패턴을 직접 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-110">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="b3184-111">다음 코드 예제에서는 데모용으로 간단한 제네릭 연결된 목록 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-111">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="b3184-112">대부분의 경우 직접 만드는 대신 .NET Framework 클래스 라이브러리에서 제공하는 <xref:System.Collections.Generic.List%601> 클래스를 사용해야 합니다. 형식 매개 변수 `T`는 일반적으로 구체적인 형식을 사용하여 목록에 저장된 항목의 형식을 나타내는 여러 위치에서 사용되며,</span><span class="sxs-lookup"><span data-stu-id="b3184-112">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="b3184-113">다음과 같은 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-113">It is used in the following ways:</span></span>

- <span data-ttu-id="b3184-114">`AddHead` 메서드에서 메서드 매개 변수의 형식.</span><span class="sxs-lookup"><span data-stu-id="b3184-114">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="b3184-115">중첩 `Node` 클래스에서 `Data` 속성의 반환 형식.</span><span class="sxs-lookup"><span data-stu-id="b3184-115">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="b3184-116">중첩 클래스에서 private 멤버 `data`의 형식.</span><span class="sxs-lookup"><span data-stu-id="b3184-116">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="b3184-117">`T`는 중첩된 `Node` 클래스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-117">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="b3184-118">`GenericList<T>`가 `GenericList<int>`와 같이 구체적인 형식으로 인스턴스화되면 `T`가 나타날 때마다 `int`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-118">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)] 

<span data-ttu-id="b3184-119">다음 코드 예제에서는 클라이언트 코드에서 제네릭 `GenericList<T>` 클래스를 사용하여 정수 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-119">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="b3184-120">형식 인수를 변경하기만 하면 다음 코드를 쉽게 수정하여 문자열이나 다른 모든 사용자 지정 형식 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-120">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="b3184-121">제네릭 개요</span><span class="sxs-lookup"><span data-stu-id="b3184-121">Generics overview</span></span>

- <span data-ttu-id="b3184-122">제네릭 형식을 사용하여 코드 재사용, 형식 안전성 및 성능을 최대화합니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-122">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="b3184-123">가장 일반적으로 제네릭은 컬렉션 클래스를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-123">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="b3184-124">.NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스에 여러 가지 새로운 제네릭 컬렉션 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-124">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="b3184-125">이러한 제네릭 컬렉션 클래스는 가능할 때마다 <xref:System.Collections> 네임스페이스의 <xref:System.Collections.ArrayList>처럼 클래스 대신 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-125">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="b3184-126">사용자 고유의 제네릭 인터페이스, 클래스, 메서드, 이벤트 및 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-126">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="b3184-127">제네릭 클래스는 특정 데이터 형식의 메서드에 액세스할 수 있도록 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-127">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="b3184-128">제네릭 데이터 형식에 사용되는 형식에 대한 정보는 리플렉션을 사용하여 런타임 시 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3184-128">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b3184-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b3184-129">Related sections</span></span>

- [<span data-ttu-id="b3184-130">제네릭 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3184-130">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="b3184-131">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="b3184-131">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="b3184-132">제네릭 클래스</span><span class="sxs-lookup"><span data-stu-id="b3184-132">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="b3184-133">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3184-133">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="b3184-134">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="b3184-134">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="b3184-135">제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="b3184-135">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="b3184-136">C++ 템플릿과 C# 제네릭의 차이점</span><span class="sxs-lookup"><span data-stu-id="b3184-136">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="b3184-137">제네릭 및 리플렉션</span><span class="sxs-lookup"><span data-stu-id="b3184-137">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="b3184-138">런타임의 제네릭</span><span class="sxs-lookup"><span data-stu-id="b3184-138">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="b3184-139">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b3184-139">C# language specification</span></span>

<span data-ttu-id="b3184-140">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/types.md#constructed-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3184-140">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3184-141">참조</span><span class="sxs-lookup"><span data-stu-id="b3184-141">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="b3184-142">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b3184-142">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b3184-143">유형</span><span class="sxs-lookup"><span data-stu-id="b3184-143">Types</span></span>](../types/index.md)
- [<span data-ttu-id="b3184-144">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="b3184-144">\<typeparam></span></span>](../xmldoc/typeparam.md)
- [<span data-ttu-id="b3184-145">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="b3184-145">\<typeparamref></span></span>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="b3184-146">.NET의 제네릭</span><span class="sxs-lookup"><span data-stu-id="b3184-146">Generics in .NET</span></span>](../../../standard/generics/index.md)
