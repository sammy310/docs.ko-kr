---
title: <returns> - C# 프로그래밍 가이드
description: XML <returns> 태그에 대해 알아봅니다. 이 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 6a098208a51ca31fe2278b7c696deb15a13f8e1e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477814"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="4929b-105">\<returns>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4929b-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4929b-106">구문</span><span class="sxs-lookup"><span data-stu-id="4929b-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="4929b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4929b-107">Parameters</span></span>

- `description`

  <span data-ttu-id="4929b-108">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4929b-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="4929b-109">설명</span><span class="sxs-lookup"><span data-stu-id="4929b-109">Remarks</span></span>

<span data-ttu-id="4929b-110">`<returns>` 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4929b-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="4929b-111">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4929b-111">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4929b-112">예제</span><span class="sxs-lookup"><span data-stu-id="4929b-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="4929b-113">참조</span><span class="sxs-lookup"><span data-stu-id="4929b-113">See also</span></span>

- [<span data-ttu-id="4929b-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4929b-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4929b-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="4929b-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
