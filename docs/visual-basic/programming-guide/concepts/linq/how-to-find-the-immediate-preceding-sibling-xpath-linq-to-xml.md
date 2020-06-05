---
title: '방법: 직접 선행 형제 찾기(XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: 8b0071b2f39b8debdd52083718fe928c1f9fb6f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364528"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="06890-102">방법: 직접 선행 형제 찾기 (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06890-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="06890-103">노드의 바로 이전 형제를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06890-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="06890-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]과 반대되는 XPath의 이전 형제 축에 대한 위치 조건자의 의미 차이 때문에 이 부분은 더 흥미로운 비교 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="06890-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>

## <a name="example"></a><span data-ttu-id="06890-105">예제</span><span class="sxs-lookup"><span data-stu-id="06890-105">Example</span></span>

<span data-ttu-id="06890-106">이 예제에서 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Linq.Enumerable.Last%2A> 연산자를 사용하여 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>에 의해 반환되는 컬렉션에서 마지막 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06890-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="06890-107">이와 반대로 XPath 식은 값이 1인 조건자를 사용하여 바로 이전 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06890-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>

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

<span data-ttu-id="06890-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="06890-108">This example produces the following output:</span></span>

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a><span data-ttu-id="06890-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06890-109">See also</span></span>

- [<span data-ttu-id="06890-110">XPath 사용자에 대 한 LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06890-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
