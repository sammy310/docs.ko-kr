---
title: <see> - C# 프로그래밍 가이드
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
ms.openlocfilehash: 0f10feb0931c6d38c817fdecb925f68d439abb59
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287248"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="b89e8-102">\<see>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b89e8-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b89e8-103">구문</span><span class="sxs-lookup"><span data-stu-id="b89e8-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="b89e8-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b89e8-104">Parameters</span></span>

- <span data-ttu-id="b89e8-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="b89e8-105">cref = "`member`"</span></span>

  <span data-ttu-id="b89e8-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b89e8-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="b89e8-108">*멤버*는 큰따옴표(“ ”)로 묶으세요.</span><span class="sxs-lookup"><span data-stu-id="b89e8-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="b89e8-109">설명</span><span class="sxs-lookup"><span data-stu-id="b89e8-109">Remarks</span></span>

<span data-ttu-id="b89e8-110">`<see>` 태그를 사용하면 텍스트 내부에서 링크를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-110">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="b89e8-111">참조 섹션에 텍스트를 배치해야 한다고 지정하려면 [\<seealso>](./seealso.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="b89e8-112">코드 요소의 문서 페이지에 대한 내부 하이퍼링크를 만들려면 [cref 특성](./cref-attribute.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="b89e8-113">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="b89e8-114">다음 예제에서는 요약 섹션의 `<see>` 태그를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b89e8-114">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="b89e8-115">참조</span><span class="sxs-lookup"><span data-stu-id="b89e8-115">See also</span></span>

- [<span data-ttu-id="b89e8-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b89e8-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b89e8-117">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="b89e8-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
