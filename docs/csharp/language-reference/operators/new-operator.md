---
title: new 연산자 - C# 참조
ms.date: 06/25/2019
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 42128cf23fe2410bf33bb40131843325939646de
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916764"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="f9ce7-102">new 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f9ce7-102">new operator (C# reference)</span></span>

<span data-ttu-id="f9ce7-103">`new` 연산자는 새 유형의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-103">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="f9ce7-104">`new` 키워드를 [멤버 선언 한정자](../keywords/new-modifier.md) 또는 [제네릭 형식 제약 조건](../keywords/new-constraint.md)으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-104">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="f9ce7-105">생성자 호출</span><span class="sxs-lookup"><span data-stu-id="f9ce7-105">Constructor invocation</span></span>

<span data-ttu-id="f9ce7-106">새 인스턴스 유형을 만들려면 일반적으로 `new` 연산자를 사용하여 해당 유형의 [생성자](../../programming-guide/classes-and-structs/constructors.md) 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-106">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="f9ce7-107">다음 예제와 같이 `new` 연산자와 함께 [개체 또는 컬렉션 이니셜라이저](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)를 사용하여 하나의 명령문에서 개체를 인스턴스화하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-107">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a><span data-ttu-id="f9ce7-108">배열 생성</span><span class="sxs-lookup"><span data-stu-id="f9ce7-108">Array creation</span></span>

<span data-ttu-id="f9ce7-109">또한 다음 예제와 같이 `new` 연산자를 사용하여 배열 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-109">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="f9ce7-110">배열 초기화 구문을 사용하여 배열 인스턴스를 만들고 하나의 명령문에 요소를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-110">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="f9ce7-111">다음 예제에서는 이를 수행하는 다양한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-111">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="f9ce7-112">배열에 대한 자세한 내용은 [배열](../../programming-guide/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-112">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="f9ce7-113">익명 형식의 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="f9ce7-113">Instantiation of anonymous types</span></span>

<span data-ttu-id="f9ce7-114">[익명 형식](../../programming-guide/classes-and-structs/anonymous-types.md)의 인스턴스를 만들려면 `new` 연산자와 개체 이니셜라이저 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-114">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="f9ce7-115">형식 인스턴스의 소멸</span><span class="sxs-lookup"><span data-stu-id="f9ce7-115">Destruction of type instances</span></span>

<span data-ttu-id="f9ce7-116">앞서 만든 형식 인스턴스를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-116">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="f9ce7-117">참조 형식과 값 형식 모두의 인스턴스는 자동으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-117">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="f9ce7-118">값 형식의 인스턴스는 포함된 컨텍스트가 제거되는 즉시 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-118">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="f9ce7-119">참조 형식의 인스턴스는 마지막 참조가 제거된 후 일부 지정되지 않은 시간에 [가비지 수집기](../../../standard/garbage-collection/index.md)에 의해 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-119">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="f9ce7-120">파일 핸들과 같이 관리되지 않은 리소스를 포함하는 형식 인스턴스의 경우에는 결정적 정리를 사용하여 포함된 리소스가 가능한 빨리 릴리스되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-120">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="f9ce7-121">자세한 내용은 <xref:System.IDisposable?displayProperty=nameWithType> API 참조 및 [명령문 사용](../keywords/using-statement.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-121">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f9ce7-122">연산자 오버로드 가능성</span><span class="sxs-lookup"><span data-stu-id="f9ce7-122">Operator overloadability</span></span>

<span data-ttu-id="f9ce7-123">사용자 정의 형식은 `new` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-123">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9ce7-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f9ce7-124">C# language specification</span></span>

<span data-ttu-id="f9ce7-125">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [new 연산자](~/_csharplang/spec/expressions.md#the-new-operator) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9ce7-125">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9ce7-126">참조</span><span class="sxs-lookup"><span data-stu-id="f9ce7-126">See also</span></span>

- [<span data-ttu-id="f9ce7-127">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f9ce7-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f9ce7-128">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="f9ce7-128">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="f9ce7-129">개체 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="f9ce7-129">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
