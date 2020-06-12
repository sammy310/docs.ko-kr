---
title: 특성을 사용하여 XML Serialization 제어
description: 특성을 사용하여 개체의 XML serialization을 제어하거나 동일한 클래스 집합에서 대체 XML 스트림을 만들 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: 79c5541b4c384e91fbec8c8f1b2130887e79a252
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289683"
---
# <a name="controlling-xml-serialization-using-attributes"></a><span data-ttu-id="c3a3e-103">특성을 사용하여 XML Serialization 제어</span><span class="sxs-lookup"><span data-stu-id="c3a3e-103">Controlling XML Serialization Using Attributes</span></span>

<span data-ttu-id="c3a3e-104">특성을 사용하여 개체의 XML serialization을 제어하거나 동일한 클래스 집합에서 대체 XML 스트림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-104">Attributes can be used to control the XML serialization of an object or to create an alternate XML stream from the same set of classes.</span></span> <span data-ttu-id="c3a3e-105">대체 XML 스트림 만들기에 대한 자세한 내용은 [방법: XML 스트림의 대체 요소 이름 지정](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-105">For more details about creating an alternate XML stream, see [How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c3a3e-106">생성된 XML이 World Wide Web 컨소시엄(W3C) 문서 [SOAP(Simple Object Access Protocol) 1.1](attributes-that-control-encoded-soap-serialization.md)의 5단원을 따르도록 하려면 [인코딩된 SOAP Serialization을 제어하는 특성](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)에 나열된 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-106">If the XML generated must conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), use the attributes listed in [Attributes That Control Encoded SOAP Serialization](attributes-that-control-encoded-soap-serialization.md).</span></span>

<span data-ttu-id="c3a3e-107">기본적으로 XML 요소 이름은 클래스 또는 멤버 이름으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-107">By default, an XML element name is determined by the class or member name.</span></span> <span data-ttu-id="c3a3e-108">`Book`이라는 간단한 클래스의 경우 이름이 `ISBN`인 필드는 다음 예제처럼 XML 요소 태그 \<ISBN>을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-108">In a simple class named `Book`, a field named `ISBN` will produce an XML element tag \<ISBN>, as shown in the following example.</span></span>

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

<span data-ttu-id="c3a3e-109">요소에 새 이름을 지정하려면 이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-109">This default behavior can be changed if you want to give the element a new name.</span></span> <span data-ttu-id="c3a3e-110">다음 코드에서는 <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A>의 <xref:System.Xml.Serialization.XmlElementAttribute> 속성을 설정하여 특성을 통해 기본 동작을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-110">The following code shows how an attribute enables this by setting the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> property of a <xref:System.Xml.Serialization.XmlElementAttribute>.</span></span>

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

