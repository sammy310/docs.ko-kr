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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154532"
---
# <a name="remove-element-for-configsections"></a>\<> 구성에 \<대한> 요소 제거

미리 정의된 단면 또는 단면 그룹을 제거합니다.

[**\<구성>**](configuration-element.md)\
&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>제거**

## <a name="syntax"></a>구문

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a>attribute

|           | Description |
| --------- | ----------- |
| **(이름)**  | 필수 특성입니다.<br><br>제거할 단면 또는 단면 그룹의 이름을 지정합니다. |

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [** \<>구성섹션** 요소](configsections-element-for-configuration.md) | 구성 섹션 및 네임스페이스 선언을 포함합니다. |

## <a name="child-elements"></a>자식 요소

None

## <a name="remarks"></a>설명

제거>요소를 사용하여 구성 파일 계층 구조의 상위 수준에서 정의된 응용 프로그램에서 섹션 및 단면 그룹을 제거할 수 있습니다. ** \<**

## <a name="example"></a>예제

다음 예제에서는 응용 프로그램 구성 파일에서 ** \<제거>** 요소를 사용하여 이전에 컴퓨터 구성 파일에 정의된 섹션을 제거하는 방법을 보여 주습니다.

다음 컴퓨터 구성 파일 코드는 섹션 ** \<sampleSection>** 선언합니다.

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

다음 응용 프로그램 구성 파일 코드는 ** \<샘플섹션을>.** 제거 후 응용 프로그램은 ** \<sampleSection>** 설정을 검색할 수 없습니다.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
