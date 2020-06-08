---
title: <system.xml.serialization> 요소
description: 이 문서에서는 XML serialization을 제어하기 위한 최상위 요소인 <system.xml.serialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289488"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="cdf66-103">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="cdf66-104">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="cdf66-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdf66-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a><span data-ttu-id="cdf66-106">구문</span><span class="sxs-lookup"><span data-stu-id="cdf66-106">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdf66-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-107">Attributes and Elements</span></span>

<span data-ttu-id="cdf66-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdf66-109">특성</span><span class="sxs-lookup"><span data-stu-id="cdf66-109">Attributes</span></span>

<span data-ttu-id="cdf66-110">없음</span><span class="sxs-lookup"><span data-stu-id="cdf66-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdf66-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-111">Child Elements</span></span>

|<span data-ttu-id="cdf66-112">요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-112">Element</span></span>|<span data-ttu-id="cdf66-113">설명</span><span class="sxs-lookup"><span data-stu-id="cdf66-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdf66-114">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-114">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)|<span data-ttu-id="cdf66-115"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-115">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="cdf66-116">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-116">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)|<span data-ttu-id="cdf66-117"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-117">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cdf66-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-118">Parent Elements</span></span>

|<span data-ttu-id="cdf66-119">요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-119">Element</span></span>|<span data-ttu-id="cdf66-120">설명</span><span class="sxs-lookup"><span data-stu-id="cdf66-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdf66-121">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-121">\<configuration> Element</span></span>](../../framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="cdf66-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-122">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="cdf66-123">예제</span><span class="sxs-lookup"><span data-stu-id="cdf66-123">Example</span></span>

<span data-ttu-id="cdf66-124">다음 코드 예제에서는 <xref:System.DateTime> 개체의 serialization 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cdf66-124">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cdf66-125">참조</span><span class="sxs-lookup"><span data-stu-id="cdf66-125">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="cdf66-126">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="cdf66-126">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="cdf66-127">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-127">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="cdf66-128">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-128">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- <span data-ttu-id="cdf66-129">[\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소</span><span class="sxs-lookup"><span data-stu-id="cdf66-129">[\<add> Element for \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)</span></span>
