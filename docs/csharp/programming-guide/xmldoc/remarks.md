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
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381504"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="296f3-106">\<remarks>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="296f3-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="296f3-107">구문</span><span class="sxs-lookup"><span data-stu-id="296f3-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="296f3-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="296f3-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="296f3-109">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="296f3-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="296f3-110">설명</span><span class="sxs-lookup"><span data-stu-id="296f3-110">Remarks</span></span>

<span data-ttu-id="296f3-111">`<remarks>` 태그는 형식에 대한 정보를 추가하여 [\<summary>](./summary.md)로 지정된 정보를 보완하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="296f3-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="296f3-112">이 정보는 개체 브라우저 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="296f3-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="296f3-113">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="296f3-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="296f3-114">예제</span><span class="sxs-lookup"><span data-stu-id="296f3-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="296f3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="296f3-115">See also</span></span>

- [<span data-ttu-id="296f3-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="296f3-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="296f3-117">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="296f3-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
