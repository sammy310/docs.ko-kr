---
title: 대리자를 선언, 인스턴스화, 사용하는 방법 - C# 프로그래밍 가이드
description: 대리자를 선언, 인스턴스화, 사용하는 방법을 알아봅니다. C# 1.0, 2.0 및 3.0 이상을 사용하는 예제를 살펴봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 83dbd2dc497fafaf1922f8ad53208d0ab14f14a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185901"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a><span data-ttu-id="8782e-104">대리자를 선언, 인스턴스화, 사용하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8782e-104">How to declare, instantiate, and use a Delegate (C# Programming Guide)</span></span>

<span data-ttu-id="8782e-105">C# 1.0 이상 버전에서는 다음 예제와 같이 대리자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-105">In C# 1.0 and later, delegates can be declared as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 <span data-ttu-id="8782e-106">C# 2.0에서는 다음 예제와 같이 더욱 간단한 방법으로 이전 선언을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-106">C# 2.0 provides a simpler way to write the previous declaration, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 <span data-ttu-id="8782e-107">C# 2.0 이상 버전에서는 다음 예제와 같이 익명 메서드를 사용하여 [delegate](../../language-reference/builtin-types/reference-types.md)를 선언하고 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-107">In C# 2.0 and later, it is also possible to use an anonymous method to declare and initialize a [delegate](../../language-reference/builtin-types/reference-types.md), as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 <span data-ttu-id="8782e-108">C# 3.0 이상에서는 다음 예제와 같이 람다 식을 사용하여 대리자를 선언하고 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-108">In C# 3.0 and later, delegates can also be declared and instantiated by using a lambda expression, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 <span data-ttu-id="8782e-109">자세한 내용은 [람다 식](../../language-reference/operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8782e-109">For more information, see [Lambda Expressions](../../language-reference/operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="8782e-110">다음 예제에서는 대리자를 선언, 인스턴스화 및 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-110">The following example illustrates declaring, instantiating, and using a delegate.</span></span> <span data-ttu-id="8782e-111">`BookDB` 클래스는 책 데이터베이스를 유지 관리하는 서점 데이터베이스를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-111">The `BookDB` class encapsulates a bookstore database that maintains a database of books.</span></span> <span data-ttu-id="8782e-112">그리고 데이터베이스의 모든 문고판 책을 찾아 각 책에 대해 대리자를 호출하는 `ProcessPaperbackBooks` 메서드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-112">It exposes a method, `ProcessPaperbackBooks`, which finds all paperback books in the database and calls a delegate for each one.</span></span> <span data-ttu-id="8782e-113">이때 사용되는 `delegate` 형식의 이름은 `ProcessBookDelegate`입니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-113">The `delegate` type that is used is named `ProcessBookDelegate`.</span></span> <span data-ttu-id="8782e-114">`Test` 클래스는 이 클래스를 사용하여 문고판 책의 제목과 평균 가격을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-114">The `Test` class uses this class to print the titles and average price of the paperback books.</span></span>  
  
 <span data-ttu-id="8782e-115">대리자를 사용하면 서점 데이터베이스와 클라이언트 코드 간에 기능을 효율적으로 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-115">The use of delegates promotes good separation of functionality between the bookstore database and the client code.</span></span> <span data-ttu-id="8782e-116">클라이언트 코드는 책이 저장되는 방식이나 서점 코드가 문고판 책을 찾는 방식을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-116">The client code has no knowledge of how the books are stored or how the bookstore code finds paperback books.</span></span> <span data-ttu-id="8782e-117">서점 코드는 발견된 문고판 책에 대해 수행되는 처리를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-117">The bookstore code has no knowledge of what processing is performed on the paperback books after it finds them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8782e-118">예제</span><span class="sxs-lookup"><span data-stu-id="8782e-118">Example</span></span>  

 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8782e-119">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8782e-119">Robust Programming</span></span>  
  
