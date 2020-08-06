---
title: 컨텍스트에 따라 요소를 찾는 쿼리를 작성하는 방법(C#)
description: 컨텍스트에 따라 요소를 찾는 쿼리를 작성하는 방법을 알아봅니다. 코드 예제를 살펴보고 추가 리소스를 확인합니다.
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 64f09a41c2c1d01b0be8f776461f9be9df9ecb5f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303194"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="96c88-104">컨텍스트에 따라 요소를 찾는 쿼리를 작성하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="96c88-104">How to write a query that finds elements based on context (C#)</span></span>
<span data-ttu-id="96c88-105">컨텍스트에 따라 요소를 선택하는 쿼리를 작성해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-105">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="96c88-106">이전 또는 다음 형제 요소를 기준으로 필터링하거나,</span><span class="sxs-lookup"><span data-stu-id="96c88-106">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="96c88-107">자식 또는 상위 요소를 기준으로 필터링하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-107">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="96c88-108">쿼리를 작성하고 `where` 절에서 쿼리의 결과를 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-108">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="96c88-109">먼저 null에 대해 테스트하고 값을 테스트해야 하는 경우에는 `let` 절에서 쿼리를 수행한 다음 `where` 절에서 결과를 사용하는 것이 더 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-109">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c88-110">예제</span><span class="sxs-lookup"><span data-stu-id="96c88-110">Example</span></span>  
 <span data-ttu-id="96c88-111">다음 예제에서는 `p` 요소 바로 이전에 있는 모든 `ul` 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-111">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="96c88-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-112">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="96c88-113">예제</span><span class="sxs-lookup"><span data-stu-id="96c88-113">Example</span></span>  
 <span data-ttu-id="96c88-114">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="96c88-115">자세한 내용은 [네임스페이스 개요(LINQ to XML)(C#)](namespaces-overview-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96c88-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="96c88-116">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96c88-116">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="96c88-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96c88-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
