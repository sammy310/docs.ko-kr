---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215486"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소

<xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp; **\<섹션 이름 >**

## <a name="attributes"></a>특성

None

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | Description |
| --- | ----------- |
| <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 추가\<** ](add-element-for-custom-2.md)  | 사용자 지정 응용 프로그램 설정을 추가 합니다. |
| <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 제거\<** ](remove-element-for-custom-2.md) | 이전에 정의 된 설정을 제거 합니다. |
| <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 지우기\<** ](clear-element-for-custom-2.md) | 섹션에서 이전에 정의 된 모든 설정을 지웁니다. |

## <a name="remarks"></a>설명

**\<섹션 이름 >** 요소는 **\<configsections >** 요소의 **\<섹션 >** 태그에 의해 정의 되는 사용자 지정 요소입니다.

다음 표에서는 ConfigurationSettings의 개체 형식을 보여 줍니다. GetConfig 메서드는 각 구성 섹션 처리기에 대해를 반환 합니다.

| 구성 섹션 처리기                        | 반환 형식                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Configuration.DictionarySectionHandler> 및 <xref:System.Configuration.NameValueSectionHandler> 클래스를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다.

첫 번째 사용자 지정 요소는 `System.dll` 어셈블리의 <xref:System.Configuration.DictionarySectionHandler> 클래스에서 읽은 설정을 포함 하는 **\<dictionarySample >** 입니다. 두 번째 사용자 지정 요소는 `System.dll` 어셈블리의 <xref:System.Configuration.NameValueSectionHandler> 클래스에서 읽은 설정을 포함 하는 **mySection >\<** 됩니다.

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

이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
