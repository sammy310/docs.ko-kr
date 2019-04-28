---
title: XML 주석 리터럴(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 149bbac6d301a9c2f166d05698e3780171126cb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938647"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="aeb5a-102">XML 주석 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aeb5a-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="aeb5a-103">리터럴 나타내는 <xref:System.Xml.Linq.XComment> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeb5a-104">구문</span><span class="sxs-lookup"><span data-stu-id="aeb5a-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="aeb5a-105">요소</span><span class="sxs-lookup"><span data-stu-id="aeb5a-105">Parts</span></span>  
  
|<span data-ttu-id="aeb5a-106">용어</span><span class="sxs-lookup"><span data-stu-id="aeb5a-106">Term</span></span>|<span data-ttu-id="aeb5a-107">정의</span><span class="sxs-lookup"><span data-stu-id="aeb5a-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="aeb5a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-108">Required.</span></span> <span data-ttu-id="aeb5a-109">XML 주석의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="aeb5a-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-110">Required.</span></span> <span data-ttu-id="aeb5a-111">XML 주석에 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="aeb5a-112">일련을의 두 개의 하이픈 (-) 또는 닫는 태그에 인접 한 하이픈으로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="aeb5a-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-113">Required.</span></span> <span data-ttu-id="aeb5a-114">XML 주석의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="aeb5a-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="aeb5a-115">Return Value</span></span>  
 <span data-ttu-id="aeb5a-116"><xref:System.Xml.Linq.XComment> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeb5a-117">설명</span><span class="sxs-lookup"><span data-stu-id="aeb5a-117">Remarks</span></span>  
 <span data-ttu-id="aeb5a-118">XML 주석 리터럴 문서 콘텐츠가 없습니다. 문서에 대 한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="aeb5a-119">XML 주석 섹션을 순서 "-->"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="aeb5a-120">이 다음 사항을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="aeb5a-121">포함된 식 구분 기호는 유효한 XML 주석 콘텐츠 때문에 XML 주석 리터럴에 포함된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="aeb5a-122">XML 주석 섹션 중첩 될 수 없으므로 있으므로 `content` "-->" 값을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="aeb5a-123">XML 주석 리터럴에 변수에 할당할 수 있습니다 또는 XML 요소 리터럴에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aeb5a-124">XML 리터럴을 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="aeb5a-125">이 기능을 사용 하면 XML 문서에서 콘텐츠를 복사 하 고 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="aeb5a-126">Visual Basic 컴파일러는 XML 주석 리터럴에 호출으로 변환 된 <xref:System.Xml.Linq.XComment.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aeb5a-127">예제</span><span class="sxs-lookup"><span data-stu-id="aeb5a-127">Example</span></span>  
 <span data-ttu-id="aeb5a-128">다음 예제에서는 "This is a comment" 텍스트가 포함 된 XML 주석을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aeb5a-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="aeb5a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="aeb5a-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="aeb5a-130">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="aeb5a-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="aeb5a-131">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="aeb5a-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="aeb5a-132">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="aeb5a-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
