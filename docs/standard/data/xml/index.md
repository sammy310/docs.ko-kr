---
description: '자세한 정보: XML 문서 및 데이터'
title: XML 문서 및 데이터
ms.date: 03/30/2017
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
ms.openlocfilehash: c2f64c218f2f6051f27087a98616b17e57583f75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713665"
---
# <a name="xml-documents-and-data"></a><span data-ttu-id="70dca-103">XML 문서 및 데이터</span><span class="sxs-lookup"><span data-stu-id="70dca-103">XML Documents and Data</span></span>

<span data-ttu-id="70dca-104">.NET Framework에서 XML 인식 응용 프로그램을 쉽게 작성할 수 있도록 하는 종합적이고 통합된 클래스 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-104">The .NET Framework provides a comprehensive and integrated set of classes that enable you to build XML-aware apps easily.</span></span> <span data-ttu-id="70dca-105">다음 네임스페이스의 클래스에서는 XML 구문 분석 및 작성, 메모리에서의 XML 데이터 편집, 데이터 유효성 검사 및 XSLT 변형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-105">The classes in the following namespaces support parsing and writing XML, editing XML data in memory, data validation, and XSLT transformation.</span></span>

- <xref:System.Xml>

- <xref:System.Xml.XPath>

- <xref:System.Xml.Xsl>

- <xref:System.Xml.Schema>

- <xref:System.Xml.Linq>

<span data-ttu-id="70dca-106">전체 목록을 보려면 [.NET API 브라우저](../../../../api/index.md?term=system.xml)에서 "System.Xml"을 검색하세요.</span><span class="sxs-lookup"><span data-stu-id="70dca-106">For a full list, search for "System.Xml" on the [.NET API browser](../../../../api/index.md?term=system.xml).</span></span>

<span data-ttu-id="70dca-107">이러한 네임스페이스의 클래스는 W3C(World Wide Web 컨소시엄) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-107">The classes in these namespaces support World Wide Web Consortium (W3C) recommendations.</span></span> <span data-ttu-id="70dca-108">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="70dca-108">For example:</span></span>

- <span data-ttu-id="70dca-109"><xref:System.Xml.XmlDocument?displayProperty=nameWithType> 클래스는 [W3C DOM(문서 개체 모델) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) 및 [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/) 권장 사항을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-109">The <xref:System.Xml.XmlDocument?displayProperty=nameWithType> class implements the [W3C Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) and [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/) recommendations.</span></span>

