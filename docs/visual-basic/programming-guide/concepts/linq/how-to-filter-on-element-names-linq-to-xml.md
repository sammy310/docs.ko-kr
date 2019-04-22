---
title: '방법: (LINQ to XML) 요소 이름 필터링 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
ms.openlocfilehash: 868647ba9536886ea84fa10d94738ff0f29d8f02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836391"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a>방법: (LINQ to XML) 요소 이름 필터링 (Visual Basic)
<xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>을 반환하는 메서드 중 하나를 호출하면 요소 이름을 기준으로 필터링할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 하위 요소의 컬렉션을 검색합니다. 하위 항목이 필터링되므로 컬렉션에는 지정된 이름을 가진 하위 항목만 포함됩니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim items As IEnumerable(Of XElement) = _  
    From el In po...<ProductName> _  
    Select el  
For Each prdName As XElement In items  
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션의 <xref:System.Xml.Linq.XElement>을 반환하는 다른 메서드는 같은 패턴을 따릅니다. 이들 메서드 시그니처는 <xref:System.Xml.Linq.XContainer.Elements%2A> 및 <xref:System.Xml.Linq.XContainer.Descendants%2A>와 비슷합니다. 다음은 메서드 시그니처가 유사한 메서드의 전체 목록입니다.  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a>참고자료

- [LINQ to XML 축(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
