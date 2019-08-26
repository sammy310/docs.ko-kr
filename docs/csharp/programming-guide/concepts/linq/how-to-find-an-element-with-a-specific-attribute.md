---
title: '방법: 특정 특성으로 요소 찾기(C#)'
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: da2d1691af6268a97e1f586e92c26bbb26906100
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593598"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="95ab7-102">방법: 특정 특성으로 요소 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="95ab7-102">How to: Find an Element with a Specific Attribute (C#)</span></span>
<span data-ttu-id="95ab7-103">이 항목에서는 특정 값을 가진 특성이 포함된 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ab7-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ab7-104">예</span><span class="sxs-lookup"><span data-stu-id="95ab7-104">Example</span></span>  
 <span data-ttu-id="95ab7-105">이 예제에서는 값이 "Billing"인 `Address` element that has a `Type` 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ab7-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="95ab7-106">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="95ab7-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="95ab7-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95ab7-107">This code produces the following output:</span></span>  
  
```xml  
<Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="example"></a><span data-ttu-id="95ab7-108">예</span><span class="sxs-lookup"><span data-stu-id="95ab7-108">Example</span></span>  
 <span data-ttu-id="95ab7-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95ab7-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="95ab7-110">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95ab7-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="95ab7-111">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="95ab7-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="95ab7-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95ab7-112">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95ab7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95ab7-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="95ab7-114">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="95ab7-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="95ab7-115">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="95ab7-115">Projection Operations (C#)</span></span>](./projection-operations.md)
