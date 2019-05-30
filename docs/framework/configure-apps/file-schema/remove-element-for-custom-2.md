---
title: <remove> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 062aa3921d29cffd33db2d96096ef25c2b819030
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300693"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<제거 > NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소

이전에 정의 된 설정을 제거합니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>구문

```xml
<add remove="key" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **key**   | 필수 특성입니다.<br><br>제거 설정의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

| 요소 | 설명 |
| ------- | ------------|
| [ **\<sectionName>** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

사용할 수는  **\<제거 >** 설정 구성 파일 계층 구조의 상위 수준에 정의 된 응용 프로그램에서 제거할 요소입니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<제거 >** 컴퓨터 구성 파일에서 이전에 정의 된 설정을 제거 하는 응용 프로그램 구성 파일의 요소입니다.

다음 컴퓨터 구성 파일 코드 섹션을 선언  **\<mySection >** 두 설정을 추가 하 고 `key1` 고 `key2`에:

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

다음 응용 프로그램 구성 파일 코드를 제거 합니다 `key2` 에서 설정  **\<mySection >** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
