---
title: '방법: 정렬 요소 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: c2c09279-6c8a-482e-8e71-b1453a815052
ms.openlocfilehash: 1bd76ade02f8f891e98b048ac866b6b9de65062f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835094"
---
# <a name="how-to-sort-elements-visual-basic"></a><span data-ttu-id="cca5e-102">방법: 정렬 요소 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca5e-102">How to: Sort Elements (Visual Basic)</span></span>
<span data-ttu-id="cca5e-103">이 예제에서는 결과를 정렬하는 쿼리를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cca5e-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca5e-104">예제</span><span class="sxs-lookup"><span data-stu-id="cca5e-104">Example</span></span>  
 <span data-ttu-id="cca5e-105">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cca5e-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim prices As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let price = Convert.ToDecimal(el.<Price>.Value) _  
    Order By (price) _  
    Select price  
For Each el As Decimal In prices  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="cca5e-106">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cca5e-106">This code produces the following output:</span></span>  
  
```console  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="cca5e-107">예제</span><span class="sxs-lookup"><span data-stu-id="cca5e-107">Example</span></span>  
 <span data-ttu-id="cca5e-108">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cca5e-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cca5e-109">자세한 내용은 [네임 스페이스 개요 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cca5e-109">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cca5e-110">이 예제에서는 XML 문서로 을 사용합니다. [샘플 XML 파일: 네임스페이스의 숫자 데이터](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="cca5e-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim prices As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let price = Convert.ToDecimal(el.<Price>.Value) _  
            Order By (price) _  
            Select price  
        For Each el As Decimal In prices  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="cca5e-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cca5e-111">This code produces the following output:</span></span>  
  
```console  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca5e-112">참조</span><span class="sxs-lookup"><span data-stu-id="cca5e-112">See also</span></span>

- [<span data-ttu-id="cca5e-113">데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="cca5e-113">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="cca5e-114">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca5e-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
