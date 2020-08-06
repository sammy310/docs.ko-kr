---
title: 인터페이스 멤버를 명시적으로 구현하는 방법 - C# 프로그래밍 가이드
description: 이 C# 예제에서는 인터페이스 멤버를 명시적으로 구현하는 방법을 알아봅니다. 멤버는 인터페이스 인스턴스를 통해 액세스합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303077"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="d76e1-104">인터페이스 멤버를 명시적으로 구현하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d76e1-104">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="d76e1-105">이 예제에서는 [interface](../../language-reference/keywords/interface.md)`IDimensions` 및 `Box` 클래스를 선언합니다. 이 클래스는 인터페이스 멤버 `GetLength` 및 `GetWidth`를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d76e1-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="d76e1-106">멤버는 인터페이스 인스턴스 `dimensions`를 통해 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d76e1-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d76e1-107">예제</span><span class="sxs-lookup"><span data-stu-id="d76e1-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d76e1-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d76e1-108">Robust Programming</span></span>  
  
- <span data-ttu-id="d76e1-109">`Main` 메서드의 다음 줄은 컴파일 오류를 생성하므로 주석으로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d76e1-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="d76e1-110">명시적으로 구현된 인터페이스 멤버는 [class](../../language-reference/keywords/class.md) 인스턴스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d76e1-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="d76e1-111">또한 `Main` 메서드의 다음 줄은 메서드가 인터페이스 인스턴스에서 호출되기 때문에 상자 크기를 성공적으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d76e1-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="d76e1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d76e1-112">See also</span></span>

- [<span data-ttu-id="d76e1-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d76e1-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d76e1-114">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="d76e1-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="d76e1-115">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d76e1-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="d76e1-116">두 인터페이스의 멤버를 명시적으로 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="d76e1-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
