---
title: XElement 클래스 개요(C#)
description: XElement 클래스는 C#의 XML 요소를 나타냅니다. 이 클래스는 LINQ to XML의 기본 클래스 중 하나입니다. XElement에서 제공하는 기능에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: f76f51703de054443f47531294777b43a9c0b004
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302180"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="5a1b8-105">XElement 클래스 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="5a1b8-105">XElement Class Overview (C#)</span></span>
<span data-ttu-id="5a1b8-106"><xref:System.Xml.Linq.XElement> 클래스는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 기본 클래스 중 하나이며</span><span class="sxs-lookup"><span data-stu-id="5a1b8-106">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="5a1b8-107">XML 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-107">It represents an XML element.</span></span> <span data-ttu-id="5a1b8-108">이 클래스를 사용하여 요소를 만들거나, 요소의 내용을 변경하거나, 자식 요소를 추가, 변경 또는 삭제하거나, 특성을 요소에 추가하거나, 요소의 내용을 텍스트 형태로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-108">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="5a1b8-109">또한 <xref:System.Xml?displayProperty=nameWithType>, <xref:System.Xml.XmlReader> 및 <xref:System.Xml.XmlWriter>과 같은 <xref:System.Xml.Xsl.XslCompiledTransform>의 다른 클래스와 상호 운용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-109">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="5a1b8-110">이 항목에서는 <xref:System.Xml.Linq.XElement> 클래스에서 제공하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-110">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="5a1b8-111">XML 트리 생성</span><span class="sxs-lookup"><span data-stu-id="5a1b8-111">Constructing XML Trees</span></span>  
 <span data-ttu-id="5a1b8-112">다음과 같은 다양한 방법으로 XML 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-112">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="5a1b8-113">코드에서 XML 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-113">You can construct an XML tree in code.</span></span> <span data-ttu-id="5a1b8-114">자세한 내용은 [XML 트리 만들기(C#)](./linq-to-xml-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-114">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="5a1b8-115"><xref:System.IO.TextReader>, 텍스트 파일 또는 웹 주소(URL)와 같은 다양한 소스에서 XML의 구문을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-115">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="5a1b8-116">자세한 내용은 [XML 구문 분석(C#)](./how-to-parse-a-string.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-116">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="5a1b8-117"><xref:System.Xml.XmlReader>를 사용하여 트리를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-117">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="5a1b8-118">자세한 내용은 <xref:System.Xml.Linq.XNode.ReadFrom%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-118">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="5a1b8-119">내용을 <xref:System.Xml.XmlWriter>에 쓸 수 있는 모듈이 있는 경우 <xref:System.Xml.Linq.XContainer.CreateWriter%2A> 메서드를 사용하여 작성기를 만들고 모듈에 작성기를 전달한 다음 <xref:System.Xml.XmlWriter>에 쓴 내용을 사용하여 XML 트리를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-119">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="5a1b8-120">그러나 XML 트리를 만드는 가장 일반적인 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-120">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="5a1b8-121">XML 트리를 만드는 또 다른 일반적인 방법에는 다음 예제에서와 같이 LINQ 쿼리의 결과를 사용하여 XML 트리를 채우는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-121">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="5a1b8-122">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-122">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="5a1b8-123">XML 트리 serialization</span><span class="sxs-lookup"><span data-stu-id="5a1b8-123">Serializing XML Trees</span></span>  
 <span data-ttu-id="5a1b8-124">XML 트리를 <xref:System.IO.File>, <xref:System.IO.TextWriter> 또는 <xref:System.Xml.XmlWriter>로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-124">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="5a1b8-125">자세한 내용은 [XML 트리 serialize(C#)](./preserving-white-space-while-serializing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-125">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="5a1b8-126">축 메서드를 통해 XML 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="5a1b8-126">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="5a1b8-127">축 메서드를 사용하여 특성, 자식 요소, 하위 요소 및 상위 요소를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-127">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="5a1b8-128">LINQ 쿼리는 축 메서드에 대해 작동하며 XML 트리를 탐색하고 처리하는 유연하고 강력한 몇 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-128">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="5a1b8-129">자세한 내용은 [LINQ to XML 축(C#)](./linq-to-xml-axes-overview.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-129">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="5a1b8-130">XML 트리 쿼리</span><span class="sxs-lookup"><span data-stu-id="5a1b8-130">Querying XML Trees</span></span>  
 <span data-ttu-id="5a1b8-131">XML 트리에서 데이터를 추출하는 LINQ 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-131">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="5a1b8-132">자세한 내용은 [XML 트리 쿼리(C#)](./how-to-find-an-element-with-a-specific-attribute.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-132">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="5a1b8-133">XML 트리 수정</span><span class="sxs-lookup"><span data-stu-id="5a1b8-133">Modifying XML Trees</span></span>  
 <span data-ttu-id="5a1b8-134">내용이나 특성을 변경하는 등의 다양한 방법으로 요소를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-134">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="5a1b8-135">또한 부모에서 요소를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-135">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="5a1b8-136">자세한 내용은 [XML 트리 수정(LINQ to XML)(C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1b8-136">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1b8-137">참조</span><span class="sxs-lookup"><span data-stu-id="5a1b8-137">See also</span></span>

- [<span data-ttu-id="5a1b8-138">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="5a1b8-138">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
