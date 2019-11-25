---
title: XML 문서 리터럴
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: db77cccd26c87e271d6db45ce514ab6dabbc53e3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349377"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="a50cb-102">XML 문서 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a50cb-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="a50cb-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span><span class="sxs-lookup"><span data-stu-id="a50cb-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="a50cb-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a50cb-105">요소</span><span class="sxs-lookup"><span data-stu-id="a50cb-105">Parts</span></span>  
  
|<span data-ttu-id="a50cb-106">용어</span><span class="sxs-lookup"><span data-stu-id="a50cb-106">Term</span></span>|<span data-ttu-id="a50cb-107">정의</span><span class="sxs-lookup"><span data-stu-id="a50cb-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="a50cb-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a50cb-108">Optional.</span></span> <span data-ttu-id="a50cb-109">Literal text declaring which encoding the document uses.</span><span class="sxs-lookup"><span data-stu-id="a50cb-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="a50cb-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a50cb-110">Optional.</span></span> <span data-ttu-id="a50cb-111">Literal text.</span><span class="sxs-lookup"><span data-stu-id="a50cb-111">Literal text.</span></span> <span data-ttu-id="a50cb-112">Must be "yes" or "no".</span><span class="sxs-lookup"><span data-stu-id="a50cb-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="a50cb-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a50cb-113">Optional.</span></span> <span data-ttu-id="a50cb-114">List of XML processing instructions and XML comments.</span><span class="sxs-lookup"><span data-stu-id="a50cb-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="a50cb-115">Takes the following format:</span><span class="sxs-lookup"><span data-stu-id="a50cb-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="a50cb-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="a50cb-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="a50cb-117">Each `piComment` can be one of the following:</span><span class="sxs-lookup"><span data-stu-id="a50cb-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="a50cb-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a50cb-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="a50cb-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a50cb-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="a50cb-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a50cb-120">Required.</span></span> <span data-ttu-id="a50cb-121">Root element of the document.</span><span class="sxs-lookup"><span data-stu-id="a50cb-121">Root element of the document.</span></span> <span data-ttu-id="a50cb-122">The format is one of the following:</span><span class="sxs-lookup"><span data-stu-id="a50cb-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="a50cb-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a50cb-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="a50cb-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="a50cb-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="a50cb-125">The `elementExp` returns one of the following:</span><span class="sxs-lookup"><span data-stu-id="a50cb-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="a50cb-126"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a50cb-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="a50cb-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span><span class="sxs-lookup"><span data-stu-id="a50cb-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="a50cb-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a50cb-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="a50cb-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="a50cb-129">Return Value</span></span>  
 <span data-ttu-id="a50cb-130"><xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a50cb-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50cb-131">주의</span><span class="sxs-lookup"><span data-stu-id="a50cb-131">Remarks</span></span>  
 <span data-ttu-id="a50cb-132">An XML document literal is identified by the XML declaration at the start of the literal.</span><span class="sxs-lookup"><span data-stu-id="a50cb-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="a50cb-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span><span class="sxs-lookup"><span data-stu-id="a50cb-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="a50cb-134">An XML document literal cannot appear in an XML element.</span><span class="sxs-lookup"><span data-stu-id="a50cb-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a50cb-135">An XML literal can span multiple lines without using line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="a50cb-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="a50cb-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="a50cb-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="a50cb-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span><span class="sxs-lookup"><span data-stu-id="a50cb-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a50cb-138">예제</span><span class="sxs-lookup"><span data-stu-id="a50cb-138">Example</span></span>  
 <span data-ttu-id="a50cb-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span><span class="sxs-lookup"><span data-stu-id="a50cb-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="a50cb-140">참조</span><span class="sxs-lookup"><span data-stu-id="a50cb-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="a50cb-141">XML 처리 명령 리터럴</span><span class="sxs-lookup"><span data-stu-id="a50cb-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="a50cb-142">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="a50cb-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="a50cb-143">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="a50cb-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="a50cb-144">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="a50cb-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="a50cb-145">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="a50cb-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="a50cb-146">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="a50cb-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
