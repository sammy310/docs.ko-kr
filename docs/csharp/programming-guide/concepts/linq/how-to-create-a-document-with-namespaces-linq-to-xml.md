---
title: 네임스페이스로 문서 만드는 방법(C#)(LINQ to XML)
description: 네임스페이스를 로컬 이름과 결합하기 위해 XNamespace 개체를 사용하여 C#에서 LINQ to XML의 네임스페이스가 있는 문서를 만드는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 6472baefc73285af1c6dca0bfe7d874003940fc4
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103389"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="cbc1f-103">네임스페이스로 문서 만드는 방법(C#)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cbc1f-103">How to create a document with namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="cbc1f-104">이 항목에서는 네임스페이스를 사용하여 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-104">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc1f-105">예제</span><span class="sxs-lookup"><span data-stu-id="cbc1f-105">Example</span></span>  
 <span data-ttu-id="cbc1f-106">네임스페이스에 포함되는 요소나 특성을 만들려면 먼저 <xref:System.Xml.Linq.XNamespace> 개체를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-106">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="cbc1f-107">그런 다음 추가 연산자 오버로드를 사용하여 네임스페이스를 문자열로 표현된 로컬 이름과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-107">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="cbc1f-108">다음 예제에서는 네임스페이스가 하나 포함된 문서를 만들고</span><span class="sxs-lookup"><span data-stu-id="cbc1f-108">The following example creates a document with one namespace.</span></span> <span data-ttu-id="cbc1f-109">기본적으로 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]은 기본 네임스페이스를 사용하여 이 문서를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-109">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="cbc1f-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-110">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="cbc1f-111">예제</span><span class="sxs-lookup"><span data-stu-id="cbc1f-111">Example</span></span>  
 <span data-ttu-id="cbc1f-112">다음 예제에서는 네임스페이스가 하나 포함된 문서를 만들고</span><span class="sxs-lookup"><span data-stu-id="cbc1f-112">The following example creates a document with one namespace.</span></span> <span data-ttu-id="cbc1f-113">네임스페이스 접두사가 포함된 네임스페이스를 선언하는 특성도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-113">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="cbc1f-114">접두사가 포함된 네임스페이스를 선언하는 특성을 만들려면 특성 이름이 네임스페이스 접두사이고 이 이름이 <xref:System.Xml.Linq.XNamespace.Xmlns%2A> 네임스페이스에 포함되는 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-114">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="cbc1f-115">이 특성의 값은 네임스페이스의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-115">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="cbc1f-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="cbc1f-117">예제</span><span class="sxs-lookup"><span data-stu-id="cbc1f-117">Example</span></span>  
 <span data-ttu-id="cbc1f-118">다음 예제에서는 두 네임스페이스가 포함된 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-118">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="cbc1f-119">두 네임스페이스 중 하나는 기본 네임스페이스이고</span><span class="sxs-lookup"><span data-stu-id="cbc1f-119">One is the default namespace.</span></span> <span data-ttu-id="cbc1f-120">다른 하나는 접두사가 포함된 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-120">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="cbc1f-121">루트 요소에 네임스페이스 특성을 포함하면 `http://www.adventure-works.com`이 기본 네임스페이스가 되도록 네임스페이스가 serialize되고 `www.fourthcoffee.com`이 "fc"의 접두사를 사용하여 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-121">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="cbc1f-122">기본 네임스페이스를 선언하는 특성을 만들려면 네임스페이스 없이 이름이 "xmlns"인 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-122">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="cbc1f-123">특성 값은 기본 네임스페이스 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-123">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="cbc1f-124">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="cbc1f-125">예제</span><span class="sxs-lookup"><span data-stu-id="cbc1f-125">Example</span></span>  
 <span data-ttu-id="cbc1f-126">다음 예제에서는 네임스페이스 접두사가 있는 두 가지 네임스페이스가 포함된 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-126">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="cbc1f-127">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-127">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="cbc1f-128">예제</span><span class="sxs-lookup"><span data-stu-id="cbc1f-128">Example</span></span>  
 <span data-ttu-id="cbc1f-129">동일한 결과를 얻는 또 다른 방법은 <xref:System.Xml.Linq.XNamespace> 개체를 선언하고 만드는 대신 확장된 이름을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-129">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="cbc1f-130">이 방법에는 성능과 관련된 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-130">This approach has performance implications.</span></span> <span data-ttu-id="cbc1f-131">확장된 이름이 포함된 문자열을 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에 전달할 때마다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 이름을 구문 분석하고 원자화된 네임스페이스를 찾은 다음 원자화된 이름을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-131">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="cbc1f-132">이 과정에는 CPU 시간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-132">This process takes CPU time.</span></span> <span data-ttu-id="cbc1f-133">성능이 중요한 경우에는 <xref:System.Xml.Linq.XNamespace> 개체를 명시적으로 선언하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-133">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="cbc1f-134">성능이 중요한 경우 자세한 내용을 보려면 [XName 개체의 사전 원자화(LINQ to XML)(C#)](./pre-atomization-of-xname-objects-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-134">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="cbc1f-135">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc1f-135">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbc1f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbc1f-136">See also</span></span>

- [<span data-ttu-id="cbc1f-137">네임스페이스 개요(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="cbc1f-137">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
