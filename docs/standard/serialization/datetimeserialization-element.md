---
title: <dateTimeSerialization> 요소
description: 이 문서에서는 DateTime 개체의 serialization 모드를 결정하는 <dateTimeSerialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375821"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="bfdcd-103">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="bfdcd-104"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="bfdcd-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bfdcd-105">\<configuration></span></span>  
<span data-ttu-id="bfdcd-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="bfdcd-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdcd-107">구문</span><span class="sxs-lookup"><span data-stu-id="bfdcd-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfdcd-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bfdcd-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfdcd-110">특성</span><span class="sxs-lookup"><span data-stu-id="bfdcd-110">Attributes</span></span>  
  
|<span data-ttu-id="bfdcd-111">특성</span><span class="sxs-lookup"><span data-stu-id="bfdcd-111">Attributes</span></span>|<span data-ttu-id="bfdcd-112">설명</span><span class="sxs-lookup"><span data-stu-id="bfdcd-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="bfdcd-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-113">Optional.</span></span> <span data-ttu-id="bfdcd-114">serialization 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-114">Specifies the serialization mode.</span></span> <span data-ttu-id="bfdcd-115"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="bfdcd-116">기본값은 **RoundTrip**입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfdcd-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-117">Child Elements</span></span>  
 <span data-ttu-id="bfdcd-118">없음</span><span class="sxs-lookup"><span data-stu-id="bfdcd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfdcd-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bfdcd-120">요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-120">Element</span></span>|<span data-ttu-id="bfdcd-121">설명</span><span class="sxs-lookup"><span data-stu-id="bfdcd-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfdcd-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="bfdcd-122">system.xml.serialization</span></span>|<span data-ttu-id="bfdcd-123">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfdcd-124">설명</span><span class="sxs-lookup"><span data-stu-id="bfdcd-124">Remarks</span></span>  
 <span data-ttu-id="bfdcd-125">.NET Framework의 1.0, 1.1 및 2.0 이상 버전에서 이 속성이 **Local**로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="bfdcd-126">즉, 로컬 표준 시간대 정보는 항상 직렬화된 데이터에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="bfdcd-127">.NET Framework 이전 버전과의 호환성을 제공하려면 이 속성을 **Local**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="bfdcd-128">이 속성이 **Roundtrip**으로 설정된 .NET Framework 버전 2.0 이상에서는 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="bfdcd-129">그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="bfdcd-130">이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 애플리케이션에 대해 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdcd-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdcd-131">참조</span><span class="sxs-lookup"><span data-stu-id="bfdcd-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="bfdcd-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bfdcd-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="bfdcd-133">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="bfdcd-134">\<schemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-134">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="bfdcd-135">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="bfdcd-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
