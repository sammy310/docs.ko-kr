---
title: SingleTagSectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635394"
---
# <a name="custom-element-for-singletagsectionhandler"></a>SingleTagSectionHandler에 대 한 사용자 지정 요소

요소에 의해 정의 되 \<section> 고 클래스를 사용 하는 사용자 지정 구성 섹션의 설정을 정의 합니다 <xref:System.Configuration.SingleTagSectionHandler> .

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*

## <a name="syntax"></a>구문

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a>특성

특성 및 특성 값은 사용자 정의 됩니다.

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

None

## <a name="remarks"></a>설명

**\<sectionName>** 요소는 요소의 태그에 의해 정의 되는 사용자 지정 요소입니다 [**\<section>**](section-element.md) [**\<configSections>**](configsections-element-for-configuration.md) . 를 호출할 때 구성 시스템에서 개체를 반환 합니다 <xref:System.Collections.IDictionary> <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .

## <a name="example"></a>예제

다음 예제에서는 **\<sampleSection>** 클래스에서 읽은 설정을 포함 하는 라는 사용자 지정 요소를 선언 합니다 <xref:System.Configuration.SingleTagSectionHandler> .

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 *없는 web.config 파일* 에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
