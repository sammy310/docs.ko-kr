---
title: XPathNavigator를 사용하여 노드 일치시키기
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: 47b0ba7e705ad602825dcca3f24c207362174a4c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289124"
---
# <a name="matching-nodes-using-xpathnavigator"></a>XPathNavigator를 사용하여 노드 일치시키기
<xref:System.Xml.XPath.XPathNavigator> 클래스는 노드가 XPath 식과 일치하는지 결정하는 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드를 제공합니다. <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 XPath 식을 입력으로 사용하며 현재 노드가 지정된 XPath 식 또는 지정된 컴파일된 <xref:System.Boolean> 개체와 일치하는지를 나타내는 <xref:System.Xml.XPath.XPathExpression>을 반환합니다.  
  
## <a name="matching-nodes"></a>노드 일치시키기  
 현재 노드가 지정된 XPath 식과 일치하는 경우 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 `true`를 반환합니다. 예를 들어, 다음 코드 예제에서 현재 노드가 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 요소이고 `true` 요소에 `b` 특성이 있을 경우 `b` 메서드는 `c`를 반환합니다.  
  
> [!NOTE]
> <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 <xref:System.Xml.XPath.XPathNavigator> 상태를 변경하지 않습니다.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [XPath 데이터 모델을 사용하여 XML 데이터 처리](process-xml-data-using-the-xpath-data-model.md)
- [XPathNavigator를 사용하여 XML 데이터 선택](select-xml-data-using-xpathnavigator.md)
- [XPathNavigator를 사용하여 XPath 식 계산](evaluate-xpath-expressions-using-xpathnavigator.md)
- [XPath 쿼리에서 인식하는 노드 형식](node-types-recognized-with-xpath-queries.md)
- [XPath 쿼리 및 네임스페이스](xpath-queries-and-namespaces.md)
- [컴파일된 XPath 식](compiled-xpath-expressions.md)
