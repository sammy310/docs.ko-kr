---
description: '자세한 정보: Serialization (Visual Basic)'
title: Serialization
ms.date: 07/20/2015
ms.assetid: 67379a76-5465-4af8-a781-0b0b25a62d9a
ms.openlocfilehash: dcc10591bc9e220bc5bebd8fa9b6ac90a307e540
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486903"
---
# <a name="serialization-visual-basic"></a><span data-ttu-id="e76d1-103">Serialization(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e76d1-103">Serialization (Visual Basic)</span></span>

<span data-ttu-id="e76d1-104">Serialization은 개체를 저장하거나 메모리, 데이터베이스 또는 파일로 전송하기 위해 개체를 바이트 스트림으로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-104">Serialization is the process of converting an object into a stream of bytes in order to store the object or transmit it to memory, a database, or a file.</span></span> <span data-ttu-id="e76d1-105">주 목적은 필요할 때 다시 개체로 만들 수 있도록 개체의 상태를 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-105">Its main purpose is to save the state of an object in order to be able to recreate it when needed.</span></span> <span data-ttu-id="e76d1-106">역 프로세스를 deserialization이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-106">The reverse process is called deserialization.</span></span>  
  
## <a name="how-serialization-works"></a><span data-ttu-id="e76d1-107">Serialization 작동 방법</span><span class="sxs-lookup"><span data-stu-id="e76d1-107">How Serialization Works</span></span>  

 <span data-ttu-id="e76d1-108">이 그림에서는 serialization의 전체 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-108">This illustration shows the overall process of serialization.</span></span>  
  
![Serialization 그래픽](./media/index/serialization-process.gif)
  
 <span data-ttu-id="e76d1-110">개체는 스트림으로 serialize되어 데이터 뿐만 아니라 버전, 문화권 및 어셈블리 이름과 같은 개체 형식에 대한 정보를 운반합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-110">The object is serialized to a stream, which carries not just the data, but information about the object's type, such as its version, culture, and assembly name.</span></span> <span data-ttu-id="e76d1-111">해당 스트림에서 데이터베이스, 파일 또는 메모리에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-111">From that stream, it can be stored in a database, a file, or memory.</span></span>  
  
### <a name="uses-for-serialization"></a><span data-ttu-id="e76d1-112">serialization의 용도</span><span class="sxs-lookup"><span data-stu-id="e76d1-112">Uses for Serialization</span></span>  

 <span data-ttu-id="e76d1-113">Serialization을 사용하여 개발자는 개체의 상태를 저장하고 필요할 때 다시 만들어 개체 교환 뿐 아니라 개체의 스토리지 기능도 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-113">Serialization allows the developer to save the state of an object and recreate it as needed, providing storage of objects as well as data exchange.</span></span> <span data-ttu-id="e76d1-114">Serialization을 통해 개발자는 웹 서비스를 통해 원격 애플리케이션에 개체를 전송하거나, 한 도메인에서 다른 도메인으로 개체를 전달하거나, 방화벽을 통해 XML 문자열로 개체를 전달하거나, 애플리케이션 간에 보안 또는 사용자별 정보를 유지 관리하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-114">Through serialization, a developer can perform actions like sending the object to a remote application by means of a Web Service, passing an object from one domain to another, passing an object through a firewall as an XML string, or maintaining security or user-specific information across applications.</span></span>  
  
