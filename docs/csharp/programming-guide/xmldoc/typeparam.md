---
title: <typeparam> - C# 프로그래밍 가이드
description: XML <typeparam> 태그에 대해 알아봅니다. 이 태그는 제네릭 형식 또는 메서드 선언의 주석에서 형식 매개 변수를 설명하는 데 사용됩니다.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 1b9d5d30c1a507e3bb7938ee0c036cdac3ef2f90
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477684"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="0636e-105">\<typeparam>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0636e-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0636e-106">구문</span><span class="sxs-lookup"><span data-stu-id="0636e-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="0636e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0636e-107">Parameters</span></span>

- `name`

  <span data-ttu-id="0636e-108">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-108">The name of the type parameter.</span></span> <span data-ttu-id="0636e-109">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="0636e-110">형식 매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="0636e-111">설명</span><span class="sxs-lookup"><span data-stu-id="0636e-111">Remarks</span></span>

<span data-ttu-id="0636e-112">`<typeparam>` 태그는 제네릭 형식 또는 메서드 선언의 주석에서 형식 매개 변수를 설명하는 데 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="0636e-113">제네릭 형식 또는 메서드의 각 형식 매개 변수에 대한 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="0636e-114">자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0636e-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="0636e-115">`<typeparam>` 태그에 대한 텍스트는 IntelliSense와 [개체 브라우저 창](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)의 코드 주석 웹 보고서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="0636e-116">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0636e-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="0636e-117">예제</span><span class="sxs-lookup"><span data-stu-id="0636e-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="0636e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0636e-118">See also</span></span>

- [<span data-ttu-id="0636e-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0636e-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="0636e-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0636e-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="0636e-121">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="0636e-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
