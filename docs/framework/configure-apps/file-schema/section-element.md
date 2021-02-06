---
description: 다음에 대해 자세히 알아보세요. <section> element
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 7756f7ee3be2391a0d068708f3719083640b5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639941"
---
# <a name="section-element"></a>\<section> 요소

구성 섹션 선언을 포함 합니다.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a>Syntax

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>필수 특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 구성 섹션의 이름을 지정 합니다. |
| **type**  | 구성 파일에서 섹션을 읽는 구성 섹션 처리기 클래스의 이름을 지정 합니다. 형식 값의 구문은 "정규화 된 섹션-클래스 이름, 단순 어셈블리 이름"입니다. 단순 어셈블리 이름은 *.dll* 파일 확장명이 없는 루트 파일 이름입니다. |

## <a name="optional-attributes"></a>선택적 특성

다음 특성은 ASP.NET 응용 프로그램에만 적용 됩니다. 구성 시스템에서는 다른 응용 프로그램 유형에 대 한 이러한 특성을 무시 합니다.

|                     | 설명 |
| ------------------- | ----------- |
| **allowDefinition** | 섹션을 사용할 수 있는 구성 파일을 지정 합니다. 다음 값 중 하나를 사용합니다.<br><br>**모든 범위**<br>섹션을 모든 구성 파일에서 사용할 수 있습니다. 기본값입니다.<br>**MachineOnly**<br>섹션을 컴퓨터 구성 파일 (*Machine.config*) 에서만 사용할 수 있습니다.<br>**MachineToApplication**<br>컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에서 섹션을 사용할 수 있습니다. |
| **allowLocation**   | 요소 내에서 섹션을 사용할 수 있는지 여부를 확인 **\<location>** 합니다. 다음 값 중 하나를 사용합니다.<br><br>**true**<br>요소 내에 섹션을 사용할 수 있습니다 **\<location>** . 기본값입니다.<br>**false**<br>에서는 요소 내에 섹션을 사용할 수 없습니다 **\<location>** . |

## <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configSections>** 요소](configsections-element-for-configuration.md) | 구성 섹션과 네임 스페이스 선언을 포함 합니다. |
| [**\<sectionGroup>** 요소인](sectiongroup-element-for-configsections.md) | 구성 섹션에 대 한 네임 스페이스를 정의 합니다. |

> [!NOTE]
> **\<section>** 요소는 또는 중 하나 **\<configSections>** 또는 둘 다의 자식 요소입니다 **\<sectionGroup>** .

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

구성 섹션을 선언 하는 것은 기본적으로 구성 파일에 대 한 새 요소를 정의 합니다. 새 요소는 구성 섹션 처리기 (즉, 인터페이스를 구현 하는 클래스)가 읽는 설정을 포함 합니다 <xref:System.Configuration.IConfigurationSectionHandler> . 사용자가 정의 하는 섹션의 특성 및 자식 요소는 설정을 읽는 데 사용 하는 섹션 처리기에 따라 달라 집니다.

*Machine.config* 파일에서 구성 섹션 처리기를 선언 하면 **allowDefinition** 특성이 달리 지정 되지 않는 한 해당 컴퓨터의 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