### <a name="making-an-object-serializable"></a><span data-ttu-id="e76d1-115">개체를 Serialize 가능하게 만들기</span><span class="sxs-lookup"><span data-stu-id="e76d1-115">Making an Object Serializable</span></span>  

 <span data-ttu-id="e76d1-116">개체를 직렬화하려면 직렬화할 개체, 직렬화된 개체를 포함할 스트림 및 <xref:System.Runtime.Serialization.Formatter>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-116">To serialize an object, you need the object to be serialized, a stream to contain the serialized object, and a <xref:System.Runtime.Serialization.Formatter>.</span></span> <span data-ttu-id="e76d1-117"><xref:System.Runtime.Serialization>은 개체를 직렬화하거나 역직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-117"><xref:System.Runtime.Serialization> contains the classes necessary for serializing and deserializing objects.</span></span>  
  
 <span data-ttu-id="e76d1-118">형식에 <xref:System.SerializableAttribute> 특성을 적용하여 이 형식의 인스턴스를 직렬화할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-118">Apply the <xref:System.SerializableAttribute> attribute to a type to indicate that instances of this type can be serialized.</span></span> <span data-ttu-id="e76d1-119">직렬화하려고 하지만 형식에 <xref:System.SerializableAttribute> 특성이 없는 경우 <xref:System.Runtime.Serialization.SerializationException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-119">A <xref:System.Runtime.Serialization.SerializationException> exception is thrown if you attempt to serialize but the type does not have the <xref:System.SerializableAttribute> attribute.</span></span>  
  
 <span data-ttu-id="e76d1-120">클래스 내의 필드를 직렬화 가능하게 하지 않으려면 <xref:System.NonSerializedAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-120">If you do not want a field within your class to be serializable, apply the <xref:System.NonSerializedAttribute> attribute.</span></span> <span data-ttu-id="e76d1-121">serialize 가능한 형식의 필드에 특정 환경과 관련된 포인터, 핸들 또는 다른 데이터 구조가 포함되어 있고 필드를 다른 환경에서 의미 있게 재구성할 수 없으면 serialize할 수 없게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-121">If a field of a serializable type contains a pointer, a handle, or some other data structure that is specific to a particular environment, and the field cannot be meaningfully reconstituted in a different environment, then you may want to make it nonserializable.</span></span>  
  
 <span data-ttu-id="e76d1-122">직렬화된 클래스에 <xref:System.SerializableAttribute>가 표시된 다른 클래스의 개체에 대한 참조가 포함된 경우 해당 개체도 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-122">If a serialized class contains references to objects of other classes that are marked <xref:System.SerializableAttribute>, those objects will also be serialized.</span></span>  
  
## <a name="binary-and-xml-serialization"></a><span data-ttu-id="e76d1-123">이진 및 XML 직렬화</span><span class="sxs-lookup"><span data-stu-id="e76d1-123">Binary and XML Serialization</span></span>  

 <span data-ttu-id="e76d1-124">이진 또는 XML serialization을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-124">Either binary or XML serialization can be used.</span></span> <span data-ttu-id="e76d1-125">이진 serialization에서는 읽기 전용이더라도 모든 멤버가 serialize되고 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-125">In binary serialization, all members, even those that are read-only, are serialized, and performance is enhanced.</span></span> <span data-ttu-id="e76d1-126">XML serialization은 상호 운용성을 위한 보다 유연한 개체 공유 및 사용 뿐만 아니라 보다 읽기 쉬운 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-126">XML serialization provides more readable code, as well as greater flexibility of object sharing and usage for interoperability purposes.</span></span>  
  
### <a name="binary-serialization"></a><span data-ttu-id="e76d1-127">이진 Serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-127">Binary Serialization</span></span>  

 <span data-ttu-id="e76d1-128">이진 serialization은 이진 인코딩을 사용하여 스토리지 또는 스트림 기반 네트워크 스트림과 같은 용도로 사용할 수 있는 압축 serialization을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-128">Binary serialization uses binary encoding to produce compact serialization for uses such as storage or socket-based network streams.</span></span>  
  
### <a name="xml-serialization"></a><span data-ttu-id="e76d1-129">XML Serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-129">XML Serialization</span></span>  

 <span data-ttu-id="e76d1-130">XML serialization은 개체의 public 필드와 속성 또는 메서드의 매개 변수와 반환 값을 특정 XSD(XML 스키마 정의 언어) 문서와 일치하는 XML 스트림으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-130">XML serialization serializes the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="e76d1-131">XML serialization을 사용하면 XML로 변환되는 public 속성 및 필드가 있는 강력한 형식의 클래스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-131">XML serialization results in strongly typed classes with public properties and fields that are converted to XML.</span></span> <span data-ttu-id="e76d1-132"><xref:System.Xml.Serialization>은 XML을 직렬화하거나 역직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-132"><xref:System.Xml.Serialization> contains the classes necessary for serializing and deserializing XML.</span></span>  
  
 <span data-ttu-id="e76d1-133"><xref:System.Xml.Serialization.XmlSerializer>가 클래스 인스턴스를 직렬화 또는 역직렬화하는 방법을 제어하기 위해 클래스 및 클래스 멤버에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-133">You can apply attributes to classes and class members in order to control the way the <xref:System.Xml.Serialization.XmlSerializer> serializes or deserializes an instance of the class.</span></span>  
  
## <a name="basic-and-custom-serialization"></a><span data-ttu-id="e76d1-134">기본 및 사용자 지정 Serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-134">Basic and Custom Serialization</span></span>  

 <span data-ttu-id="e76d1-135">serialization은 기본 및 사용자 지정의 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-135">Serialization can be performed in two ways, basic and custom.</span></span> <span data-ttu-id="e76d1-136">기본 serialization은 .NET Framework를 사용하여 개체를 자동으로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-136">Basic serialization uses the .NET Framework to automatically serialize the object.</span></span>  
  
