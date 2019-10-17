---
title: '방법: 특성 컬렉션 검색 (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: 7c0f809c5a0707f2e6575cb8bca1b2a312f6daeb
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321332"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a>방법: 특성 컬렉션 검색 (LINQ to XML) (Visual Basic)
이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드에 대해 소개합니다. 이 메서드는 요소의 특성을 검색합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```console  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>참조

- [LINQ to XML 축(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
