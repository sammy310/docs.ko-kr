---
title: XML 요소 및 XML 특성 이름을 한정하는 방법
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: db0795dd83cc96aba49dd435c875e98a9a6c18cb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159873"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="9a298-102">XML 요소 및 XML 특성 이름을 한정하는 방법</span><span class="sxs-lookup"><span data-stu-id="9a298-102">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="9a298-103">클래스의 인스턴스에 의해 포함된 XML 네임스페이스는 <xref:System.Xml.Serialization.XmlSerializerNamespaces>[Namespaces in XML](https://www.w3.org/TR/REC-xml-names/)이라는 W3C(World Wide Web 컨소시엄) 사양을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="9a298-104">XML 네임스페이스는 XML 문서에서 XML 요소 및 XML 특성의 이름을 정규화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="9a298-105">정규화된 이름은 콜론으로 구분된 접두사와 로컬 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="9a298-106">접두사는 자리 표시자로만 기능하여 네임스페이스를 지정하는 URI에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="9a298-107">보편적으로 관리되는 URI 네임스페이스와 로컬 이름을 조합하면 보편적으로 고유한 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="9a298-108">`XmlSerializerNamespaces`의 인스턴스를 만들고 네임스페이스 쌍을 개체에 추가하면 XML 문서에 사용되는 접두사를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="9a298-109">XML 문서에서 정규화된 이름을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9a298-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="9a298-110">`XmlSerializerNamespaces` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="9a298-111">모든 접두사와 네임스페이스 쌍을 `XmlSerializerNamespaces`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="9a298-112">적절한 `System.Xml.Serialization` 특성을 <xref:System.Xml.Serialization.XmlSerializer>가 XML 문서로 serialize할 각 멤버나 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="9a298-113">사용할 수 있는 특성은 <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> 및 <xref:System.Xml.Serialization.XmlTypeAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="9a298-114">각 특성의 `Namespace` 속성을 `XmlSerializerNamespaces`의 네임스페이스 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="9a298-115">`XmlSerializerNamespaces`를 `XmlSerializer`의 `Serialize` 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="9a298-116">예제</span><span class="sxs-lookup"><span data-stu-id="9a298-116">Example</span></span>

<span data-ttu-id="9a298-117">다음 예제에서는 `XmlSerializerNamespaces`를 만들고 두 개의 접두사와 네임스페이스 쌍을 개체에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="9a298-118">코드에서는 `XmlSerializer` 클래스의 인스턴스를 serialize하는 데 사용되는 `Books`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="9a298-119">코드는 `Serialize`를 사용하여 `XmlSerializerNamespaces` 메서드를 호출하여 XML이 접두사가 지정된 네임스페이스를 포함할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a298-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book
    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }

    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a><span data-ttu-id="9a298-120">참조</span><span class="sxs-lookup"><span data-stu-id="9a298-120">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="9a298-121">XML 스키마 정의 도구 및 XML serialization</span><span class="sxs-lookup"><span data-stu-id="9a298-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="9a298-122">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="9a298-122">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="9a298-123">XmlSerializer 클래스</span><span class="sxs-lookup"><span data-stu-id="9a298-123">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="9a298-124">XML serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="9a298-124">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="9a298-125">방법: XML 스트림의 대체 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="9a298-125">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="9a298-126">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="9a298-126">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="9a298-127">방법: 개체 역직렬화</span><span class="sxs-lookup"><span data-stu-id="9a298-127">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
