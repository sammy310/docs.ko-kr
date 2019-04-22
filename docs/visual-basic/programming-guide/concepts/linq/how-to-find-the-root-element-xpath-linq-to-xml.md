---
title: '방법: (XPath 및 LINQ to XML) 루트 요소 찾기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 72c3aed5-9522-4454-a876-2070aad13f2e
ms.openlocfilehash: 0936300a51c697eaff5a1aeafff70e37b04a2a96
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816757"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="55ca7-102">방법: (XPath 및 LINQ to XML) 루트 요소 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ca7-102">How to: Find the Root Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="55ca7-103">이 항목에서는 XPath와 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 루트 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55ca7-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="55ca7-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55ca7-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="55ca7-105">예제</span><span class="sxs-lookup"><span data-stu-id="55ca7-105">Example</span></span>  
 <span data-ttu-id="55ca7-106">이 예제에서는 루트 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="55ca7-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="55ca7-107">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="55ca7-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim el1 As XElement = po.Root  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1.Name)  
```  
  
 <span data-ttu-id="55ca7-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="55ca7-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="55ca7-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="55ca7-109">See also</span></span>

- [<span data-ttu-id="55ca7-110">XPath 사용자 (Visual Basic)를 위한 LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="55ca7-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
