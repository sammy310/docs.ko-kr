---
title: 요소 이름으로 필터링하는 방법(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 74efb19ef5ec77ca29145d27a8e5aa977530b68b
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141270"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a>요소 이름으로 필터링하는 방법(LINQ to XML)(C#)
<xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>을 반환하는 메서드 중 하나를 호출하면 요소 이름을 기준으로 필터링할 수 있습니다.  
  
## <a name="example"></a>예  
 이 예제에서는 하위 요소의 컬렉션을 검색합니다. 하위 항목이 필터링되므로 컬렉션에는 지정된 이름을 가진 하위 항목만 포함됩니다.  
  
 이 예제에서는 다음 XML 문서를 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```output  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션의 <xref:System.Xml.Linq.XElement>을 반환하는 다른 메서드는 같은 패턴을 따릅니다. 이들 메서드 시그니처는 <xref:System.Xml.Linq.XContainer.Elements%2A> 및 <xref:System.Xml.Linq.XContainer.Descendants%2A>와 비슷합니다. 다음은 메서드 시그니처가 유사한 메서드의 전체 목록입니다.  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a>예  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.  
  
 이 예제에서는 다음 XML 문서를 사용합니다. [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](./sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```output  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a>참고 항목

- [LINQ to XML 축(C#)](./linq-to-xml-axes-overview.md)
