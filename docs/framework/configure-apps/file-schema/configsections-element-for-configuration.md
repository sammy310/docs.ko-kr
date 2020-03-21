---
title: <configuration>에 대한 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155351"
---
# <a name="configsections-element-for-configuration"></a>\<구성> 대한 \<구성섹션> 요소

구성 섹션 및 네임스페이스 선언을 포함합니다.

구성 &nbsp; &nbsp;>[** \<**](configuration-element.md) ** \<구성섹션>**

## <a name="attributes"></a>특성

None

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [**\<구성>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | Description |
| --- | ----------- |
| [**\<섹션>**](section-element.md) | 구성 섹션 선언을 포함합니다. |
| [**\<섹션 그룹>**](sectiongroup-element-for-configsections.md) | 구성 섹션에 대한 네임스페이스를 정의합니다. |
| [**\<>제거**](remove-element-for-configsections.md) | 미리 정의된 단면 또는 단면 그룹을 제거합니다. |
| [**\<클리어>**](clear-element-for-configsections.md) | 이전에 정의된 모든 단면 및 단면 그룹을 지웁니다. |

## <a name="remarks"></a>설명

이 요소가 구성 파일에 있는 경우 ** \<구성>** 요소의 첫 번째 자식 요소여야 합니다.

## <a name="example"></a>예제

다음 예제에서는 구성 섹션을 정의하고 해당 섹션에 대한 설정을 정의하는 방법을 보여 주며 있습니다.

```xml
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

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
