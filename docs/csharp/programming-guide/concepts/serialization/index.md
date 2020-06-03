---
title: Serialization(C#)
ms.date: 01/02/2020
ms.openlocfilehash: b2532ccf281fdfaa951d56675066f1e239f9f480
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241983"
---
# <a name="serialization-c"></a><span data-ttu-id="c5aa8-102">Serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="c5aa8-102">Serialization (C#)</span></span>

<span data-ttu-id="c5aa8-103">Serialization은 개체를 저장하거나 메모리, 데이터베이스 또는 파일로 전송하기 위해 개체를 바이트 스트림으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-103">Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file.</span></span> <span data-ttu-id="c5aa8-104">주 목적은 필요할 때 다시 개체로 만들 수 있도록 개체의 상태를 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-104">Its main purpose is to save the state of an object in order to be able to recreate it when needed.</span></span> <span data-ttu-id="c5aa8-105">역 프로세스를 deserialization이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-105">The reverse process is called deserialization.</span></span>

## <a name="how-serialization-works"></a><span data-ttu-id="c5aa8-106">Serialization 작동 방법</span><span class="sxs-lookup"><span data-stu-id="c5aa8-106">How serialization works</span></span>

<span data-ttu-id="c5aa8-107">아래 그림에서는 serialization의 전체 프로세스 과정을 보여 줍니다:</span><span class="sxs-lookup"><span data-stu-id="c5aa8-107">This illustration shows the overall process of serialization:</span></span>

![Serialization 그래픽](./media/index/serialization-process.gif)

<span data-ttu-id="c5aa8-109">개체는 데이터를 전달하는 스트림으로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-109">The object is serialized to a stream that carries the data.</span></span> <span data-ttu-id="c5aa8-110">스트림에는 버전, 문화권 및 어셈블리 이름과 같은 개체 형식 정보가 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-110">The stream may also have information about the object's type, such as its version, culture, and assembly name.</span></span> <span data-ttu-id="c5aa8-111">해당 스트림의 개체를 데이터베이스, 파일 또는 메모리에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-111">From that stream, the object can be stored in a database, a file, or memory.</span></span>

### <a name="uses-for-serialization"></a><span data-ttu-id="c5aa8-112">Serialization 용도</span><span class="sxs-lookup"><span data-stu-id="c5aa8-112">Uses for serialization</span></span>

<span data-ttu-id="c5aa8-113">Serialization은 개발자가 개체의 상태를 저장하고 필요에 따라 개체를 다시 만들 수 있게 함으로써 데이터 교환뿐 아니라 개체 스토리지 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-113">Serialization allows the developer to save the state of an object and re-create it as needed, providing storage of objects as well as data exchange.</span></span> <span data-ttu-id="c5aa8-114">Serialization을 통해 개발자는 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-114">Through serialization, a developer can perform actions such as:</span></span>

* <span data-ttu-id="c5aa8-115">웹 서비스를 사용하여 원격 애플리케이션에 개체 보내기</span><span class="sxs-lookup"><span data-stu-id="c5aa8-115">Sending the object to a remote application by using a web service</span></span>
* <span data-ttu-id="c5aa8-116">한 도메인에서 다른 도메인으로 개체 전달</span><span class="sxs-lookup"><span data-stu-id="c5aa8-116">Passing an object from one domain to another</span></span>
* <span data-ttu-id="c5aa8-117">방화벽을 통해 JSON 또는 XML 문자열로 개체 전달</span><span class="sxs-lookup"><span data-stu-id="c5aa8-117">Passing an object through a firewall as a JSON or XML string</span></span>
* <span data-ttu-id="c5aa8-118">애플리케이션 간에 보안 또는 사용자 관련 정보 유지</span><span class="sxs-lookup"><span data-stu-id="c5aa8-118">Maintaining security or user-specific information across applications</span></span>

## <a name="json-serialization"></a><span data-ttu-id="c5aa8-119">JSON serialization</span><span class="sxs-lookup"><span data-stu-id="c5aa8-119">JSON serialization</span></span>

<span data-ttu-id="c5aa8-120"><xref:System.Text.Json> 네임스페이스에는 JSON(JavaScript Object Notation) serialization 및 deserialization 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-120">The <xref:System.Text.Json> namespace contains classes for JavaScript Object Notation (JSON) serialization and deserialization.</span></span> <span data-ttu-id="c5aa8-121">JSON은 웹에서 데이터를 공유하는 데 일반적으로 사용되는 개방형 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-121">JSON is an open standard that is commonly used for sharing data across the web.</span></span>

<span data-ttu-id="c5aa8-122">JSON serialization은 개체의 퍼블릭 속성을 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259)을 따르는 문자열, 바이트 배열 또는 스트림으로 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-122">JSON serialization serializes the public properties of an object into a string, byte array, or stream that conforms to [the RFC 8259 JSON specification](https://tools.ietf.org/html/rfc8259).</span></span> <span data-ttu-id="c5aa8-123"><xref:System.Text.Json.JsonSerializer>가 클래스 인스턴스를 직렬화 또는 역직렬화하는 방식을 제어하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-123">To control the way <xref:System.Text.Json.JsonSerializer> serializes or deserializes an instance of the class:</span></span>

