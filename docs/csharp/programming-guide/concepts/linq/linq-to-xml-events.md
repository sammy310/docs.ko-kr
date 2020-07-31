---
title: LINQ to XML 이벤트(C#)
description: C#의 LINQ to XML 이벤트를 XObject의 인스턴스에 추가합니다. 이벤트 처리기는 해당 XObject의 XML 트리가 수정될 때 이벤트를 수신합니다.
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 576b0a5d0472bddd66e01d3bef8f3affa1c9458b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165421"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="31421-104">LINQ to XML 이벤트(C#)</span><span class="sxs-lookup"><span data-stu-id="31421-104">LINQ to XML Events (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="31421-105">이벤트를 통해 XML 트리가 변경될 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-105">events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="31421-106"><xref:System.Xml.Linq.XObject>의 인스턴스에 이벤트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-106">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="31421-107">이벤트 처리기는 이 <xref:System.Xml.Linq.XObject>와 해당 하위 항목의 수정에 대한 이벤트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-107">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="31421-108">예를 들어, 이벤트 처리기를 트리의 루트에 추가하고 해당 이벤트 처리기에서 트리의 모든 수정을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-108">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="31421-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 이벤트의 예제는 <xref:System.Xml.Linq.XObject.Changing> 및 <xref:System.Xml.Linq.XObject.Changed>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31421-109">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="31421-110">형식 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="31421-110">Types and Events</span></span>  
 <span data-ttu-id="31421-111">이벤트 작업을 할 때 다음 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-111">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="31421-112">Type</span><span class="sxs-lookup"><span data-stu-id="31421-112">Type</span></span>|<span data-ttu-id="31421-113">설명</span><span class="sxs-lookup"><span data-stu-id="31421-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="31421-114"><xref:System.Xml.Linq.XObject>에 대한 이벤트가 발생할 때 이벤트 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-114">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="31421-115"><xref:System.Xml.Linq.XObject.Changing> 및 <xref:System.Xml.Linq.XObject.Changed> 이벤트에 대한 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="31421-116">다음 이벤트는 XML 트리를 수정할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="31421-117">이벤트</span><span class="sxs-lookup"><span data-stu-id="31421-117">Event</span></span>|<span data-ttu-id="31421-118">Description</span><span class="sxs-lookup"><span data-stu-id="31421-118">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="31421-119">이 <xref:System.Xml.Linq.XObject> 또는 해당 하위 항목이 변경되기 직전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-119">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="31421-120"><xref:System.Xml.Linq.XObject>가 변경되거나 해당 하위 항목이 변경될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-120">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="31421-121">예제</span><span class="sxs-lookup"><span data-stu-id="31421-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="31421-122">설명</span><span class="sxs-lookup"><span data-stu-id="31421-122">Description</span></span>  
 <span data-ttu-id="31421-123">XML 트리에 특정 집계 정보를 유지 관리하려는 경우 이벤트가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-123">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="31421-124">예를 들어, 청구서의 개별 품목에 대한 합계인 청구서 총계를 유지 관리하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-124">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="31421-125">이 예제에서는 이벤트를 사용하여 복합 요소 `Items` 아래의 모든 자식 요소에 대한 총계를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="31421-125">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="31421-126">코드</span><span class="sxs-lookup"><span data-stu-id="31421-126">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="31421-127">주석</span><span class="sxs-lookup"><span data-stu-id="31421-127">Comments</span></span>  
 <span data-ttu-id="31421-128">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31421-128">This code produces the following output:</span></span>  
  
```output  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  