---
title: <see> - C# 프로그래밍 가이드
description: XML <see> 태그에 대해 알아봅니다. 이 태그를 사용하면 예를 들어 cref 특성을 사용하여 텍스트 내에서 링크를 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 154feca5e7e4f4d3f5313c4ae05cd991e69e298f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477766"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="7cd67-104">\<see>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7cd67-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7cd67-105">구문</span><span class="sxs-lookup"><span data-stu-id="7cd67-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="7cd67-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7cd67-106">Parameters</span></span>

- <span data-ttu-id="7cd67-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="7cd67-107">cref = "`member`"</span></span>

  <span data-ttu-id="7cd67-108">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="7cd67-109">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="7cd67-110">*멤버* 는 큰따옴표(“ ”)로 묶으세요.</span><span class="sxs-lookup"><span data-stu-id="7cd67-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="7cd67-111">설명</span><span class="sxs-lookup"><span data-stu-id="7cd67-111">Remarks</span></span>

<span data-ttu-id="7cd67-112">`<see>` 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="7cd67-113">참조 섹션에 텍스트를 배치해야 한다고 지정하려면 [\<seealso>](./seealso.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="7cd67-114">코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](./cref-attribute.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="7cd67-115">또한 ``href``는 하이퍼링크로 작동하는 유효한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="7cd67-116">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

<span data-ttu-id="7cd67-117">다음 예제에서는 요약 섹션의 `<see>` 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cd67-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="7cd67-118">참조</span><span class="sxs-lookup"><span data-stu-id="7cd67-118">See also</span></span>

- [<span data-ttu-id="7cd67-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7cd67-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7cd67-120">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="7cd67-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
