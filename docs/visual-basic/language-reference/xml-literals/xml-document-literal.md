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
ms.openlocfilehash: 3a2182d2937827bc8dc45e22307a3668420261a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400204"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="4ba4c-102">XML 문서 리터럴(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ba4c-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="4ba4c-103">개체를 나타내는 리터럴입니다 <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="4ba4c-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba4c-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ba4c-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4ba4c-105">부분</span><span class="sxs-lookup"><span data-stu-id="4ba4c-105">Parts</span></span>  
  
|<span data-ttu-id="4ba4c-106">용어</span><span class="sxs-lookup"><span data-stu-id="4ba4c-106">Term</span></span>|<span data-ttu-id="4ba4c-107">정의</span><span class="sxs-lookup"><span data-stu-id="4ba4c-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="4ba4c-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-108">Optional.</span></span> <span data-ttu-id="4ba4c-109">문서에서 사용 하는 인코딩을 선언 하는 리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="4ba4c-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-110">Optional.</span></span> <span data-ttu-id="4ba4c-111">리터럴 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-111">Literal text.</span></span> <span data-ttu-id="4ba4c-112">"Yes" 또는 "no" 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="4ba4c-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-113">Optional.</span></span> <span data-ttu-id="4ba4c-114">XML 처리 명령 및 XML 주석 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="4ba4c-115">는 다음과 같은 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="4ba4c-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="4ba4c-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="4ba4c-117">각 `piComment` 항목은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="4ba4c-118">-   [XML 처리 명령 리터럴입니다](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4ba4c-118">-   [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="4ba4c-119">-   [XML 주석 리터럴입니다](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4ba4c-119">-   [XML Comment Literal](xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="4ba4c-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-120">Required.</span></span> <span data-ttu-id="4ba4c-121">문서의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-121">Root element of the document.</span></span> <span data-ttu-id="4ba4c-122">형식은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4ba4c-123">[XML 요소 리터럴입니다](xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4ba4c-123">[XML Element Literal](xml-element-literal.md).</span></span></li><li><span data-ttu-id="4ba4c-124">형식의 포함 된 식 `<%=` `elementExp` `%>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="4ba4c-125">는 `elementExp` 다음 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4ba4c-126"><xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="4ba4c-127">하나의 <xref:System.Xml.Linq.XElement> 개체와 임의의 수의 <xref:System.Xml.Linq.XProcessingInstruction> 및 개체가 포함 된 컬렉션입니다 <xref:System.Xml.Linq.XComment> .</span><span class="sxs-lookup"><span data-stu-id="4ba4c-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="4ba4c-128">자세한 내용은 [XML의 포함 식](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-128">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="4ba4c-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="4ba4c-129">Return Value</span></span>  
 <span data-ttu-id="4ba4c-130"><xref:System.Xml.Linq.XDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ba4c-131">설명</span><span class="sxs-lookup"><span data-stu-id="4ba4c-131">Remarks</span></span>  
 <span data-ttu-id="4ba4c-132">XML 문서 리터럴은 리터럴의 시작 부분에 있는 XML 선언으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="4ba4c-133">각 XML 문서 리터럴에는 정확히 하나의 루트 XML 요소가 있어야 하지만 xml 처리 명령과 XML 주석이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="4ba4c-134">Xml 문서 리터럴은 XML 요소에 나타날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ba4c-135">XML 리터럴은 줄 연속 문자를 사용 하지 않고 여러 줄에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="4ba4c-136">이렇게 하면 XML 문서에서 콘텐츠를 복사 하 여 Visual Basic 프로그램에 직접 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4ba4c-137">Visual Basic 컴파일러는 XML 문서 리터럴을 및 생성자에 대 한 호출로 변환 합니다 <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="4ba4c-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba4c-138">예제</span><span class="sxs-lookup"><span data-stu-id="4ba4c-138">Example</span></span>  
 <span data-ttu-id="4ba4c-139">다음 예제에서는 XML 선언, 처리 명령, 주석 및 다른 요소를 포함 하는 요소가 포함 된 XML 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ba4c-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="4ba4c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ba4c-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="4ba4c-141">XML 처리 명령 리터럴</span><span class="sxs-lookup"><span data-stu-id="4ba4c-141">XML Processing Instruction Literal</span></span>](xml-processing-instruction-literal.md)
- [<span data-ttu-id="4ba4c-142">XML 주석 리터럴</span><span class="sxs-lookup"><span data-stu-id="4ba4c-142">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="4ba4c-143">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="4ba4c-143">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="4ba4c-144">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="4ba4c-144">XML Literals</span></span>](index.md)
- [<span data-ttu-id="4ba4c-145">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="4ba4c-145">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4ba4c-146">XML의 포함 식</span><span class="sxs-lookup"><span data-stu-id="4ba4c-146">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
