---
title: <para> - C# 프로그래밍 가이드
description: XML <para> 태그에 대해 알아봅니다. 이 태그를 사용하면 다음과 같은 다른 태그의 텍스트에 구조체를 추가할 수 있습니다. <summary>, <remarks>또는 <returns>.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381855"
---
# <a name="para-c-programming-guide"></a><span data-ttu-id="ad0dd-108">\<para>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ad0dd-108">\<para> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad0dd-109">구문</span><span class="sxs-lookup"><span data-stu-id="ad0dd-109">Syntax</span></span>

```xml
<para>content</para>
```

## <a name="parameters"></a><span data-ttu-id="ad0dd-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad0dd-110">Parameters</span></span>

- `content`

  <span data-ttu-id="ad0dd-111">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-111">The text of the paragraph.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad0dd-112">설명</span><span class="sxs-lookup"><span data-stu-id="ad0dd-112">Remarks</span></span>

<span data-ttu-id="ad0dd-113">`<para>` 태그는 [\<summary>](./summary.md), [\<remarks>](./remarks.md) 또는 [\<returns>](./returns.md) 같은 태그 내에 사용되어 텍스트에 구조를 추가할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-113">The `<para>` tag is for use inside a tag, such as [\<summary>](./summary.md), [\<remarks>](./remarks.md), or [\<returns>](./returns.md), and lets you add structure to the text.</span></span>

<span data-ttu-id="ad0dd-114">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ad0dd-115">예제</span><span class="sxs-lookup"><span data-stu-id="ad0dd-115">Example</span></span>

<span data-ttu-id="ad0dd-116">`<para>` 사용 예제는 [\<summary>](./summary.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-116">See [\<summary>](./summary.md) for an example of using `<para>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad0dd-117">참조</span><span class="sxs-lookup"><span data-stu-id="ad0dd-117">See also</span></span>

- [<span data-ttu-id="ad0dd-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ad0dd-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ad0dd-119">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="ad0dd-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
