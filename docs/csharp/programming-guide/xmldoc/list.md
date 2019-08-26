---
title: <list> - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: aadb24c43d49acb3e71490efd156b14d9fc5f133
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587979"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="f29db-102">\<list>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f29db-102">\<list> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f29db-103">구문</span><span class="sxs-lookup"><span data-stu-id="f29db-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f29db-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f29db-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="f29db-105">`description`에서 정의되는, 정의할 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="f29db-106">글머리 기호 또는 번호 매기기 목록의 항목이나 `term`의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f29db-107">설명</span><span class="sxs-lookup"><span data-stu-id="f29db-107">Remarks</span></span>  
 <span data-ttu-id="f29db-108">\<listheader> 블록은 테이블 또는 정의 목록의 머리글 행을 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="f29db-109">테이블을 정의할 때는 머리글에 용어 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="f29db-110">목록의 각 항목은 \<item> 블록을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="f29db-111">정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="f29db-112">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우 `description` 항목만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="f29db-113">목록 또는 테이블에 \<item> 블록을 필요한 개수만큼 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="f29db-114">[/doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f29db-114">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f29db-115">예</span><span class="sxs-lookup"><span data-stu-id="f29db-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f29db-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f29db-116">See also</span></span>

- [<span data-ttu-id="f29db-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f29db-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f29db-118">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="f29db-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
