---
description: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소에 대해 자세히 알아보세요. <add>
title: <add> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 5a8cf22b21370e60086408f792f8137386d07aa3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713054"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<add> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소

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

| 요소 | 설명 |
| ------- | ------------|
| [**\<sectionName>** 요소](custom-element-2.md) | 및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다. |

## <a name="child-elements"></a>자식 요소

없음

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

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
