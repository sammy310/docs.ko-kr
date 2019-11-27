---
title: '방법: 요소 컬렉션 검색(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 592ef68206df59bc848644d0a62bf0efdb10609e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347593"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a>방법: 요소 컬렉션 검색 (LINQ to XML) (Visual Basic)
이 항목에서는 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드를 보여 줍니다. 이 메서드는 요소의 자식 요소 컬렉션을 검색합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `purchaseOrder` 요소의 자식 요소를 반복합니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)을 사용합니다.  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 이 예제의 결과는 다음과 같습니다.  
  
```console  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>참고자료

- [LINQ to XML 축(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
