---
title: <add>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215445"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<add>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소

사용자 지정 응용 프로그램 설정을 추가 합니다. 각 **\<add>** 태그에는 키/값 쌍이 포함 되어 있습니다.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>구문

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a>특성

| attribute | Description |
| --------- | ----------- |
| **key**   | 필수 특성입니다.<br><br>설정의 이름을 지정 합니다. |
| **value** | 필수 특성입니다.<br><br>설정 값을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

| 요소 | Description |
| ------- | ------------|
| [**\<sectionName>** 요소인](custom-element-2.md) | 및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다. |

## <a name="child-elements"></a>자식 요소

None

## <a name="example"></a>예제

다음 예제에서는 사용자 지정 구성 섹션을 정의 하 고 요소를 사용 하 여 섹션에 설정을 추가 하는 방법을 보여 줍니다 **\<add>** .

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
