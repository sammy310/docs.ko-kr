---
title: 생성자 - C# 프로그래밍 가이드
description: 클래스 또는 구조체가 만들어지면 C#의 생성자가 호출됩니다. 생성자를 사용하여 기본값을 설정하고, 인스턴스화를 제한하고, 유연하고 읽기 쉬운 코드를 씁니다.
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 4a731e648143f5e0ecf8860625962d8baa29fe26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474906"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="4ceaa-104">생성자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4ceaa-104">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="4ceaa-105">[class](../../language-reference/keywords/class.md) 또는 [struct](../../language-reference/builtin-types/struct.md)를 만들 때마다 해당 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-105">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="4ceaa-106">클래스 또는 구조체에는 서로 다른 인수를 사용하는 여러 생성자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-106">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="4ceaa-107">프로그래머는 생성자를 통해 기본값을 설정하고, 인스턴스화를 제한하며, 유연하고 읽기 쉬운 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-107">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="4ceaa-108">자세한 내용 및 예제는 [생성자 사용](./using-constructors.md) 및 [인스턴스 생성자](./instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-108">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="4ceaa-109">매개 변수 없는 생성자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-109">Parameterless constructors</span></span>
  
<span data-ttu-id="4ceaa-110">클래스에 대한 생성자를 제공하지 않으면 C#이 기본적으로 개체를 인스턴스화하고 멤버 변수를 [C# 형식의 기본값](../../language-reference/builtin-types/default-values.md)에 나열된 기본값으로 설정하는 생성자를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-110">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="4ceaa-111">구조체에 대한 생성자를 제공하지 않으면 C#이 *암시적 매개 변수 없는 생성자*를 사용하여 각 필드를 자동으로 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-111">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="4ceaa-112">자세한 내용 및 예제는 [인스턴스 생성자](instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-112">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="4ceaa-113">생성자 구문</span><span class="sxs-lookup"><span data-stu-id="4ceaa-113">Constructor syntax</span></span>

<span data-ttu-id="4ceaa-114">생성자는 이름이 해당 형식의 이름과 동일한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-114">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="4ceaa-115">해당 메서드 시그니처에는 메서드 이름과 매개 변수 목록만 포함되고 반환 형식은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-115">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="4ceaa-116">다음 예제에서는 `Person`이라는 클래스에 대한 생성자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-116">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="4ceaa-117">생성자를 단일 문으로 구현할 수 있는 경우 [식 본문 정의](../statements-expressions-operators/expression-bodied-members.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-117">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="4ceaa-118">다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-118">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="4ceaa-119">식 본문 정의에서 `locationName` 필드에 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-119">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="4ceaa-120">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-120">Static constructors</span></span>

<span data-ttu-id="4ceaa-121">앞의 예제에서는 새 개체를 만드는 인스턴스 생성자를 모두 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="4ceaa-122">클래스 또는 구조체에 형식의 정적 멤버를 초기화하는 정적 생성자도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="4ceaa-123">정적 생성자에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-123">Static constructors are parameterless.</span></span> <span data-ttu-id="4ceaa-124">정적 필드를 초기화하는 정적 생성자를 제공하지 않으면 C# 컴파일러는 정적 필드를 [C# 형식의 기본값](../../language-reference/builtin-types/default-values.md)에 나열된 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-124">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="4ceaa-125">다음 예제에서는 정적 생성자를 사용하여 정적 필드를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-125">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="4ceaa-126">다음 예제와 같이 식 본문 정의를 사용하여 정적 생성자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-126">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="4ceaa-127">자세한 내용 및 예제는 [정적 생성자](./static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ceaa-127">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ceaa-128">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4ceaa-128">In This Section</span></span>  
 [<span data-ttu-id="4ceaa-129">생성자 사용</span><span class="sxs-lookup"><span data-stu-id="4ceaa-129">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="4ceaa-130">인스턴스 생성자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-130">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="4ceaa-131">전용 생성자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-131">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="4ceaa-132">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-132">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="4ceaa-133">복사 생성자 작성 방법</span><span class="sxs-lookup"><span data-stu-id="4ceaa-133">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ceaa-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ceaa-134">See also</span></span>

- [<span data-ttu-id="4ceaa-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4ceaa-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4ceaa-136">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="4ceaa-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="4ceaa-137">종료자</span><span class="sxs-lookup"><span data-stu-id="4ceaa-137">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="4ceaa-138">static</span><span class="sxs-lookup"><span data-stu-id="4ceaa-138">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="4ceaa-139">이니셜라이저가 생성자와 반대 순서로 실행되는 이유는 무엇인가요? 1부</span><span class="sxs-lookup"><span data-stu-id="4ceaa-139">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