- <span data-ttu-id="70dca-110"><xref:System.Xml.XmlReader?displayProperty=nameWithType> 및 <xref:System.Xml.XmlWriter?displayProperty=nameWithType> 클래스는 [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) 및 [XML의 네임스페이스](https://www.w3.org/TR/REC-xml-names/) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-110">The <xref:System.Xml.XmlReader?displayProperty=nameWithType> and <xref:System.Xml.XmlWriter?displayProperty=nameWithType> classes support the [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) and the [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/) recommendations.</span></span>

- <span data-ttu-id="70dca-111"><xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> 지원 클래스의 스키마는 [W3C XML 스키마 파트 1: 구조](https://www.w3.org/TR/xmlschema-1/) 및 [XML 스키마 파트 2: Datatypes](https://www.w3.org/TR/xmlschema-2/) 권장 사항을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-111">Schemas in the <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> class support the [W3C XML Schema Part 1: Structures](https://www.w3.org/TR/xmlschema-1/) and [XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>

- <span data-ttu-id="70dca-112"><xref:System.Xml.Xsl?displayProperty=nameWithType> 네임스페이스의 클래스는 [W3C XSLT 1.0](https://www.w3.org/TR/xslt) 권장 사항을 준수하는 XSLT 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-112">Classes in the <xref:System.Xml.Xsl?displayProperty=nameWithType> namespace support XSLT transformations that conform to the [W3C XSLT 1.0](https://www.w3.org/TR/xslt) recommendation.</span></span>

<span data-ttu-id="70dca-113">.NET Framework의 XML 클래스는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-113">The XML classes in the .NET Framework provide these benefits:</span></span>

- <span data-ttu-id="70dca-114">**생산성**</span><span class="sxs-lookup"><span data-stu-id="70dca-114">**Productivity.**</span></span> <span data-ttu-id="70dca-115">[LINQ to XML(C#)](../../linq/linq-xml-overview.md) 및 [LINQ to XML(Visual Basic)](../../linq/linq-xml-overview.md)을 통해 XML로 프로그래밍하기 쉽고 SQL과 유사한 쿼리 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-115">[LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md) makes it easier to program with XML and provides a query experience that is similar to SQL.</span></span>

- <span data-ttu-id="70dca-116">**확장성**</span><span class="sxs-lookup"><span data-stu-id="70dca-116">**Extensibility.**</span></span> <span data-ttu-id="70dca-117">.NET Framework의 XML 클래스는 추상 기본 클래스와 가상 메서드를 사용하여 확장 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-117">The XML classes in the .NET Framework are extensible through the use of abstract base classes and virtual methods.</span></span> <span data-ttu-id="70dca-118">예를 들어, 캐시 스트림을 로컬 디스크에 저장하는 <xref:System.Xml.XmlUrlResolver> 클래스의 파생 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-118">For example, you can create a derived class of the <xref:System.Xml.XmlUrlResolver> class that stores the cache stream to the local disk.</span></span>

- <span data-ttu-id="70dca-119">**플러그형 아키텍처**</span><span class="sxs-lookup"><span data-stu-id="70dca-119">**Pluggable architecture.**</span></span> <span data-ttu-id="70dca-120">.NET Framework는 구성 요소를 서로 이용할 수 있고, 구성 요소 간에 데이터를 스트리밍할 수 있는 아키텍처를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-120">The .NET Framework provides an architecture in which components can utilize one another, and data can be streamed between components.</span></span> <span data-ttu-id="70dca-121">예를 들어 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체와 같은 데이터 저장소는 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 변형할 수 있고, 출력이 다른 저장소로 스트리밍되거나 웹 서비스에서 스트림으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-121">For example, a data store, such as an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, can be transformed with the <xref:System.Xml.Xsl.XslCompiledTransform> class, and the output can then be streamed either into another store or returned as a stream from a web service.</span></span>

- <span data-ttu-id="70dca-122">**성능.**</span><span class="sxs-lookup"><span data-stu-id="70dca-122">**Performance.**</span></span> <span data-ttu-id="70dca-123">응용 프로그램 성능 개선을 위해 .NET Framework의 일부 XML 클래스는 다음과 같은 특징을 가진 스트리밍 기반 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-123">For better app performance, some of the XML classes in the .NET Framework support a streaming-based model with the following characteristics:</span></span>

  - <span data-ttu-id="70dca-124">앞으로만 이동 가능한 풀 모델 구문 분석을 위한 최소 캐시(<xref:System.Xml.XmlReader>)</span><span class="sxs-lookup"><span data-stu-id="70dca-124">Minimal caching for forward-only, pull-model parsing (<xref:System.Xml.XmlReader>).</span></span>

  - <span data-ttu-id="70dca-125">앞으로만 이동 가능한 유효성 검사(<xref:System.Xml.XmlReader>)</span><span class="sxs-lookup"><span data-stu-id="70dca-125">Forward-only validation (<xref:System.Xml.XmlReader>).</span></span>

  - <span data-ttu-id="70dca-126">노드 생성이 단일 가상 노드로 최소화되지만 문서에 임의로 액세스할 수 있는 커서 스타일 탐색(<xref:System.Xml.XPath.XPathNavigator>).</span><span class="sxs-lookup"><span data-stu-id="70dca-126">Cursor style navigation that minimizes node creation to a single virtual node while providing random access to the document (<xref:System.Xml.XPath.XPathNavigator>).</span></span>

  <span data-ttu-id="70dca-127">성능 향상을 위해 XSLT 처리가 필요할 때마다 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용합니다. <xref:System.Xml.Xsl.XslCompiledTransform>는  클래스와 함께 효율적으로 사용하도록 디자인된 XPath 쿼리를 위한 최적화된 읽기 전용 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-127">For better performance whenever XSLT processing is required, you can use the <xref:System.Xml.XPath.XPathDocument> class, which is an optimized, read-only store for XPath queries designed to work efficiently with the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>

- <span data-ttu-id="70dca-128">**ADO.NET과의 통합**</span><span class="sxs-lookup"><span data-stu-id="70dca-128">**Integration with ADO.NET.**</span></span> <span data-ttu-id="70dca-129">XML 클래스 및 [ADO.NET](../../../framework/data/adonet/index.md)은 관계형 데이터와 XML을 하나로 결합하도록 긴밀히 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-129">The XML classes and [ADO.NET](../../../framework/data/adonet/index.md) are tightly integrated to bring together relational data and XML.</span></span> <span data-ttu-id="70dca-130"><xref:System.Data.DataSet> 클래스는 데이터베이스에서 파생된 데이터의 메모리 내 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-130">The <xref:System.Data.DataSet> class is an in-memory cache of data retrieved from a database.</span></span> <span data-ttu-id="70dca-131"><xref:System.Data.DataSet> 클래스에서는 <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter> 클래스를 사용하여 XML을 읽고 쓰며, 내부 관계형 스키마 구조를 XSD(XML 스키마)로 유지할 수 있을 뿐 아니라 XML 문서의 스키마 구조를 예측할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-131">The <xref:System.Data.DataSet> class has the ability to read and write XML by using the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> classes, to persist its internal relational schema structure as XML schemas (XSD), and to infer the schema structure of an XML document.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="70dca-132">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="70dca-132">In This Section</span></span>

<span data-ttu-id="70dca-133">[XML 처리 옵션](xml-processing-options.md) XML 데이터를 처리하기 위한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-133">[XML Processing Options](xml-processing-options.md) Discusses options for processing XML data.</span></span>

<span data-ttu-id="70dca-134">[메모리 내 XML 데이터 처리](processing-xml-data-in-memory.md) 메모리 내 XML 데이터를 처리하기 위한 다음과 같은 세 가지 모델을 설명합니다. [LINQ to XML(C#)](../../linq/linq-xml-overview.md) 및 [LINQ to XML(Visual Basic)](../../linq/linq-xml-overview.md), <xref:System.Xml.XmlDocument> 클래스(W3C 문서 개체 모델 기반) 및 <xref:System.Xml.XPath.XPathDocument> 클래스(XPath 데이터 모델 기반).</span><span class="sxs-lookup"><span data-stu-id="70dca-134">[Processing XML Data In-Memory](processing-xml-data-in-memory.md) Discusses the three models for processing XML data in-memory: [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md), the <xref:System.Xml.XmlDocument> class (based on the W3C Document Object Model), and the <xref:System.Xml.XPath.XPathDocument> class (based on the XPath data model).</span></span>

<span data-ttu-id="70dca-135">[XSLT 변환](xslt-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-135">[XSLT Transformations](xslt-transformations.md)</span></span>\
<span data-ttu-id="70dca-136">XSLT 프로세서의 사용 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-136">Describes how to use the XSLT processor.</span></span>

<span data-ttu-id="70dca-137">[XML SOM(스키마 개체 모델)](xml-schema-object-model-som.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-137">[XML Schema Object Model (SOM)](xml-schema-object-model-som.md)</span></span>\
<span data-ttu-id="70dca-138"><xref:System.Xml.Schema.XmlSchema> 클래스를 제공하여 XSD(XML 스키마)를 빌드 및 조작하고 스키마를 로드 및 편집하는 데 사용되는 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-138">Describes the classes used for building and manipulating XML Schemas (XSD) by providing an <xref:System.Xml.Schema.XmlSchema> class to load and edit a schema.</span></span>

<span data-ttu-id="70dca-139">[관계형 데이터 및 ADO.NET과의 XML 통합](xml-integration-with-relational-data-and-adonet.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-139">[XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md)</span></span>\
<span data-ttu-id="70dca-140">.NET Framework에서 <xref:System.Data.DataSet> 개체 및 <xref:System.Xml.XmlDataDocument> 개체를 사용하여 관계형 데이터와 계층형 데이터에 실시간으로 동시에 액세스할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-140">Describes how the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the <xref:System.Data.DataSet> object and the <xref:System.Xml.XmlDataDocument> object.</span></span>

<span data-ttu-id="70dca-141">[XML 문서의 네임스페이스 관리](managing-namespaces-in-an-xml-document.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-141">[Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md)</span></span>\
<span data-ttu-id="70dca-142"><xref:System.Xml.XmlNamespaceManager> 클래스를 사용하여 네임스페이스 정보를 저장하고 유지 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-142">Describes how the <xref:System.Xml.XmlNamespaceManager> class is used to store and maintain namespace information.</span></span>

<span data-ttu-id="70dca-143">[System.Xml 클래스의 형식 지원](type-support-in-the-system-xml-classes.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-143">[Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md)</span></span>\
<span data-ttu-id="70dca-144">XML 데이터 형식을 CLR 형식으로 매핑하는 방법, XML 데이터 형식을 변환하는 방법 및 <xref:System.Xml> 클래스의 기능을 지원하는 기타 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-144">Describes how XML data types map to CLR types, how to convert XML data types, and other type support features in the <xref:System.Xml> classes.</span></span>

## <a name="related-sections"></a><span data-ttu-id="70dca-145">관련 단원</span><span class="sxs-lookup"><span data-stu-id="70dca-145">Related Sections</span></span>

<span data-ttu-id="70dca-146">[ADO.NET](../../../framework/data/adonet/index.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-146">[ADO.NET](../../../framework/data/adonet/index.md)</span></span>\
<span data-ttu-id="70dca-147">ADO.NET을 사용하여 데이터에 액세스하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-147">Provides information on how to access data using ADO.NET.</span></span>

<span data-ttu-id="70dca-148">[보안](../../security/index.md)</span><span class="sxs-lookup"><span data-stu-id="70dca-148">[Security](../../security/index.md)</span></span>\
<span data-ttu-id="70dca-149">.NET Framework 보안 시스템을 개략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70dca-149">Provides an overview of the .NET Framework security system.</span></span>
