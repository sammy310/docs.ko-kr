---
title: 직접 선행 형제를 찾는 방법(XPath 및 LINQ to XML)(C#)
description: 이 C# 예제에서는 노드 바로 앞에 오는 형제를 찾는 방법에 대해 XPath와 LINQ to XML을 비교합니다.
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: eaee7f1205ce0d0b2a9c2c41d96ba532573a1384
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105201"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a>직접 선행 형제를 찾는 방법(XPath 및 LINQ to XML)(C#)
노드의 바로 이전 형제를 찾으려는 경우가 있습니다. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]과 반대되는 XPath의 이전 형제 축에 대한 위치 조건자의 의미 차이 때문에 이 부분은 더 흥미로운 비교 중 하나입니다.  
  
## <a name="example"></a>예제  
 이 예제에서 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Linq.Enumerable.Last%2A> 연산자를 사용하여 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>에 의해 반환되는 컬렉션에서 마지막 노드를 찾습니다. 이와 반대로 XPath 식은 값이 1인 조건자를 사용하여 바로 이전 요소를 찾습니다.  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```output  
Results are identical  
<Child3 />  
```  
