---
title: 특정 자식 요소로 요소를 찾는 방법(C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141153"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a>특정 자식 요소로 요소를 찾는 방법(C#)
이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.  
  
 이 예제에서는 다음 XML 문서를 사용합니다. [샘플 XML 파일: 테스트 구성(LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).  
  
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
  
```output  
0002  
0006  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다. 자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.  
  
 이 예제에서는 다음 XML 문서를 사용합니다. [샘플 XML 파일: 네임스페이스에서 테스트 구성](./sample-xml-file-test-configuration-in-a-namespace1.md).  
  
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
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [표준 쿼리 연산자 개요(C#)](./standard-query-operators-overview.md)
- [프로젝션 작업(C#)](./projection-operations.md)
