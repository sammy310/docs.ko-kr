---
title: protected 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713185"
---
# <a name="protected-c-reference"></a><span data-ttu-id="32c67-102">protected(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="32c67-102">protected (C# Reference)</span></span>

<span data-ttu-id="32c67-103">`protected` 키워드는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="32c67-104">이 페이지에서는 `protected` 액세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-104">This page covers `protected` access.</span></span> <span data-ttu-id="32c67-105">`protected` 키워드는 [`protected internal`](protected-internal.md) 및 [`private protected`](private-protected.md) 액세스 한정자의 일부이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="32c67-106">protected 멤버는 해당 클래스 내에서 파생 클래스 인스턴스가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="32c67-107">`protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32c67-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="32c67-108">예제</span><span class="sxs-lookup"><span data-stu-id="32c67-108">Example</span></span>

<span data-ttu-id="32c67-109">기본 클래스의 protected 멤버는 파생 클래스 형식을 통해 액세스가 발생하는 경우에만 파생 클래스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="32c67-110">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="32c67-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="32c67-111">`a.x = 10` 문은 정적 메서드 Main 내에서 작성되었으며 클래스 B의 인스턴스가 아니므로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="32c67-112">구조체를 상속할 수 없기 때문에 구조체 멤버는 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="32c67-113">예제</span><span class="sxs-lookup"><span data-stu-id="32c67-113">Example</span></span>

<span data-ttu-id="32c67-114">이 예제에서 `DerivedPoint` 클래스는 `Point`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="32c67-115">따라서 파생 클래스에서 직접 기본 클래스의 protected 멤버를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="32c67-116">`x` 및 `y`의 액세스 수준을 [private](private.md)로 변경하는 경우 컴파일러가 오류 메시지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="32c67-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="32c67-117">C# language specification</span></span>  

<span data-ttu-id="32c67-118">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [선언된 내게 필요한 옵션](~/_csharplang/spec/basic-concepts.md#declared-accessibility)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32c67-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="32c67-119">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32c67-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="32c67-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32c67-120">See also</span></span>

- [<span data-ttu-id="32c67-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="32c67-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="32c67-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="32c67-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32c67-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="32c67-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="32c67-124">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="32c67-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="32c67-125">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="32c67-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="32c67-126">한정자</span><span class="sxs-lookup"><span data-stu-id="32c67-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="32c67-127">public</span><span class="sxs-lookup"><span data-stu-id="32c67-127">public</span></span>](public.md)
- [<span data-ttu-id="32c67-128">private</span><span class="sxs-lookup"><span data-stu-id="32c67-128">private</span></span>](private.md)
- [<span data-ttu-id="32c67-129">internal</span><span class="sxs-lookup"><span data-stu-id="32c67-129">internal</span></span>](internal.md)
- <span data-ttu-id="32c67-130">[internal virtual 키워드에 대한 보안 문제](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="32c67-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