- <span data-ttu-id="8782e-120">대리자 선언</span><span class="sxs-lookup"><span data-stu-id="8782e-120">Declaring a delegate.</span></span>  
  
     <span data-ttu-id="8782e-121">다음 문은 새 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-121">The following statement declares a new delegate type.</span></span>  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     <span data-ttu-id="8782e-122">각 대리자 형식은 인수의 수와 형식 및 캡슐화 가능한 메서드의 형식과 반환 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-122">Each delegate type describes the number and types of the arguments, and the type of the return value of methods that it can encapsulate.</span></span> <span data-ttu-id="8782e-123">새 인수 형식 또는 반환 값 형식 집합이 필요할 때마다 새 대리자 형식을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-123">Whenever a new set of argument types or return value type is needed, a new delegate type must be declared.</span></span>  
  
- <span data-ttu-id="8782e-124">대리자 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="8782e-124">Instantiating a delegate.</span></span>  
  
     <span data-ttu-id="8782e-125">대리자 형식을 선언한 후에는 대리자 개체를 생성하여 특정 메서드와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-125">After a delegate type has been declared, a delegate object must be created and associated with a particular method.</span></span> <span data-ttu-id="8782e-126">이전 예제의 경우 다음 예제와 같이 `PrintTitle` 메서드를 `ProcessPaperbackBooks` 메서드에 전달하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-126">In the previous example, you do this by passing the `PrintTitle` method to the `ProcessPaperbackBooks` method as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     <span data-ttu-id="8782e-127">이렇게 하면 [정적](../../language-reference/keywords/static.md) 메서드 `Test.PrintTitle`에 연결된 새 대리자 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-127">This creates a new delegate object associated with the [static](../../language-reference/keywords/static.md) method `Test.PrintTitle`.</span></span> <span data-ttu-id="8782e-128">마찬가지로 개체 `totaller`의 비정적 메서드 `AddBookToTotal`도 다음 예제와 같이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-128">Similarly, the non-static method `AddBookToTotal` on the object `totaller` is passed as in the following example:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     <span data-ttu-id="8782e-129">두 경우 모두 새 대리자 개체가 `ProcessPaperbackBooks` 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-129">In both cases a new delegate object is passed to the `ProcessPaperbackBooks` method.</span></span>  
  
     <span data-ttu-id="8782e-130">대리자를 만든 후에도 대리자가 연결된 메서드는 변경되지 않습니다. 대리자 개체는 변경이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-130">After a delegate is created, the method it is associated with never changes; delegate objects are immutable.</span></span>  
  
- <span data-ttu-id="8782e-131">대리자 호출</span><span class="sxs-lookup"><span data-stu-id="8782e-131">Calling a delegate.</span></span>  
  
     <span data-ttu-id="8782e-132">생성된 대리자 개체는 대개 대리자를 호출하는 다른 코드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-132">After a delegate object is created, the delegate object is typically passed to other code that will call the delegate.</span></span> <span data-ttu-id="8782e-133">대리자 개체의 이름 뒤에 대리자로 전달할 인수를 괄호로 묶어 추가한 형식을 사용하여 대리자 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-133">A delegate object is called by using the name of the delegate object, followed by the parenthesized arguments to be passed to the delegate.</span></span> <span data-ttu-id="8782e-134">아래에 대리자 호출의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-134">Following is an example of a delegate call:</span></span>  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     <span data-ttu-id="8782e-135">대리자는 이 예제와 같이 동기적으로 호출할 수도 있고 `BeginInvoke` 및 `EndInvoke` 메서드를 사용하여 비동기적으로 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8782e-135">A delegate can be either called synchronously, as in this example, or asynchronously by using `BeginInvoke` and `EndInvoke` methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8782e-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8782e-136">See also</span></span>

- [<span data-ttu-id="8782e-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8782e-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8782e-138">이벤트</span><span class="sxs-lookup"><span data-stu-id="8782e-138">Events</span></span>](../events/index.md)
- [<span data-ttu-id="8782e-139">대리자</span><span class="sxs-lookup"><span data-stu-id="8782e-139">Delegates</span></span>](./index.md)
