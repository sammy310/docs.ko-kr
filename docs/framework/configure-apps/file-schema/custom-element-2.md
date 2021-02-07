---
description: '자세히 알아보기: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소'
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: c1bb5b2fb321e2cc9235e02be2158c0875d42032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698728"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소

및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a>특성

None

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<add>**](add-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler>  | 사용자 지정 응용 프로그램 설정을 추가 합니다. |
| [**\<remove>**](remove-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | 이전에 정의 된 설정을 제거 합니다. |
| [**\<clear>**](clear-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler> | 섹션에서 이전에 정의 된 모든 설정을 지웁니다. |

## <a name="remarks"></a>설명

**\<sectionName>** 요소는 요소의 태그에 의해 정의 되는 사용자 지정 요소입니다 **\<section>** **\<configSections>** .

다음 표에서는 ConfigurationSettings의 개체 형식을 보여 줍니다. GetConfig 메서드는 각 구성 섹션 처리기에 대해를 반환 합니다.

| 구성 섹션 처리기                        | 반환 형식                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>예제

다음 예제에서는 및 클래스를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다 <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> .

첫 번째 사용자 지정 요소는 이며,이는 **\<dictionarySample>** <xref:System.Configuration.DictionarySectionHandler> 어셈블리의 클래스에서 읽은 설정을 포함 합니다 `System.dll` . 두 번째 사용자 지정 요소는 이며,이는 **\<mySection>** <xref:System.Configuration.NameValueSectionHandler> 어셈블리의 클래스에서 읽은 설정을 포함 합니다 `System.dll` .

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
