---
title: 요소를 정렬하는 방법(C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7fad9fcb43905072c88a5704c56672917bfc377c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347374"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="1f516-102">요소를 정렬하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="1f516-102">How to sort elements (C#)</span></span>
<span data-ttu-id="1f516-103">이 예제에서는 결과를 정렬하는 쿼리를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f516-104">예제</span><span class="sxs-lookup"><span data-stu-id="1f516-104">Example</span></span>  
 <span data-ttu-id="1f516-105">이 예제에서는 XML 문서 [샘플 XML 파일: 숫자 데이터(LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="1f516-106">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-106">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="1f516-107">예제</span><span class="sxs-lookup"><span data-stu-id="1f516-107">Example</span></span>  
 <span data-ttu-id="1f516-108">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="1f516-109">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f516-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1f516-110">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스의 숫자 데이터](./sample-xml-file-numerical-data-in-a-namespace.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="1f516-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f516-111">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f516-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f516-112">See also</span></span>

- [<span data-ttu-id="1f516-113">데이터 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="1f516-113">Sorting Data (C#)</span></span>](./sorting-data.md)