* <span data-ttu-id="c5aa8-124"><xref:System.Text.Json.JsonSerializerOptions> 개체 사용</span><span class="sxs-lookup"><span data-stu-id="c5aa8-124">Use a <xref:System.Text.Json.JsonSerializerOptions> object</span></span>
* <span data-ttu-id="c5aa8-125">클래스 또는 속성에 <xref:System.Text.Json.Serialization> 네임스페이스의 특성 적용</span><span class="sxs-lookup"><span data-stu-id="c5aa8-125">Apply attributes from the <xref:System.Text.Json.Serialization> namespace to classes or properties</span></span>
* [<span data-ttu-id="c5aa8-126">사용자 지정 변환기 구현</span><span class="sxs-lookup"><span data-stu-id="c5aa8-126">Implement custom converters</span></span>](../../../../standard/serialization/system-text-json-converters-how-to.md)

## <a name="binary-and-xml-serialization"></a><span data-ttu-id="c5aa8-127">이진 및 XML Serialization</span><span class="sxs-lookup"><span data-stu-id="c5aa8-127">Binary and XML serialization</span></span>

<span data-ttu-id="c5aa8-128"><xref:System.Runtime.Serialization> 네임스페이스에는 이진 및 XML serialization 및 deserialization 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-128">The <xref:System.Runtime.Serialization> namespace contains classes for binary and XML serialization and deserialization.</span></span>

<span data-ttu-id="c5aa8-129">이진 serialization은 이진 인코딩을 사용하여 스토리지 또는 스트림 기반 네트워크 스트림과 같은 용도로 사용할 수 있는 압축 serialization을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-129">Binary serialization uses binary encoding to produce compact serialization for uses such as storage or socket-based network streams.</span></span> <span data-ttu-id="c5aa8-130">이진 Serialization에서 멤버가 읽기 전용이더라도 모든 멤버가 Serialize되고 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-130">In binary serialization, all members, even members that are read-only, are serialized, and performance is enhanced.</span></span>

<span data-ttu-id="c5aa8-131">XML serialization은 개체의 public 필드와 속성 또는 메서드의 매개 변수와 반환 값을 특정 XSD(XML 스키마 정의 언어) 문서와 일치하는 XML 스트림으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-131">XML serialization serializes the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="c5aa8-132">XML serialization을 사용하면 XML로 변환되는 public 속성 및 필드가 있는 강력한 형식의 클래스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-132">XML serialization results in strongly typed classes with public properties and fields that are converted to XML.</span></span> <span data-ttu-id="c5aa8-133"><xref:System.Xml.Serialization>에는 XML을 직렬화 및 역직렬화하기 위한 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-133"><xref:System.Xml.Serialization> contains classes for serializing and deserializing XML.</span></span> <span data-ttu-id="c5aa8-134"><xref:System.Xml.Serialization.XmlSerializer>가 클래스 인스턴스를 직렬화 또는 역직렬화하는 방법을 제어하기 위해 클래스 및 클래스 멤버에 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-134">You apply attributes to classes and class members to control the way the <xref:System.Xml.Serialization.XmlSerializer> serializes or deserializes an instance of the class.</span></span>

