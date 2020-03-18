---
title: 루트 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 1c5526f436b5b9d88ca359ef7e0fc04c5c3cf43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345955"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="a20a5-102">루트 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a20a5-102">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a20a5-103">이 항목에서는 XPath와 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 루트 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a20a5-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="a20a5-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a20a5-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="a20a5-105">예제</span><span class="sxs-lookup"><span data-stu-id="a20a5-105">Example</span></span>  
 <span data-ttu-id="a20a5-106">이 예제에서는 루트 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a20a5-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="a20a5-107">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a20a5-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="a20a5-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a20a5-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
