---
title: 요소 컬렉션을 검색하는 방법(LINQ to XML)(C#)
description: C#의 Elements 메서드는 요소의 자식 요소 컬렉션을 검색합니다. 이 LINQ to XML 예제에서는 요소의 자식 요소를 반복합니다.
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 4f9b6ae4713af9ce1a4eeb5257f57cd9724f68b2
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103357"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="c0736-104">요소 컬렉션을 검색하는 방법(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="c0736-104">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="c0736-105">이 항목에서는 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0736-105">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="c0736-106">이 메서드는 요소의 자식 요소 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c0736-106">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0736-107">예제</span><span class="sxs-lookup"><span data-stu-id="c0736-107">Example</span></span>  
 <span data-ttu-id="c0736-108">이 예제에서는 `purchaseOrder` 요소의 자식 요소를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c0736-108">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="c0736-109">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)에서 설명하는 것과 같은 일반적인 XML 구매 주문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0736-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="c0736-110">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0736-110">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0736-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0736-111">See also</span></span>

- [<span data-ttu-id="c0736-112">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="c0736-112">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
