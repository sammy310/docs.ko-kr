---
title: 네임스페이스 접두사 제어 방법(C#)(LINQ to XML)
description: CML 트리를 C#의 LINQ to XML로 serialize할 때 네임스페이스를 제어하는 방법에 대해 알아봅니다. 경우에 따라 네임스페이스 접두사를 제어해야 합니다.
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: b0c5cbfa7488f3a7105595830ef6765e6bfb1f12
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105309"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="ba1af-104">네임스페이스 접두사 제어 방법(C#)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ba1af-104">How to control namespace prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="ba1af-105">이 항목에서는 XML 트리를 serialize할 때 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-105">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="ba1af-106">대부분의 경우에는 네임스페이스 접두사를 제어할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-106">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="ba1af-107">그러나 일부 XML 프로그래밍 도구를 사용할 때는 네임스페이스 접두사를 특수하게 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-107">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="ba1af-108">예를 들어, 특정 네임스페이스 접두사를 참조하는 포함된 XPath 식이 들어 있는 XSLT 스타일시트나 XAML 문서를 조작할 수 있습니다. 이 경우 해당 문서가 특정 접두사를 사용하여 serialize되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-108">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="ba1af-109">이는 네임스페이스 접두사를 제어해야 하는 가장 일반적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-109">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="ba1af-110">네임스페이스 접두사를 제어하는 또 다른 일반적인 경우는 사용자가 XML 문서를 수동으로 편집하도록 하고 사용자가 입력하기 편한 네임스페이스 접두사를 만들려고 할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-110">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="ba1af-111">예를 들어, XSD 문서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-111">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="ba1af-112">스키마 규칙에서는 스키마 네임스페이스의 접두사로 `xs` 또는 `xsd`를 사용하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-112">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="ba1af-113">네임스페이스 접두사를 제어하려면 네임스페이스를 선언하는 특성을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-113">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="ba1af-114">특정 접두사가 포함된 네임스페이스를 선언하는 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 serialize할 때 네임스페이스 접두사를 고려하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-114">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="ba1af-115">접두사가 포함된 네임스페이스를 선언하는 특성을 만들려면 특성 이름의 네임스페이스가 <xref:System.Xml.Linq.XNamespace.Xmlns%2A>이고 특성의 이름이 네임스페이스 접두사인 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-115">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="ba1af-116">특성 값은 네임스페이스의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-116">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba1af-117">예제</span><span class="sxs-lookup"><span data-stu-id="ba1af-117">Example</span></span>  
 <span data-ttu-id="ba1af-118">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="ba1af-118">This example declares two namespaces.</span></span> <span data-ttu-id="ba1af-119">`http://www.adventure-works.com` 네임스페이스가 `aw` 접두사를 갖고 `www.fourthcoffee.com`네임스페이스가 `fc` 접두사를 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-119">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="ba1af-120">이 예에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba1af-120">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba1af-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba1af-121">See also</span></span>

- [<span data-ttu-id="ba1af-122">네임스페이스 개요(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="ba1af-122">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
