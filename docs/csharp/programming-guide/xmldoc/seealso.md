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
ms.openlocfilehash: e8618ef352a4fa7f0fd4c88733c6568b0e12e376
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380646"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="fc1a1-105">\<seealso>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fc1a1-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="fc1a1-106">구문</span><span class="sxs-lookup"><span data-stu-id="fc1a1-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="fc1a1-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc1a1-107">Parameters</span></span>

- <span data-ttu-id="fc1a1-108">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="fc1a1-108">cref = " `member`"</span></span>

  <span data-ttu-id="fc1a1-109">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="fc1a1-110">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다. `member`</span><span class="sxs-lookup"><span data-stu-id="fc1a1-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="fc1a1-111">는 큰따옴표(“ ”)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="fc1a1-112">제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [cref 특성](./cref-attribute.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="fc1a1-113">설명</span><span class="sxs-lookup"><span data-stu-id="fc1a1-113">Remarks</span></span>

<span data-ttu-id="fc1a1-114">`<seealso>` 태그를 사용하면 참고 항목 섹션에 표시할 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="fc1a1-115">텍스트 내에서 링크를 지정하려면 [\<see>](./see.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="fc1a1-116">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="fc1a1-117">예제</span><span class="sxs-lookup"><span data-stu-id="fc1a1-117">Example</span></span>

<span data-ttu-id="fc1a1-118">\<seealso> 사용 예제는 [\<summary>](./summary.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc1a1-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc1a1-119">참조</span><span class="sxs-lookup"><span data-stu-id="fc1a1-119">See also</span></span>

- [<span data-ttu-id="fc1a1-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fc1a1-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="fc1a1-121">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="fc1a1-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
