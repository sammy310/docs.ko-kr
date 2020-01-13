---
title: 식 본문 멤버 - C# 프로그래밍 가이드
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711989"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="ae023-102">식 본문 멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ae023-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="ae023-103">식 본문 정의를 사용하면 간결하고 읽을 수 있는 형식으로 멤버 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="ae023-104">메서드 또는 속성과 같은 지원되는 멤버에 대한 논리가 단일 식으로 구성된 경우 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="ae023-105">식 본문 정의의 일반 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="ae023-106">여기서 *expression*은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="ae023-107">C# 6에서는 메서드 및 읽기 전용 속성에 식 본문 정의 지원이 제공되었으며, C# 7.0에서는 해당 지원이 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="ae023-108">다음 표에 나열된 형식 멤버와 함께 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="ae023-109">멤버</span><span class="sxs-lookup"><span data-stu-id="ae023-109">Member</span></span>  |<span data-ttu-id="ae023-110">지원 버전</span><span class="sxs-lookup"><span data-stu-id="ae023-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="ae023-111">메서드</span><span class="sxs-lookup"><span data-stu-id="ae023-111">Method</span></span>](#methods)  |<span data-ttu-id="ae023-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="ae023-112">C# 6</span></span> |
|[<span data-ttu-id="ae023-113">읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="ae023-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="ae023-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="ae023-114">C# 6</span></span>  |
|[<span data-ttu-id="ae023-115">Property</span><span class="sxs-lookup"><span data-stu-id="ae023-115">Property</span></span>](#properties)  |<span data-ttu-id="ae023-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="ae023-116">C# 7.0</span></span> |
|[<span data-ttu-id="ae023-117">생성자</span><span class="sxs-lookup"><span data-stu-id="ae023-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="ae023-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="ae023-118">C# 7.0</span></span> |
|[<span data-ttu-id="ae023-119">종료자</span><span class="sxs-lookup"><span data-stu-id="ae023-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="ae023-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="ae023-120">C# 7.0</span></span> |
|[<span data-ttu-id="ae023-121">인덱서</span><span class="sxs-lookup"><span data-stu-id="ae023-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="ae023-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="ae023-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="ae023-123">메서드</span><span class="sxs-lookup"><span data-stu-id="ae023-123">Methods</span></span>

<span data-ttu-id="ae023-124">식 본문 메서드는 형식이 메서드의 반환 형식과 일치하는 값을 반환하거나 `void`를 반환하는 메서드의 경우 일부 작업을 수행하는 단일 식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="ae023-125">예를 들어 <xref:System.Object.ToString%2A> 메서드를 재정의하는 형식에는 일반적으로 현재 개체의 문자열 표현을 반환하는 단일 식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="ae023-126">다음 예제에<xref:System.Object.ToString%2A> 메서드를 식 본문 정의로 재정의하는 `Person` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="ae023-127">또한 이름을 콘솔에 표시하는 `DisplayName` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="ae023-128">`return` 키워드는 `ToString` 식 본문 정의에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="ae023-129">자세한 내용은 [메서드(C# 프로그래밍 가이드)](../classes-and-structs/methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="ae023-130">읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="ae023-130">Read-only properties</span></span>

<span data-ttu-id="ae023-131">C# 6부터는 읽기 전용 속성을 구현하기 위해 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="ae023-132">이를 위해 사용하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="ae023-133">다음 예제에서는 `Location` 클래스를 정의합니다. 이 클래스의 읽기 전용 `Name` 속성은 `locationName` 비공개 필드의 값을 반환하는 식 본문 정의로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="ae023-134">속성에 대한 자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="ae023-135">속성</span><span class="sxs-lookup"><span data-stu-id="ae023-135">Properties</span></span>

<span data-ttu-id="ae023-136">C# 7.0부터는 식 본문 정의를 사용하여 `get` 및 `set` 속성 접근자를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="ae023-137">다음 예제에서는 이를 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="ae023-138">속성에 대한 자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="ae023-139">생성자</span><span class="sxs-lookup"><span data-stu-id="ae023-139">Constructors</span></span>

<span data-ttu-id="ae023-140">생성자에 대한 식 본문 정의는 일반적으로 생성자의 인수를 처리하거나 인스턴스 상태를 초기화하는 단일 할당 식 또는 메서드 호출로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="ae023-141">다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="ae023-142">식 본문 정의에서 `Name` 속성에 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="ae023-143">자세한 내용은 [생성자(C# 프로그래밍 가이드)](../classes-and-structs/constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="ae023-144">종료자</span><span class="sxs-lookup"><span data-stu-id="ae023-144">Finalizers</span></span>

<span data-ttu-id="ae023-145">종료자에 대한 식 본문 정의에는 일반적으로 관리되지 않는 리소스를 해제하는 문 등의 정리 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="ae023-146">다음 예제에서는 식 본문 정의를 사용하여 종료자가 호출되었음을 나타내는 종료자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="ae023-147">자세한 내용은 [종료자(C# 프로그래밍 가이드)](../classes-and-structs/destructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="ae023-148">인덱서</span><span class="sxs-lookup"><span data-stu-id="ae023-148">Indexers</span></span>

<span data-ttu-id="ae023-149">속성과 마찬가지로, `get` 접근자가 값을 반환하는 단일 식으로 구성되거나 `set` 접근자가 단순 할당을 수행하는 경우 인덱서의 `get` 및 `set` 접근자는 식 본문 정의로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="ae023-150">다음 예제에서는 다양한 스포츠의 이름이 포함된 내부 <xref:System.String> 배열을 포함하는 `Sports`라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="ae023-151">인덱서의 `get` 및 `set` 접근자는 둘 다 식 본문 정의로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae023-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="ae023-152">자세한 내용은 [인덱서(C# 프로그래밍 가이드)](../indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae023-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