### <a name="basic-serialization"></a><span data-ttu-id="e76d1-137">기본 Serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-137">Basic Serialization</span></span>  

 <span data-ttu-id="e76d1-138">기본 serialization의 유일한 요구 사항은 개체에 <xref:System.SerializableAttribute> 특성이 적용되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-138">The only requirement in basic serialization is that the object has the <xref:System.SerializableAttribute> attribute applied.</span></span> <span data-ttu-id="e76d1-139"><xref:System.NonSerializedAttribute>는 특정 필드가 직렬화되지 않도록 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-139">The <xref:System.NonSerializedAttribute> can be used to keep specific fields from being serialized.</span></span>  
  
 <span data-ttu-id="e76d1-140">기본 serialization을 사용하면 개체의 버전을 관리하는 데 문제가 발생할 수 있습니다. 이 경우에는 사용자 지정 serialization이 더 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-140">When you use basic serialization, the versioning of objects may create problems, in which case custom serialization may be preferable.</span></span> <span data-ttu-id="e76d1-141">기본 serialization은 serialization을 수행하는 가장 쉬운 방법이지만 프로세스를 강력하게 제어하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-141">Basic serialization is the easiest way to perform serialization, but it does not provide much control over the process.</span></span>  
  
### <a name="custom-serialization"></a><span data-ttu-id="e76d1-142">사용자 지정 Serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-142">Custom Serialization</span></span>  

 <span data-ttu-id="e76d1-143">사용자 지정 serialization에서는 serialize될 개체 및 수행 방법을 정확하게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-143">In custom serialization, you can specify exactly which objects will be serialized and how it will be done.</span></span> <span data-ttu-id="e76d1-144">클래스에 <xref:System.SerializableAttribute>가 표시되어야 하고 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-144">The class must be marked <xref:System.SerializableAttribute> and implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 <span data-ttu-id="e76d1-145">개체를 사용자 지정 방식으로 역직렬화하려면 사용자 지정 생성자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-145">If you want your object to be deserialized in a custom manner as well, you must use a custom constructor.</span></span>  
  
## <a name="designer-serialization"></a><span data-ttu-id="e76d1-146">디자이너 serialization</span><span class="sxs-lookup"><span data-stu-id="e76d1-146">Designer Serialization</span></span>  

 <span data-ttu-id="e76d1-147">디자이너 serialization은 일반적으로 개발 도구와 관련해서 개체 지속성이 적용되는 특수한 형태의 serialization입니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-147">Designer serialization is a special form of serialization that involves the kind of object persistence usually associated with development tools.</span></span> <span data-ttu-id="e76d1-148">디자이너 serialization은 개체 그래프를 소스 파일로 변환하여 나중에 개체 그래프를 복구하는 데 사용할 수 있도록 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-148">Designer serialization is the process of converting an object graph into a source file that can later be used to recover the object graph.</span></span> <span data-ttu-id="e76d1-149">소스 파일에는 코드, 태그 또는 심지어 SQL 테이블 정보도 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-149">A source file can contain code, markup, or even SQL table information.</span></span>  
  
## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> <span data-ttu-id="e76d1-150">관련 항목 및 예제</span><span class="sxs-lookup"><span data-stu-id="e76d1-150">Related Topics and Examples</span></span>  

 [<span data-ttu-id="e76d1-151">연습: Visual Studio에서 개체 유지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e76d1-151">Walkthrough: Persisting an Object in Visual Studio (Visual Basic)</span></span>](walkthrough-persisting-an-object-in-visual-studio.md)  
 <span data-ttu-id="e76d1-152">serialization을 사용하여 인스턴스 간에 개체의 데이터를 유지함으로써 다음에 개체를 인스턴스화할 때 값을 저장하고 검색하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-152">Demonstrates how serialization can be used to persist an object's data between instances, allowing you to store values and retrieve them the next time the object is instantiated.</span></span>  
  
 [<span data-ttu-id="e76d1-153">방법: XML 파일에서 개체 데이터 읽기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e76d1-153">How to: Read Object Data from an XML File (Visual Basic)</span></span>](how-to-read-object-data-from-an-xml-file.md)  
 <span data-ttu-id="e76d1-154"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-154">Shows how to read object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
 [<span data-ttu-id="e76d1-155">방법: XML 파일에 개체 데이터 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e76d1-155">How to: Write Object Data to an XML File (Visual Basic)</span></span>](how-to-write-object-data-to-an-xml-file.md)  
 <span data-ttu-id="e76d1-156"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 클래스의 개체를 XML 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e76d1-156">Shows how to write the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>
