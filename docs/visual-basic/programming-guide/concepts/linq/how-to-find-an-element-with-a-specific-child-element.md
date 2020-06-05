---
title: '방법: 특정 자식 요소로 요소 찾기'
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: a05504070fe3d2ea5eb6135fd3bf697b131686c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405289"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a>방법: 특정 자식 요소를 사용 하 여 요소 찾기 (Visual Basic)
이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 테스트 구성(LINQ to XML)](sample-xml-file-test-configuration-linq-to-xml.md)을 사용합니다.  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```console  
0002  
0006  
```  
  
 이 예에서는 xml [자식 축 속성](../../../language-reference/xml-axis/xml-child-axis-property.md), [xml 특성 축 속성](../../../language-reference/xml-axis/xml-attribute-axis-property.md)및 [xml Value 속성](../../../language-reference/xml-axis/xml-value-property.md)을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [네임 스페이스 개요 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)를 참조 하세요.  
  
 이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 테스트 구성](sample-xml-file-test-configuration-in-a-namespace.md)을 사용합니다.  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```console  
0002  
0006  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [기본 쿼리 (LINQ to XML) (Visual Basic)](basic-queries-linq-to-xml.md)
- [표준 쿼리 연산자 개요(Visual Basic)](standard-query-operators-overview.md)
- [프로젝션 작업 (Visual Basic)](projection-operations.md)
