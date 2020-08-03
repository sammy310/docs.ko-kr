---
title: 루트 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)
description: 이 C# 예제에서는 샘플 XML 문서의 루트 요소를 가져오는 방법에 대해 XPath와 LINQ to XML을 비교합니다.
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 220899823210c5cd6e9834541ca87e4d8394b4ff
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105192"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="328a5-103">루트 요소를 찾는 방법(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="328a5-103">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="328a5-104">이 항목에서는 XPath와 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 루트 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="328a5-104">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="328a5-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="328a5-105">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="328a5-106">예제</span><span class="sxs-lookup"><span data-stu-id="328a5-106">Example</span></span>  
 <span data-ttu-id="328a5-107">이 예제에서는 루트 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="328a5-107">This example finds the root element.</span></span>  
  
 <span data-ttu-id="328a5-108">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="328a5-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="328a5-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="328a5-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
