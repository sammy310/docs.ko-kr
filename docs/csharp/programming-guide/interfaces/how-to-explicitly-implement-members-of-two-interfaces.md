---
title: 두 인터페이스의 멤버를 명시적으로 구현하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c7adc08f62a7f8a14b8e10f8b5ecdd6e37db811d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701240"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="d73c5-102">두 인터페이스의 멤버를 명시적으로 구현하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d73c5-102">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="d73c5-103">명시적 [인터페이스](../../language-reference/keywords/interface.md) 구현을 통해 프로그래머는 멤버 이름이 같고 각 인터페이스 멤버에 별도 구현을 제공하는 두 인터페이스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="d73c5-104">이 예제에서는 미터 단위와 인치 단위 모두로 상자 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="d73c5-105">상자 [class](../../language-reference/keywords/class.md)는 서로 다른 측정 시스템을 나타내는 두 인터페이스 IEnglishDimensions 및 IMetricDimensions를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="d73c5-106">두 인터페이스에 동일한 멤버 이름 Length와 Width가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d73c5-107">예제</span><span class="sxs-lookup"><span data-stu-id="d73c5-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d73c5-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d73c5-108">Robust Programming</span></span>  
 <span data-ttu-id="d73c5-109">기본 측정값을 인치 단위로 설정하려면 일반적으로 Length 및 Width 메서드를 구현하고, IMetricDimensions 인터페이스에서 Length 및 Width 메서드를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="d73c5-110">이 경우 클래스 인스턴스에서 인치 단위에 액세스하고 인터페이스 인스턴스에서 미터 단위에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d73c5-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d73c5-111">참조</span><span class="sxs-lookup"><span data-stu-id="d73c5-111">See also</span></span>

- [<span data-ttu-id="d73c5-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d73c5-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d73c5-113">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="d73c5-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="d73c5-114">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d73c5-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="d73c5-115">인터페이스 멤버를 명시적으로 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="d73c5-115">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
