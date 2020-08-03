---
title: LINQ to XML 클래스 개요(C#)
description: 이 문서에서는 System.Xml.Linq 네임스페이스의 C#에 있는 LINQ to XML 클래스와 각 클래스에 대한 간단한 설명을 요약합니다.
ms.date: 07/20/2015
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
ms.openlocfilehash: 34508f86792cdc7589569b8f12584ffc4379a5fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165438"
---
# <a name="linq-to-xml-classes-overview-c"></a><span data-ttu-id="dd2b7-103">LINQ to XML 클래스 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="dd2b7-103">LINQ to XML Classes Overview (C#)</span></span>
<span data-ttu-id="dd2b7-104">이 항목에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 네임스페이스의 <xref:System.Xml.Linq> 클래스 목록을 제공하며 각 클래스에 대한 간략한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-104">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="dd2b7-105">LINQ to XML 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-105">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="dd2b7-106">XAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-106">XAttribute Class</span></span>  
 <span data-ttu-id="dd2b7-107"><xref:System.Xml.Linq.XAttribute>는 XML 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-107"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="dd2b7-108">자세한 내용과 예제는 [XAttribute 클래스 개요(C#)](./xattribute-class-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-108">For detailed information and examples, see [XAttribute Class Overview (C#)](./xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="dd2b7-109">XCData 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-109">XCData Class</span></span>  
 <span data-ttu-id="dd2b7-110"><xref:System.Xml.Linq.XCData>는 CDATA 텍스트 노드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-110"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="dd2b7-111">XComment 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-111">XComment Class</span></span>  
 <span data-ttu-id="dd2b7-112"><xref:System.Xml.Linq.XComment>는 XML 주석을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-112"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="dd2b7-113">XContainer 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-113">XContainer Class</span></span>  
 <span data-ttu-id="dd2b7-114"><xref:System.Xml.Linq.XContainer>는 자식 노드를 가질 수 있는 모든 노드의 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-114"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="dd2b7-115">다음 클래스는 <xref:System.Xml.Linq.XContainer> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-115">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
- <xref:System.Xml.Linq.XElement>  
  
- <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="dd2b7-116">XDeclaration 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-116">XDeclaration Class</span></span>  
 <span data-ttu-id="dd2b7-117"><xref:System.Xml.Linq.XDeclaration>은 XML 선언을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-117"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="dd2b7-118">XML 선언은 XML 버전과 문서의 인코딩을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-118">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="dd2b7-119">또한 XML 선언은 XML 문서가 독립 실행형인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-119">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="dd2b7-120">XML 문서가 독립 실행형인 경우 외부 DTD나 내부 하위 집합에서 참조된 외부 매개 변수 엔터티에 외부 태그 선언이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-120">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="dd2b7-121">XDocument 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-121">XDocument Class</span></span>  
 <span data-ttu-id="dd2b7-122"><xref:System.Xml.Linq.XDocument>는 XML 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-122"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="dd2b7-123">자세한 내용과 예제는 [XDocument 클래스 개요(C#)](./xdocument-class-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-123">For detailed information and examples, see [XDocument Class Overview (C#)](./xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="dd2b7-124">XDocumentType 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-124">XDocumentType Class</span></span>  
 <span data-ttu-id="dd2b7-125"><xref:System.Xml.Linq.XDocumentType>은 XML DTD(문서 종류 정의)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-125"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="dd2b7-126">XElement 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-126">XElement Class</span></span>  
 <span data-ttu-id="dd2b7-127"><xref:System.Xml.Linq.XElement>는 XML 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-127"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="dd2b7-128">자세한 내용과 예제는 [XElement 클래스 개요(C#)](./xelement-class-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-128">For detailed information and examples, see [XElement Class Overview (C#)](./xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="dd2b7-129">XName 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-129">XName Class</span></span>  
 <span data-ttu-id="dd2b7-130"><xref:System.Xml.Linq.XName>은 요소(<xref:System.Xml.Linq.XElement>)와 특성(<xref:System.Xml.Linq.XAttribute>)의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-130"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="dd2b7-131">자세한 내용과 예제는 [XDocument 클래스 개요(C#)](./xdocument-class-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-131">For detailed information and examples, see [XDocument Class Overview (C#)](./xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="dd2b7-132">은 XML 이름을 가능한 한 간단하게 만들도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-132">is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="dd2b7-133">복잡성 때문에 XML 이름은 흔히 XML의 고급 항목으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-133">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="dd2b7-134">거의 틀림없이 이 복잡성은 개발자가 프로그래밍에서 정기적으로 사용하는 네임스페이스 때문이 아니라 네임스페이스 접두사 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-134">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="dd2b7-135">네임스페이스 접두사는 XML을 입력하거나 XML을 읽기 쉽게 만드는 데 필요한 키 입력을 줄이는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-135">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="dd2b7-136">그러나 접두사는 전체 XML 네임스페이스를 사용하기 위한 바로 가기일 뿐인 경우가 많으며 대부분의 경우 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-136">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="dd2b7-137">에서는 모든 접두사를 해당 XML 네임스페이스로 확인하여 XML 이름을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-137">simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="dd2b7-138">접두사가 필요한 경우 <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> 메서드를 통해 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-138">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="dd2b7-139">필요한 경우 네임스페이스 접두사를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-139">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="dd2b7-140">경우에 따라 XSLT, XAML 등의 다른 XML 시스템으로 작업하는 경우 네임스페이스 접두사를 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-140">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="dd2b7-141">예를 들어 XSLT 스타일시트에 포함된 네임스페이스 접두사를 사용하는 XPath 식이 있는 경우 XML 문서가 XPath 식에 사용된 것과 일치하는 네임스페이스 접두사로 serialize되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-141">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="dd2b7-142">XNamespace 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-142">XNamespace Class</span></span>  
 <span data-ttu-id="dd2b7-143"><xref:System.Xml.Linq.XNamespace>는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>의 네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-143"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="dd2b7-144">네임스페이스는 <xref:System.Xml.Linq.XName>의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-144">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="dd2b7-145">XNode 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-145">XNode Class</span></span>  
 <span data-ttu-id="dd2b7-146"><xref:System.Xml.Linq.XNode>는 XML 트리의 노드를 나타내는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-146"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="dd2b7-147">다음 클래스는 <xref:System.Xml.Linq.XNode> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-147">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
- <xref:System.Xml.Linq.XText>  
  
- <xref:System.Xml.Linq.XContainer>  
  
- <xref:System.Xml.Linq.XComment>  
  
- <xref:System.Xml.Linq.XProcessingInstruction>  
  
- <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="dd2b7-148">XNodeDocumentOrderComparer 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-148">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="dd2b7-149"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>는 노드의 문서 순서를 비교하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-149"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="dd2b7-150">XNodeEqualityComparer 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-150">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="dd2b7-151"><xref:System.Xml.Linq.XNodeEqualityComparer>는 노드의 값이 동일한지 비교하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-151"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="dd2b7-152">XObject 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-152">XObject Class</span></span>  
 <span data-ttu-id="dd2b7-153"><xref:System.Xml.Linq.XObject>는 <xref:System.Xml.Linq.XNode> 및 <xref:System.Xml.Linq.XAttribute>의 추상 기본 클래스이며,</span><span class="sxs-lookup"><span data-stu-id="dd2b7-153"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="dd2b7-154">주석과 이벤트 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-154">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="dd2b7-155">XObjectChange 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-155">XObjectChange Class</span></span>  
 <span data-ttu-id="dd2b7-156"><xref:System.Xml.Linq.XObjectChange>는 <xref:System.Xml.Linq.XObject>에 대한 이벤트가 발생할 때 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-156"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="dd2b7-157">XObjectChangeEventArgs 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-157">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="dd2b7-158"><xref:System.Xml.Linq.XObjectChangeEventArgs>는 <xref:System.Xml.Linq.XObject.Changing> 및 <xref:System.Xml.Linq.XObject.Changed> 이벤트에 대한 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-158"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="dd2b7-159">XProcessingInstruction 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-159">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="dd2b7-160"><xref:System.Xml.Linq.XProcessingInstruction>은 XML 처리 명령을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-160"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="dd2b7-161">처리 명령은 XML을 처리하는 정보를 애플리케이션에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-161">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="dd2b7-162">XText 클래스</span><span class="sxs-lookup"><span data-stu-id="dd2b7-162">XText Class</span></span>  
 <span data-ttu-id="dd2b7-163"><xref:System.Xml.Linq.XText>는 텍스트 노드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-163"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="dd2b7-164">대부분의 경우 이 클래스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-164">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="dd2b7-165">이 클래스는 혼합 내용에 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b7-165">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2b7-166">참조</span><span class="sxs-lookup"><span data-stu-id="dd2b7-166">See also</span></span>

- [<span data-ttu-id="dd2b7-167">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="dd2b7-167">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
