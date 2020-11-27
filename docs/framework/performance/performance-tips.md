---
title: .NET 성능 팁
description: .NET에서 프로그램의 실행 속도를 개선 하기 위해 성능 팁을 살펴보세요. Boxing 및 unboxing, 문자열 및 소멸자의 팁을 참조 하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 526dd0d42b82dd4987e446382e7639f322e063aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281705"
---
# <a name="net-performance-tips"></a><span data-ttu-id="31b0b-104">.NET 성능 팁</span><span class="sxs-lookup"><span data-stu-id="31b0b-104">.NET Performance Tips</span></span>

<span data-ttu-id="31b0b-105">*성능* 이라는 용어는 일반적으로 프로그램의 실행 속도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-105">The term *performance* generally refers to the execution speed of a program.</span></span> <span data-ttu-id="31b0b-106">경우에 따라 소스 코드에서 특정 기본 규칙을 따라 실행 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-106">You can sometimes increase execution speed by following certain basic rules in your source code.</span></span> <span data-ttu-id="31b0b-107">일부 프로그램에서는 코드를 자세히 검사하고 프로파일러를 사용하여 최대한 빠르게 실행 중인지 확인하는 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-107">In some programs, it is important to examine code closely and use profilers to make sure that it is running as fast as possible.</span></span> <span data-ttu-id="31b0b-108">다른 프로그램에서는 코드가 작성된 대로 만족스럽게 실행되므로 이러한 최적화를 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-108">In other programs, you do not have to perform such optimization because the code is running acceptably fast as it is written.</span></span> <span data-ttu-id="31b0b-109">이 문서에서는 성능이 떨어질 수 있는 몇 가지 일반적인 영역과 성능 향상 팁 및 추가 성능 항목에 대한 링크를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-109">This article lists some common areas where performance can suffer and tips for improving it as well as links to additional performance topics.</span></span> <span data-ttu-id="31b0b-110">성능 계획 및 측정에 대한 자세한 내용은 [성능](index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b0b-110">For more information about planning and measuring for performance, see [Performance](index.md)</span></span>  
  
