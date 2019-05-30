---
title: <configSections>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 7c0173879c692588cc2e15f0b14a5687bb0404fb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300670"
---
# <a name="remove-element-for-configsections"></a>\<제거 > 요소에 대 한 \<configSections >

미리 정의 된 섹션 또는 섹션 그룹을 제거합니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**

## <a name="syntax"></a>구문

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 필수 특성입니다.<br><br>섹션 또는 제거할 섹션 그룹의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<configSections >** 요소](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 구성 섹션 및 네임 스페이스 선언을 포함합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

사용할 수는  **\<제거 >** 구성 파일 계층 구조의 상위 수준에 정의 된 응용 프로그램에서 섹션 및 섹션 그룹을 제거할 요소입니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<제거 >** 컴퓨터 구성 파일에서 이전에 정의 된 섹션을 제거할 응용 프로그램 구성 파일의 요소입니다.

다음 컴퓨터 구성 파일 코드 섹션을 선언  **\<sampleSection >** :

```xml
<!-- Machine.config file -->
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

다음 응용 프로그램 구성 파일 코드를 제거 합니다  **\<sampleSection >** 섹션입니다. 제거한 후 응용 프로그램의 설정을 검색할 수 없습니다  **\<sampleSection >** 합니다.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
