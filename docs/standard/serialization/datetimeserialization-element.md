---
title: <dateTimeSerialization> 요소
description: 이 문서에서는 DateTime 개체의 serialization 모드를 결정하는 <dateTimeSerialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 90ae911c8942fef7a9e8238921990b0a52a47ca0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281763"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="d6ba9-103">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="d6ba9-104"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="d6ba9-105">구문</span><span class="sxs-lookup"><span data-stu-id="d6ba9-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6ba9-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d6ba9-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6ba9-108">특성</span><span class="sxs-lookup"><span data-stu-id="d6ba9-108">Attributes</span></span>  
  
|<span data-ttu-id="d6ba9-109">특성</span><span class="sxs-lookup"><span data-stu-id="d6ba9-109">Attributes</span></span>|<span data-ttu-id="d6ba9-110">설명</span><span class="sxs-lookup"><span data-stu-id="d6ba9-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="d6ba9-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-111">Optional.</span></span> <span data-ttu-id="d6ba9-112">serialization 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-112">Specifies the serialization mode.</span></span> <span data-ttu-id="d6ba9-113"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="d6ba9-114">기본값은 **RoundTrip** 입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6ba9-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-115">Child Elements</span></span>  
 <span data-ttu-id="d6ba9-116">없음</span><span class="sxs-lookup"><span data-stu-id="d6ba9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6ba9-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d6ba9-118">요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-118">Element</span></span>|<span data-ttu-id="d6ba9-119">설명</span><span class="sxs-lookup"><span data-stu-id="d6ba9-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6ba9-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="d6ba9-120">system.xml.serialization</span></span>|<span data-ttu-id="d6ba9-121">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6ba9-122">설명</span><span class="sxs-lookup"><span data-stu-id="d6ba9-122">Remarks</span></span>  

<span data-ttu-id="d6ba9-123">이 속성이 **Local** 로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-123">When this property is set to **Local** , <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="d6ba9-124">즉, 로컬 표준 시간대 정보는 항상 직렬화된 데이터에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-124">That is, local time zone information is always included with the serialized data.</span></span>
  
<span data-ttu-id="d6ba9-125">이 속성이 **Roundtrip** 으로 설정되면 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-125">When this property is set to **Roundtrip** , <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="d6ba9-126">그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-126">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="d6ba9-127">이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 애플리케이션에 대해 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ba9-127">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ba9-128">참조</span><span class="sxs-lookup"><span data-stu-id="d6ba9-128">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="d6ba9-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d6ba9-129">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d6ba9-130">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-130">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- <span data-ttu-id="d6ba9-131">[\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-131">[\<add> Element for \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="d6ba9-132">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="d6ba9-132">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
