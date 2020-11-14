---
title: <schemaImporterExtensions> 요소
description: <schemaImporterExtensions> 요소에는 XmlSchemaImporter가 XSD 형식을 .NET 형식에 매핑하기 위해 사용하는 형식이 포함되어 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 35626618a8dd7c63a7008d10bc3568484836a488
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282274"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="d9848-103">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-103">\<schemaImporterExtensions> element</span></span>

<span data-ttu-id="d9848-104"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET 형식에 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9848-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span> <span data-ttu-id="d9848-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9848-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9848-106">구문</span><span class="sxs-lookup"><span data-stu-id="d9848-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="d9848-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-107">Child Elements</span></span>  
  
|<span data-ttu-id="d9848-108">요소</span><span class="sxs-lookup"><span data-stu-id="d9848-108">Element</span></span>|<span data-ttu-id="d9848-109">설명</span><span class="sxs-lookup"><span data-stu-id="d9848-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9848-110">[\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-110">[\<add> Element for \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)</span></span>|<span data-ttu-id="d9848-111"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 매핑을 만들기 위해 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d9848-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="d9848-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d9848-113">요소</span><span class="sxs-lookup"><span data-stu-id="d9848-113">Element</span></span>|<span data-ttu-id="d9848-114">설명</span><span class="sxs-lookup"><span data-stu-id="d9848-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9848-115">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="d9848-116">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d9848-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9848-117">예제</span><span class="sxs-lookup"><span data-stu-id="d9848-117">Example</span></span>  
 <span data-ttu-id="d9848-118">다음 코드 예제는 XSD 형식을 .NET 형식에 매핑할 때 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9848-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9848-119">참조</span><span class="sxs-lookup"><span data-stu-id="d9848-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="d9848-120">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d9848-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d9848-121">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- <span data-ttu-id="d9848-122">[\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-122">[\<add> Element for \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="d9848-123">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d9848-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
