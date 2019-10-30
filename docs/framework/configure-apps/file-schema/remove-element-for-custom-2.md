---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc1519a794e24e04074dd2a674ecc2c0f3666521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118561"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 > 요소 \<제거

이전에 정의 된 설정을 제거 합니다.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<섹션 이름 >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<제거**

## <a name="syntax"></a>구문

```xml
<add remove="key" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **key**   | 필수 특성입니다.<br><br>제거할 설정의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

| 요소 | 설명 |
| ------- | ------------|
| [ **\<섹션 이름 >** 요소인](custom-element-2.md) | <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>주의

**\<제거 >** 요소를 사용 하 여 구성 파일 계층 구조에서 상위 수준으로 정의 된 응용 프로그램에서 설정을 제거할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 응용 프로그램 구성 파일에서 **\<제거 >** 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 설정을 제거 하는 방법을 보여 줍니다.

다음 컴퓨터 구성 파일 코드는 **\<mysection >** 섹션을 선언 하 고이에 `key1` 및 `key2`두 가지 설정을 추가 합니다.

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

다음 응용 프로그램 구성 파일 코드는 **\<mySection >** 에서 `key2` 설정을 제거 합니다.

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.

## <a name="see-also"></a>참조

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
