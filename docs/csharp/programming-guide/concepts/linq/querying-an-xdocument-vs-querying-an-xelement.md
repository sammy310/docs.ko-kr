---
title: XDocument 쿼리와 XElement 쿼리 비교(C#)
description: XDocument 쿼리와 XElement 쿼리의 차이점을 알아봅니다. 이러한 차이점을 보여 주는 코드 예제를 검토합니다.
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 0c81768f06148308a639f96f4041e464b24edd33
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300321"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="2c95c-104">XDocument 쿼리와 XElement 쿼리 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="2c95c-104">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="2c95c-105"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>를 통해 문서를 로드하는 경우에는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>를 통해 로드하는 경우와 약간 다르게 쿼리를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-105">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="2c95c-106">XDocument.Load와 XElement.Load의 비교</span><span class="sxs-lookup"><span data-stu-id="2c95c-106">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="2c95c-107"><xref:System.Xml.Linq.XElement>를 통해 XML 문서를 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>에 로드하면 XML 트리의 루트에 있는 <xref:System.Xml.Linq.XElement>에 로드된 문서의 루트 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-107">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="2c95c-108">그러나 <xref:System.Xml.Linq.XDocument>를 통해 동일한 XML 문서를 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>에 로드하면 트리의 루트가 <xref:System.Xml.Linq.XDocument> 노드이고 로드된 문서의 루트 요소가 <xref:System.Xml.Linq.XElement>의 허용된 하나의 자식 <xref:System.Xml.Linq.XDocument> 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-108">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="2c95c-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 축은 루트 노드와 상대적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-109">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="2c95c-110">이 첫 번째 예제에서는 <xref:System.Xml.Linq.XElement.Load%2A>를 사용하여 XML 트리를 로드한 다음</span><span class="sxs-lookup"><span data-stu-id="2c95c-110">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="2c95c-111">트리 루트의 자식 요소에 대해 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-111">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="2c95c-112">예상대로 이 예제는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-112">As expected, this example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="2c95c-113">다음 예제는 XML 트리가 <xref:System.Xml.Linq.XDocument> 대신 <xref:System.Xml.Linq.XElement>에 로드되는 점을 제외하고 위의 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-113">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="2c95c-114">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-114">This example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="2c95c-115">동일한 쿼리에서 세 자식 노드 대신 하나의 `Root` 노드를 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-115">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="2c95c-116">이를 처리하는 한 가지 방법은 축 메서드에 액세스하기 전에 다음과 같이 <xref:System.Xml.Linq.XDocument.Root%2A> 속성을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-116">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="2c95c-117">이 쿼리는 이제 <xref:System.Xml.Linq.XElement>에서 시작하는 트리에 대한 쿼리와 동일한 방식으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-117">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="2c95c-118">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c95c-118">The example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  