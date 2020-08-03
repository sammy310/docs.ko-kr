---
title: 파일에서 XML을 로드하는 방법(C#)
description: C#에서 XElement.Load 메서드를 사용하여 URI에서 XML을 로드하는 방법을 보여줍니다. 이 예제에서는 XML 파일을 로드하고 XML 트리를 콘솔에 인쇄합니다.
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: 29de914139d1e9abcda2097addca9219d44d2696
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104951"
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="c74aa-104">파일에서 XML을 로드하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c74aa-104">How to load XML from a file (C#)</span></span>
<span data-ttu-id="c74aa-105">이 항목에서는 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 메서드를 사용하여 URI에서 XML을 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c74aa-105">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c74aa-106">예제</span><span class="sxs-lookup"><span data-stu-id="c74aa-106">Example</span></span>  
 <span data-ttu-id="c74aa-107">다음 예제에서는 파일에서 XML 문서를 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c74aa-107">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="c74aa-108">다음 예제에서는 books.xml을 로드하고 XML 트리를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c74aa-108">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="c74aa-109">이 예제에서는 XML 문서로을 사용합니다. [샘플 XML 파일: Books(LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c74aa-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="c74aa-110">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c74aa-110">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
  <Book id="bk101">  
    <Author>Garghentini, Davide</Author>  
    <Title>XML Developer's Guide</Title>  
    <Genre>Computer</Genre>  
    <Price>44.95</Price>  
    <PublishDate>2000-10-01</PublishDate>  
    <Description>An in-depth look at creating applications
      with XML.</Description>  
  </Book>  
  <Book id="bk102">  
    <Author>Garcia, Debra</Author>  
    <Title>Midnight Rain</Title>  
    <Genre>Fantasy</Genre>  
    <Price>5.95</Price>  
    <PublishDate>2000-12-16</PublishDate>  
    <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>  
  </Book>  
</Catalog>  
```  
  