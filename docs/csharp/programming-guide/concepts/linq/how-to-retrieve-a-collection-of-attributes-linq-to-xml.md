---
title: '방법: 특성 컬렉션 검색(LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: b37600f02cd012e688d161a079c3c8647545cb2c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592671"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="d9111-102">방법: 특성 컬렉션 검색(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9111-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="d9111-103">이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d9111-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="d9111-104">이 메서드는 요소의 특성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d9111-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9111-105">예</span><span class="sxs-lookup"><span data-stu-id="d9111-105">Example</span></span>  
 <span data-ttu-id="d9111-106">다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9111-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 <span data-ttu-id="d9111-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9111-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9111-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9111-108">See also</span></span>

- [<span data-ttu-id="d9111-109">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="d9111-109">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
