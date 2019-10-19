---
title: '방법: 직접 선행 형제 찾기 (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: 46f5b0d2d32e8dcba5f8c9e164a027a8e8118f4d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582700"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a>방법: 직접 선행 형제 찾기 (XPath-LINQ to XML) (Visual Basic)

노드의 바로 이전 형제를 찾으려는 경우가 있습니다. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]과 반대되는 XPath의 이전 형제 축에 대한 위치 조건자의 의미 차이 때문에 이 부분은 더 흥미로운 비교 중 하나입니다.

## <a name="example"></a>예제

이 예제에서 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Linq.Enumerable.Last%2A> 연산자를 사용하여 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>에 의해 반환되는 컬렉션에서 마지막 노드를 찾습니다. 이와 반대로 XPath 식은 값이 1인 조건자를 사용하여 바로 이전 요소를 찾습니다.

```vb
Dim root As XElement = _
    <Root>
        <Child1/>
        <Child2/>
        <Child3/>
        <Child4/>
    </Root>
Dim child4 As XElement = root.Element("Child4")

' LINQ to XML query
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()

' XPath expression
Dim el2 As XElement = _
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _
    IEnumerable).Cast(Of XElement)().First()

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1)
```

이 예제는 다음과 같은 출력을 생성합니다.

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a>참조

- [XPath 사용자에 대 한 LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
