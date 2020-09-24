---
description: value 상황별 키워드 제거 - C# 참조
title: value 상황별 키워드 제거 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ad2eb6f12d8c295dc5203994d6c570cd2377e3ee
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828918"
---
# <a name="value-c-reference"></a><span data-ttu-id="8d7e8-103">value(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8d7e8-103">value (C# Reference)</span></span>

<span data-ttu-id="8d7e8-104">상황별 키워드 `value`는 [속성](../../programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../programming-guide/indexers/index.md) 선언의 `set` 접근자에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-104">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="8d7e8-105">메서드의 입력 매개 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-105">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="8d7e8-106">`value` 단어는 클라이언트 코드에서 속성 또는 인덱서에 할당하려는 값을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-106">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="8d7e8-107">다음 예에서 `MyDerivedClass`에는 `Name`이라는 속성이 있습니다. 이 속성은 `value` 매개 변수를 사용하여 지원 필드 `name`에 새 문자열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-107">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="8d7e8-108">클라이언트 코드의 관점에서 이 작업은 단순한 할당으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-108">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="8d7e8-109">자세한 내용은 [속성](../../programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../programming-guide/indexers/index.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d7e8-109">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexers](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8d7e8-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8d7e8-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8d7e8-111">참조</span><span class="sxs-lookup"><span data-stu-id="8d7e8-111">See also</span></span>

- [<span data-ttu-id="8d7e8-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8d7e8-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8d7e8-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8d7e8-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8d7e8-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8d7e8-114">C# Keywords</span></span>](index.md)
