---
title: '방법: 인코딩된 문서 읽기 및 쓰기 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
ms.openlocfilehash: 02311a572afac427329b051251639a10d2e7f5f8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582809"
---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a><span data-ttu-id="8a157-102">방법: 인코딩된 문서 읽기 및 쓰기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a157-102">How to: Read and Write an Encoded Document (Visual Basic)</span></span>

<span data-ttu-id="8a157-103">인코딩된 XML 문서를 만들려면 <xref:System.Xml.Linq.XDeclaration>을 XML 트리에 추가하여 인코딩을 원하는 코드 페이지 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>

<span data-ttu-id="8a157-104"><xref:System.Text.Encoding.WebName%2A>에서 반환하는 모든 값은 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>

<span data-ttu-id="8a157-105">인코딩된 문서를 읽는 경우 <xref:System.Xml.Linq.XDeclaration.Encoding%2A> 속성이 코드 페이지 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>

<span data-ttu-id="8a157-106"><xref:System.Xml.Linq.XDeclaration.Encoding%2A>을 유효한 코드 페이지 이름으로 설정하는 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 지정된 인코딩을 사용하여 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>

## <a name="example"></a><span data-ttu-id="8a157-107">예제</span><span class="sxs-lookup"><span data-stu-id="8a157-107">Example</span></span>

<span data-ttu-id="8a157-108">다음 예제에서는 UTF-8 인코딩을 사용하여 문서를 하나 만들고 UTF-16 인코딩을 사용하여 문서를 하나 만든 다음</span><span class="sxs-lookup"><span data-stu-id="8a157-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="8a157-109">그런 다음 문서를 로드하고 인코딩을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-109">It then loads the documents and prints the encoding to the console.</span></span>

```vb
Console.WriteLine("Creating a document with utf-8 encoding")
Dim encodedDoc8 As XDocument = _
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>
        <Root>Content</Root>

encodedDoc8.Save("EncodedUtf8.xml")
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)
Console.WriteLine()

Console.WriteLine("Creating a document with utf-16 encoding")
Dim encodedDoc16 As XDocument = _
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>
        <Root>Content</Root>

encodedDoc16.Save("EncodedUtf16.xml")
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)
Console.WriteLine()

Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")
Console.WriteLine("Encoded document:")
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))
Console.WriteLine()
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)
Console.WriteLine()

Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")
Console.WriteLine("Encoded document:")
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))
Console.WriteLine()
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)
```

<span data-ttu-id="8a157-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-110">This example produces the following output:</span></span>

```console
Creating a document with utf-8 encoding
Encoding is:utf-8

Creating a document with utf-16 encoding
Encoding is:utf-16

Encoded document:
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Root>Content</Root>

Encoding of loaded document is:utf-8

Encoded document:
<?xml version="1.0" encoding="utf-16" standalone="yes"?>
<Root>Content</Root>

Encoding of loaded document is:utf-16
```

## <a name="see-also"></a><span data-ttu-id="8a157-111">참조</span><span class="sxs-lookup"><span data-stu-id="8a157-111">See also</span></span>

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8a157-112">Visual Basic (Advanced LINQ to XML 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="8a157-112">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
