---
title: <system.xml.serialization> 요소
description: 이 문서에서는 XML serialization을 제어하기 위한 최상위 요소인 <system.xml.serialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380123"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="8bb34-103">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="8bb34-104">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="8bb34-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb34-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="8bb34-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8bb34-106">\<configuration></span></span>\
<span data-ttu-id="8bb34-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="8bb34-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="8bb34-108">구문</span><span class="sxs-lookup"><span data-stu-id="8bb34-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8bb34-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-109">Attributes and Elements</span></span>

<span data-ttu-id="8bb34-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8bb34-111">특성</span><span class="sxs-lookup"><span data-stu-id="8bb34-111">Attributes</span></span>

<span data-ttu-id="8bb34-112">없음</span><span class="sxs-lookup"><span data-stu-id="8bb34-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8bb34-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-113">Child Elements</span></span>

|<span data-ttu-id="8bb34-114">요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-114">Element</span></span>|<span data-ttu-id="8bb34-115">설명</span><span class="sxs-lookup"><span data-stu-id="8bb34-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8bb34-116">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="8bb34-117"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="8bb34-118">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="8bb34-119"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8bb34-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-120">Parent Elements</span></span>

|<span data-ttu-id="8bb34-121">요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-121">Element</span></span>|<span data-ttu-id="8bb34-122">설명</span><span class="sxs-lookup"><span data-stu-id="8bb34-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8bb34-123">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="8bb34-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="8bb34-125">예제</span><span class="sxs-lookup"><span data-stu-id="8bb34-125">Example</span></span>

<span data-ttu-id="8bb34-126">다음 코드 예제에서는 <xref:System.DateTime> 개체의 serialization 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bb34-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="8bb34-127">참조</span><span class="sxs-lookup"><span data-stu-id="8bb34-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="8bb34-128">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8bb34-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8bb34-129">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="8bb34-130">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="8bb34-131">\<schemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="8bb34-131">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
