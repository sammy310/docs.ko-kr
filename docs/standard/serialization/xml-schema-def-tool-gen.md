---
title: '방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성'
description: XML 스키마 정의 도구를 사용하여 클래스를 설명하는 XML 스키마를 생성하거나 XML 스키마로 정의된 클래스를 생성하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 21ce4ad846e21a328ba199f6253bd259be9d932b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379529"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="6c936-103">방법: XML 스키마 정의 도구를 사용하여 클래스 및 XML 스키마 문서 생성</span><span class="sxs-lookup"><span data-stu-id="6c936-103">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="6c936-104">XML 스키마 정의 도구(Xsd.exe)를 사용하면 클래스를 설명하는 XML 스키마를 생성하거나 XML 스키마로 정의된 클래스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-104">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="6c936-105">다음 절차에서는 이러한 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-105">The following procedures show how to perform these operations.</span></span>

<span data-ttu-id="6c936-106">XML 스키마 정의 도구(Xsd.exe)는 일반적으로 다음 path:\에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-106">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:\</span></span>
<span data-ttu-id="6c936-107">_C:\\Program Files(x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span><span class="sxs-lookup"><span data-stu-id="6c936-107">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="6c936-108">특정 스키마를 따르는 클래스를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="6c936-108">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="6c936-109">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-109">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="6c936-110">XML 스키마를 XML 스키마 정의 도구에 인수로 전달합니다. 그러면 예를 들어 XML 스키마에 정확하게 일치하는 클래스 집합이 만들어 집니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-110">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="6c936-111">도구는 2001년 3월 16일자 World Wide Web 컨소시엄 XML 사양을 참조하는 스키마만 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-111">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="6c936-112">즉, XML 스키마 네임스페이스는 다음 예제와 같이 "http://www.w3.org/2001/XMLSchema"여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-112">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. <span data-ttu-id="6c936-113">필요에 따라 메서드, 속성 또는 필드로 클래스를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-113">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="6c936-114">특성을 사용하여 클래스를 수정하는 방법에 대한 자세한 내용은 [특성을 사용하여 XML Serialization 제어](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) 및 [인코딩된 SOAP Serialization을 제어하는 특성](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c936-114">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="6c936-115">클래스의 인스턴스가 serialize될 때 생성되는 XML 스트림의 스키마를 검사하는 것이 유용할 때가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-115">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="6c936-116">예를 들어 스키마를 다른 사람이 사용할 수 있도록 게시하거나 준수를 위해 다른 스키마와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-116">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="6c936-117">클래스 집합에서 XML 스키마 문서를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="6c936-117">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="6c936-118">클래스를 DLL로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-118">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="6c936-119">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-119">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="6c936-120">DLL을 Xsd.exe에 인수로 전달합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-120">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="6c936-121">스키마가 이름 "schema0.xsd"로 시작하여 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c936-121">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c936-122">참조</span><span class="sxs-lookup"><span data-stu-id="6c936-122">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="6c936-123">XML 스키마 정의 도구 및 XML serialization</span><span class="sxs-lookup"><span data-stu-id="6c936-123">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="6c936-124">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="6c936-124">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="6c936-125">XML 스키마 정의 도구(Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="6c936-125">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="6c936-126">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="6c936-126">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="6c936-127">방법: 개체 역직렬화</span><span class="sxs-lookup"><span data-stu-id="6c936-127">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
