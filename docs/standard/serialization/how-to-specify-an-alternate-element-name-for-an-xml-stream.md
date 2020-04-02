---
title: '방법: XML 스트림의 대체 요소 이름 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: 2dc1110b858f639624e05382a67ddccf3ea1b047
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588462"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="efd1b-102">방법: XML 스트림의 대체 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="efd1b-102">How to: Specify an Alternate Element Name for an XML Stream</span></span>
  
<span data-ttu-id="efd1b-103"><xref:System.Xml.Serialization.XmlSerializer>를 사용하면 동일한 클래스 집합을 가진 XML 스트림을 두 개 이상 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-103">Using the <xref:System.Xml.Serialization.XmlSerializer>, you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="efd1b-104">두 개의 서로 다른 XML Web services에 약간만 다른 동일한 기본 정보가 필요한 경우 이런 작업이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-104">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="efd1b-105">예를 들어 책 주문을 처리하기 때문에 둘 모두에 ISBN 번호가 필요한 두 개의 XML Web services를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-105">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="efd1b-106">한 서비스는 \<ISBN> 태그를 사용하고 다른 서비스는 \<BookID> 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-106">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="efd1b-107">`Book`이라는 필드가 포함된 `ISBN`이라는 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-107">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="efd1b-108">`Book` 클래스의 인스턴스가 serialize될 때 기본적으로 멤버 이름(ISBN)을 태그 요소 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-108">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="efd1b-109">첫 번째 XML Web services의 경우에는 예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-109">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="efd1b-110">하지만 XML 스트림을 두 번째 XML Web services로 전송하려면 태그의 요소 이름이 `BookID`가 되도록 serialization을 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-110">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="efd1b-111">대체 요소 이름을 사용하여 XML 스트림을 만들려면</span><span class="sxs-lookup"><span data-stu-id="efd1b-111">To create an XML stream with an alternate element name</span></span>  
  
1. <span data-ttu-id="efd1b-112"><xref:System.Xml.Serialization.XmlElementAttribute> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-112">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2. <span data-ttu-id="efd1b-113"><xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>의 <xref:System.Xml.Serialization.XmlElementAttribute>을 "BookID"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-113">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3. <span data-ttu-id="efd1b-114"><xref:System.Xml.Serialization.XmlAttributes> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-114">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4. <span data-ttu-id="efd1b-115">`XmlElementAttribute`의 <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> 속성을 통해 액세스되는 컬렉션에 <xref:System.Xml.Serialization.XmlAttributes> 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-115">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5. <span data-ttu-id="efd1b-116"><xref:System.Xml.Serialization.XmlAttributeOverrides> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-116">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6. <span data-ttu-id="efd1b-117">`XmlAttributes`를 <xref:System.Xml.Serialization.XmlAttributeOverrides>에 추가하고 재정의할 개체의 형식과 재정의될 멤버의 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-117">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7. <span data-ttu-id="efd1b-118">`XmlSerializer`로 `XmlAttributeOverrides` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-118">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8. <span data-ttu-id="efd1b-119">`Book` 클래스의 인스턴스를 만들고 이를 직렬화 또는 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-119">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efd1b-120">예제</span><span class="sxs-lookup"><span data-stu-id="efd1b-120">Example</span></span>  
  
```vb  
Public Function SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public void SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 <span data-ttu-id="efd1b-121">해당 XML 스트림은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd1b-121">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="efd1b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efd1b-122">See also</span></span>

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [<span data-ttu-id="efd1b-123">XML 및 SOAP Serialization</span><span class="sxs-lookup"><span data-stu-id="efd1b-123">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="efd1b-124">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="efd1b-124">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="efd1b-125">방법: 개체 역직렬화</span><span class="sxs-lookup"><span data-stu-id="efd1b-125">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
