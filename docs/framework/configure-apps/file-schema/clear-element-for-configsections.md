---
title: <configSections>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155429"
---
# <a name="clear-element-for-configsections"></a>\<구성에 대한 \<명확한> 요소>

이전에 정의된 모든 단면 및 단면 그룹을 지웁니다.

&nbsp; &nbsp; &nbsp; **구성 \<**>&nbsp; &nbsp;구성섹션 &nbsp;>명확한>[** \<**](configuration-element.md) [** \<**](configsections-element-for-configuration.md)

## <a name="syntax"></a>구문

```xml
<clear/>
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

명확한>요소는 현재 구성 파일의 이전 또는 구성 파일 계층 구조의 상위 수준에서 정의된 응용 프로그램에서 모든 섹션 및 단면 그룹을 제거합니다. ** \<**

## <a name="example"></a>예제

이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의하고 응용 프로그램 구성 파일에서 ** \<clear>** 요소를 사용하여 이전에 컴퓨터 구성 파일에 정의된 섹션을 지우는 방법을 보여 주며 이 예제를 보여 주며, 응용 프로그램 구성 파일에서 미리 정의된 섹션을 지우는 방법을 보여 주며 있습니다.

다음 컴퓨터 구성 파일 코드는 ** \<sampleSection>** 및 ** \<응용 **프로그램 구성 파일 앞에 읽히는 다른SampleSection>두 섹션을 선언합니다.

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

다음 응용 프로그램 구성 파일 코드는 이전에 선언된 모든 섹션을 지웁니다. 응용 프로그램은 컴퓨터 구성 파일에 선언된 섹션 중 하나에서 설정을 사용하거나 검색할 수 없습니다. 그러나, 그것은 ** \<다른에서** 설정을 사용할 수 ** \<있습니다명확한>** 요소 후 제공되기 때문에>섹션.

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

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
