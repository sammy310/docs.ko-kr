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
ms.openlocfilehash: a39e896f1242452c7bcc94faa1e7ef3086ae2149
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380724"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="02923-104">\<typeparamref>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="02923-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="02923-105">구문</span><span class="sxs-lookup"><span data-stu-id="02923-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="02923-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02923-106">Parameters</span></span>

- `name`

  <span data-ttu-id="02923-107">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="02923-107">The name of the type parameter.</span></span> <span data-ttu-id="02923-108">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="02923-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="02923-109">설명</span><span class="sxs-lookup"><span data-stu-id="02923-109">Remarks</span></span>

<span data-ttu-id="02923-110">제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02923-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="02923-111">이 태그를 사용하면 문서 파일의 소비자가 기울임꼴 등 다른 고유한 방식으로 단어의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02923-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="02923-112">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="02923-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="02923-113">예제</span><span class="sxs-lookup"><span data-stu-id="02923-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="02923-114">참조</span><span class="sxs-lookup"><span data-stu-id="02923-114">See also</span></span>

- [<span data-ttu-id="02923-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="02923-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="02923-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="02923-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
