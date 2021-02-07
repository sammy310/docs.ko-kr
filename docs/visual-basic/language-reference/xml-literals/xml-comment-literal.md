---
description: '자세한 정보: XML 주석 리터럴 (Visual Basic)'
title: XML 주석 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: f44d2e132236d74d312910921fabb3a85afd82d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768742"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="c4939-103">XML 주석 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4939-103">XML Comment Literal (Visual Basic)</span></span>

<span data-ttu-id="c4939-104">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XComment> .</span><span class="sxs-lookup"><span data-stu-id="c4939-104">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4939-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4939-105">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="c4939-106">부분</span><span class="sxs-lookup"><span data-stu-id="c4939-106">Parts</span></span>  
  
|<span data-ttu-id="c4939-107">용어</span><span class="sxs-lookup"><span data-stu-id="c4939-107">Term</span></span>|<span data-ttu-id="c4939-108">정의</span><span class="sxs-lookup"><span data-stu-id="c4939-108">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="c4939-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c4939-109">Required.</span></span> <span data-ttu-id="c4939-110">XML 주석의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-110">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="c4939-111">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-111">Required.</span></span> <span data-ttu-id="c4939-112">XML 주석에 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-112">Text to appear in the XML comment.</span></span> <span data-ttu-id="c4939-113">두 개의 하이픈 (--)을 포함 하거나 닫는 태그 옆에 하이픈으로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-113">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="c4939-114">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-114">Required.</span></span> <span data-ttu-id="c4939-115">XML 주석의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-115">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="c4939-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="c4939-116">Return Value</span></span>  

 <span data-ttu-id="c4939-117"><xref:System.Xml.Linq.XComment> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-117">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4939-118">설명</span><span class="sxs-lookup"><span data-stu-id="c4939-118">Remarks</span></span>  

 <span data-ttu-id="c4939-119">XML 주석 리터럴에 문서 내용이 포함 되어 있지 않습니다. 문서에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-119">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="c4939-120">XML 주석 섹션은 "-->" 시퀀스로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-120">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="c4939-121">이는 다음 사항을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-121">This implies the following points:</span></span>  
  
- <span data-ttu-id="c4939-122">포함 된 식 구분 기호가 유효한 XML 주석 내용 이므로 XML 주석 리터럴에 포함 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-122">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="c4939-123">XML 주석 섹션은 중첩 될 수 없습니다 `content` .에는 "-->" 값을 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-123">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="c4939-124">XML 주석 리터럴을 변수에 할당 하거나 XML 요소 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-124">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4939-125">XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-125">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="c4939-126">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-126">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="c4939-127">Visual Basic 컴파일러는 XML 주석 리터럴을 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XComment.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="c4939-127">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4939-128">예제</span><span class="sxs-lookup"><span data-stu-id="c4939-128">Example</span></span>  

 <span data-ttu-id="c4939-129">다음 예에서는 "This is comment" 라는 텍스트가 포함 된 XML 주석을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4939-129">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c4939-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4939-130">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="c4939-131">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="c4939-131">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="c4939-132">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="c4939-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="c4939-133">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="c4939-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
