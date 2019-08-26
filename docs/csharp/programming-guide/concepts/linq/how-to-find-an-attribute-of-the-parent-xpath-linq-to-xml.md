---
title: '방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 2e6c124d2653fb4426b3abb693f0b58daa5413c2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593619"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="3ccaf-102">방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="3ccaf-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="3ccaf-103">이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ccaf-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="3ccaf-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccaf-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="3ccaf-105">예</span><span class="sxs-lookup"><span data-stu-id="3ccaf-105">Example</span></span>

<span data-ttu-id="3ccaf-106">이 예제에서는 먼저 `Author` 요소를 찾은 다음</span><span class="sxs-lookup"><span data-stu-id="3ccaf-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="3ccaf-107">부모 요소의 `id` 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3ccaf-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="3ccaf-108">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3ccaf-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="3ccaf-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ccaf-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
