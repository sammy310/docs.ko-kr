---
title: <exception> - C# 프로그래밍 가이드
description: XML <exception> 태그에 대해 알아봅니다. 이 태그는 throw할 수 있는 예외를 지정하는 데 사용되며 메서드, 속성, 이벤트 및 인덱서에 적용될 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381738"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="50a65-104">\<exception>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="50a65-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="50a65-105">구문</span><span class="sxs-lookup"><span data-stu-id="50a65-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="50a65-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50a65-106">Parameters</span></span>

- <span data-ttu-id="50a65-107">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="50a65-107">cref = " `member`"</span></span>

  <span data-ttu-id="50a65-108">현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="50a65-109">컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="50a65-110">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="50a65-111">제네릭 형식을 참조하도록 `member` 형식을 지정하는 방법에 대한 자세한 내용은 [XML 파일 처리](processing-the-xml-file.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a65-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="50a65-112">예외에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="50a65-113">설명</span><span class="sxs-lookup"><span data-stu-id="50a65-113">Remarks</span></span>

<span data-ttu-id="50a65-114">`<exception>` 태그를 사용하면 throw할 수 있는 예외를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="50a65-115">이 태그는 메서드, 속성, 이벤트 및 인덱서에 대한 정의에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="50a65-116">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="50a65-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="50a65-117">예외 처리에 대한 자세한 내용은 [예외 및 예외 처리](../exceptions/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a65-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="50a65-118">예제</span><span class="sxs-lookup"><span data-stu-id="50a65-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="50a65-119">참조</span><span class="sxs-lookup"><span data-stu-id="50a65-119">See also</span></span>

- [<span data-ttu-id="50a65-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="50a65-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="50a65-121">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="50a65-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
