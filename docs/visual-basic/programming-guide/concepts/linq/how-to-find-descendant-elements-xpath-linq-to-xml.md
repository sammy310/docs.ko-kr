---
title: '방법: 하위 항목 요소 찾기(XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: ee67a54116a7d91f6cf6af179d6398a4dcece9c4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405237"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a>방법: 하위 요소 찾기 (XPath-LINQ to XML) (Visual Basic)
이 항목에서는 특정 이름을 가진 하위 요소를 가져오는 방법을 보여 줍니다.  
  
 XPath 식은 `//Name`입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Name`이라는 모든 하위 요소를 찾습니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```console
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a>참고 항목

- [XPath 사용자에 대 한 LINQ to XML (Visual Basic)](linq-to-xml-for-xpath-users.md)
