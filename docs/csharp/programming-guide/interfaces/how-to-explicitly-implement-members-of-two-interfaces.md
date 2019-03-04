---
title: '방법: 두 인터페이스의 멤버를 명시적으로 구현 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 9e4805f2a9d1a4a18166ea7bcc8fbf8a099e0b9e
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200912"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="01cf0-102">방법: 두 인터페이스의 멤버를 명시적으로 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="01cf0-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="01cf0-103">명시적 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 구현을 통해 프로그래머는 멤버 이름이 같고 각 인터페이스 멤버에 별도 구현을 제공하는 두 인터페이스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="01cf0-104">이 예제에서는 미터 단위와 인치 단위 모두로 상자 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="01cf0-105">상자 [class](../../../csharp/language-reference/keywords/class.md)는 서로 다른 측정 시스템을 나타내는 두 인터페이스 IEnglishDimensions 및 IMetricDimensions를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="01cf0-106">두 인터페이스에 동일한 멤버 이름 Length와 Width가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01cf0-107">예제</span><span class="sxs-lookup"><span data-stu-id="01cf0-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="01cf0-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="01cf0-108">Robust Programming</span></span>  
 <span data-ttu-id="01cf0-109">기본 측정값을 인치 단위로 설정하려면 일반적으로 Length 및 Width 메서드를 구현하고, IMetricDimensions 인터페이스에서 Length 및 Width 메서드를 명시적으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="01cf0-110">이 경우 클래스 인스턴스에서 인치 단위에 액세스하고 인터페이스 인스턴스에서 미터 단위에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01cf0-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="01cf0-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01cf0-111">See also</span></span>

- [<span data-ttu-id="01cf0-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="01cf0-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="01cf0-113">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="01cf0-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="01cf0-114">인터페이스</span><span class="sxs-lookup"><span data-stu-id="01cf0-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="01cf0-115">방법: 인터페이스 멤버를 명시적으로 구현</span><span class="sxs-lookup"><span data-stu-id="01cf0-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
