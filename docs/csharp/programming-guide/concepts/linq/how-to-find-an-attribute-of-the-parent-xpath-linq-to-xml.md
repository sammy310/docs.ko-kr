---
title: 부모의 특성을 찾는 방법(XPath-LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: bfe7554a5c767adde5e7170c8e1ea0537155f6df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141169"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="4c942-102">부모의 특성을 찾는 방법(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="4c942-102">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="4c942-103">이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c942-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="4c942-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4c942-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="4c942-105">예제</span><span class="sxs-lookup"><span data-stu-id="4c942-105">Example</span></span>

<span data-ttu-id="4c942-106">이 예제에서는 먼저 `Author` 요소를 찾은 다음</span><span class="sxs-lookup"><span data-stu-id="4c942-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="4c942-107">부모 요소의 `id` 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4c942-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="4c942-108">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](./sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c942-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="4c942-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c942-109">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
