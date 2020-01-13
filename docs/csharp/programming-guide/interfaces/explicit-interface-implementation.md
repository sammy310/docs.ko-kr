---
title: 명시적 인터페이스 구현 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ac90726fd50f104d1b9251d4f9b097b721ea5e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701760"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="e8eb5-102">명시적 인터페이스 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e8eb5-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="e8eb5-103">[클래스](../../language-reference/keywords/class.md)가 시그니처가 동일한 멤버를 포함하는 두 인터페이스를 구현하는 경우, 해당 멤버를 클래스에 구현하면 양쪽 인터페이스 모두가 해당 멤버를 구현에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="e8eb5-104">다음 예제에서 `Paint`에 대한 모든 호출은 같은 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#39)]  
  
 <span data-ttu-id="e8eb5-105">그러나 두 [인터페이스](../../language-reference/keywords/interface.md)가 동일한 기능을 수행하지 않을 경우, 인터페이스 둘 중 하나 또는 둘 다 잘못 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-105">If the two [interface](../../language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="e8eb5-106">인터페이스를 통해서만 호출되고 특정 인터페이스에만 관련되는 클래스 멤버를 만드는 방식으로 인터페이스 멤버를 명시적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="e8eb5-107">이렇게 하려면 인터페이스 이름과 마침표를 사용하여 클래스 멤버의 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="e8eb5-108">예:</span><span class="sxs-lookup"><span data-stu-id="e8eb5-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#40)]  
  
 <span data-ttu-id="e8eb5-109">클래스 멤버 `IControl.Paint`는 `IControl` 인터페이스를 통해서만 사용할 수 있고 `ISurface.Paint`는 `ISurface`를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="e8eb5-110">두 메서드 구현은 서로 별개이며 어느 쪽도 클래스에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="e8eb5-111">예:</span><span class="sxs-lookup"><span data-stu-id="e8eb5-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#41)]  
  
 <span data-ttu-id="e8eb5-112">명시적 구현은 또한 두 인터페이스가 속성과 메서드와 같이 동일한 이름을 가진 서로 다른 멤버를 선언하는 사례를 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#42)]  
  
 <span data-ttu-id="e8eb5-113">두 인터페이스를 모두 구현하려면 클래스는 P 속성이나 P 메서드 중 하나 또는 모두에 대해 명시적 구현을 사용하여 컴파일러 오류를 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="e8eb5-114">예:</span><span class="sxs-lookup"><span data-stu-id="e8eb5-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#43)]  
  
## <a name="see-also"></a><span data-ttu-id="e8eb5-115">참조</span><span class="sxs-lookup"><span data-stu-id="e8eb5-115">See also</span></span>

- [<span data-ttu-id="e8eb5-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e8eb5-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e8eb5-117">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="e8eb5-117">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e8eb5-118">인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8eb5-118">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e8eb5-119">상속</span><span class="sxs-lookup"><span data-stu-id="e8eb5-119">Inheritance</span></span>](../classes-and-structs/inheritance.md)
