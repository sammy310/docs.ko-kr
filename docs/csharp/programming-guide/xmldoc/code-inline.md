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
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382024"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="d72bf-104">\<c>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d72bf-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="d72bf-105">구문</span><span class="sxs-lookup"><span data-stu-id="d72bf-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="d72bf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d72bf-106">Parameters</span></span>

- `text`

  <span data-ttu-id="d72bf-107">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="d72bf-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d72bf-108">설명</span><span class="sxs-lookup"><span data-stu-id="d72bf-108">Remarks</span></span>

<span data-ttu-id="d72bf-109">`<c>` 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72bf-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="d72bf-110">여러 줄을 코드로 지정하려면 [\<code>](./code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d72bf-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="d72bf-111">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d72bf-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="d72bf-112">예제</span><span class="sxs-lookup"><span data-stu-id="d72bf-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="d72bf-113">참조</span><span class="sxs-lookup"><span data-stu-id="d72bf-113">See also</span></span>

- [<span data-ttu-id="d72bf-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d72bf-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="d72bf-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="d72bf-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
