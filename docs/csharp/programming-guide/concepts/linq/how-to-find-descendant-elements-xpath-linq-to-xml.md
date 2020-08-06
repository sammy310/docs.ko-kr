---
title: 하위 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)
description: XPath 식을 사용하여 특정 이름을 가진 하위 요소를 찾는 방법을 알아봅니다. 샘플 XML 파일을 사용하는 코드 예제를 검토합니다.
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c5a998a05f866203f3b684b8847a4a5647c12e5b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303272"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="bf0bd-104">하위 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="bf0bd-104">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="bf0bd-105">이 항목에서는 특정 이름을 가진 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf0bd-105">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="bf0bd-106">XPath 식은 `//Name`입니다.</span><span class="sxs-lookup"><span data-stu-id="bf0bd-106">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf0bd-107">예제</span><span class="sxs-lookup"><span data-stu-id="bf0bd-107">Example</span></span>  
 <span data-ttu-id="bf0bd-108">이 예제에서는 `Name`이라는 모든 하위 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bf0bd-108">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="bf0bd-109">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bf0bd-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="bf0bd-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf0bd-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
