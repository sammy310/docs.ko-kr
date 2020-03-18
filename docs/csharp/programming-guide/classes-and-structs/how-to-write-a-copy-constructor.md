---
title: 복사 생성자를 작성하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714846"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="a0096-102">복사 생성자를 작성하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a0096-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="a0096-103">C#에서는 개체에 대한 복사 생성자를 제공하지 않지만 직접 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0096-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0096-104">예제</span><span class="sxs-lookup"><span data-stu-id="a0096-104">Example</span></span>  
 <span data-ttu-id="a0096-105">다음 예제에서 `Person`[클래스](../../language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a0096-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="a0096-106">인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0096-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="a0096-107">코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0096-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="a0096-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0096-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="a0096-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a0096-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a0096-110">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="a0096-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="a0096-111">생성자</span><span class="sxs-lookup"><span data-stu-id="a0096-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="a0096-112">종료자</span><span class="sxs-lookup"><span data-stu-id="a0096-112">Finalizers</span></span>](./destructors.md)
