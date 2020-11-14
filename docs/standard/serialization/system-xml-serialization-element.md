---
title: <system.xml.serialization> 요소
description: 이 문서에서는 XML serialization을 제어하기 위한 최상위 요소인 <system.xml.serialization> 요소에 대해 설명합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 6291799aadc429e943996f2256d773ac36dd370f
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282393"
---
# <a name="systemxmlserialization-element"></a>\<system.xml.serialization> 요소

XML serialization을 제어하기 위한 최상위 요소입니다. 구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../framework/configure-apps/file-schema/index.md)를 참조하세요.

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a>구문

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[\<dateTimeSerialization> 요소](datetimeserialization-element.md)|<xref:System.DateTime> 개체의 serialization 모드를 결정합니다.|
|[\<schemaImporterExtensions> 요소](schemaimporterextensions-element.md)|<xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET 형식에 매핑하는 데 사용되는 형식을 포함합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[\<configuration> 요소](../../framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|

## <a name="example"></a>예제

다음 코드 예제는 <xref:System.DateTime> 개체의 직렬화 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET 형식에 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.

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

## <a name="see-also"></a>참조

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [구성 파일 스키마](../../framework/configure-apps/file-schema/index.md)
- [\<dateTimeSerialization> 요소](datetimeserialization-element.md)
- [\<schemaImporterExtensions> 요소](schemaimporterextensions-element.md)
- [\<add>에 대한 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 요소
