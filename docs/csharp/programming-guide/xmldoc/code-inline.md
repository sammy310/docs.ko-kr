---
title: <c> - C# 프로그래밍 가이드
description: XML <c> 태그에 대해 알아봅니다. 이 태그는 설명의 한 줄 텍스트를 코드로 표시하고, <code> indicates multiple lines.
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: fc445c7245287c3835543e4bbe4b3b46ec46fd35
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478695"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="821c4-104">\<c>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="821c4-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="821c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="821c4-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="821c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="821c4-106">Parameters</span></span>

- `text`

  <span data-ttu-id="821c4-107">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="821c4-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="821c4-108">설명</span><span class="sxs-lookup"><span data-stu-id="821c4-108">Remarks</span></span>

<span data-ttu-id="821c4-109">`<c>` 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="821c4-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="821c4-110">여러 줄을 코드로 지정하려면 [\<code>](./code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="821c4-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="821c4-111">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="821c4-111">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="821c4-112">예제</span><span class="sxs-lookup"><span data-stu-id="821c4-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="821c4-113">참조</span><span class="sxs-lookup"><span data-stu-id="821c4-113">See also</span></span>

- [<span data-ttu-id="821c4-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="821c4-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="821c4-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="821c4-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
