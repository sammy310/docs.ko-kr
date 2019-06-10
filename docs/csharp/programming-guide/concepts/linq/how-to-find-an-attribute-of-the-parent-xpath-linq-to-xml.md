---
title: '방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: f30c810483d8253132b9fe3e0959d04a8b4d26a0
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690065"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>방법: 부모의 특성 찾기(XPath-LINQ to XML)(C#)

이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.

XPath 식은 다음과 같습니다.

`../@id`

## <a name="example"></a>예제

이 예제에서는 먼저 `Author` 요소를 찾은 다음 부모 요소의 `id` 특성을 찾습니다.

이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).

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

이 예제는 다음과 같은 출력을 생성합니다.

```
Results are identical
id="bk101"
```
