---
title: '방법: (XPath 및 LINQ to XML) 자식 요소 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 96ad54d6f89aefd004a7803baef855d656b8a82d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821532"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>방법: (XPath 및 LINQ to XML) 자식 요소 찾기 (Visual Basic)
이 항목에서는 XPath 자식 요소 축과 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> 메서드를 비교합니다.  
  
 XPath 식은 `DeliveryNotes`입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 자식 요소 `DeliveryNotes`를 찾습니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>참고자료

- [XPath 사용자 (Visual Basic)를 위한 LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
