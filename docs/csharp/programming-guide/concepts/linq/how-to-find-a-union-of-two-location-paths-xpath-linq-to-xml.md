---
title: 두 위치 경로의 공용 구조체를 찾는 방법(XPath-LINQ to XML)(C#)
description: XPath 식을 사용하여 두 XPath 위치 경로의 합집합을 찾는 방법을 알아봅니다. 샘플 XML 파일을 사용하는 코드 예제를 검토합니다.
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 65b20fe25a0990fd82ce3bd08c3433499e728512
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303324"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="a1da6-104">두 위치 경로의 공용 구조체를 찾는 방법(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a1da6-104">How to find a union of two location paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a1da6-105">XPath를 사용하여 두 XPath 위치 경로의 통합을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-105">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="a1da6-106">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-106">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="a1da6-107"><xref:System.Linq.Enumerable.Concat%2A> 표준 쿼리 연산자를 사용하여 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-107">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1da6-108">예제</span><span class="sxs-lookup"><span data-stu-id="a1da6-108">Example</span></span>  
 <span data-ttu-id="a1da6-109">이 예제에서는 모든 `Category` 요소와 모든 `Price` 요소를 찾은 다음 단일 컬렉션으로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-109">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="a1da6-110">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리는 <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>을 호출하여 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-110">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="a1da6-111">XPath 식 계산의 결과도 문서 순서로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-111">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="a1da6-112">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 숫자 데이터(LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a1da6-112">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="a1da6-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1da6-113">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  