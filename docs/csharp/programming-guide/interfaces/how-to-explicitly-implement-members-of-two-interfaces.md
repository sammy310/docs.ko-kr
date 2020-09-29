---
title: 두 인터페이스의 멤버를 명시적으로 구현하는 방법 - C# 프로그래밍 가이드
description: 이 C# 예제에서는 멤버 이름이 동일한 두 인터페이스를 명시적으로 구현하고 각 인터페이스 멤버에 별도의 구현을 제공하는 방법을 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 18b1f9cfb1690d35c0bca0a3c79c1b80ae5dd44d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205089"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="83474-103">두 인터페이스의 멤버를 명시적으로 구현하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="83474-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="83474-104">명시적 [인터페이스](../../language-reference/keywords/interface.md) 구현을 통해 프로그래머는 멤버 이름이 같고 각 인터페이스 멤버에 별도 구현을 제공하는 두 인터페이스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83474-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="83474-105">이 예제에서는 미터 단위와 인치 단위 모두로 상자 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83474-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="83474-106">상자 [class](../../language-reference/keywords/class.md)는 서로 다른 측정 시스템을 나타내는 두 인터페이스 IEnglishDimensions 및 IMetricDimensions를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="83474-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="83474-107">두 인터페이스에 동일한 멤버 이름 Length와 Width가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83474-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83474-108">예제</span><span class="sxs-lookup"><span data-stu-id="83474-108">Example</span></span>  

 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="83474-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="83474-109">Robust Programming</span></span>  

 <span data-ttu-id="83474-110">기본 측정값을 인치 단위로 설정하려면 일반적으로 Length 및 Width 메서드를 구현하고, IMetricDimensions 인터페이스에서 Length 및 Width 메서드를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="83474-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="83474-111">이 경우 클래스 인스턴스에서 인치 단위에 액세스하고 인터페이스 인스턴스에서 미터 단위에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83474-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="83474-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83474-112">See also</span></span>

- [<span data-ttu-id="83474-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="83474-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="83474-114">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="83474-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="83474-115">인터페이스</span><span class="sxs-lookup"><span data-stu-id="83474-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="83474-116">인터페이스 멤버를 명시적으로 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="83474-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
