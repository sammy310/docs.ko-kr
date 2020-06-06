---
title: <configSections>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154532"
---
# <a name="remove-element-for-configsections"></a>\<configSections>에 대한 \<remove> 요소

미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>구문

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>attribute

|           | Description |
| --------- | ----------- |
| **name**  | 필수 특성입니다.<br><br>제거할 섹션 또는 섹션 그룹의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [**\<configSections>** 요소인](configsections-element-for-configuration.md) | 구성 섹션과 네임 스페이스 선언을 포함 합니다. |

## <a name="child-elements"></a>자식 요소

None

## <a name="remarks"></a>설명

요소를 사용 하 여 **\<remove>** 구성 파일 계층 구조에서 상위 수준에 정의 된 섹션 및 섹션 그룹을 응용 프로그램에서 제거할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 **\<remove>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 제거 하는 방법을 보여 줍니다.

다음 컴퓨터 구성 파일 코드는 섹션을 선언 합니다 **\<sampleSection>** .

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

다음 응용 프로그램 구성 파일 코드는 섹션을 제거 합니다 **\<sampleSection>** . 제거 후 응용 프로그램은에서 설정을 검색할 수 없습니다 **\<sampleSection>** .

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
