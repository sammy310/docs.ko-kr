---
title: 관련 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: f74c338019c0451ab5e3ac0d8da10392ae5601ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169235"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="919fa-102">관련 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="919fa-102">How to find related elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="919fa-103">이 항목에서는 다른 요소의 값에 의해 참조되는 특성을 기준으로 선택하여 요소를 가져오는 방법을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="919fa-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="919fa-105">예제</span><span class="sxs-lookup"><span data-stu-id="919fa-105">Example</span></span>  
 <span data-ttu-id="919fa-106">이 예제에서는 12번째 `Order` 요소를 찾은 다음 해당 주문의 고객을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="919fa-107">.NET에서 목록의 인덱싱은 ‘0’부터 시작하고</span><span class="sxs-lookup"><span data-stu-id="919fa-107">Note that indexing into a list in .NET is 'zero' based.</span></span> <span data-ttu-id="919fa-108">XPath 조건자에서 노드 컬렉션의 인덱싱은 1부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="919fa-109">이 예제에서는 이 차이를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="919fa-110">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 <span data-ttu-id="919fa-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="919fa-111">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
