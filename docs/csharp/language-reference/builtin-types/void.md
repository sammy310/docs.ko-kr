---
description: C#의 void 키워드에 관한 자세한 정보
title: void - C# 참조
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
- (void)
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: fb22fffadeff4db9fcd8e1c8753d44455186aa5a
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471639"
---
# <a name="void-c-reference"></a><span data-ttu-id="9a0c4-103">void(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9a0c4-103">void (C# reference)</span></span>

<span data-ttu-id="9a0c4-104">`void`를 [메서드](../../programming-guide/classes-and-structs/methods.md)(또는 [로컬 함수](../../programming-guide/classes-and-structs/local-functions.md))의 반환 형식으로 사용하여 메서드가 값을 반환하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0c4-104">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/shared/VoidType.cs#VoidExample)]

<span data-ttu-id="9a0c4-105">`void`를 참조 형식으로 사용하여 알 수 없는 형식에 대한 포인터를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a0c4-105">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="9a0c4-106">자세한 내용은 [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a0c4-106">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="9a0c4-107">`void`는 변수 형식으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a0c4-107">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a0c4-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a0c4-108">See also</span></span>

- [<span data-ttu-id="9a0c4-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9a0c4-109">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
