---
title: C#에서 기본 네임스페이스 범위1
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: d60f489f616a413e25bf5cd427bd467852a97c7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379447"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="88054-102">C\#에서 기본 네임스페이스 범위</span><span class="sxs-lookup"><span data-stu-id="88054-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="88054-103">XML 트리에 나타나는 기본 네임스페이스는 쿼리에 범위에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88054-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="88054-104">기본 네임스페이스에 있는 XML을 사용하는 경우 <xref:System.Xml.Linq.XNamespace> 변수를 선언하고 로컬 이름과 결합하여 쿼리에서 사용할 정규화된 이름을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88054-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="88054-105">XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88054-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="88054-106">이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되지만 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88054-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="88054-107">두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88054-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88054-108">예제</span><span class="sxs-lookup"><span data-stu-id="88054-108">Example</span></span>  
 <span data-ttu-id="88054-109">이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88054-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88054-110">코드</span><span class="sxs-lookup"><span data-stu-id="88054-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="88054-111">설명</span><span class="sxs-lookup"><span data-stu-id="88054-111">Comments</span></span>  
 <span data-ttu-id="88054-112">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88054-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="88054-113">예제</span><span class="sxs-lookup"><span data-stu-id="88054-113">Example</span></span>  
 <span data-ttu-id="88054-114">이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88054-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="88054-115">위의 잘못 코딩된 예제와 달리 C#을 사용하는 경우의 올바른 방법은 <xref:System.Xml.Linq.XNamespace> 개체를 선언하고 초기화하여 <xref:System.Xml.Linq.XName> 개체를 지정할 때 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88054-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="88054-116">이 경우 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드의 인수는 <xref:System.Xml.Linq.XName> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="88054-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88054-117">코드</span><span class="sxs-lookup"><span data-stu-id="88054-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="88054-118">설명</span><span class="sxs-lookup"><span data-stu-id="88054-118">Comments</span></span>  
 <span data-ttu-id="88054-119">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88054-119">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="88054-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88054-120">See also</span></span>

- [<span data-ttu-id="88054-121">XML 네임스페이스 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="88054-121">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