### <a name="making-an-object-serializable"></a><span data-ttu-id="c5aa8-135">개체를 Serialize 가능하게 만들기</span><span class="sxs-lookup"><span data-stu-id="c5aa8-135">Making an object serializable</span></span>

<span data-ttu-id="c5aa8-136">이진 또는 XML serialization의 경우 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-136">For binary or XML serialization, you need:</span></span>

* <span data-ttu-id="c5aa8-137">직렬화할 개체</span><span class="sxs-lookup"><span data-stu-id="c5aa8-137">The object to be serialized</span></span>
* <span data-ttu-id="c5aa8-138">직렬화된 개체를 포함할 스트림</span><span class="sxs-lookup"><span data-stu-id="c5aa8-138">A stream to contain the serialized object</span></span>
* <span data-ttu-id="c5aa8-139"><xref:System.Runtime.Serialization.Formatter?displayProperty=fullName> 인스턴스</span><span class="sxs-lookup"><span data-stu-id="c5aa8-139">A <xref:System.Runtime.Serialization.Formatter?displayProperty=fullName> instance</span></span>

<span data-ttu-id="c5aa8-140">형식에 <xref:System.SerializableAttribute> 특성을 적용하여 이 형식의 인스턴스를 직렬화할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-140">Apply the <xref:System.SerializableAttribute> attribute to a type to indicate that instances of the type can be serialized.</span></span> <span data-ttu-id="c5aa8-141">형식에 <xref:System.SerializableAttribute> 특성이 없는 경우 직렬화하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-141">An  exception is thrown if you attempt to serialize but the type doesn't have the <xref:System.SerializableAttribute> attribute.</span></span>

<span data-ttu-id="c5aa8-142">필드가 직렬화되지 않도록 하려면 <xref:System.NonSerializedAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-142">To prevent a field from being serialized, apply the <xref:System.NonSerializedAttribute> attribute.</span></span> <span data-ttu-id="c5aa8-143">serialize 가능한 형식의 필드에 특정 환경과 관련된 포인터, 핸들 또는 다른 데이터 구조가 포함되어 있고 필드를 다른 환경에서 의미 있게 재구성할 수 없으면 serialize할 수 없게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-143">If a field of a serializable type contains a pointer, a handle, or some other data structure that is specific to a particular environment, and the field cannot be meaningfully reconstituted in a different environment, then you may want to make it nonserializable.</span></span>

<span data-ttu-id="c5aa8-144">직렬화된 클래스에 <xref:System.SerializableAttribute>가 표시된 다른 클래스의 개체에 대한 참조가 포함된 경우 해당 개체도 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-144">If a serialized class contains references to objects of other classes that are marked <xref:System.SerializableAttribute>, those objects will also be serialized.</span></span>

### <a name="basic-and-custom-serialization"></a><span data-ttu-id="c5aa8-145">기본 및 사용자 지정 Serialization</span><span class="sxs-lookup"><span data-stu-id="c5aa8-145">Basic and custom serialization</span></span>

<span data-ttu-id="c5aa8-146">이진 및 XML serialization은 기본 및 사용자 지정의 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-146">Binary and XML serialization can be performed in two ways, basic and custom.</span></span>

<span data-ttu-id="c5aa8-147">기본 serialization은 .NET을 사용하여 개체를 자동으로 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-147">Basic serialization uses .NET to automatically serialize the object.</span></span> <span data-ttu-id="c5aa8-148">유일한 요구 사항은 클래스에 <xref:System.SerializableAttribute> 특성이 적용되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-148">The only requirement is that the class has the <xref:System.SerializableAttribute> attribute applied.</span></span> <span data-ttu-id="c5aa8-149"><xref:System.NonSerializedAttribute>는 특정 필드가 직렬화되지 않도록 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-149">The <xref:System.NonSerializedAttribute> can be used to keep specific fields from being serialized.</span></span>

<span data-ttu-id="c5aa8-150">기본 Serialization을 사용하면 개체의 버전 관리에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-150">When you use basic serialization, the versioning of objects may create problems.</span></span> <span data-ttu-id="c5aa8-151">버전 관리 문제가 중요하면 사용자 지정 Serialization을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-151">You would use custom serialization when versioning issues are important.</span></span> <span data-ttu-id="c5aa8-152">기본 serialization은 serialization을 수행하는 가장 쉬운 방법이지만 프로세스를 강력하게 제어하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-152">Basic serialization is the easiest way to perform serialization, but it does not provide much control over the process.</span></span>

