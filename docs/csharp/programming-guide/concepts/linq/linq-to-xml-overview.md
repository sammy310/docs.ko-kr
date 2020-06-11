---
title: LINQ to XML 개요(C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: dd41d8607ef3f2e6e6be9a1f3964ef0ae937e2ac
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241840"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="f53f1-102">LINQ to XML 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="f53f1-102">LINQ to XML Overview (C#)</span></span>

<span data-ttu-id="f53f1-103">LINQ to XML에서는 .NET LINQ(Language-Integrated Query) Framework를 사용하는 메모리 내 XML 프로그래밍 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-103">LINQ to XML provides an in-memory XML programming interface that leverages the .NET Language-Integrated Query (LINQ) Framework.</span></span> <span data-ttu-id="f53f1-104">LINQ to XML은 .NET 기능을 사용하며 업데이트되고 다시 디자인된 DOM(문서 개체 모델) XML 프로그래밍 인터페이스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-104">LINQ to XML uses .NET capabilities and is comparable to an updated, redesigned Document Object Model (DOM) XML programming interface.</span></span>

<span data-ttu-id="f53f1-105">XML은 다양한 컨텍스트에서 데이터의 형식을 지정하는 방법으로 널리 채택되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-105">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="f53f1-106">예를 들어, 웹에 있는 구성 파일, Microsoft Office Word 파일 및 데이터베이스에서 XML을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-106">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="f53f1-107">은 XML을 사용한 프로그래밍을 위해 다시 디자인된 최신 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-107">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="f53f1-108">DOM(문서 개체 모델)의 메모리 내 문서 수정 기능을 제공하며 LINQ 쿼리 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-108">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports LINQ query expressions.</span></span> <span data-ttu-id="f53f1-109">이러한 쿼리 식은 구문적으로 XPath와 다르지만 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-109">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>

## <a name="linq-to-xml-developers"></a><span data-ttu-id="f53f1-110">LINQ to XML 개발자</span><span class="sxs-lookup"><span data-stu-id="f53f1-110">LINQ to XML Developers</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="f53f1-111">은 다양한 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-111">targets a variety of developers.</span></span> <span data-ttu-id="f53f1-112">특정 작업을 수행하려는 일반 개발자의 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 SQL과 유사한 쿼리 경험을 제공하므로 XML을 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-112">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="f53f1-113">프로그래머는 약간의 시간만 투자해도 원하는 프로그래밍 언어로 간결하고 강력한 쿼리를 작성하는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-113">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>

<span data-ttu-id="f53f1-114">전문 개발자는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 생산성을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-114">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="f53f1-115">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 통해 더욱 표현성이 크고 압축적이며 강력한 코드를 더 적게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-115">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="f53f1-116">이와 동시에 여러 데이터 도메인에서 쿼리 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-116">They can use query expressions from multiple data domains at the same time.</span></span>

## <a name="what-is-linq-to-xml"></a><span data-ttu-id="f53f1-117">LINQ to XML이란?</span><span class="sxs-lookup"><span data-stu-id="f53f1-117">What Is LINQ to XML?</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="f53f1-118">은 LINQ를 사용할 수 있는 메모리 내 XML 프로그래밍 인터페이스로, .NET 프로그래밍 언어에서 XML 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-118">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET programming languages.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="f53f1-119">은 XML 문서를 메모리로 가져온다는 점에서 DOM(문서 개체 모델)과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-119">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="f53f1-120">문서를 쿼리하고 수정할 수 있으며 문서를 수정한 후 파일에 저장하거나 serialize하고 네트워크를 통해 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-120">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="f53f1-121">그러나 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]는 DOM과 다릅니다. LINQ to XML은 간단하고 작업하기 쉬우며 C#의 언어 기능을 활용하는 새로운 개체 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-121">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>

<span data-ttu-id="f53f1-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 가장 중요한 이점은 LINQ(Language-Integrated Query)와 통합되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-122">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="f53f1-123">이 통합을 통해 메모리 내 XML 문서에 대한 쿼리를 작성하여 요소와 특성의 컬렉션을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-123">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="f53f1-124">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 쿼리 기능은 기능 면에서(구문 면에서는 아니지만) XPath 및 XQuery와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-124">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="f53f1-125">C#의 LINQ 통합은 더욱 강력한 형식 지정, 컴파일 시간 검사 및 개선된 디버거 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-125">The integration of LINQ in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>

<span data-ttu-id="f53f1-126">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 또 다른 이점은 쿼리 결과를 <xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XAttribute> 개체 생성자에 대한 매개 변수로 사용할 수 있다는 점입니다. 이러한 이점은 XML 트리를 만드는 강력한 방법의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-126">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="f53f1-127">개발자는 *함수 생성*이라는 이 방법을 사용하여 XML 트리의 모양을 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-127">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>

<span data-ttu-id="f53f1-128">예를 들어 [샘플 XML File: 일반적인 구매 주문(LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md)에서 설명하는 것과 같은 일반적인 XML 구매 주문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-128">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span> <span data-ttu-id="f53f1-129">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 다음 쿼리를 실행하면 구매 주문의 모든 품목 요소에 대한 부품 번호 특성 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-129">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

<span data-ttu-id="f53f1-130">이는 메서드 구문 형식으로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-130">This can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="f53f1-131">또 다른 예로, $100보다 큰 값을 가진 품목의 목록을 부품 번호 순서로 정렬하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-131">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="f53f1-132">이 정보를 얻으려면 다음 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-132">To obtain this information, you could run the following query:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

<span data-ttu-id="f53f1-133">마찬가지로 메서드 구문 형식으로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-133">Again, this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

<span data-ttu-id="f53f1-134">이러한 LINQ 기능 외에도 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 향상된 XML 프로그래밍 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-134">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="f53f1-135">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-135">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>

- <span data-ttu-id="f53f1-136">[파일](how-to-load-xml-from-a-file.md) 또는 [스트림](how-to-stream-xml-fragments-from-an-xmlreader.md)에서 XML을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-136">Load XML from [files](how-to-load-xml-from-a-file.md) or [streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span></span>

- <span data-ttu-id="f53f1-137">파일이나 스트림에서 XML을 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-137">Serialize XML to files or streams.</span></span>

- <span data-ttu-id="f53f1-138">함수 생성을 사용하여 XML을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-138">Create XML from scratch by using functional construction.</span></span>

- <span data-ttu-id="f53f1-139">XPath와 같은 축을 사용하여 XML을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-139">Query XML using XPath-like axes.</span></span>

- <span data-ttu-id="f53f1-140"><xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 및 <xref:System.Xml.Linq.XElement.SetValue%2A>와 같은 메서드를 사용하여 메모리 내 XML 트리를 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-140">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>

- <span data-ttu-id="f53f1-141">XSD를 사용하여 XML 트리의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-141">Validate XML trees using XSD.</span></span>

- <span data-ttu-id="f53f1-142">이러한 기능을 함께 사용하여 XML 트리의 모양을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-142">Use a combination of these features to transform XML trees from one shape into another.</span></span>

## <a name="creating-xml-trees"></a><span data-ttu-id="f53f1-143">XML 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="f53f1-143">Creating XML Trees</span></span>

<span data-ttu-id="f53f1-144">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용하여 프로그래밍하는 경우의 가장 중요한 이점 중 하나는 XML 트리를 쉽게 만들 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-144">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="f53f1-145">예를 들어 작은 XML 트리를 만들려면 다음과 같이 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f53f1-145">For example, to create a small XML tree, you can write code as follows:</span></span>

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

<span data-ttu-id="f53f1-146">자세한 내용은 [XML 트리 만들기(C#)](./creating-xml-trees-linq-to-xml-2.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f53f1-146">For more information, see [Creating XML Trees (C#)](./creating-xml-trees-linq-to-xml-2.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f53f1-147">참조</span><span class="sxs-lookup"><span data-stu-id="f53f1-147">See also</span></span>

- [<span data-ttu-id="f53f1-148">참조(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="f53f1-148">Reference (LINQ to XML)</span></span>](./reference-linq-to-xml.md)
- [<span data-ttu-id="f53f1-149">LINQ to XML과 DOM 비교(C#)</span><span class="sxs-lookup"><span data-stu-id="f53f1-149">LINQ to XML vs. DOM (C#)</span></span>](./linq-to-xml-vs-dom.md)
- [<span data-ttu-id="f53f1-150">LINQ to XML과 기타 XML 기술 비교</span><span class="sxs-lookup"><span data-stu-id="f53f1-150">LINQ to XML vs. Other XML Technologies</span></span>](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
