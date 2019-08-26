---
title: '방법: XML에서 텍스트 파일 생성(C#)'
ms.date: 07/20/2015
ms.assetid: 9ad283f7-7cac-42ff-bf32-92aa866e6883
ms.openlocfilehash: 51828c11b54f99131b89e0a30979f3f3acdb12ae
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593349"
---
# <a name="how-to-generate-text-files-from-xml-c"></a><span data-ttu-id="842fd-102">방법: XML에서 텍스트 파일 생성(C#)</span><span class="sxs-lookup"><span data-stu-id="842fd-102">How to: Generate Text Files from XML (C#)</span></span>
<span data-ttu-id="842fd-103">이 예제에서는 XML 파일에서 CSV(쉼표로 구분된 값) 파일을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="842fd-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842fd-104">예</span><span class="sxs-lookup"><span data-stu-id="842fd-104">Example</span></span>  
 <span data-ttu-id="842fd-105">이 예제의 C# 버전에서는 메서드 구문과 `Aggregate` 연산자를 사용하여 단일 식으로 XML 문서에서 CSV 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="842fd-105">The C# version of this example uses method syntax and the `Aggregate` operator to generate a CSV file from an XML document in a single expression.</span></span> <span data-ttu-id="842fd-106">자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](./query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="842fd-106">For more information, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="842fd-107">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="842fd-107">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
string csv =  
    (from el in custOrd.Element("Customers").Elements("Customer")  
    select  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}",  
            (string)el.Attribute("CustomerID"),  
            (string)el.Element("CompanyName"),  
            (string)el.Element("ContactName"),  
            (string)el.Element("ContactTitle"),  
            (string)el.Element("Phone"),  
            (string)el.Element("FullAddress").Element("Address"),  
            (string)el.Element("FullAddress").Element("City"),  
            (string)el.Element("FullAddress").Element("Region"),  
            (string)el.Element("FullAddress").Element("PostalCode"),  
            (string)el.Element("FullAddress").Element("Country"),  
            Environment.NewLine  
        )  
    )  
    .Aggregate(  
        new StringBuilder(),  
        (sb, s) => sb.Append(s),  
        sb => sb.ToString()  
    );  
Console.WriteLine(csv);  
```  
  
 <span data-ttu-id="842fd-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="842fd-108">This code produces the following output:</span></span>  
  
```  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="842fd-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="842fd-109">See also</span></span>

- [<span data-ttu-id="842fd-110">프로젝션 및 변환(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="842fd-110">Projections and Transformations (LINQ to XML) (C#)</span></span>](./projections-and-transformations-linq-to-xml.md)
