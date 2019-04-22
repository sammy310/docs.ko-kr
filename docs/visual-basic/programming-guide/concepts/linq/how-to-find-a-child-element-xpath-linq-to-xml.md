---
title: '방법: (XPath 및 LINQ to XML) 자식 요소 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 96ad54d6f89aefd004a7803baef855d656b8a82d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821532"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="c4890-102">방법: (XPath 및 LINQ to XML) 자식 요소 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4890-102">How to: Find a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c4890-103">이 항목에서는 XPath 자식 요소 축과 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> 메서드를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c4890-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="c4890-104">XPath 식은 `DeliveryNotes`입니다.</span><span class="sxs-lookup"><span data-stu-id="c4890-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4890-105">예제</span><span class="sxs-lookup"><span data-stu-id="c4890-105">Example</span></span>  
 <span data-ttu-id="c4890-106">이 예제에서는 자식 요소 `DeliveryNotes`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c4890-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="c4890-107">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c4890-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="c4890-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c4890-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4890-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4890-109">See also</span></span>

- [<span data-ttu-id="c4890-110">XPath 사용자 (Visual Basic)를 위한 LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c4890-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