<span data-ttu-id="c5aa8-153">사용자 지정 serialization에서는 serialize될 개체 및 수행 방법을 정확하게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-153">In custom serialization, you can specify exactly which objects will be serialized and how it will be done.</span></span> <span data-ttu-id="c5aa8-154">클래스에 <xref:System.SerializableAttribute>가 표시되어야 하고 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-154">The class must be marked <xref:System.SerializableAttribute> and implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="c5aa8-155">개체를 사용자 지정 방식으로도 역직렬화하려는 경우 사용자 지정 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-155">If you want your object to be deserialized in a custom manner as well, use a custom constructor.</span></span>

## <a name="designer-serialization"></a><span data-ttu-id="c5aa8-156">디자이너 Serialization</span><span class="sxs-lookup"><span data-stu-id="c5aa8-156">Designer serialization</span></span>

<span data-ttu-id="c5aa8-157">디자이너 Serialization은 개발 도구와 관련해서 개체 지속성이 적용되는 특수한 형태의 Serialization입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-157">Designer serialization is a special form of serialization that involves the kind of object persistence associated with development tools.</span></span> <span data-ttu-id="c5aa8-158">디자이너 serialization은 개체 그래프를 소스 파일로 변환하여 나중에 개체 그래프를 복구하는 데 사용할 수 있도록 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-158">Designer serialization is the process of converting an object graph into a source file that can later be used to recover the object graph.</span></span> <span data-ttu-id="c5aa8-159">소스 파일에는 코드, 태그 또는 심지어 SQL 테이블 정보도 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-159">A source file can contain code, markup, or even SQL table information.</span></span>

## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> <span data-ttu-id="c5aa8-160">관련 항목 및 예제</span><span class="sxs-lookup"><span data-stu-id="c5aa8-160">Related Topics and Examples</span></span>  

<span data-ttu-id="c5aa8-161">[System.Text.Json 개요](../../../../standard/serialization/system-text-json-overview.md) `System.Text.Json` 라이브러리를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-161">[System.Text.Json overview](../../../../standard/serialization/system-text-json-overview.md) Shows how to get the `System.Text.Json` library.</span></span>

<span data-ttu-id="c5aa8-162">[.NET에서 JSON을 직렬화 및 역직렬화하는 방법](../../../../standard/serialization/system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="c5aa8-162">[How to serialize and deserialize JSON in .NET](../../../../standard/serialization/system-text-json-how-to.md).</span></span>
<span data-ttu-id="c5aa8-163"><xref:System.Text.Json.JsonSerializer> 클래스를 사용하여 JSON에서 개체 데이터를 읽고 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-163">Shows how to read and write object data to and from JSON using the <xref:System.Text.Json.JsonSerializer> class.</span></span>

[<span data-ttu-id="c5aa8-164">연습: Visual Studio에서 개체 유지(C#)</span><span class="sxs-lookup"><span data-stu-id="c5aa8-164">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>](walkthrough-persisting-an-object-in-visual-studio.md)  
<span data-ttu-id="c5aa8-165">serialization을 사용하여 인스턴스 간에 개체의 데이터를 유지함으로써 다음에 개체를 인스턴스화할 때 값을 저장하고 검색하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-165">Demonstrates how serialization can be used to persist an object's data between instances, allowing you to store values and retrieve them the next time the object is instantiated.</span></span>

[<span data-ttu-id="c5aa8-166">XML 파일에서 개체 데이터를 읽는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c5aa8-166">How to read object data from an XML file (C#)</span></span>](how-to-read-object-data-from-an-xml-file.md)  
<span data-ttu-id="c5aa8-167"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-167">Shows how to read object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>

[<span data-ttu-id="c5aa8-168">XML 파일에 개체 데이터를 쓰는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c5aa8-168">How to write object data to an XML file (C#)</span></span>](how-to-write-object-data-to-an-xml-file.md)  
<span data-ttu-id="c5aa8-169"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 클래스의 개체를 XML 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5aa8-169">Shows how to write the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>
