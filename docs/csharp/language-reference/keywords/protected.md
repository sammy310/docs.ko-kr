---
description: protected 키워드 - C# 참조
title: protected 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: d8d9a75bb5e07816adaa8d09c96cee8a240130fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688915"
---
# <a name="protected-c-reference"></a><span data-ttu-id="bd5b8-103">protected(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bd5b8-103">protected (C# Reference)</span></span>

<span data-ttu-id="bd5b8-104">`protected` 키워드는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-104">The `protected` keyword is a member access modifier.</span></span>

> [!NOTE]
> <span data-ttu-id="bd5b8-105">이 페이지에서는 `protected` 액세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-105">This page covers `protected` access.</span></span> <span data-ttu-id="bd5b8-106">`protected` 키워드는 [`protected internal`](protected-internal.md) 및 [`private protected`](private-protected.md) 액세스 한정자의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-106">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="bd5b8-107">protected 멤버는 해당 클래스 내에서 파생 클래스 인스턴스가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-107">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="bd5b8-108">`protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-108">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="bd5b8-109">예제</span><span class="sxs-lookup"><span data-stu-id="bd5b8-109">Example</span></span>

<span data-ttu-id="bd5b8-110">기본 클래스의 protected 멤버는 파생 클래스 형식을 통해 액세스가 발생하는 경우에만 파생 클래스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-110">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="bd5b8-111">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-111">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="bd5b8-112">`a.x = 10` 문은 정적 메서드 Main 내에서 작성되었으며 클래스 B의 인스턴스가 아니므로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-112">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="bd5b8-113">구조체를 상속할 수 없기 때문에 구조체 멤버는 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-113">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="bd5b8-114">예제</span><span class="sxs-lookup"><span data-stu-id="bd5b8-114">Example</span></span>

<span data-ttu-id="bd5b8-115">이 예제에서 `DerivedPoint` 클래스는 `Point`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-115">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="bd5b8-116">따라서 파생 클래스에서 직접 기본 클래스의 protected 멤버를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-116">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="bd5b8-117">`x` 및 `y`의 액세스 수준을 [private](private.md)로 변경하는 경우 컴파일러가 오류 메시지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-117">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="bd5b8-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bd5b8-118">C# language specification</span></span>  

<span data-ttu-id="bd5b8-119">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [선언된 내게 필요한 옵션](~/_csharplang/spec/basic-concepts.md#declared-accessibility)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="bd5b8-120">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd5b8-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd5b8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd5b8-121">See also</span></span>

- [<span data-ttu-id="bd5b8-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bd5b8-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bd5b8-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bd5b8-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bd5b8-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="bd5b8-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bd5b8-125">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="bd5b8-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="bd5b8-126">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="bd5b8-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="bd5b8-127">한정자</span><span class="sxs-lookup"><span data-stu-id="bd5b8-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="bd5b8-128">public</span><span class="sxs-lookup"><span data-stu-id="bd5b8-128">public</span></span>](public.md)
- [<span data-ttu-id="bd5b8-129">private</span><span class="sxs-lookup"><span data-stu-id="bd5b8-129">private</span></span>](private.md)
- [<span data-ttu-id="bd5b8-130">internal</span><span class="sxs-lookup"><span data-stu-id="bd5b8-130">internal</span></span>](internal.md)
- <span data-ttu-id="bd5b8-131">[internal virtual 키워드에 대한 보안 문제](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd5b8-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