<span data-ttu-id="c3a3e-111">특성에 대한 자세한 내용은 [특성](../attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-111">For more information about attributes, see [Attributes](../attributes/index.md).</span></span> <span data-ttu-id="c3a3e-112">XML serialization을 제어하는 특성의 목록은 [XML Serialization을 제어하는 특성](attributes-that-control-xml-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-112">For a list of attributes that control XML serialization, see [Attributes That Control XML Serialization](attributes-that-control-xml-serialization.md).</span></span>

## <a name="controlling-array-serialization"></a><span data-ttu-id="c3a3e-113">배열 serialization 제어</span><span class="sxs-lookup"><span data-stu-id="c3a3e-113">Controlling Array Serialization</span></span>

<span data-ttu-id="c3a3e-114"><xref:System.Xml.Serialization.XmlArrayAttribute> 및 <xref:System.Xml.Serialization.XmlArrayItemAttribute> 특성은 배열의 serialization을 제어하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-114">The <xref:System.Xml.Serialization.XmlArrayAttribute> and the <xref:System.Xml.Serialization.XmlArrayItemAttribute> attributes are designed to control the serialization of arrays.</span></span> <span data-ttu-id="c3a3e-115">이러한 특성을 사용하여 요소 이름, 네임스페이스 및 XML 스키마(XSD) 데이터 유형을 제어할 수 있습니다(World Wide Web 컨소시엄[www.w3.org] 문서 "XML Schema Part 2: Datatypes"에 정의된 대로).</span><span class="sxs-lookup"><span data-stu-id="c3a3e-115">Using these attributes, you can control the element name, namespace, and XML Schema (XSD) data type (as defined in the World Wide Web Consortium [www.w3.org] document titled "XML Schema Part 2: Datatypes").</span></span> <span data-ttu-id="c3a3e-116">또한 배열에 포함될 수 있는 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-116">You can also specify the types that can be included in an array.</span></span>

<span data-ttu-id="c3a3e-117"><xref:System.Xml.Serialization.XmlArrayAttribute>는 배열이 serialize될 때 발생하는 바깥쪽 XML 요소의 속성을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-117">The <xref:System.Xml.Serialization.XmlArrayAttribute> will determine the properties of the enclosing XML element that results when an array is serialized.</span></span> <span data-ttu-id="c3a3e-118">예를 들어 기본적으로 아래 배열을 serialize하면 `Employees`라는 이름의 XML 요소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-118">For example, by default, serializing the array below will result in an XML element named `Employees`.</span></span> <span data-ttu-id="c3a3e-119">`Employees` 요소에는 배열 형식 `Employee`를 따라 이름이 지정된 일련의 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-119">The `Employees` element will contain a series of elements named after the array type `Employee`.</span></span>

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

<span data-ttu-id="c3a3e-120">serialize된 인스턴스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-120">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

<span data-ttu-id="c3a3e-121"><xref:System.Xml.Serialization.XmlArrayAttribute>를 적용하여 다음과 같이 XML 요소의 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-121">By applying a <xref:System.Xml.Serialization.XmlArrayAttribute>, you can change the name of the XML element, as follows.</span></span>

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

<span data-ttu-id="c3a3e-122">결과 XML은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-122">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<span data-ttu-id="c3a3e-123">반면 <xref:System.Xml.Serialization.XmlArrayItemAttribute>는 배열에 포함된 항목을 serialize하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-123">The <xref:System.Xml.Serialization.XmlArrayItemAttribute>, on the other hand, controls how the items contained in the array are serialized.</span></span> <span data-ttu-id="c3a3e-124">특성은 배열을 반환하는 필드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-124">Note that the attribute is applied to the field returning the array.</span></span>

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

<span data-ttu-id="c3a3e-125">결과 XML은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-125">The resulting XML might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a><span data-ttu-id="c3a3e-126">파생 클래스 serialize</span><span class="sxs-lookup"><span data-stu-id="c3a3e-126">Serializing Derived Classes</span></span>

<span data-ttu-id="c3a3e-127"><xref:System.Xml.Serialization.XmlArrayItemAttribute>의 다른 용도는 파생 클래스의 serialize를 가능하게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-127">Another use of the <xref:System.Xml.Serialization.XmlArrayItemAttribute> is to allow the serialization of derived classes.</span></span> <span data-ttu-id="c3a3e-128">예를 들어 `Manager`에서 파생되는 `Employee`라는 다른 클래스를 이전 예제에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-128">For example, another class named `Manager` that derives from `Employee` can be added to the previous example.</span></span> <span data-ttu-id="c3a3e-129"><xref:System.Xml.Serialization.XmlArrayItemAttribute>를 적용하지 않으면 파생된 클래스 형식이 인식되지 않기 때문에 코드는 런타임에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-129">If you do not apply the <xref:System.Xml.Serialization.XmlArrayItemAttribute>, the code will fail at run time because the derived class type will not be recognized.</span></span> <span data-ttu-id="c3a3e-130">이를 해결하려면 사용 가능한 각 형식(기본 및 파생)에 대해 <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> 속성을 설정할 때마다 특성을 적용하여 두 번 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-130">To remedy this, apply the attribute twice, each time setting the <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> property for each acceptable type (base and derived).</span></span>

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

<span data-ttu-id="c3a3e-131">serialize된 인스턴스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-131">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a><span data-ttu-id="c3a3e-132">배열을 요소 시퀀스로 serialize</span><span class="sxs-lookup"><span data-stu-id="c3a3e-132">Serializing an Array as a Sequence of Elements</span></span>

<span data-ttu-id="c3a3e-133">다음과 같이 배열을 반환하는 필드에 <xref:System.Xml.Serialization.XmlElementAttribute>를 적용하여 배열을 XML 요소의 평면 시퀀스로 serialize할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-133">You can also serialize an array as a flat sequence of XML elements by applying a <xref:System.Xml.Serialization.XmlElementAttribute> to the field returning the array as follows.</span></span>

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

<span data-ttu-id="c3a3e-134">serialize된 인스턴스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-134">A serialized instance might resemble the following.</span></span>

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

<span data-ttu-id="c3a3e-135">두 XML 스트림을 구분하는 다른 방법은 XML 스키마 정의 도구를 사용하여 컴파일된 코드에서 XML 스키마(XSD) 문서를 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-135">Another way to differentiate the two XML streams is to use the XML Schema Definition tool to generate the XML Schema (XSD) document files from the compiled code.</span></span> <span data-ttu-id="c3a3e-136">도구 사용에 대한 자세한 내용은 [XML 스키마 정의 도구 및 XML serialization](the-xml-schema-definition-tool-and-xml-serialization.md)을 참조하세요. 필드에 특성이 적용되지 않은 경우 스키마는 다음 방식으로 요소를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-136">(For more details on using the tool, see [The XML Schema Definition Tool and XML Serialization](the-xml-schema-definition-tool-and-xml-serialization.md).) When no attribute is applied to the field, the schema describes the element in the following manner.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

<span data-ttu-id="c3a3e-137"><xref:System.Xml.Serialization.XmlElementAttribute>가 필드에 적용되는 경우 결과 스키마는 다음과 같이 요소를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-137">When the <xref:System.Xml.Serialization.XmlElementAttribute> is applied to the field, the resulting schema describes the element as follows.</span></span>

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a><span data-ttu-id="c3a3e-138">ArrayList serialize</span><span class="sxs-lookup"><span data-stu-id="c3a3e-138">Serializing an ArrayList</span></span>

<span data-ttu-id="c3a3e-139"><xref:System.Collections.ArrayList> 클래스에는 다양한 개체의 컬렉션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-139">The <xref:System.Collections.ArrayList> class can contain a collection of diverse objects.</span></span> <span data-ttu-id="c3a3e-140">따라서 <xref:System.Collections.ArrayList>는 배열을 사용할 때 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-140">You can therefore use a <xref:System.Collections.ArrayList> much as you use an array.</span></span> <span data-ttu-id="c3a3e-141">하지만 형식화된 개체의 배열을 반환하는 필드를 만드는 대신 단일 <xref:System.Collections.ArrayList>를 반환하는 필드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-141">Instead of creating a field that returns an array of typed objects, however, you can create a field that returns a single <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="c3a3e-142">하지만 배열과 마찬가지로 <xref:System.Xml.Serialization.XmlSerializer>에 포함된 개체 형식을 <xref:System.Collections.ArrayList>에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-142">However, as with arrays, you must inform the <xref:System.Xml.Serialization.XmlSerializer> of the types of objects the <xref:System.Collections.ArrayList> contains.</span></span> <span data-ttu-id="c3a3e-143">이렇게 하려면 다음 예제처럼 <xref:System.Xml.Serialization.XmlElementAttribute>의 여러 인스턴스를 필드에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-143">To accomplish this, assign multiple instances of the <xref:System.Xml.Serialization.XmlElementAttribute> to the field, as shown in the following example.</span></span>

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a><span data-ttu-id="c3a3e-144">XmlRootAttribute 및 XmlTypeAttribute를 사용하여 클래스의 serialization 제어</span><span class="sxs-lookup"><span data-stu-id="c3a3e-144">Controlling Serialization of Classes Using XmlRootAttribute and XmlTypeAttribute</span></span>

<span data-ttu-id="c3a3e-145">클래스에 적용할 수 있는(클래스에만 적용 가능) <xref:System.Xml.Serialization.XmlRootAttribute> 및 <xref:System.Xml.Serialization.XmlTypeAttribute>의 두 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-145">There are two attributes that can be applied to a class (and only a class): <xref:System.Xml.Serialization.XmlRootAttribute> and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span> <span data-ttu-id="c3a3e-146">이 두 특성은 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-146">These attributes are very similar.</span></span> <span data-ttu-id="c3a3e-147"><xref:System.Xml.Serialization.XmlRootAttribute>는 serialize되었을 때 XML 문서의 열기 및 닫기 요소(즉, 루트 요소)를 나타내는 클래스인 하나의 클래스에만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-147">The <xref:System.Xml.Serialization.XmlRootAttribute> can be applied to only one class: the class that, when serialized, represents the XML document's opening and closing element—in other words, the root element.</span></span> <span data-ttu-id="c3a3e-148">반면 <xref:System.Xml.Serialization.XmlTypeAttribute>는 루트 클래스를 포함한 모든 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-148">The <xref:System.Xml.Serialization.XmlTypeAttribute>, on the other hand, can be applied to any class, including the root class.</span></span>

<span data-ttu-id="c3a3e-149">예를 들어 이전 예제에서 `Group` 클래스는 루트 클래스이며 이 클래스의 모든 public 필드와 속성은 XML 문서에서 찾을 수 있는 XML 요소가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-149">For example, in the previous examples, the `Group` class is the root class, and all its public fields and properties become the XML elements found in the XML document.</span></span> <span data-ttu-id="c3a3e-150">따라서 하나의 루트 클래스만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-150">Therefore, there can be only one root class.</span></span> <span data-ttu-id="c3a3e-151"><xref:System.Xml.Serialization.XmlRootAttribute>를 적용하면 <xref:System.Xml.Serialization.XmlSerializer>로 생성된 XML 스트림을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-151">By applying the <xref:System.Xml.Serialization.XmlRootAttribute>, you can control the XML stream generated by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="c3a3e-152">예를 들어 요소 이름과 네임스페이스를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-152">For example, you can change the element name and namespace.</span></span>

<span data-ttu-id="c3a3e-153"><xref:System.Xml.Serialization.XmlTypeAttribute>를 사용하면 생성된 XML의 스키마를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-153">The <xref:System.Xml.Serialization.XmlTypeAttribute> allows you to control the schema of the generated XML.</span></span> <span data-ttu-id="c3a3e-154">이 기능은 XML Web services를 통해 스키마를 게시해야 할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-154">This capability is useful when you need to publish the schema through an XML Web service.</span></span> <span data-ttu-id="c3a3e-155">다음 예제에서는 <xref:System.Xml.Serialization.XmlTypeAttribute> 및 <xref:System.Xml.Serialization.XmlRootAttribute>를 같은 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-155">The following example applies both the <xref:System.Xml.Serialization.XmlTypeAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the same class.</span></span>

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

<span data-ttu-id="c3a3e-156">이 클래스가 컴파일되고 XML 스키마 정의 도구가 스키마 생성에 사용되는 경우 `Group`을 설명하는 다음 XML을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-156">If this class is compiled, and the XML Schema Definition tool is used to generate its schema, you would find the following XML describing `Group`.</span></span>

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

<span data-ttu-id="c3a3e-157">이와 반대로 클래스의 인스턴스를 serialize하면 `NewGroupName`이 XML 문서에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-157">In contrast, if you were to serialize an instance of the class, only `NewGroupName` would be found in the XML document.</span></span>

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a><span data-ttu-id="c3a3e-158">XmlIgnoreAttribute로 serialization 방지</span><span class="sxs-lookup"><span data-stu-id="c3a3e-158">Preventing Serialization with the XmlIgnoreAttribute</span></span>

<span data-ttu-id="c3a3e-159">public 속성이나 필드를 serialize할 필요가 없는 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-159">There might be situations when a public property or field does not need to be serialized.</span></span> <span data-ttu-id="c3a3e-160">예를 들어 메타데이터를 포함하기 위해 필드나 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-160">For example, a field or property could be used to contain metadata.</span></span> <span data-ttu-id="c3a3e-161">이러한 경우에는 <xref:System.Xml.Serialization.XmlIgnoreAttribute>를 필드 또는 속성에 적용하면 <xref:System.Xml.Serialization.XmlSerializer>가 이를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-161">In such cases, apply the <xref:System.Xml.Serialization.XmlIgnoreAttribute> to the field or property and the <xref:System.Xml.Serialization.XmlSerializer> will skip over it.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3a3e-162">참조</span><span class="sxs-lookup"><span data-stu-id="c3a3e-162">See also</span></span>

- [<span data-ttu-id="c3a3e-163">XML serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="c3a3e-163">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="c3a3e-164">인코딩된 SOAP serialization을 제어하는 특성</span><span class="sxs-lookup"><span data-stu-id="c3a3e-164">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="c3a3e-165">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="c3a3e-165">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="c3a3e-166">XML serialization 예제</span><span class="sxs-lookup"><span data-stu-id="c3a3e-166">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)
- [<span data-ttu-id="c3a3e-167">방법: XML 스트림의 대체 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="c3a3e-167">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="c3a3e-168">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="c3a3e-168">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="c3a3e-169">방법: 개체 역직렬화</span><span class="sxs-lookup"><span data-stu-id="c3a3e-169">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
