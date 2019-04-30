---
title: <schemaImporterExtensions> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 43f8439708c73e8e5241a923360caf549bf09d8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017967"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="a53ea-102">\<schemaImporterExtensions > 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="a53ea-103"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a53ea-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="a53ea-104">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a53ea-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53ea-105">구문</span><span class="sxs-lookup"><span data-stu-id="a53ea-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="a53ea-106">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-106">Child Elements</span></span>  
  
|<span data-ttu-id="a53ea-107">요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-107">Element</span></span>|<span data-ttu-id="a53ea-108">설명</span><span class="sxs-lookup"><span data-stu-id="a53ea-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a53ea-109">\<추가 > 요소에 대 한 \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="a53ea-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="a53ea-110"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 매핑을 만들기 위해 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a53ea-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="a53ea-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a53ea-112">요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-112">Element</span></span>|<span data-ttu-id="a53ea-113">설명</span><span class="sxs-lookup"><span data-stu-id="a53ea-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a53ea-114">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="a53ea-115">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a53ea-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a53ea-116">예제</span><span class="sxs-lookup"><span data-stu-id="a53ea-116">Example</span></span>  
 <span data-ttu-id="a53ea-117">다음 코드 예제에서는 XSD 형식을 .NET Framework 형식으로 매핑할 때 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a53ea-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a53ea-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a53ea-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="a53ea-119">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a53ea-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a53ea-120">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="a53ea-121">\<추가 > 요소에 대 한 \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="a53ea-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="a53ea-122">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="a53ea-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
