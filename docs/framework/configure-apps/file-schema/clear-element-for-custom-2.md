---
title: <clear> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e5ab12150c5200dc346e950541443d5286f739c8
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301244"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<지우기 > NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소

섹션에서 이전에 정의 된 모든 설정을 지웁니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>구문

```xml
<clear />
```

## <a name="attributes"></a>특성

없음

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ------------|
| [ **\<sectionName>** Element](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

사용할 수는  **\<지우기 >** 구성 파일 계층 구조의 상위 수준에 정의 된 응용 프로그램에서 모든 설정을 제거 하는 요소입니다.

## <a name="example"></a>예제

이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다 합니다  **\<지우기 >** 요소에서 이전에 정의 된 섹션의 선택을 취소 하는 응용 프로그램 구성 파일에는 컴퓨터 구성 파일입니다.

다음 컴퓨터 구성 파일 코드 섹션을 선언  **\<mySection >** :

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

다음 응용 프로그램 구성 파일 코드의 모든 설정을 제거  **\<mySection >** 합니다. 응용 프로그램에 선언 된 설정 중 필요한 설정을 검색할 수 없습니다는에  **\<mySection >** 컴퓨터 구성 파일의 섹션입니다.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
