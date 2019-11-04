---
title: <dateTimeSerialization> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459268"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="9ef48-102">\<dateTimeSerialization > 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="9ef48-103"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="9ef48-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9ef48-104">\<configuration></span></span>  
<span data-ttu-id="9ef48-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="9ef48-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef48-106">구문</span><span class="sxs-lookup"><span data-stu-id="9ef48-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ef48-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9ef48-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ef48-109">특성</span><span class="sxs-lookup"><span data-stu-id="9ef48-109">Attributes</span></span>  
  
|<span data-ttu-id="9ef48-110">특성</span><span class="sxs-lookup"><span data-stu-id="9ef48-110">Attributes</span></span>|<span data-ttu-id="9ef48-111">설명</span><span class="sxs-lookup"><span data-stu-id="9ef48-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="9ef48-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9ef48-112">Optional.</span></span> <span data-ttu-id="9ef48-113">serialization 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-113">Specifies the serialization mode.</span></span> <span data-ttu-id="9ef48-114"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="9ef48-115">기본값은 **RoundTrip**입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ef48-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-116">Child Elements</span></span>  
 <span data-ttu-id="9ef48-117">없음.</span><span class="sxs-lookup"><span data-stu-id="9ef48-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ef48-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9ef48-119">요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-119">Element</span></span>|<span data-ttu-id="9ef48-120">설명</span><span class="sxs-lookup"><span data-stu-id="9ef48-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ef48-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="9ef48-121">system.xml.serialization</span></span>|<span data-ttu-id="9ef48-122">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ef48-123">주의</span><span class="sxs-lookup"><span data-stu-id="9ef48-123">Remarks</span></span>  
 <span data-ttu-id="9ef48-124">.NET Framework의 1.0, 1.1 및 2.0 이상 버전에서 이 속성이 **Local**로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="9ef48-125">즉, 로컬 표준 시간대 정보는 항상 serialize 된 데이터에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="9ef48-126">.NET Framework 이전 버전과의 호환성을 제공하려면 이 속성을 **Local**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9ef48-127">이 속성이 **Roundtrip**으로 설정된 .NET Framework 버전 2.0 이상에서는 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="9ef48-128">그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="9ef48-129">이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 애플리케이션에 대해 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef48-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef48-130">참조</span><span class="sxs-lookup"><span data-stu-id="9ef48-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="9ef48-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9ef48-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9ef48-132">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="9ef48-133">\<schemaImporterExtensions에 대 한 > 요소 \<추가 ></span><span class="sxs-lookup"><span data-stu-id="9ef48-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="9ef48-134">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="9ef48-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
