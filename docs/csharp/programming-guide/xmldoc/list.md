---
title: <list> - C# 프로그래밍 가이드
description: XML <list> 태그에 대해 알아봅니다. 이 태그는 'item' 블록을 사용하여 테이블 및 정의, 글머리 기호 또는 번호 매기기 목록을 만드는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 39674e3c07444e454dfeeceff6c99e65f34bb02f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478387"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="5f4fa-105">\<list>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5f4fa-105">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5f4fa-106">구문</span><span class="sxs-lookup"><span data-stu-id="5f4fa-106">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="5f4fa-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f4fa-107">Parameters</span></span>

- `term`

  <span data-ttu-id="5f4fa-108">`description`에서 정의되는, 정의할 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-108">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="5f4fa-109">글머리 기호 또는 번호 매기기 목록의 항목이나 `term`의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-109">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5f4fa-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f4fa-110">Remarks</span></span>

<span data-ttu-id="5f4fa-111">`<listheader>` 블록은 테이블 또는 정의 목록의 머리글 행을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-111">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="5f4fa-112">테이블을 정의할 때는 머리글에 용어 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-112">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="5f4fa-113">목록의 각 항목은 `<item>` 블록을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="5f4fa-114">정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-114">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="5f4fa-115">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우 `description` 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-115">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="5f4fa-116">목록 또는 테이블에 `<item>` 블록을 필요한 개수만큼 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-116">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="5f4fa-117">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4fa-117">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="5f4fa-118">예제</span><span class="sxs-lookup"><span data-stu-id="5f4fa-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="5f4fa-119">참조</span><span class="sxs-lookup"><span data-stu-id="5f4fa-119">See also</span></span>

- [<span data-ttu-id="5f4fa-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5f4fa-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5f4fa-121">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="5f4fa-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
