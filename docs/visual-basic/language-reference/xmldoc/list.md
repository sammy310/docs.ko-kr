---
title: <list> (Visual Basic)
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
ms.openlocfilehash: 61b0b018b3d06a2307aa280a748b7d07c5fa7915
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496068"
---
# <a name="list-visual-basic"></a><span data-ttu-id="3e44d-102">\<목록 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e44d-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="3e44d-103">목록 또는 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e44d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e44d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3e44d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e44d-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="3e44d-106">형식 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-106">The type of the list.</span></span> <span data-ttu-id="3e44d-107">글머리 기호 목록, 번호 매기기 목록 또는 "table" 2 열 테이블에 대 한 "number"에 대 한 "bullet" 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="3e44d-108">경우에 사용 `type` "table"은</span><span class="sxs-lookup"><span data-stu-id="3e44d-108">Only used when `type` is "table."</span></span> <span data-ttu-id="3e44d-109">설명 태그에 정의 된 용어를 정의 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="3e44d-110">때 `type` "bullet" 또는 "숫자" `description` 목록의 항목은 때 `type` "table"은 `description` 의 정의 `term`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e44d-111">설명</span><span class="sxs-lookup"><span data-stu-id="3e44d-111">Remarks</span></span>  
 <span data-ttu-id="3e44d-112">`<listheader>` 블록은 테이블 또는 정의 목록의 머리글을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="3e44d-113">에 대 한 진입점을 제공할 수만 있는 테이블을 정의할 때 `term` 제목에서입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="3e44d-114">지정 된 목록의 각 항목을 `<item>` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="3e44d-115">둘 다 지정 해야 정의 목록을 만들 때는 `term` 고 `description`입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="3e44d-116">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록만 제공 해야 항목이 `description`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="3e44d-117">목록 또는 테이블 만큼 있습니다 `<item>` 필요에 따라 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="3e44d-118">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e44d-119">예제</span><span class="sxs-lookup"><span data-stu-id="3e44d-119">Example</span></span>  
 <span data-ttu-id="3e44d-120">이 예제에서는 `<list>` 주의 섹션의 글머리 기호 목록을 정의 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="3e44d-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="3e44d-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3e44d-121">See also</span></span>
- [<span data-ttu-id="3e44d-122">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="3e44d-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
