---
title: <remarks> - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 739027786e02e559d86f990bf614e261b497c76f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287287"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="b4bc4-102">\<remarks>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b4bc4-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4bc4-103">구문</span><span class="sxs-lookup"><span data-stu-id="b4bc4-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="b4bc4-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4bc4-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="b4bc4-105">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4bc4-106">설명</span><span class="sxs-lookup"><span data-stu-id="b4bc4-106">Remarks</span></span>

<span data-ttu-id="b4bc4-107">`<remarks>` 태그는 형식에 대한 정보를 추가하여 [\<summary>](./summary.md)로 지정된 정보를 보완하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-107">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="b4bc4-108">이 정보는 개체 브라우저 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="b4bc4-109">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b4bc4-110">예제</span><span class="sxs-lookup"><span data-stu-id="b4bc4-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="b4bc4-111">참조</span><span class="sxs-lookup"><span data-stu-id="b4bc4-111">See also</span></span>

- [<span data-ttu-id="b4bc4-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b4bc4-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b4bc4-113">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="b4bc4-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
