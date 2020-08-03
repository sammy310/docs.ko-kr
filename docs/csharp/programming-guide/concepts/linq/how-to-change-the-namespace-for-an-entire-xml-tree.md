---
title: 전체 XML 트리에 대한 네임스페이스 변경 방법(C#)
description: C#의 LINQ to XML에서 요소나 특성의 네임스페이스를 프로그래밍 방식으로 변경하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: 0bf4c9d8f3cf569f14b654dfd0c4291a7eb647df
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105366"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="1fe3c-103">전체 XML 트리에 대한 네임스페이스 변경 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="1fe3c-103">How to change the namespace for an entire XML tree (C#)</span></span>
<span data-ttu-id="1fe3c-104">요소나 특성의 네임스페이스를 프로그래밍 방식으로 변경해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-104">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="1fe3c-105">LINQ to XML을 사용하면 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-105">LINQ to XML makes this easy.</span></span> <span data-ttu-id="1fe3c-106"><xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> 속성은 설정될 수 있지만,</span><span class="sxs-lookup"><span data-stu-id="1fe3c-106">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="1fe3c-107"><xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> 속성은 설정될 수 없습니다. 하지만 쉽게 특성을 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>에 복사하고 기존 특성을 제거한 다음 원하는 새 네임스페이스에 있는 새 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-107">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="1fe3c-108">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-108">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fe3c-109">예제</span><span class="sxs-lookup"><span data-stu-id="1fe3c-109">Example</span></span>  
 <span data-ttu-id="1fe3c-110">다음 코드에서는 네임스페이스에 없는 두 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="1fe3c-110">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="1fe3c-111">각 트리의 네임스페이스를 변경하고 이러한 트리를 단일 트리로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-111">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1fe3c-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe3c-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
