---
description: 네임스페이스 키워드 - C# 참조
title: 네임스페이스 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: a6cfd1c3d37cbdef1f0dd72ddca85ce91f2e183b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139582"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="fc117-103">namespace(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fc117-103">namespace (C# Reference)</span></span>

<span data-ttu-id="fc117-104">`namespace` 키워드는 관련 개체 집합을 포함하는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-104">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="fc117-105">네임스페이스를 사용하여 코드 요소를 구성하고 전역적으로 고유한 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-105">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="fc117-106">설명</span><span class="sxs-lookup"><span data-stu-id="fc117-106">Remarks</span></span>

<span data-ttu-id="fc117-107">네임스페이스 내에서 다음 형식 중 0개 이상을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-107">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="fc117-108">다른 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fc117-108">another namespace</span></span>

- [<span data-ttu-id="fc117-109">class</span><span class="sxs-lookup"><span data-stu-id="fc117-109">class</span></span>](class.md)

- [<span data-ttu-id="fc117-110">interface</span><span class="sxs-lookup"><span data-stu-id="fc117-110">interface</span></span>](interface.md)

- [<span data-ttu-id="fc117-111">struct</span><span class="sxs-lookup"><span data-stu-id="fc117-111">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="fc117-112">enum</span><span class="sxs-lookup"><span data-stu-id="fc117-112">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="fc117-113">delegate</span><span class="sxs-lookup"><span data-stu-id="fc117-113">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="fc117-114">C# 소스 파일에서 네임스페이스를 명시적으로 선언하는지 여부에 관계없이 컴파일러는 기본 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="fc117-115">전역 네임스페이스라고도 하는 이 명명되지 않은 네임스페이스는 모든 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="fc117-116">전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="fc117-117">네임스페이스는 암시적으로 공용 액세스를 사용하며 이 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="fc117-118">네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 설명은 [액세스 한정자](access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc117-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="fc117-119">둘 이상의 선언에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="fc117-120">예를 들어 다음 예제에서는 `MyCompany` 네임스페이스의 일부로 두 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="fc117-121">예제</span><span class="sxs-lookup"><span data-stu-id="fc117-121">Example</span></span>

<span data-ttu-id="fc117-122">다음 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc117-122">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="fc117-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fc117-123">C# language specification</span></span>

<span data-ttu-id="fc117-124">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [네임스페이스](~/_csharplang/spec/namespaces.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc117-124">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc117-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc117-125">See also</span></span>

- [<span data-ttu-id="fc117-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fc117-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fc117-127">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fc117-127">C# keywords</span></span>](index.md)
- [<span data-ttu-id="fc117-128">using</span><span class="sxs-lookup"><span data-stu-id="fc117-128">using</span></span>](using-directive.md)
- [<span data-ttu-id="fc117-129">Static 사용</span><span class="sxs-lookup"><span data-stu-id="fc117-129">using static</span></span>](using-static.md)
- [<span data-ttu-id="fc117-130">네임스페이스 별칭 한정자`::`</span><span class="sxs-lookup"><span data-stu-id="fc117-130">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="fc117-131">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fc117-131">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
