---
title: 네임스페이스에서 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: da9d819be5234a2429b6eab276f89bd0d877d4a7
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141072"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="77e3b-102">네임스페이스에서 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="77e3b-102">How to find elements in a namespace (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="77e3b-103">XPath 식은 특정 네임스페이스에서 노드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="77e3b-104">XPath 식은 네임스페이스를 지정하는 데 네임스페이스 접두사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="77e3b-105">네임스페이스 접두사가 포함된 XPath 식의 구문을 분석하려면 <xref:System.Xml.IXmlNamespaceResolver>를 구현하는 XPath 메서드에 개체를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="77e3b-106">이 예제에서는 <xref:System.Xml.XmlNamespaceManager>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>

<span data-ttu-id="77e3b-107">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-107">The XPath expression is:</span></span>

`./aw:*`

## <a name="example"></a><span data-ttu-id="77e3b-108">예</span><span class="sxs-lookup"><span data-stu-id="77e3b-108">Example</span></span>

<span data-ttu-id="77e3b-109">다음 예제에서는 두 네임스페이스가 포함된 XML 트리를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="77e3b-110">여기에서는 <xref:System.Xml.XmlReader>를 사용하여 XML 문서를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="77e3b-111">그런 다음 <xref:System.Xml.XmlNameTable>에서 <xref:System.Xml.XmlReader>을 가져오고 <xref:System.Xml.XmlNamespaceManager>에서 <xref:System.Xml.XmlNameTable>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="77e3b-112">또한 요소를 선택할 때 <xref:System.Xml.XmlNamespaceManager>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

<span data-ttu-id="77e3b-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3b-113">This example produces the following output:</span></span>

```output
Results are identical
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">
    <aw:ShippingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:ShippingAddress>
    <aw:BillingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:BillingAddress>
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>
    <aw:Item PartNum="LIT-01">
      <aw:ProductID>Litware Networking Card</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>20.99</aw:Price>
    </aw:Item>
    <aw:Item PartNum="LIT-25">
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>199.99</aw:Price>
    </aw:Item>
  </aw:PurchaseOrder>
```
