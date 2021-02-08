---
description: 다음에 대해 자세히 알아보세요. <list> (Visual Basic)
title: <list>
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: c9e2e8d1c370bfdeefae4a8f19b25acc6a336ecc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787437"
---
# <a name="list-visual-basic"></a><span data-ttu-id="3991c-103">\<list>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3991c-103">\<list> (Visual Basic)</span></span>

<span data-ttu-id="3991c-104">목록 또는 테이블을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-104">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3991c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3991c-105">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
## <a name="parameters"></a><span data-ttu-id="3991c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3991c-106">Parameters</span></span>  

 `type`  
 <span data-ttu-id="3991c-107">목록의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-107">The type of the list.</span></span> <span data-ttu-id="3991c-108">글머리 기호 목록에 대 한 "글머리 기호", 숫자 목록의 경우 "숫자" 또는 두 열 테이블의 경우 "table" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-108">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="3991c-109">`type`가 "table" 인 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-109">Only used when `type` is "table."</span></span> <span data-ttu-id="3991c-110">정의 하는 용어로 설명 태그에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-110">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="3991c-111">`type`가 "bullet" 또는 "number" 인 경우가 `description` "table" 이면 `type` `description` 의 정의입니다 `term` .</span><span class="sxs-lookup"><span data-stu-id="3991c-111">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3991c-112">설명</span><span class="sxs-lookup"><span data-stu-id="3991c-112">Remarks</span></span>  

 <span data-ttu-id="3991c-113">`<listheader>`블록은 테이블 또는 정의 목록의 머리글을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-113">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="3991c-114">테이블을 정의할 때 제목에에 대 한 항목만 제공 하면 `term` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-114">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="3991c-115">목록의 각 항목은 `<item>` 블록을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-115">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="3991c-116">정의 목록을 만들 때 및를 모두 지정 해야 합니다 `term` `description` .</span><span class="sxs-lookup"><span data-stu-id="3991c-116">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="3991c-117">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는에 대 한 항목만 제공 하면 `description` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-117">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="3991c-118">목록 또는 테이블에 `<item>` 블록을 필요한 개수만큼 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-118">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="3991c-119">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-119">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3991c-120">예제</span><span class="sxs-lookup"><span data-stu-id="3991c-120">Example</span></span>  

 <span data-ttu-id="3991c-121">이 예제에서는 태그를 사용 하 여 `<list>` 설명 섹션에서 글머리 기호 목록을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991c-121">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="3991c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3991c-122">See also</span></span>

- [<span data-ttu-id="3991c-123">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="3991c-123">XML Comment Tags</span></span>](index.md)
