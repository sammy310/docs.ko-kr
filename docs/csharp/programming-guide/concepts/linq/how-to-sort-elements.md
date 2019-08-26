---
title: '방법: 요소 정렬(C#)'
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 074428413fa57d8f0e5ae94970c2aeeeb9e4cc7c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592460"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="1cbb9-102">방법: 요소 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="1cbb9-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="1cbb9-103">이 예제에서는 결과를 정렬하는 쿼리를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cbb9-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cbb9-104">예</span><span class="sxs-lookup"><span data-stu-id="1cbb9-104">Example</span></span>  
 <span data-ttu-id="1cbb9-105">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 숫자 데이터(LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1cbb9-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="1cbb9-106">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cbb9-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="1cbb9-107">예</span><span class="sxs-lookup"><span data-stu-id="1cbb9-107">Example</span></span>  
 <span data-ttu-id="1cbb9-108">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cbb9-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="1cbb9-109">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cbb9-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1cbb9-110">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스의 숫자 데이터](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="1cbb9-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="1cbb9-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1cbb9-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cbb9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cbb9-112">See also</span></span>

- [<span data-ttu-id="1cbb9-113">데이터 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="1cbb9-113">Sorting Data (C#)</span></span>](./sorting-data.md)
