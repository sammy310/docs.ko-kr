---
title: 클래스와 구조체 간의 선택
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
ms.openlocfilehash: 34ab2589364e244fed1c64c1703205fb4b0832e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709519"
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="ac18b-102">클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="ac18b-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="ac18b-103">모든 프레임 워크 디자이너에 대 한 기본 설계 결정 사항 중 하나는 형식을 클래스 (참조 형식)로 디자인할 것인지 아니면 구조체 (값 형식)로 디자인할 것인지를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="ac18b-104">참조 형식 및 값 형식의 동작의 차이점을 이해 하는 것은이를 선택 하는 데 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="ac18b-105">참조 형식 및 값 형식 간의 첫 번째 차이점은 참조 형식이 힙에 할당 되 고 가비지 수집 된다는 것입니다. 반면 값 형식은 스택에 할당 되거나 포함 하는 형식에서 인라인으로 할당 되 고 스택에 할당이 취소 됩니다. 해제 또는 포함 하는 형식이 할당 취소 되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="ac18b-106">따라서 값 형식의 할당 및 할당 취소는 참조 형식의 할당 및 할당 취소 보다 일반적으로 비용이 저렴 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="ac18b-107">다음으로 참조 형식의 배열이 아웃오브 라인으로 할당 됩니다. 즉, 배열 요소는 힙에 있는 참조 형식의 인스턴스를 참조 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="ac18b-108">값 형식 배열은 인라인으로 할당 됩니다. 즉, 배열 요소는 값 형식의 실제 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="ac18b-109">따라서 값 형식 배열의 할당 및 할당 취소는 참조 형식 배열의 할당 및 할당 취소 보다 훨씬 저렴 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="ac18b-110">또한 대부분의 경우 값 형식 배열은 참조 집약성이 훨씬 더 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="ac18b-111">다음 차이점은 메모리 사용량과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="ac18b-112">값 형식은 참조 형식 또는 구현 하는 인터페이스 중 하나로 캐스팅 될 때 boxed를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="ac18b-113">값 형식으로 다시 캐스팅 될 때 unboxed가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="ac18b-114">상자는 힙에 할당 되 고 가비지 수집 되는 개체 이기 때문에 너무 많은 boxing 및 unboxing은 힙, 가비지 수집기 및 궁극적으로 응용 프로그램의 성능에 부정적인 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="ac18b-115">이와 대조적으로 참조 형식이 캐스팅 될 때 이러한 boxing이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-115">In contrast, no such boxing occurs as reference types are cast.</span></span> <span data-ttu-id="ac18b-116">자세한 내용은 [Boxing 및 Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac18b-116">(For more information, see [Boxing and Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)).</span></span>
  
 <span data-ttu-id="ac18b-117">다음으로 참조 형식 할당은 참조를 복사 하는 반면 값 형식 할당은 전체 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-117">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="ac18b-118">따라서 대량 참조 형식의 할당은 대량 값 형식의 할당 보다 저렴 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-118">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="ac18b-119">마지막으로 참조 형식은 참조로 전달 되는 반면 값 형식은 값으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-119">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="ac18b-120">참조 형식의 인스턴스를 변경 하면 인스턴스를 가리키는 모든 참조에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-120">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="ac18b-121">값 형식 인스턴스는 값으로 전달 될 때 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-121">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="ac18b-122">값 형식의 인스턴스를 변경 하는 경우 해당 복사본에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-122">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="ac18b-123">복사본이 사용자에 의해 명시적으로 생성 되지 않지만 인수가 전달 되거나 반환 값이 반환 될 때 암시적으로 만들어지므로 변경할 수 있는 값 형식은 여러 사용자에 게 혼란을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-123">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="ac18b-124">따라서 값 형식은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-124">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="ac18b-125">일반적으로 프레임 워크에서 대부분의 형식은 클래스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-125">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="ac18b-126">그러나 값 형식의 특성으로 인해 구조체를 사용 하는 것이 더 적합 한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-126">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="ac18b-127">**✓ CONSIDER** 형식 인스턴스의 작고 일반적으로 수명이 또는 일반적으로 다른 개체에 포함 된 경우 클래스 대신 구조체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-127">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="ac18b-128">**X AVOID** 형식에는 다음과 같은 특성을 모두 하지 않으면 구조체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-128">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
- <span data-ttu-id="ac18b-129">이는 기본 형식 (`int`, `double`등)과 비슷한 단일 값을 논리적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-129">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
- <span data-ttu-id="ac18b-130">인스턴스 크기는 16 바이트 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-130">It has an instance size under 16 bytes.</span></span>  
  
- <span data-ttu-id="ac18b-131">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-131">It is immutable.</span></span>  
  
- <span data-ttu-id="ac18b-132">자주 boxing 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-132">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="ac18b-133">다른 모든 경우에는 형식을 클래스로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac18b-133">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="ac18b-134">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="ac18b-134">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ac18b-135">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ac18b-135">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac18b-136">참조</span><span class="sxs-lookup"><span data-stu-id="ac18b-136">See also</span></span>

- [<span data-ttu-id="ac18b-137">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ac18b-137">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="ac18b-138">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ac18b-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
