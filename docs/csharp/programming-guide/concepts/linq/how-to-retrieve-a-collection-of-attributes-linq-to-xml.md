---
title: 특성 컬렉션을 검색하는 방법(LINQ to XML)(C#)
description: C#의 Attributes 메서드는 요소의 특성을 검색합니다. 이 LINQ to XML 예제에서는 요소의 특성 컬렉션을 반복합니다.
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: 5994086db6133530e63eb1328a7b524d30a0797d
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103379"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a><span data-ttu-id="a9333-104">특성 컬렉션을 검색하는 방법(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a9333-104">How to retrieve a collection of attributes (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a9333-105">이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="a9333-105">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="a9333-106">이 메서드는 요소의 특성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a9333-106">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9333-107">예제</span><span class="sxs-lookup"><span data-stu-id="a9333-107">Example</span></span>  
 <span data-ttu-id="a9333-108">다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9333-108">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
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
  
 <span data-ttu-id="a9333-109">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9333-109">This code produces the following output:</span></span>  
  
```output  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9333-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9333-110">See also</span></span>

- [<span data-ttu-id="a9333-111">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="a9333-111">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
