---
title: '방법: XmlReader에서 트리 만들기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: c90fbee29a380824cdc32dd62622e55ea40044fd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583022"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="a0bb4-102">방법: XmlReader에서 트리 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0bb4-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>

<span data-ttu-id="a0bb4-103">이 항목에서는 <xref:System.Xml.XmlReader>에서 XML 트리를 직접 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="a0bb4-104"><xref:System.Xml.Linq.XElement>에서 <xref:System.Xml.XmlReader>를 만들려면 요소 노드에 <xref:System.Xml.XmlReader>를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="a0bb4-105"><xref:System.Xml.XmlReader>는 주석과 처리 명령을 건너뛰지만 <xref:System.Xml.XmlReader>가 텍스트 노드에 배치되면 오류가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="a0bb4-106">이러한 오류를 방지하려면 <xref:System.Xml.XmlReader>에서 XML 트리를 만들기 전에 항상 <xref:System.Xml.XmlReader>를 요소에 배치하세요.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>

## <a name="example"></a><span data-ttu-id="a0bb4-107">예제</span><span class="sxs-lookup"><span data-stu-id="a0bb4-107">Example</span></span>

<span data-ttu-id="a0bb4-108">이 예제에서는 XML 문서 [샘플 XML 파일: Books(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>

<span data-ttu-id="a0bb4-109">다음 코드에서는 `T:System.Xml.XmlReader` 개체를 만들고 첫 번째 요소 노드를 찾을 때까지 노드를 읽은 다음</span><span class="sxs-lookup"><span data-stu-id="a0bb4-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="a0bb4-110"><xref:System.Xml.Linq.XElement> 개체를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

<span data-ttu-id="a0bb4-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bb4-111">This example produces the following output:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a0bb4-112">참조</span><span class="sxs-lookup"><span data-stu-id="a0bb4-112">See also</span></span>

- [<span data-ttu-id="a0bb4-113">XML 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0bb4-113">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
