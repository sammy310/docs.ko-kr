---
title: '방법: 특정 자식 요소로 요소 찾기(C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 71068774b93581fdd82a0fe57651bc7780ca1ef1
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485576"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a>방법: 특정 자식 요소로 요소 찾기(C#)
이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 테스트 구성(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
0002  
0006  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)을 참조하세요.  
  
 이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 테스트 구성](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [프로젝션 작업(C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
