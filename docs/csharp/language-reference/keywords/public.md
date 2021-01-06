---
description: public 키워드 - C# 참조
title: public 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938470"
---
# <a name="public-c-reference"></a><span data-ttu-id="e503d-103">public(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e503d-103">public (C# Reference)</span></span>

<span data-ttu-id="e503d-104">`public` 키워드는 형식 및 형식 멤버에 대한 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="e503d-105">공용 액세스는 허용 범위가 가장 큰 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="e503d-106">다음 예제와 같이, 공용 멤버 액세스에 대한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="e503d-107">자세한 내용은 [액세스 한정자](../../programming-guide/classes-and-structs/access-modifiers.md) 및 [액세스 가능성 수준](accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e503d-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="e503d-108">예제</span><span class="sxs-lookup"><span data-stu-id="e503d-108">Example</span></span>

<span data-ttu-id="e503d-109">다음 예제에서는 두 개의 클래스, `PointTest` 및 `Program`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-109">In the following example, two classes are declared, `PointTest` and `Program`.</span></span> <span data-ttu-id="e503d-110">`PointTest`의 공용 멤버 `x` 및 `y`는 `Program`에서 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-110">The public members `x` and `y` of `PointTest` are accessed directly from `Program`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="e503d-111">`public` 액세스 수준을 [private](private.md) 또는 [protected](protected.md)로 변경하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="e503d-112">보호 수준 때문에 'PointTest.y'에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e503d-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e503d-113">C# language specification</span></span>  

<span data-ttu-id="e503d-114">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [선언된 내게 필요한 옵션](~/_csharplang/spec/basic-concepts.md#declared-accessibility)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e503d-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="e503d-115">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e503d-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="e503d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e503d-116">See also</span></span>

- [<span data-ttu-id="e503d-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e503d-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e503d-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e503d-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e503d-119">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="e503d-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="e503d-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="e503d-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e503d-121">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="e503d-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="e503d-122">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="e503d-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="e503d-123">한정자</span><span class="sxs-lookup"><span data-stu-id="e503d-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e503d-124">private</span><span class="sxs-lookup"><span data-stu-id="e503d-124">private</span></span>](private.md)
- [<span data-ttu-id="e503d-125">protected</span><span class="sxs-lookup"><span data-stu-id="e503d-125">protected</span></span>](protected.md)
- [<span data-ttu-id="e503d-126">internal</span><span class="sxs-lookup"><span data-stu-id="e503d-126">internal</span></span>](internal.md)
