---
title: 부모의 특성을 찾는 방법(XPath-LINQ to XML)(C#)
description: 부모 요소의 특성을 찾는 방법을 알아봅니다. 샘플 XML 파일을 사용하는 코드 예제를 살펴봅니다.
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303298"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="cecb9-104">부모의 특성을 찾는 방법(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="cecb9-104">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="cecb9-105">이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cecb9-105">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="cecb9-106">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cecb9-106">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="cecb9-107">예제</span><span class="sxs-lookup"><span data-stu-id="cecb9-107">Example</span></span>

<span data-ttu-id="cecb9-108">이 예제에서는 먼저 `Author` 요소를 찾은 다음</span><span class="sxs-lookup"><span data-stu-id="cecb9-108">This example first finds an `Author` element.</span></span> <span data-ttu-id="cecb9-109">부모 요소의 `id` 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cecb9-109">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="cecb9-110">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cecb9-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="cecb9-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cecb9-111">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
