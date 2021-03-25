---
title: <seealso> - C# 프로그래밍 가이드
description: XML <seealso> 태그를 사용하는 방법을 알아봅니다. 이 태그를 사용하면 '참고 항목' 섹션에 표시할 텍스트를 지정할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: c5baefbfca3a94095a90eb43c2bf13eb924c8cdc
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477762"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="80b84-105">\<seealso>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="80b84-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="80b84-106">구문</span><span class="sxs-lookup"><span data-stu-id="80b84-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="80b84-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80b84-107">Parameters</span></span>

- <span data-ttu-id="80b84-108">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="80b84-108">cref = " `member`"</span></span>

  <span data-ttu-id="80b84-109">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="80b84-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="80b84-110">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member`</span><span class="sxs-lookup"><span data-stu-id="80b84-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="80b84-111">는 큰따옴표(“ ”)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b84-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="80b84-112">제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [cref 특성](./cref-attribute.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80b84-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="80b84-113">설명</span><span class="sxs-lookup"><span data-stu-id="80b84-113">Remarks</span></span>

<span data-ttu-id="80b84-114">`<seealso>` 태그를 사용하면 참고 항목 섹션에 표시할 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80b84-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="80b84-115">텍스트 내에서 링크를 지정하려면 [\<see>](./see.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80b84-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="80b84-116">[**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="80b84-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="80b84-117">예제</span><span class="sxs-lookup"><span data-stu-id="80b84-117">Example</span></span>

<span data-ttu-id="80b84-118">\<seealso> 사용 예제는 [\<summary>](./summary.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80b84-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="80b84-119">참조</span><span class="sxs-lookup"><span data-stu-id="80b84-119">See also</span></span>

- [<span data-ttu-id="80b84-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="80b84-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="80b84-121">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="80b84-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
