---
title: 단일 자식 요소를 검색하는 방법(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: 0e10cf230a73e6419f2d9c663766f9a24a0930af
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347468"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a>단일 자식 요소를 검색하는 방법(LINQ to XML)(C#)
이 항목에서는 자식 요소의 이름이 제공되는 경우 단일 자식 요소를 검색하는 방법에 대해 설명합니다. 자식 요소의 이름과 해당 이름을 가진 요소가 하나만 있음을 알고 있는 경우 컬렉션 대신 한 요소만 검색하는 것이 편리할 수 있습니다.  
  
 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드는 지정된 <xref:System.Xml.Linq.XElement>을 가진 첫 번째 자식 <xref:System.Xml.Linq.XName>를 반환합니다.  
  
 Visual Basic에서 단일 자식 요소를 검색하려는 경우 일반적인 방법은 XML 속성을 사용한 다음 배열 인덱서 표기법을 사용하여 첫 번째 요소를 검색하는 것입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Xml.Linq.XContainer.Element%2A> 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `po`라는 XML 트리를 가져와서 `Comment`라는 첫 번째 요소를 찾습니다.  
  
 Visual Basic 예제에서는 배열 인덱서 표기법을 사용하여 단일 요소를 검색하는 방법을 보여 줍니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)에서 설명하는 것과 같은 일반적인 XML 구매 주문이 있을 수 있습니다.  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 코드를 보여 줍니다. 자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](./sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>참조

- [LINQ to XML 축(C#)](./linq-to-xml-axes-overview.md)