## <a name="boxing-and-unboxing"></a><span data-ttu-id="31b0b-111">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="31b0b-111">Boxing and Unboxing</span></span>  

 <span data-ttu-id="31b0b-112">예를 들어 <xref:System.Collections.ArrayList?displayProperty=nameWithType>와 같이 제네릭이 아닌 컬렉션 클래스에서 상당히 많은 횟수로 boxing되어야 하는 경우 값 형식을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-112">It is best to avoid using value types in situations where they must be boxed a high number of times, for example in non-generic collections classes such as <xref:System.Collections.ArrayList?displayProperty=nameWithType>.</span></span> <span data-ttu-id="31b0b-113"><xref:System.Collections.Generic.List%601?displayProperty=nameWithType>와 같은 제네릭 컬렉션을 사용하는 경우 값 형식을 boxing하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-113">You can avoid boxing of value types by using generic collections such as <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="31b0b-114">Boxing 및 unboxing은 계산을 많이 해야 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-114">Boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="31b0b-115">값 형식이 boxing되면 완전히 새로운 개체가 생성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-115">When a value type is boxed, an entirely new object must be created.</span></span> <span data-ttu-id="31b0b-116">이 작업은 단순 참조 할당보다 20배나 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-116">This can take up to 20 times longer than a simple reference assignment.</span></span> <span data-ttu-id="31b0b-117">unboxing 시 캐스팅 프로세스는 할당의 4배에 달하는 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-117">When unboxing, the casting process can take four times as long as an assignment.</span></span> <span data-ttu-id="31b0b-118">자세한 내용은 [boxing 및 unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b0b-118">For more information, see [Boxing and Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="strings"></a><span data-ttu-id="31b0b-119">문자열</span><span class="sxs-lookup"><span data-stu-id="31b0b-119">Strings</span></span>  

 <span data-ttu-id="31b0b-120">예를 들어 연속 루프에서 다수의 문자열 변수를 연결하는 경우 C# [+ 연산자](../../csharp/language-reference/operators/addition-operator.md) 또는 Visual Basic [연결 연산자](../../visual-basic/language-reference/operators/concatenation-operators.md)가 아니라 <xref:System.Text.StringBuilder?displayProperty=nameWithType>를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-120">When you concatenate a large number of string variables, for example in a tight loop, use <xref:System.Text.StringBuilder?displayProperty=nameWithType> instead of the C# [+ operator](../../csharp/language-reference/operators/addition-operator.md) or the Visual Basic [Concatenation Operators](../../visual-basic/language-reference/operators/concatenation-operators.md).</span></span> <span data-ttu-id="31b0b-121">자세한 내용은 [Visual Basic에서](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)여러 문자열 및 연결 연산자를 [연결 하는 방법](../../csharp/how-to/concatenate-multiple-strings.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31b0b-121">For more information, see [How to concatenate multiple strings](../../csharp/how-to/concatenate-multiple-strings.md) and [Concatenation Operators in Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).</span></span>  
  
## <a name="destructors"></a><span data-ttu-id="31b0b-122">소멸자</span><span class="sxs-lookup"><span data-stu-id="31b0b-122">Destructors</span></span>  

 <span data-ttu-id="31b0b-123">빈 소멸자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-123">Empty destructors should not be used.</span></span> <span data-ttu-id="31b0b-124">클래스에 소멸자가 포함되어 있으면 Finalize 큐에서 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-124">When a class contains a destructor, an entry is created in the Finalize queue.</span></span> <span data-ttu-id="31b0b-125">소멸자를 호출하면 가비지 수집기가 호출되어 큐를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-125">When the destructor is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="31b0b-126">소멸자가 비어 있으면 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b0b-126">If the destructor is empty, this simply results in a loss of performance.</span></span> <span data-ttu-id="31b0b-127">자세한 내용은 [소멸자](../../csharp/programming-guide/classes-and-structs/destructors.md) 및 [개체 수명: 개체가 만들어지고 소멸되는 방법](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b0b-127">For more information, see [Destructors](../../csharp/programming-guide/classes-and-structs/destructors.md) and [Object Lifetime: How Objects Are Created and Destroyed](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="31b0b-128">관련 자료</span><span class="sxs-lookup"><span data-stu-id="31b0b-128">Other Resources</span></span>  
  
- <span data-ttu-id="31b0b-129">[관리 코드를 더 빠르게 작성: 리소스를 많이 사용하는 요소 파악](/previous-versions/dotnet/articles/ms973852(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="31b0b-129">[Writing Faster Managed Code: Know What Things Cost](/previous-versions/dotnet/articles/ms973852(v=msdn.10))</span></span>  
  
- <span data-ttu-id="31b0b-130">[고성능의 관리되는 애플리케이션 작성: 입문서](/previous-versions/dotnet/articles/ms973858(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="31b0b-130">[Writing High-Performance Managed Applications: A Primer](/previous-versions/dotnet/articles/ms973858(v=msdn.10))</span></span>  
  
- <span data-ttu-id="31b0b-131">[가비지 수집기 기본 및 성능 힌트](/previous-versions/dotnet/articles/ms973837(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="31b0b-131">[Garbage Collector Basics and Performance Hints](/previous-versions/dotnet/articles/ms973837(v=msdn.10))</span></span>  
  
- <span data-ttu-id="31b0b-132">[.NET 애플리케이션에서의 성능 팁과 요량](/previous-versions/dotnet/articles/ms973839(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="31b0b-132">[Performance Tips and Tricks in .NET Applications](/previous-versions/dotnet/articles/ms973839(v=msdn.10))</span></span>  

- [<span data-ttu-id="31b0b-133">Rico Mariani의 성능 정보</span><span class="sxs-lookup"><span data-stu-id="31b0b-133">Rico Mariani's Performance Tidbits</span></span>](/archive/blogs/ricom/)  

- [<span data-ttu-id="31b0b-134">Vance Morrison의 블로그</span><span class="sxs-lookup"><span data-stu-id="31b0b-134">Vance Morrison's Blog</span></span>](/archive/blogs/vancem/)
  
## <a name="see-also"></a><span data-ttu-id="31b0b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31b0b-135">See also</span></span>

- [<span data-ttu-id="31b0b-136">성능</span><span class="sxs-lookup"><span data-stu-id="31b0b-136">Performance</span></span>](index.md)
- [<span data-ttu-id="31b0b-137">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="31b0b-137">Visual Basic Programming Guide</span></span>](../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="31b0b-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="31b0b-138">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)
