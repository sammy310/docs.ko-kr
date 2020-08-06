---
title: <example> - C# 프로그래밍 가이드
description: XML <example> 태그에 대해 알아봅니다. 이 태그를 사용하면 메서드 또는 기타 라이브러리 멤버를 사용하는 방법의 예제를 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381530"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="1a957-105">\<example>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1a957-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a957-106">구문</span><span class="sxs-lookup"><span data-stu-id="1a957-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="1a957-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a957-107">Parameters</span></span>

- `description`

  <span data-ttu-id="1a957-108">코드 샘플에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1a957-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a957-109">설명</span><span class="sxs-lookup"><span data-stu-id="1a957-109">Remarks</span></span>

<span data-ttu-id="1a957-110">`<example>` 태그를 사용하면 메서드 또는 기타 라이브러리 멤버를 사용하는 방법의 예제를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a957-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="1a957-111">여기에는 일반적으로 [\<code>](./code.md) 태그를 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a957-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="1a957-112">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1a957-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1a957-113">예제</span><span class="sxs-lookup"><span data-stu-id="1a957-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="1a957-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a957-114">See also</span></span>

- [<span data-ttu-id="1a957-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1a957-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1a957-116">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="1a957-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
