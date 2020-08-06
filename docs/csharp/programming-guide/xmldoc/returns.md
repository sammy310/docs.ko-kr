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
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381400"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="90260-105">\<returns>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="90260-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="90260-106">구문</span><span class="sxs-lookup"><span data-stu-id="90260-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="90260-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90260-107">Parameters</span></span>

- `description`

  <span data-ttu-id="90260-108">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="90260-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="90260-109">설명</span><span class="sxs-lookup"><span data-stu-id="90260-109">Remarks</span></span>

<span data-ttu-id="90260-110">`<returns>` 태그는 메서드 선언의 주석에서 반환 값을 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90260-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="90260-111">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="90260-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="90260-112">예제</span><span class="sxs-lookup"><span data-stu-id="90260-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="90260-113">참조</span><span class="sxs-lookup"><span data-stu-id="90260-113">See also</span></span>

- [<span data-ttu-id="90260-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="90260-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="90260-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="90260-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
