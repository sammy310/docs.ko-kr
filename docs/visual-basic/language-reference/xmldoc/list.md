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
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524754"
---
# <a name="list-visual-basic"></a><span data-ttu-id="f0f4b-102">\<list > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0f4b-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="f0f4b-103">목록 또는 테이블을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0f4b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f0f4b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0f4b-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="f0f4b-106">목록의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-106">The type of the list.</span></span> <span data-ttu-id="f0f4b-107">글머리 기호 목록에 대 한 "글머리 기호", 숫자 목록의 경우 "숫자" 또는 두 열 테이블의 경우 "table" 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="f0f4b-108">@No__t_0 "table" 인 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-108">Only used when `type` is "table."</span></span> <span data-ttu-id="f0f4b-109">정의 하는 용어로 설명 태그에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="f0f4b-110">@No__t_0 "글머리 기호" 또는 "숫자" 인 경우 `type`가 "table" 인 경우 `description`은 목록에 있는 항목이 며 `term`에 대 한 정의 `description`입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f4b-111">주의</span><span class="sxs-lookup"><span data-stu-id="f0f4b-111">Remarks</span></span>  
 <span data-ttu-id="f0f4b-112">@No__t_0 블록은 테이블 또는 정의 목록의 머리글을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="f0f4b-113">테이블을 정의할 때 제목에 `term`에 대 한 항목만 제공 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="f0f4b-114">목록의 각 항목은 `<item>` 블록을 사용 하 여 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="f0f4b-115">정의 목록을 만들 때 `term`와 `description`를 모두 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="f0f4b-116">그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는 `description`에 대 한 항목만 제공 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="f0f4b-117">목록 또는 테이블에는 필요한 만큼의 `<item>` 블록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="f0f4b-118">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0f4b-119">예제</span><span class="sxs-lookup"><span data-stu-id="f0f4b-119">Example</span></span>  
 <span data-ttu-id="f0f4b-120">이 예제에서는 `<list>` 태그를 사용 하 여 설명 섹션에서 글머리 기호 목록을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f4b-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="f0f4b-121">참조</span><span class="sxs-lookup"><span data-stu-id="f0f4b-121">See also</span></span>

- [<span data-ttu-id="f0f4b-122">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="f0f4b-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
