---
title: LINQ to XML을 사용하여 사전 작업을 수행하는 방법(C#)
description: LINQ to XML을 사용하여 사전 작업을 수행하는 방법을 알아봅니다. 사전을 XML로 변환하고 다시 XML을 다른 데이터 구조체로 변환하는 예제를 살펴봅니다.
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: bdba7a2b3dfc16fab1e239ac804c317dfefb7d9e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302622"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="94ef4-104">LINQ to XML을 사용하여 사전 작업을 수행하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="94ef4-104">How to work with dictionaries using LINQ to XML (C#)</span></span>
<span data-ttu-id="94ef4-105">다양한 데이터 구조를 XML로 변환하고 XML을 다시 다른 데이터 구조로 변환하는 것이 편리한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-105">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="94ef4-106">이 항목에서는 <xref:System.Collections.Generic.Dictionary%602>를 XML로 변환하고 다시 그 반대로 변환하여 이 일반적인 방법을 구체적으로 구현하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-106">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94ef4-107">예제</span><span class="sxs-lookup"><span data-stu-id="94ef4-107">Example</span></span>  
 <span data-ttu-id="94ef4-108">이 예제에서는 쿼리가 새 <xref:System.Xml.Linq.XElement> 개체를 프로젝션하고 생성된 컬렉션이 루트 <xref:System.Xml.Linq.XElement> 개체의 생성자에 인수로 전달되는 함수 구문의 형태를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-108">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="94ef4-109">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-109">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="94ef4-110">예제</span><span class="sxs-lookup"><span data-stu-id="94ef4-110">Example</span></span>  
 <span data-ttu-id="94ef4-111">다음 코드에서는 XML에서 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-111">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="94ef4-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94ef4-112">This code produces the following output:</span></span>  
  
```output  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
