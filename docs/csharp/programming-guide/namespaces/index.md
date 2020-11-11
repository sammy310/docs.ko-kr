---
title: 네임스페이스 - C# 프로그래밍 가이드
description: C# 프로그래밍에서 네임스페이스에 대해 알아봅니다. 네임스페이스 속성의 개요를 확인하고 추가 리소스를 봅니다.
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 41a666fd5f368e6990e08a36700e18f648939213
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440343"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="56b67-104">네임스페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="56b67-104">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="56b67-105">네임스페이스는 C# 프로그래밍에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-105">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="56b67-106">먼저 .NET은 다음과 같이 네임스페이스를 사용하여 여러 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-106">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="56b67-107"><xref:System>은 네임스페이스이고 <xref:System.Console>은 해당 네임스페이스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-107"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="56b67-108">전체 키워드가 필요하지 않으므로 다음 예처럼 `using` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-108">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="56b67-109">자세한 내용은 [using 지시문](../../language-reference/keywords/using-directive.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56b67-109">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="56b67-110">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-110">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="56b67-111">다음 예와 같이 [네임스페이스](../../language-reference/keywords/namespace.md) 키워드를 사용하여 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-111">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="56b67-112">네임스페이스 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-112">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="56b67-113">네임스페이스 개요</span><span class="sxs-lookup"><span data-stu-id="56b67-113">Namespaces overview</span></span>

<span data-ttu-id="56b67-114">네임스페이스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-114">Namespaces have the following properties:</span></span>

- <span data-ttu-id="56b67-115">대규모 코드 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-115">They organize large code projects.</span></span>
- <span data-ttu-id="56b67-116">`.` 연산자를 사용하여 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-116">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="56b67-117">`using` 지시문은 모든 클래스에 대해 네임스페이스 이름을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-117">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="56b67-118">`global` 네임스페이스는 “루트” 네임스페이스입니다. `global::System`은 항상 .NET <xref:System> 네임스페이스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="56b67-118">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56b67-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="56b67-119">C# language specification</span></span>

<span data-ttu-id="56b67-120">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [네임스페이스](~/_csharplang/spec/namespaces.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56b67-120">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56b67-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56b67-121">See also</span></span>

- [<span data-ttu-id="56b67-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="56b67-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="56b67-123">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="56b67-123">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="56b67-124">My 네임스페이스를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="56b67-124">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="56b67-125">식별자 이름</span><span class="sxs-lookup"><span data-stu-id="56b67-125">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="56b67-126">using 지시문</span><span class="sxs-lookup"><span data-stu-id="56b67-126">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="56b67-127">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="56b67-127">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
