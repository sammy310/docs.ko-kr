---
title: new 제약 조건 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 6f6d1b663d03dc9b3adf0e7055dcffacc79d83dc
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795341"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="78aa4-102">new 제약 조건(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="78aa4-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="78aa4-103">`new` 제약 조건은 제네릭 클래스 선언의 형식 인수에 공용 매개 변수가 없는 생성자가 있어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78aa4-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="78aa4-104">`new` 제약 조건을 사용하기 위해 유형을 추상화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78aa4-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="78aa4-105">다음 예제와 같이 제네릭 클래스가 형식의 새 인스턴스를 만드는 경우 형식 매개 변수에 `new` 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="78aa4-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="78aa4-106">다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 마지막에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78aa4-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="78aa4-107">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78aa4-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="78aa4-108">`new` 키워드를 사용하여 [형식의 인스턴스를 만들](../operators/new-operator.md)거나 [멤버 선언 한정자](new-modifier.md)로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78aa4-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="78aa4-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="78aa4-109">C# language specification</span></span>

<span data-ttu-id="78aa4-110">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/classes.md#type-parameter-constraints)의 [유형 매개 변수 제약 조건](~/_csharplang/spec/introduction.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78aa4-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78aa4-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78aa4-111">See also</span></span>

- [<span data-ttu-id="78aa4-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="78aa4-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="78aa4-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="78aa4-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="78aa4-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="78aa4-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="78aa4-115">제네릭</span><span class="sxs-lookup"><span data-stu-id="78aa4-115">Generics</span></span>](../../programming-guide/generics/index.md)
