---
title: value 상황별 키워드 제거 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: cfd370df771998057fd421a0917b3e2fcd96d9f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633034"
---
# <a name="value-c-reference"></a><span data-ttu-id="a71d4-102">value(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a71d4-102">value (C# Reference)</span></span>

<span data-ttu-id="a71d4-103">상황별 키워드 `value`는 일반 속성 선언의 set 접근자에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71d4-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="a71d4-104">메서드의 입력 매개 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="a71d4-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="a71d4-105">`value` 단어는 클라이언트 코드가 속성에 할당하려고 시도하는 값을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a71d4-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="a71d4-106">다음 예에서 `MyDerivedClass`에는 `Name`이라는 속성이 있습니다. 이 속성은 `value` 매개 변수를 사용하여 지원 필드 `name`에 새 문자열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a71d4-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="a71d4-107">클라이언트 코드의 관점에서 이 작업은 단순한 할당으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71d4-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="a71d4-108">`value` 사용에 대한 자세한 내용은 [속성](../../programming-guide/classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a71d4-108">For more information about the use of `value`, see [Properties](../../programming-guide/classes-and-structs/properties.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a71d4-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a71d4-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a71d4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a71d4-110">See also</span></span>

- [<span data-ttu-id="a71d4-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a71d4-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a71d4-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a71d4-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a71d4-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a71d4-113">C# Keywords</span></span>](index.md)
