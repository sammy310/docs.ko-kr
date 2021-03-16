---
title: 복사 생성자를 작성하는 방법 - C# 프로그래밍 가이드
description: C#에서 클래스의 인스턴스를 가져와서 입력 값으로 새 인스턴스를 반환하는 복사 생성자를 작성하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: c61018444dd600d6f33765b104034355d0301667
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255238"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="ff25c-103">복사 생성자를 작성하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ff25c-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="ff25c-104">C# [레코드](records.md)는 개체의 복사 생성자를 제공하지만 클래스의 경우 직접 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff25c-104">C# [records](records.md) provide a copy constructor for objects, but for classes you have to write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff25c-105">예제</span><span class="sxs-lookup"><span data-stu-id="ff25c-105">Example</span></span>  

 <span data-ttu-id="ff25c-106">다음 예제에서 `Person`[클래스](../../language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff25c-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="ff25c-107">인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff25c-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="ff25c-108">코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff25c-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[CopyConstructor](snippets/how-to-write-a-copy-constructor/Program.cs)]

## <a name="see-also"></a><span data-ttu-id="ff25c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff25c-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="ff25c-110">레코드</span><span class="sxs-lookup"><span data-stu-id="ff25c-110">Records</span></span>](records.md)
- [<span data-ttu-id="ff25c-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ff25c-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ff25c-112">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="ff25c-112">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="ff25c-113">생성자</span><span class="sxs-lookup"><span data-stu-id="ff25c-113">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="ff25c-114">종료자</span><span class="sxs-lookup"><span data-stu-id="ff25c-114">Finalizers</span></span>](./destructors.md)
