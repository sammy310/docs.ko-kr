---
title: '방법: 복사 생성자 작성 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 169bdfc53d0c30ffc14e5a9525920679a94fbf23
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982143"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="fb9a1-102">방법: 복사 생성자 작성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fb9a1-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="fb9a1-103">C#에서는 개체에 대한 복사 생성자를 제공하지 않지만 직접 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb9a1-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb9a1-104">예제</span><span class="sxs-lookup"><span data-stu-id="fb9a1-104">Example</span></span>  
 <span data-ttu-id="fb9a1-105">다음 예제에서 `Person`[클래스](../../../csharp/language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9a1-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="fb9a1-106">인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb9a1-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="fb9a1-107">코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb9a1-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="fb9a1-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb9a1-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="fb9a1-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fb9a1-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fb9a1-110">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="fb9a1-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="fb9a1-111">생성자</span><span class="sxs-lookup"><span data-stu-id="fb9a1-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="fb9a1-112">종료자</span><span class="sxs-lookup"><span data-stu-id="fb9a1-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
