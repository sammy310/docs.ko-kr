---
title: '방법: (XPath 및 LINQ to XML) 자식 요소 목록 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 2868abfd-9f7b-412a-9cb5-f643f0fed146
ms.openlocfilehash: 7ed31f17157176a6c100a8d02e065843a62b9587
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825016"
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="c8353-102">방법: (XPath 및 LINQ to XML) 자식 요소 목록 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8353-102">How to: Find a List of Child Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c8353-103">이 항목에서는 XPath 자식 요소 축과 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> 축을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c8353-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="c8353-104">XPath 식은 `./*`입니다.</span><span class="sxs-lookup"><span data-stu-id="c8353-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8353-105">예제</span><span class="sxs-lookup"><span data-stu-id="c8353-105">Example</span></span>  
 <span data-ttu-id="c8353-106">이 예제에서는 `Address` 요소의 모든 자식 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c8353-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="c8353-107">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c8353-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.<Address>.FirstOrDefault  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po.Elements()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("./*")  
  
If (list1.Count() = list2.Count()) AndAlso _  
    (list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="c8353-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8353-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8353-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8353-109">See also</span></span>

- [<span data-ttu-id="c8353-110">XPath 사용자 (Visual Basic)를 위한 LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c8353-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
