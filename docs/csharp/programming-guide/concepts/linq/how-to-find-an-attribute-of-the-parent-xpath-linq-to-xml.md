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
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>부모의 특성을 찾는 방법(XPath-LINQ to XML)(C#)

이 항목에서는 부모 요소를 탐색하고 부모 요소의 특성을 찾는 방법을 보여 줍니다.

XPath 식은 다음과 같습니다.

`../@id`

## <a name="example"></a>예제

이 예제에서는 먼저 `Author` 요소를 찾은 다음 부모 요소의 `id` 특성을 찾습니다.

이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).

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

```output
Results are identical
id="bk101"
```
