---
title: XML의 포함 식
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332349"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="16a11-102">XML의 포함 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16a11-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="16a11-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span><span class="sxs-lookup"><span data-stu-id="16a11-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="16a11-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="16a11-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="16a11-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span><span class="sxs-lookup"><span data-stu-id="16a11-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="16a11-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span><span class="sxs-lookup"><span data-stu-id="16a11-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="16a11-107">Embedded Expression Location and Validation</span><span class="sxs-lookup"><span data-stu-id="16a11-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="16a11-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span><span class="sxs-lookup"><span data-stu-id="16a11-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="16a11-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span><span class="sxs-lookup"><span data-stu-id="16a11-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="16a11-110">The following table describes the allowed locations and types of embedded expressions.</span><span class="sxs-lookup"><span data-stu-id="16a11-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="16a11-111">Location in literal</span><span class="sxs-lookup"><span data-stu-id="16a11-111">Location in literal</span></span>|<span data-ttu-id="16a11-112">Type of expression</span><span class="sxs-lookup"><span data-stu-id="16a11-112">Type of expression</span></span>|<span data-ttu-id="16a11-113">Handling of `Nothing`</span><span class="sxs-lookup"><span data-stu-id="16a11-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="16a11-114">XML element name</span><span class="sxs-lookup"><span data-stu-id="16a11-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="16a11-115">Error</span><span class="sxs-lookup"><span data-stu-id="16a11-115">Error</span></span>|  
|<span data-ttu-id="16a11-116">XML element content</span><span class="sxs-lookup"><span data-stu-id="16a11-116">XML element content</span></span>|<span data-ttu-id="16a11-117">`Object` or array of `Object`</span><span class="sxs-lookup"><span data-stu-id="16a11-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="16a11-118">무시됨</span><span class="sxs-lookup"><span data-stu-id="16a11-118">Ignored</span></span>|  
|<span data-ttu-id="16a11-119">XML element attribute name</span><span class="sxs-lookup"><span data-stu-id="16a11-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="16a11-120">Error, unless the attribute value is also `Nothing`</span><span class="sxs-lookup"><span data-stu-id="16a11-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="16a11-121">XML element attribute value</span><span class="sxs-lookup"><span data-stu-id="16a11-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="16a11-122">Attribute declaration ignored</span><span class="sxs-lookup"><span data-stu-id="16a11-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="16a11-123">XML element attribute</span><span class="sxs-lookup"><span data-stu-id="16a11-123">XML element attribute</span></span>|<span data-ttu-id="16a11-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="16a11-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="16a11-125">무시됨</span><span class="sxs-lookup"><span data-stu-id="16a11-125">Ignored</span></span>|  
|<span data-ttu-id="16a11-126">XML document root element</span><span class="sxs-lookup"><span data-stu-id="16a11-126">XML document root element</span></span>|<span data-ttu-id="16a11-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span><span class="sxs-lookup"><span data-stu-id="16a11-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="16a11-128">무시됨</span><span class="sxs-lookup"><span data-stu-id="16a11-128">Ignored</span></span>|  
  
- <span data-ttu-id="16a11-129">Example of an embedded expression in an XML element name:</span><span class="sxs-lookup"><span data-stu-id="16a11-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="16a11-130">Example of an embedded expression in the content of an XML element:</span><span class="sxs-lookup"><span data-stu-id="16a11-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="16a11-131">Example of an embedded expression in an XML element attribute name:</span><span class="sxs-lookup"><span data-stu-id="16a11-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="16a11-132">Example of an embedded expression in an XML element attribute value:</span><span class="sxs-lookup"><span data-stu-id="16a11-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="16a11-133">Example of an embedded expression in an XML element attribute:</span><span class="sxs-lookup"><span data-stu-id="16a11-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="16a11-134">Example of an embedded expression in an XML document root element:</span><span class="sxs-lookup"><span data-stu-id="16a11-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="16a11-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span><span class="sxs-lookup"><span data-stu-id="16a11-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="16a11-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span><span class="sxs-lookup"><span data-stu-id="16a11-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="16a11-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span><span class="sxs-lookup"><span data-stu-id="16a11-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="16a11-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span><span class="sxs-lookup"><span data-stu-id="16a11-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="16a11-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span><span class="sxs-lookup"><span data-stu-id="16a11-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="16a11-140">Required values, such as element and attribute names, cannot be `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="16a11-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="16a11-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="16a11-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="16a11-142">범위 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="16a11-142">Scoping Rules</span></span>  
 <span data-ttu-id="16a11-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span><span class="sxs-lookup"><span data-stu-id="16a11-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="16a11-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span><span class="sxs-lookup"><span data-stu-id="16a11-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="16a11-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span><span class="sxs-lookup"><span data-stu-id="16a11-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="16a11-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="16a11-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="16a11-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span><span class="sxs-lookup"><span data-stu-id="16a11-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="16a11-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span><span class="sxs-lookup"><span data-stu-id="16a11-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16a11-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span><span class="sxs-lookup"><span data-stu-id="16a11-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="16a11-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span><span class="sxs-lookup"><span data-stu-id="16a11-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="16a11-151">You cannot use an embedded expression to specify the XML namespace value.</span><span class="sxs-lookup"><span data-stu-id="16a11-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a11-152">참조</span><span class="sxs-lookup"><span data-stu-id="16a11-152">See also</span></span>

- [<span data-ttu-id="16a11-153">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="16a11-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="16a11-154">XML 문서 리터럴</span><span class="sxs-lookup"><span data-stu-id="16a11-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="16a11-155">XML 요소 리터럴</span><span class="sxs-lookup"><span data-stu-id="16a11-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="16a11-156">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="16a11-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="16a11-157">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="16a11-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="16a11-158">XML 리터럴 개요</span><span class="sxs-lookup"><span data-stu-id="16a11-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
