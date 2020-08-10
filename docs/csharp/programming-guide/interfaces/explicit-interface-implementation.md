---
title: 명시적 인터페이스 구현 - C# 프로그래밍 가이드
description: 클래스는 C#에서 동일한 시그니처를 가진 멤버를 포함하는 인터페이스를 구현할 수 있습니다. 명시적 구현에서는 하나의 인터페이스에 고유한 클래스 멤버를 만듭니다.
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: a6ec328c08d1da84a11431d9400a094df8c72223
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303089"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="3119f-104">명시적 인터페이스 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3119f-104">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="3119f-105">[클래스](../../language-reference/keywords/class.md)가 시그니처가 동일한 멤버를 포함하는 두 인터페이스를 구현하는 경우, 해당 멤버를 클래스에 구현하면 양쪽 인터페이스 모두가 해당 멤버를 구현에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-105">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="3119f-106">다음 예제에서 `Paint`에 대한 모든 호출은 같은 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-106">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="3119f-107">이 첫 번째 샘플에서는 다음 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-107">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="3119f-108">다음 샘플에서는 다음 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-108">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="3119f-109">두 인터페이스 멤버가 동일한 기능을 수행하지 않을 경우, 인터페이스 둘 중 하나 또는 둘 다 잘못 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-109">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="3119f-110">인터페이스를 통해서만 호출되고 해당 인터페이스에만 관련되는 클래스 멤버를 만드는 방식으로 인터페이스 멤버를 명시적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-110">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="3119f-111">인터페이스 이름과 마침표를 사용하여 클래스 멤버의 이름을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-111">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="3119f-112">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3119f-112">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="3119f-113">클래스 멤버 `IControl.Paint`는 `IControl` 인터페이스를 통해서만 사용할 수 있고 `ISurface.Paint`는 `ISurface`를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-113">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="3119f-114">두 메서드 구현은 서로 별개이며 어느 쪽도 클래스에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-114">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="3119f-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3119f-115">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="3119f-116">명시적 구현은 두 인터페이스가 속성이나 메서드와 같이 동일한 이름을 가진 서로 다른 멤버를 선언하는 사례를 해결하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-116">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="3119f-117">두 인터페이스를 모두 구현하려면 클래스는 `P` 속성이나 `P` 메서드 중 하나 또는 둘 다에 대해 명시적 구현을 사용하여 컴파일러 오류를 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-117">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="3119f-118">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="3119f-118">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="3119f-119">[C# 8.0](../../whats-new/csharp-8.md#default-interface-methods)부터 인터페이스에 선언된 멤버에 대한 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-119">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="3119f-120">클래스가 인터페이스로부터 메서드 구현을 상속하는 경우, 해당 메서드는 인터페이스 형식의 참조를 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-120">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="3119f-121">상속된 멤버는 public 인터페이스의 일부로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-121">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="3119f-122">다음 샘플은 인터페이스에 메서드에 대한 기본 구현을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-122">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="3119f-123">다음 샘플은 기본 구현을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-123">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="3119f-124">`IControl` 인터페이스를 구현하는 모든 클래스는 기본 `Paint` 메서드를 public 메서드로 또는 명시적 인터페이스 구현으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3119f-124">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3119f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3119f-125">See also</span></span>

- [<span data-ttu-id="3119f-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3119f-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3119f-127">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="3119f-127">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="3119f-128">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3119f-128">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="3119f-129">상속</span><span class="sxs-lookup"><span data-stu-id="3119f-129">Inheritance</span></span>](../classes-and-structs/inheritance.md)
