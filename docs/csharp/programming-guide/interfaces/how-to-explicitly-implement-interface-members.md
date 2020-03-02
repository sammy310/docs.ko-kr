---
title: 인터페이스 멤버를 명시적으로 구현하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: dff094aca237ed6146bd9b52813c40549bc99b9b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627787"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="bbfdd-102">인터페이스 멤버를 명시적으로 구현하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="bbfdd-102">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="bbfdd-103">이 예제에서는 [interface](../../language-reference/keywords/interface.md)`IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `GetLength` 및 `GetWidth`를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bbfdd-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="bbfdd-104">멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bbfdd-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbfdd-105">예제</span><span class="sxs-lookup"><span data-stu-id="bbfdd-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="bbfdd-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bbfdd-106">Robust Programming</span></span>  
  
- <span data-ttu-id="bbfdd-107">`Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbfdd-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="bbfdd-108">명시적으로 구현된 인터페이스 멤버는 [class](../../language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbfdd-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="bbfdd-109">또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="bbfdd-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="bbfdd-110">참조</span><span class="sxs-lookup"><span data-stu-id="bbfdd-110">See also</span></span>

- [<span data-ttu-id="bbfdd-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bbfdd-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bbfdd-112">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="bbfdd-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="bbfdd-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbfdd-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="bbfdd-114">두 인터페이스의 멤버를 명시적으로 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="bbfdd-114">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
