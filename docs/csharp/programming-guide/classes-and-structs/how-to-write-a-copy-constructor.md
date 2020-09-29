---
title: 복사 생성자를 작성하는 방법 - C# 프로그래밍 가이드
description: C#에서 클래스의 인스턴스를 가져와서 입력 값으로 새 인스턴스를 반환하는 복사 생성자를 작성하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 52fd5aedea6a0e3b7c22e20db523329a00bba9ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204010"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="776a4-103">복사 생성자를 작성하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="776a4-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="776a4-104">C#에서는 개체에 대한 복사 생성자를 제공하지 않지만 직접 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776a4-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="776a4-105">예제</span><span class="sxs-lookup"><span data-stu-id="776a4-105">Example</span></span>  

 <span data-ttu-id="776a4-106">다음 예제에서 `Person`[클래스](../../language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="776a4-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="776a4-107">인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="776a4-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="776a4-108">코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776a4-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="776a4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="776a4-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="776a4-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="776a4-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="776a4-111">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="776a4-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="776a4-112">생성자</span><span class="sxs-lookup"><span data-stu-id="776a4-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="776a4-113">종료자</span><span class="sxs-lookup"><span data-stu-id="776a4-113">Finalizers</span></span>](./destructors.md)
