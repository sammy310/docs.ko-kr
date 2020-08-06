---
title: 노드를 사용한 프로그래밍(C#)
description: 노드를 사용한 프로그래밍에 대해 알아봅니다. 이를 통해 개발자는 요소 및 특성보다 세부적인 수준에서 작동하는 프로그램을 작성할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 8a31d6459ab644a682d480239cabc3d88fd7dc14
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301686"
---
# <a name="programming-with-nodes-c"></a><span data-ttu-id="1ccef-104">노드를 사용한 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="1ccef-104">Programming with Nodes (C#)</span></span>
<span data-ttu-id="1ccef-105">XML 편집기, 변환 시스템 또는 보고서 작성기와 같은 프로그램을 작성해야 하는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개발자는 요소와 특성보다 세부적인 단위에서 작업하는 프로그램을 작성해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="1ccef-106">LINQ to XML 개발자는 흔히 노드 수준에서 작업하여 텍스트 노드, 처리 명령 및 주석을 조작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-106">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="1ccef-107">이 항목에서는 노드 수준의 프로그래밍에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-107">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="1ccef-108">노드 정보</span><span class="sxs-lookup"><span data-stu-id="1ccef-108">Node Details</span></span>  
 <span data-ttu-id="1ccef-109">노드 수준에서 작업하는 프로그래머가 알고 있어야 하는 프로그래밍 세부 정보가 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-109">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="1ccef-110">XDocument에 대한 자식 노드의 부모 속성이 Null로 설정됨</span><span class="sxs-lookup"><span data-stu-id="1ccef-110">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="1ccef-111"><xref:System.Xml.Linq.XObject.Parent%2A> 속성에는 부모 노드가 아니라 부모 <xref:System.Xml.Linq.XElement>가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-111">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="1ccef-112"><xref:System.Xml.Linq.XDocument>의 자식 노드에는 부모 <xref:System.Xml.Linq.XElement>가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-112">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="1ccef-113">이러한 노드의 부모는 문서이므로 해당 노드의 <xref:System.Xml.Linq.XObject.Parent%2A> 속성은 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-113">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="1ccef-114">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-114">The following example demonstrates this:</span></span>  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 <span data-ttu-id="1ccef-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-115">This example produces the following output:</span></span>  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="1ccef-116">인접 텍스트 노드가 가능함</span><span class="sxs-lookup"><span data-stu-id="1ccef-116">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="1ccef-117">많은 XML 프로그래밍 모델에서 인접 텍스트 노드는 항상 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-117">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="1ccef-118">이를 텍스트 노드의 표준화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-118">This is sometimes called normalization of text nodes.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1ccef-119">에서는 텍스트 노드를 표준화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-119">does not normalize text nodes.</span></span> <span data-ttu-id="1ccef-120">동일한 요소에 두 텍스트 노드를 추가하는 경우 인접 텍스트 노드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-120">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="1ccef-121">그러나 <xref:System.Xml.Linq.XText> 노드가 아니라 문자열로 지정된 내용을 추가하는 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 인접 텍스트 노드를 사용하여 문자열을 병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-121">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="1ccef-122">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-122">The following example demonstrates this:</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 <span data-ttu-id="1ccef-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-123">This example produces the following output:</span></span>  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="1ccef-124">빈 텍스트 노드가 가능함</span><span class="sxs-lookup"><span data-stu-id="1ccef-124">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="1ccef-125">일부 XML 프로그래밍 모델에서 텍스트 노드는 빈 문자열을 포함하지 않도록 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-125">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="1ccef-126">그 이유는 이러한 텍스트 노드가 XML의 serialization에 영향을 미치지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-126">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="1ccef-127">그러나 인접 텍스트 노드가 가능한 것과 동일한 이유로, 값을 빈 문자열로 설정하여 텍스트 노드에서 텍스트를 제거하는 경우 텍스트 노드 자체는 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-127">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 <span data-ttu-id="1ccef-128">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-128">This example produces the following output:</span></span>  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="1ccef-129">빈 텍스트 노드가 serialization에 영향을 미침</span><span class="sxs-lookup"><span data-stu-id="1ccef-129">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="1ccef-130">요소에 빈 자식 텍스트 노드만 포함되어 있으면 `<Child></Child>`와 같은 긴 태그 구문으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-130">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="1ccef-131">요소에 자식 노드가 포함되어 있지 않으면 `<Child />`와 같은 짧은 태그 구문으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-131">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 <span data-ttu-id="1ccef-132">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-132">This example produces the following output:</span></span>  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="1ccef-133">네임스페이스가 LINQ to XML 트리의 특성임</span><span class="sxs-lookup"><span data-stu-id="1ccef-133">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="1ccef-134">네임스페이스 선언의 구문은 특성의 구문과 동일하지만 XSLT 및 XPath와 같은 일부 프로그래밍 인터페이스에서 네임스페이스 선언은 특성으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-134">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="1ccef-135">그러나 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 네임스페이스는 XML 트리에서 <xref:System.Xml.Linq.XAttribute> 개체로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-135">However, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="1ccef-136">네임스페이스 선언이 포함된 요소의 특성을 반복하는 경우 네임스페이스 선언이 반환된 컬렉션의 항목 중 하나로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-136">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="1ccef-137"><xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> 속성은 특성이 네임스페이스 선언인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-137">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 <span data-ttu-id="1ccef-138">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-138">This example produces the following output:</span></span>  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="1ccef-139">XPath 축 메서드에서 XDocument의 자식 공백을 반환하지 않음</span><span class="sxs-lookup"><span data-stu-id="1ccef-139">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1ccef-140">에서는 텍스트 노드에 공백만 포함되어 있는 경우 <xref:System.Xml.Linq.XDocument>의 자식 텍스트 노드를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-140">allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="1ccef-141">그러나 XPath 개체 모델에서는 문서의 자식 노드로 공백을 포함하지 않으므로 <xref:System.Xml.Linq.XContainer.Nodes%2A> 축을 사용하여 <xref:System.Xml.Linq.XDocument>의 자식을 반복할 때 공백 텍스트 노드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-141">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white-space text nodes will be returned.</span></span> <span data-ttu-id="1ccef-142">그러나 XPath 축 메서드를 사용하여 <xref:System.Xml.Linq.XDocument>의 자식을 반복하는 경우에는 공백 텍스트 노드가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-142">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white-space text nodes will not be returned.</span></span>  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 <span data-ttu-id="1ccef-143">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-143">This example produces the following output:</span></span>  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="1ccef-144">XDeclaration 개체는 노드가 아님</span><span class="sxs-lookup"><span data-stu-id="1ccef-144">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="1ccef-145"><xref:System.Xml.Linq.XDocument>의 자식 노드를 반복할 때 XML 선언 개체가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-145">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="1ccef-146">XML 선언 개체는 문서의 자식 노드가 아니라 문서의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-146">It is a property of the document, not a child node of it.</span></span>  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 <span data-ttu-id="1ccef-147">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1ccef-147">This example produces the following output:</span></span>  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  