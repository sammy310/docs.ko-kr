---
title: '방법: (Visual Basic) XML에서 텍스트 파일 생성'
ms.date: 07/20/2015
ms.assetid: 3b33f191-4abe-4419-b81b-3cb81d9a317f
ms.openlocfilehash: 6273152995b458da110a2bda56ebdc35d49b6769
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829488"
---
# <a name="how-to-generate-text-files-from-xml-visual-basic"></a><span data-ttu-id="eddac-102">방법: (Visual Basic) XML에서 텍스트 파일 생성</span><span class="sxs-lookup"><span data-stu-id="eddac-102">How to: Generate Text Files from XML (Visual Basic)</span></span>
<span data-ttu-id="eddac-103">이 예제에서는 XML 파일에서 CSV(쉼표로 구분된 값) 파일을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eddac-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eddac-104">예제</span><span class="sxs-lookup"><span data-stu-id="eddac-104">Example</span></span>  
 <span data-ttu-id="eddac-105">Visual Basic 버전 절차적 코드를 사용 하 여 문자열의 컬렉션을 단일 문자열로 집계 합니다.</span><span class="sxs-lookup"><span data-stu-id="eddac-105">The Visual Basic version uses procedural code to aggregate the collection of strings into a single string.</span></span>  
  
 <span data-ttu-id="eddac-106">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="eddac-106">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim strCollection As IEnumerable(Of String) = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select _  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}", _  
            el.@CustomerID, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value, _  
            el.<ContactTitle>.Value, _  
            el.<Phone>.Value, _  
            el.<FullAddress>.<Address>.Value, _  
            el.<FullAddress>.<City>.Value, _  
            el.<FullAddress>.<Region>.Value, _  
            el.<FullAddress>.<PostalCode>.Value, _  
            el.<FullAddress>.<Country>.Value, _  
            Environment.NewLine _  
        )  
Dim sb As StringBuilder = New StringBuilder()  
For Each str As String In strCollection  
    sb.Append(str)  
Next  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="eddac-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eddac-107">This code produces the following output:</span></span>  
  
```  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="eddac-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="eddac-108">See also</span></span>

- [<span data-ttu-id="eddac-109">프로젝션 및 변형 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eddac-109">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
