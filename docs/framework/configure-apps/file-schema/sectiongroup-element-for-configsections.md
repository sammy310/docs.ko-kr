---
title: <configSections>에 대한 <sectionGroup> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 750708483f9680745eef4531d86fa7ecaa329f51
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301187"
---
# <a name="sectiongroup-element-for-configsections"></a>\<sectionGroup > 요소에 대 한 \<configSections >

구성 섹션에 대 한 네임 스페이스를 정의합니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup>**

## <a name="syntax"></a>구문

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 필수 특성입니다.<br><br>정의 하는 섹션 그룹의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<configSections >** 요소](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 구성 섹션 및 네임 스페이스 선언을 포함합니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [ **\<section>** ](~/docs/framework/configure-apps/file-schema/section-element.md) | 구성 섹션 선언을 포함합니다. |

## <a name="remarks"></a>설명

구성 섹션에 대 한 컨테이너 태그를 만들고 하면 다른 사용자가 정의 하는 구성 섹션 이름과 충돌 하지 않습니다 섹션 그룹을 선언 합니다. 중첩할 수 있습니다  **\<sectionGroup >** 서로의 내부 요소입니다.

## <a name="example"></a>예제

다음 예제에서는 섹션 그룹 내의 섹션을 선언 하 고 섹션 그룹을 선언 하는 방법을 보여 줍니다.

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
