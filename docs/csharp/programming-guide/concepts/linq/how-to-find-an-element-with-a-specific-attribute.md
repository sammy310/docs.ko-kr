---
title: 특정 특성으로 요소를 찾는 방법(C#)
description: 특정 값을 갖는 특성이 포함된 요소를 찾는 방법을 알아봅니다. 코드 예제 및 추가 리소스를 확인합니다.
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 44875ca2104e7a8f83e83da983af49ef85c89f0a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303285"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="b1105-104">특정 특성으로 요소를 찾는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="b1105-104">How to find an element with a specific attribute (C#)</span></span>
<span data-ttu-id="b1105-105">이 항목에서는 특정 값을 가진 특성이 포함된 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1105-105">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1105-106">예제</span><span class="sxs-lookup"><span data-stu-id="b1105-106">Example</span></span>  
 <span data-ttu-id="b1105-107">이 예제에서는 값이 "Billing"인 `Address` element that has a `Type` 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1105-107">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="b1105-108">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="b1105-108">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="b1105-109">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1105-109">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="b1105-110">예제</span><span class="sxs-lookup"><span data-stu-id="b1105-110">Example</span></span>  
 <span data-ttu-id="b1105-111">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1105-111">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b1105-112">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1105-112">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b1105-113">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b1105-113">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="b1105-114">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1105-114">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b1105-115">참조</span><span class="sxs-lookup"><span data-stu-id="b1105-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="b1105-116">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="b1105-116">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b1105-117">프로젝션 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="b1105-117">Projection Operations (C#)</span></span>](./projection-operations.md)
