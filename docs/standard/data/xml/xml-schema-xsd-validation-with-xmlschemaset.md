---
title: XmlSchemaSet을 사용하여 XSD(XML 스키마) 유효성 검사
description: .NET의 XmlSchemaSet 클래스를 사용하여 XSD(XML 스키마 정의 언어) 스키마에 대해 XML 문서의 유효성을 검사하는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 995323d1882da13d45cdac516518d5b67845715a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594506"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="e5957-103">XmlSchemaSet을 사용하여 XSD(XML 스키마) 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e5957-103">XML schema (XSD) validation with XmlSchemaSet</span></span>

<span data-ttu-id="e5957-104"><xref:System.Xml.Schema.XmlSchemaSet>의 XSD(XML 스키마 정의 언어) 스키마에 대해 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-104">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validate-xml-documents"></a><span data-ttu-id="e5957-105">XML 문서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e5957-105">Validate XML documents</span></span>  
 <span data-ttu-id="e5957-106"><xref:System.Xml.XmlReader.Create%2A> 클래스의 <xref:System.Xml.XmlReader> 메서드를 사용하여 XML 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-106">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="e5957-107">XML 문서의 유효성을 검사하려면 XML 문서의 유효성을 검사하는 데 사용할 XSD(XML 스키마 정의 언어) 스키마가 포함된 <xref:System.Xml.XmlReaderSettings> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-107">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5957-108"><xref:System.Xml.Schema> 네임스페이스에는 [LINQ to XML(C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) 및 [LINQ to XML(Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)을 사용할 때 XSD 파일에 대한 XML 트리의 유효성을 쉽게 검사할 수 있도록 하는 확장 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-108">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="e5957-109">LINQ to XML을 사용하여 XML 문서의 유효성을 검사하는 방법에 대한 자세한 내용은 [XSD(LINQ to XML)를 사용하여 유효성을 검사하는 방법(C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) 및 [ XSD를 사용하여 유효성 검사(LINQ to XML)(Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5957-109">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="e5957-110">개별 스키마 또는 스키마 집합(<xref:System.Xml.Schema.XmlSchemaSet>) 중 하나를 <xref:System.Xml.Schema.XmlSchemaSet>의 <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> 메서드에 대한 매개 변수로 전달하여 개별 스키마 또는 스키마 집합을 <xref:System.Xml.Schema.XmlSchemaSet>에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-110">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="e5957-111">문서 유효성을 확인할 때 문서의 대상 네임스페이스는 스키마 집합에 있는 스키마의 대상 네임스페이스와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-111">When validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="e5957-112">다음은 XML 문서 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-112">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="e5957-113">다음은 XML 문서 예제의 유효성을 검사하는 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-113">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="e5957-114">다음 코드 예제에서는 <xref:System.Xml.XmlReaderSettings> 개체의 <xref:System.Xml.XmlReaderSettings.Schemas%2A> 속성에 위 스키마가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-114">In the code example that follows, the schema above is added to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="e5957-115">위 XML 문서의 유효성을 검사하는 <xref:System.Xml.XmlReaderSettings> 개체의 <xref:System.Xml.XmlReader.Create%2A> 메서드에 <xref:System.Xml.XmlReader> 개체가 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-115">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="e5957-116"><xref:System.Xml.XmlReaderSettings.ValidationType%2A> 개체의 <xref:System.Xml.XmlReaderSettings> 메서드에 의해 XML 문서의 유효성이 검사되도록 `Schema` 개체의 <xref:System.Xml.XmlReader.Create%2A> 속성이 <xref:System.Xml.XmlReader>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-116">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="e5957-117"><xref:System.Xml.Schema.ValidationEventHandler>가 <xref:System.Xml.XmlReaderSettings> 개체에 추가되어 XML 문서와 스키마의 유효성을 검사하는 동안 발견된 오류로 인해 발생한 <xref:System.Xml.Schema.XmlSeverityType.Warning> 또는 <xref:System.Xml.Schema.XmlSeverityType.Error> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e5957-117">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e5957-118">참조</span><span class="sxs-lookup"><span data-stu-id="e5957-118">See also</span></span>

- [<span data-ttu-id="e5957-119">스키마 컴파일을 위한 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="e5957-119">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="e5957-120">XML 스키마 사용</span><span class="sxs-lookup"><span data-stu-id="e5957-120">Working with XML Schemas</span></span>](working-with-xml-schemas.md)
