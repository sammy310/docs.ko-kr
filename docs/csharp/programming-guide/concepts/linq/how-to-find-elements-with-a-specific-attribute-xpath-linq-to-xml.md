---
title: 특정 특성으로 요소를 찾는 방법(XPath-LINQ to XML)(C#)
description: 이 C# 예제에서는 특정 특성이 있는 요소를 찾는 방법에 대해 XPath와 LINQ to XML을 비교합니다.
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: eb0b5c27fb3993b487c5e8d70c6562c1d0562860
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105269"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="e5490-103">특정 특성으로 요소를 찾는 방법(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="e5490-103">How to find elements with a specific attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="e5490-104">특정 특성을 가진 모든 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5490-104">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="e5490-105">특성의 내용에는 관심이 없으며,</span><span class="sxs-lookup"><span data-stu-id="e5490-105">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="e5490-106">대신 특성의 존재에 따라 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5490-106">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="e5490-107">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5490-107">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="e5490-108">예제</span><span class="sxs-lookup"><span data-stu-id="e5490-108">Example</span></span>  
 <span data-ttu-id="e5490-109">다음 코드에서는 `Select` 특성을 가진 요소만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5490-109">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e5490-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e5490-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  