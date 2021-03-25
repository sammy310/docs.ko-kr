---
title: <remarks> - C# 프로그래밍 가이드
description: XML <remarks> 태그에 대해 알아봅니다. 이 태그는 형식에 대한 정보를 추가하여 다음으로 지정된 정보를 보완하기 위해 사용됩니다. <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 2227dd8bd4d81f5fda8cf529e18c7a613cca6b8e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477817"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="eaa3e-106">\<remarks>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="eaa3e-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="eaa3e-107">구문</span><span class="sxs-lookup"><span data-stu-id="eaa3e-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="eaa3e-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eaa3e-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="eaa3e-109">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="eaa3e-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="eaa3e-110">설명</span><span class="sxs-lookup"><span data-stu-id="eaa3e-110">Remarks</span></span>

<span data-ttu-id="eaa3e-111">`<remarks>` 태그는 형식에 대한 정보를 추가하여 [\<summary>](./summary.md)로 지정된 정보를 보완하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa3e-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="eaa3e-112">이 정보는 개체 브라우저 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa3e-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="eaa3e-113">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa3e-113">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="eaa3e-114">예제</span><span class="sxs-lookup"><span data-stu-id="eaa3e-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="eaa3e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaa3e-115">See also</span></span>

- [<span data-ttu-id="eaa3e-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eaa3e-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="eaa3e-117">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="eaa3e-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
