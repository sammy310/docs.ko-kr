---
title: <returns> - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 784d9effa589c962b8a2b982fd199f74309fb4dc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789707"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="b2096-102">\<returns>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b2096-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2096-103">구문</span><span class="sxs-lookup"><span data-stu-id="b2096-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="b2096-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2096-104">Parameters</span></span>

- `description`

  <span data-ttu-id="b2096-105">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b2096-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2096-106">설명</span><span class="sxs-lookup"><span data-stu-id="b2096-106">Remarks</span></span>

<span data-ttu-id="b2096-107">\<returns> 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2096-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="b2096-108">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b2096-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b2096-109">예제</span><span class="sxs-lookup"><span data-stu-id="b2096-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="b2096-110">참조</span><span class="sxs-lookup"><span data-stu-id="b2096-110">See also</span></span>

- [<span data-ttu-id="b2096-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b2096-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b2096-112">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="b2096-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
