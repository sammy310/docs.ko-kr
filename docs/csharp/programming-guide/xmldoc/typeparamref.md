---
title: <typeparamref> - C# 프로그래밍 가이드
description: XML <typeparamref> 태그에 대해 알아봅니다. 이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 1bb9a73f4122f3b9d521565a7172a9b8f75f7a98
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477672"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="2d173-104">\<typeparamref>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2d173-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d173-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d173-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="2d173-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d173-106">Parameters</span></span>

- `name`

  <span data-ttu-id="2d173-107">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2d173-107">The name of the type parameter.</span></span> <span data-ttu-id="2d173-108">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="2d173-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="2d173-109">설명</span><span class="sxs-lookup"><span data-stu-id="2d173-109">Remarks</span></span>

<span data-ttu-id="2d173-110">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d173-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="2d173-111">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d173-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="2d173-112">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2d173-112">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2d173-113">예제</span><span class="sxs-lookup"><span data-stu-id="2d173-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="2d173-114">참조</span><span class="sxs-lookup"><span data-stu-id="2d173-114">See also</span></span>

- [<span data-ttu-id="2d173-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2d173-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="2d173-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="2d173-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
