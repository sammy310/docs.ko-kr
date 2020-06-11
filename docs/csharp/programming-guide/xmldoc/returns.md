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
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287235"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="8ea57-102">\<returns>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8ea57-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ea57-103">구문</span><span class="sxs-lookup"><span data-stu-id="8ea57-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="8ea57-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ea57-104">Parameters</span></span>

- `description`

  <span data-ttu-id="8ea57-105">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea57-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ea57-106">설명</span><span class="sxs-lookup"><span data-stu-id="8ea57-106">Remarks</span></span>

<span data-ttu-id="8ea57-107">`<returns>` 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea57-107">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="8ea57-108">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea57-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8ea57-109">예제</span><span class="sxs-lookup"><span data-stu-id="8ea57-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="8ea57-110">참조</span><span class="sxs-lookup"><span data-stu-id="8ea57-110">See also</span></span>

- [<span data-ttu-id="8ea57-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8ea57-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8ea57-112">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="8ea57-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
