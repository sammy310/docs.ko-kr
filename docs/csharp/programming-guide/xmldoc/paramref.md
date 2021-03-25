---
title: <paramref> - C# 프로그래밍 가이드
description: XML <paramref> 태그에 대해 알아봅니다. 이 태그는 코드의 단어가 매개 변수임을 나타내는 방법을 제공합니다.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e559a899aad7806bb7ccef32be49954fabed6a32
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477881"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="04074-104">\<paramref>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="04074-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="04074-105">구문</span><span class="sxs-lookup"><span data-stu-id="04074-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="04074-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04074-106">Parameters</span></span>

- `name`

  <span data-ttu-id="04074-107">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04074-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="04074-108">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="04074-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="04074-109">설명</span><span class="sxs-lookup"><span data-stu-id="04074-109">Remarks</span></span>

<span data-ttu-id="04074-110">`<paramref>` 태그를 사용하면 `<summary>` 또는 `<remarks>` 블록 등의 코드 주석에 포함된 단어가 매개 변수를 참조함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04074-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="04074-111">XML 파일을 처리하여 굵게, 기울임꼴 글꼴 등의 고유한 방식으로 이 단어에 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04074-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="04074-112">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="04074-112">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="04074-113">예제</span><span class="sxs-lookup"><span data-stu-id="04074-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="04074-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04074-114">See also</span></span>

- [<span data-ttu-id="04074-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04074-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04074-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="04074-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
