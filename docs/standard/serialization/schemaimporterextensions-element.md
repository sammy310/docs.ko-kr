---
title: <schemaImporterExtensions> 요소
description: <schemaImporterExtensions> 요소에는 XmlSchemaImporter가 XSD 형식을 .NET Framework 형식으로 매핑하기 위해 사용하는 형식이 포함되어 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5b9820ccdf2c75bed9beda72358c4c4d82ff9ff7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379798"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="7d2c0-103">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="7d2c0-104"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c0-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="7d2c0-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2c0-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d2c0-106">구문</span><span class="sxs-lookup"><span data-stu-id="7d2c0-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="7d2c0-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-107">Child Elements</span></span>  
  
|<span data-ttu-id="7d2c0-108">요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-108">Element</span></span>|<span data-ttu-id="7d2c0-109">설명</span><span class="sxs-lookup"><span data-stu-id="7d2c0-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d2c0-110">\<schemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-110">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="7d2c0-111"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 매핑을 만들기 위해 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c0-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="7d2c0-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="7d2c0-113">요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-113">Element</span></span>|<span data-ttu-id="7d2c0-114">설명</span><span class="sxs-lookup"><span data-stu-id="7d2c0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d2c0-115">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-115">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="7d2c0-116">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c0-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d2c0-117">예제</span><span class="sxs-lookup"><span data-stu-id="7d2c0-117">Example</span></span>  
 <span data-ttu-id="7d2c0-118">다음 코드 예제에서는 XSD 형식을 .NET Framework 형식으로 매핑할 때 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d2c0-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d2c0-119">참조</span><span class="sxs-lookup"><span data-stu-id="7d2c0-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="7d2c0-120">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7d2c0-120">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7d2c0-121">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-121">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="7d2c0-122">\<schemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-122">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="7d2c0-123">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="7d2c0-123">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
