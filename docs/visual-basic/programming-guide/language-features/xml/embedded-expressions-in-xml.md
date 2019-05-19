---
title: XML의 포함 식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: ef8ac62d9d969ce4463931d69b0302376ca0ccc4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881533"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="b4b1f-102">XML의 포함 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4b1f-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="b4b1f-103">포함 식을 통해 식을 런타임에 계산 되는 식을 포함 하는 XML 리터럴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="b4b1f-104">포함된 식에 대 한 구문은 `<%=` `expression` `%>`, ASP.NET에 사용 된 구문으로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="b4b1f-105">예를 들어 만들면 XML 요소 리터럴 리터럴 텍스트 콘텐츠를 사용 하 여 포함 된 식을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="b4b1f-106">하는 경우 `isbnNumber` 12345 정수를 포함 하 고 `modifiedDate` 날짜가 포함 3 5 2006 년 월을 경우이 코드가 실행 되는 값 `book` 는:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="b4b1f-107">포함된 식 위치 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="b4b1f-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="b4b1f-108">포함된 식은 XML 리터럴 식 내의 특정 위치에만 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="b4b1f-109">식 형식는 식 위치 컨트롤을 반환할 수 있습니다 방법과 `Nothing` 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="b4b1f-110">다음 표에서 허용 되는 위치 및 포함 된 식의 형식에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="b4b1f-111">리터럴에 위치</span><span class="sxs-lookup"><span data-stu-id="b4b1f-111">Location in literal</span></span>|<span data-ttu-id="b4b1f-112">식의 형식</span><span class="sxs-lookup"><span data-stu-id="b4b1f-112">Type of expression</span></span>|<span data-ttu-id="b4b1f-113">처리 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="b4b1f-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="b4b1f-114">XML 요소 이름</span><span class="sxs-lookup"><span data-stu-id="b4b1f-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="b4b1f-115">Error</span><span class="sxs-lookup"><span data-stu-id="b4b1f-115">Error</span></span>|  
|<span data-ttu-id="b4b1f-116">XML 요소 내용</span><span class="sxs-lookup"><span data-stu-id="b4b1f-116">XML element content</span></span>|<span data-ttu-id="b4b1f-117">`Object` 또는 배열 `Object`</span><span class="sxs-lookup"><span data-stu-id="b4b1f-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="b4b1f-118">무시됨</span><span class="sxs-lookup"><span data-stu-id="b4b1f-118">Ignored</span></span>|  
|<span data-ttu-id="b4b1f-119">XML 요소 특성 이름</span><span class="sxs-lookup"><span data-stu-id="b4b1f-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="b4b1f-120">오류를 특성 값도 아닌 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="b4b1f-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="b4b1f-121">XML 요소 특성 값</span><span class="sxs-lookup"><span data-stu-id="b4b1f-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="b4b1f-122">특성 선언이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="b4b1f-123">XML 요소 특성</span><span class="sxs-lookup"><span data-stu-id="b4b1f-123">XML element attribute</span></span>|<span data-ttu-id="b4b1f-124"><xref:System.Xml.Linq.XAttribute> 또는 컬렉션 <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="b4b1f-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="b4b1f-125">무시됨</span><span class="sxs-lookup"><span data-stu-id="b4b1f-125">Ignored</span></span>|  
|<span data-ttu-id="b4b1f-126">XML 문서 루트 요소</span><span class="sxs-lookup"><span data-stu-id="b4b1f-126">XML document root element</span></span>|<span data-ttu-id="b4b1f-127"><xref:System.Xml.Linq.XElement> 또는 하나의 컬렉션 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 고 <xref:System.Xml.Linq.XComment> 개체</span><span class="sxs-lookup"><span data-stu-id="b4b1f-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="b4b1f-128">무시됨</span><span class="sxs-lookup"><span data-stu-id="b4b1f-128">Ignored</span></span>|  
  
- <span data-ttu-id="b4b1f-129">XML 요소 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="b4b1f-130">XML 요소의 내용에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="b4b1f-131">XML 요소 특성 이름에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="b4b1f-132">XML 요소 특성 값에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="b4b1f-133">XML 요소 특성에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="b4b1f-134">XML 문서 루트 요소에 포함 된 식의 예:</span><span class="sxs-lookup"><span data-stu-id="b4b1f-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="b4b1f-135">사용 하도록 설정 하면 `Option Strict`, 컴파일러는 각 포함 된 식의 형식을 필요한 형식으로 확대를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="b4b1f-136">유일한 예외는 코드를 실행할 때 확인 되는 XML 문서의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="b4b1f-137">없이 컴파일하면 `Option Strict`, 식의 형식 포함할 수 있습니다 `Object` 런타임에 해당 형식을 검증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="b4b1f-138">콘텐츠는 선택 사항이 위치에 포함 된 식을 포함 `Nothing` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="b4b1f-139">즉, 요소 콘텐츠, 특성 값을 확인 해야 하 고 배열 요소에는 없는 `Nothing` XML 리터럴의 사용 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="b4b1f-140">요소 및 특성 이름과 같은 값이 될 수 없습니다. 필요한 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="b4b1f-141">리터럴의 특정 형식에 포함 된 식을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)하십시오 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="b4b1f-142">범위 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="b4b1f-142">Scoping Rules</span></span>  
 <span data-ttu-id="b4b1f-143">컴파일러는 적절 한 리터럴 형식에 대 한 생성자 호출으로 각 XML 리터럴을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="b4b1f-144">리터럴 내용과 XML 리터럴에 식 포함 된 생성자에 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="b4b1f-145">즉, XML 리터럴을 사용할 수 있는 모든 Visual Basic 프로그래밍 요소는 해당 포함 된 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="b4b1f-146">XML 리터럴 내에서 사용 하 여 접두사를 선언 하는 XML 네임 스페이스에 액세스할 수 있습니다는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="b4b1f-147">새 XML 네임 스페이스 접두사를 선언 하거나 기존 XML 네임 스페이스 접두사를 사용 하 여 요소에서를 숨길 수 있습니다는 `xmlns` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="b4b1f-148">새 네임 스페이스는 해당 요소의 자식 노드가 아니라 XML 리터럴을 포함 된 식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4b1f-149">XML 네임 스페이스 접두사를 사용 하 여 선언 되는 경우는 `xmlns` 네임 스페이스 특성을 특성 값을 상수 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="b4b1f-150">이런 점에서 사용 하 여는 `xmlns` 사용과 같은 특성은는 `Imports` XML 네임 스페이스를 선언 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="b4b1f-151">XML 네임 스페이스 값을 지정 하려면 포함 된 식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4b1f-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b1f-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4b1f-152">See also</span></span>

- [<span data-ttu-id="b4b1f-153">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="b4b1f-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b4b1f-154">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="b4b1f-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="b4b1f-155">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="b4b1f-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="b4b1f-156">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="b4b1f-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="b4b1f-157">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="b4b1f-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="b4b1f-158">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="b4b1f-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
