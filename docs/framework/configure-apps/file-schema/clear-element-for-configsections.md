---
title: <configSections>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e79def513637937262d00b0edb1b0f7676fd120b
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300798"
---
# <a name="clear-element-for-configsections"></a>\<지우기 > 요소에 대 한 \<configSections >

모든 이전에 정의 된 섹션 및 섹션 그룹을 지웁니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>구문

```xml
<clear/>
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

합니다  **\<지우기 >** 요소 또는 구성 파일 계층 구조의 상위 수준에 현재 구성 파일에서 이전에 정의 된 응용 프로그램에서 모든 섹션 및 섹션 그룹을 제거 합니다.

## <a name="example"></a>예제

이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다 합니다  **\<지우기 >** 요소에서 이전에 정의 된 섹션의 선택을 취소 하는 응용 프로그램 구성 파일에는 컴퓨터 구성 파일입니다.

다음 컴퓨터 구성 파일 코드에는 두 섹션이 선언  **\<sampleSection >** 하 고  **\<anotherSampleSection >** , 응용 프로그램 전에 읽은 구성 파일:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

다음 응용 프로그램 구성 파일 코드는 이전에 선언 된 모든 섹션을 지웁니다. 응용 프로그램을 사용 하거나 컴퓨터 구성 파일에 선언 된 섹션 중 하나에서 설정을 가져올 수 없습니다. 그러나 설정에서 사용할 수 있습니다  **\<anotherSection >** 후 있기 때문에  **\<지우기 >** 요소입니다.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
