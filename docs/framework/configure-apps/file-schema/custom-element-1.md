---
title: 싱글태그섹션핸들러용 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155156"
---
# <a name="custom-element-for-singletagsectionhandler"></a>싱글태그섹션핸들러용 사용자 지정 요소

\<섹션> 요소에 의해 정의되고 <xref:System.Configuration.SingleTagSectionHandler> 클래스를 사용하는 사용자 지정 구성 섹션에서 설정을 정의합니다.

구성 &nbsp; &nbsp;>[** \<**](configuration-element.md) * \<섹션이름>*

## <a name="syntax"></a>구문

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>특성

특성 및 특성 값은 사용자가 정의합니다.

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [**\<구성>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

None

## <a name="remarks"></a>설명

섹션Name>요소는 [** \<구성**](configsections-element-for-configuration.md) 섹션>요소의 [** \<>**](section-element.md) 태그에 의해 정의된 사용자 지정 요소입니다. ** \<** 구성 시스템은 을 <xref:System.Collections.IDictionary> 호출할 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>때 개체를 반환합니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Configuration.SingleTagSectionHandler> ** \<sampleSection>** 라는 사용자 지정 요소를 선언 합니다 만 클래스에서 읽은 설정을 포함 합니다.

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

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
