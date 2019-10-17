---
title: '방법: 특성 값 검색 (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6f9a5936c962111eb75a05f5e3704f7132618143
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320469"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>방법: 특성 값 검색 (LINQ to XML) (Visual Basic)
이 항목에서는 특성의 값을 가져오는 방법을 보여 줍니다. 두 가지 주요 방법이 있습니다. <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅할 수 있습니다. 그러면 명시적 변환 연산자가 요소나 특성의 내용을 지정된 형식으로 변환합니다. 또는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 사용할 수 있습니다. 그러나 일반적으로 캐스팅이 더 나은 방법입니다. 특성을 nullable 형식으로 캐스팅하면 존재하지 않을 수도 있는 특성의 값을 검색하는 경우 코드를 더 간단하게 작성할 수 있습니다. 이 기술에 대 한 예제 [는 방법: 요소 값 검색 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 검색할 수 있습니다.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>예제  
 Visual Basic에서는 통합 특성 속성을 사용하여 특성의 값을 설정할 수 있습니다. 또한 통합 특성 속성을 사용하여 존재하지 않는 특성의 값을 설정하는 경우 특성이 만들어집니다.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 특성이 네임스페이스에 있는 경우 특성의 값을 검색하는 방법을 보여 줍니다. 자세한 내용은 [네임 스페이스 개요 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)를 참조 하세요.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>참조

- [LINQ to XML 축(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
