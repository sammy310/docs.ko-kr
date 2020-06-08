---
title: XPathNavigator를 사용하여 XML 데이터 추출
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: e639931204a416c3cde87044730364a4f387799a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287768"
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="3be26-102">XPathNavigator를 사용하여 XML 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="3be26-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="3be26-103">Microsoft .NET Framework에서는 여러 가지 방법으로 XML 문서를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="3be26-104">예를 들어, <xref:System.String>을 사용하거나 <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 클래스를 사용하여 XML 문서를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="3be26-105">여러 가지 XML 문서 표현 간을 이동할 수 있도록 <xref:System.Xml.XPath.XPathNavigator> 클래스는 XML을 <xref:System.String>, <xref:System.Xml.XmlReader> 개체 또는 <xref:System.Xml.XmlWriter> 개체로 추출하는 많은 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="3be26-106">XPathNavigator를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="3be26-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="3be26-107"><xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> 클래스의 <xref:System.Xml.XPath.XPathNavigator> 속성을 사용하여 전체 XML 문서의 태그를 가져오거나 단일 노드 및 해당 자식 노드의 태그만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3be26-108"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> 속성은 노드의 자식 노드의 태그만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="3be26-109">다음 코드 예제에서는 <xref:System.Xml.XPath.XPathNavigator> 개체에 <xref:System.String>으로 포함된 전체 XML 문서 및 단일 노드와 자식 노드를 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="3be26-110">XPathNavigator를 XmlReader로 변환</span><span class="sxs-lookup"><span data-stu-id="3be26-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="3be26-111"><xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> 메서드를 사용하면 XML 문서의 전체 내용이나 단일 노드 및 해당 자식 노드만 <xref:System.Xml.XmlReader> 개체로 스트림할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="3be26-112">현재 노드 및 자식 노드를 사용하여 <xref:System.Xml.XmlReader> 개체를 만든 경우 <xref:System.Xml.XmlReader> 개체의 <xref:System.Xml.XmlReader.ReadState%2A> 속성은 <xref:System.Xml.ReadState.Initial>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="3be26-113"><xref:System.Xml.XmlReader> 개체의 <xref:System.Xml.XmlReader.Read%2A> 메서드를 처음으로 호출하면 <xref:System.Xml.XmlReader>가 <xref:System.Xml.XPath.XPathNavigator>의 현재 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="3be26-114">새 <xref:System.Xml.XmlReader> 개체는 XML 트리 끝에 도달할 때까지 계속 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="3be26-115">이때 <xref:System.Xml.XmlReader.Read%2A> 메서드는 `false`를 반환하고 <xref:System.Xml.XmlReader> 개체의 <xref:System.Xml.XmlReader.ReadState%2A> 속성은 <xref:System.Xml.ReadState.EndOfFile>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="3be26-116"><xref:System.Xml.XPath.XPathNavigator> 개체를 만들거나 이동해도 <xref:System.Xml.XmlReader> 개체의 위치는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="3be26-117"><xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> 메서드는 요소 또는 루트 노드에 있을 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="3be26-118">다음 예제에서는 <xref:System.Xml.XmlReader> 개체의 전체 XML 문서를 포함하는 <xref:System.Xml.XPath.XPathDocument> 개체뿐만 아니라 단일 노드 및 해당 자식 노드도 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="3be26-119">이 예제에서는 `books.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="3be26-120">XPathNavigator를 XmlWriter로 변환</span><span class="sxs-lookup"><span data-stu-id="3be26-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="3be26-121"><xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> 메서드를 사용하면 XML 문서의 전체 내용이나 단일 노드 및 해당 자식 노드만 <xref:System.Xml.XmlWriter> 개체로 스트림할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="3be26-122"><xref:System.Xml.XPath.XPathNavigator> 개체를 만들어도 <xref:System.Xml.XmlWriter> 개체의 위치는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="3be26-123">다음 예제에서는 <xref:System.Xml.XmlWriter> 개체의 전체 XML 문서를 포함하는 <xref:System.Xml.XPath.XPathDocument> 개체뿐만 아니라 단일 노드 및 해당 자식 노드도 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="3be26-124">이 예제에서는 이 항목의 앞부분에 있는 `books.xml` 파일을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3be26-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be26-125">참조</span><span class="sxs-lookup"><span data-stu-id="3be26-125">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="3be26-126">XPath 데이터 모델을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="3be26-126">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="3be26-127">XPathNavigator를 사용하여 노드 집합 탐색</span><span class="sxs-lookup"><span data-stu-id="3be26-127">Node Set Navigation Using XPathNavigator</span></span>](node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="3be26-128">XPathNavigator를 사용하여 특성 및 네임스페이스 노드 탐색</span><span class="sxs-lookup"><span data-stu-id="3be26-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="3be26-129">XPathNavigator를 사용하여 강력한 형식의 XML 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="3be26-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
