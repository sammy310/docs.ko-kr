---
title: <dateTimeSerialization> 요소
description: 이 문서에서는 DateTime 개체의 serialization 모드를 결정하는 <dateTimeSerialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 1623517e66955c14b7e738c860ec16086fe30429
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678976"
---
# <a name="datetimeserialization-element"></a>\<dateTimeSerialization> 요소

<xref:System.DateTime> 개체의 serialization 모드를 결정합니다.  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a>구문  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|----------------|-----------------|  
|`mode`|선택 사항입니다. serialization 모드를 지정합니다. <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다. 기본값은 **RoundTrip** 입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|system.xml.serialization|XML serialization을 제어하기 위한 최상위 요소입니다.|  
  
## <a name="remarks"></a>설명  

이 속성이 **Local** 로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 지정됩니다. 즉, 로컬 표준 시간대 정보는 항상 직렬화된 데이터에 포함됩니다.
  
이 속성이 **Roundtrip** 으로 설정되면 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다. 그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다. 이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 애플리케이션에 대해 이를 사용하는 것이 좋습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [구성 파일 스키마](../../framework/configure-apps/file-schema/index.md)
- [\<schemaImporterExtensions> 요소](schemaimporterextensions-element.md)
- [\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소
- [\<system.xml.serialization> 요소](system-xml-serialization-element.md)
