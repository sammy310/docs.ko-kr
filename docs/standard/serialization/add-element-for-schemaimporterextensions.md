---
title: <schemaImporterExtensions>에 대한 <add> 요소
description: <add> 요소는 XmlSchemaImporter 클래스가 XSD 형식을 .NET Framework 형식에 매핑하기 위해 사용하는 형식을 추가합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378474"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="d28a6-103">\<\<schemaImporterExtensions>에 대한 add> 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="d28a6-104"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="d28a6-105">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d28a6-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="d28a6-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d28a6-106">\<configuration></span></span>  
<span data-ttu-id="d28a6-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="d28a6-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="d28a6-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d28a6-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="d28a6-109">\<add></span><span class="sxs-lookup"><span data-stu-id="d28a6-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28a6-110">구문</span><span class="sxs-lookup"><span data-stu-id="d28a6-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d28a6-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d28a6-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d28a6-113">특성</span><span class="sxs-lookup"><span data-stu-id="d28a6-113">Attributes</span></span>  
  
|<span data-ttu-id="d28a6-114">특성</span><span class="sxs-lookup"><span data-stu-id="d28a6-114">Attribute</span></span>|<span data-ttu-id="d28a6-115">설명</span><span class="sxs-lookup"><span data-stu-id="d28a6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d28a6-116">**name**</span><span class="sxs-lookup"><span data-stu-id="d28a6-116">**name**</span></span>|<span data-ttu-id="d28a6-117">인스턴스를 찾는 데 사용되는 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="d28a6-118">**type**</span><span class="sxs-lookup"><span data-stu-id="d28a6-118">**type**</span></span>|<span data-ttu-id="d28a6-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d28a6-119">Required.</span></span> <span data-ttu-id="d28a6-120">추가할 스키마 확장 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="d28a6-121">**type** 특성 값은 한 줄로 표시되어야 하며 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="d28a6-122">GAC(전역 어셈블리 캐시)에 추가되는 어셈블리에는 서명된 어셈블리의 버전, 문화권 및 공개 키 토큰도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d28a6-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-123">Child Elements</span></span>  
 <span data-ttu-id="d28a6-124">없음</span><span class="sxs-lookup"><span data-stu-id="d28a6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d28a6-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d28a6-126">요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-126">Element</span></span>|<span data-ttu-id="d28a6-127">설명</span><span class="sxs-lookup"><span data-stu-id="d28a6-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d28a6-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="d28a6-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="d28a6-129"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d28a6-130">예제</span><span class="sxs-lookup"><span data-stu-id="d28a6-130">Example</span></span>  
 <span data-ttu-id="d28a6-131">다음 코드 예제에서는 XmlSchemaImporter가 형식을 매핑할 때 사용할 수 있는 확장 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d28a6-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d28a6-132">참조</span><span class="sxs-lookup"><span data-stu-id="d28a6-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="d28a6-133">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="d28a6-134">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="d28a6-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
