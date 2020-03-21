---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153734"
---
# <a name="section-element"></a>\<단면> 요소

구성 섹션 선언을 포함합니다.

[**\<구성>**](configuration-element.md)\
&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션>**

[**\<구성>**](configuration-element.md)\
&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<섹션 그룹>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션>**

## <a name="syntax"></a>구문

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>필수 특성

|           | Description |
| --------- | ----------- |
| **(이름)**  | 구성 섹션의 이름을 지정합니다. |
| **종류**  | 구성 파일에서 섹션을 읽는 구성 섹션 처리기 클래스의 이름을 지정합니다. 형식 값에는 "정규화된 섹션-핸들러 클래스 이름, 간단한 어셈블리 이름"이라는 구문이 있습니다. 간단한 어셈블리 이름은 *.dll* 파일 확장자 없이 루트 파일 이름입니다. |

## <a name="optional-attributes"></a>선택적 특성

다음 특성은 ASP.NET 응용 프로그램에만 적용됩니다. 구성 시스템은 다른 응용 프로그램 형식에 대해 이러한 특성을 무시합니다.

|                     | Description |
| ------------------- | ----------- |
| **허용정의** | 섹션에서 사용할 수 있는 구성 파일을 지정합니다. 다음 값 중 하나를 사용합니다.<br><br>**모든 범위**<br>섹션을 모든 구성 파일에서 사용할 수 있습니다. 이것이 기본값입니다.<br>**기계 만**<br>섹션을 컴퓨터 구성*파일(Machine.config)에서만*사용할 수 있습니다.<br>**기계 응용 프로그램**<br>섹션을 컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에 사용할 수 있습니다. |
| **허용위치**   | 위치>요소 내에서 단면을 사용할 수 있는지 여부를 결정합니다. ** \<** 다음 값 중 하나를 사용합니다.<br><br>**true**<br>위치>요소 내에서 섹션을 사용할 수 있습니다. ** \<** 이것이 기본값입니다.<br>**false**<br>위치>요소 내에서 섹션을 사용할 수 없습니다. ** \<** |

## <a name="parent-elements"></a>부모 요소

|     | Description |
| --- | ----------- |
| [** \<>구성섹션** 요소](configsections-element-for-configuration.md) | 구성 섹션 및 네임스페이스 선언을 포함합니다. |
| [** \<섹션그룹>** 요소](sectiongroup-element-for-configsections.md) | 구성 섹션에 대한 네임스페이스를 정의합니다. |

> [!NOTE]
> 섹션>요소는 ** \<구성섹션>** 또는 ** \<** ** \<섹션그룹>** 하위 요소이지만 둘 다 는 아닙니다.

## <a name="child-elements"></a>자식 요소

None

## <a name="remarks"></a>설명

구성 섹션을 선언하는 것은 기본적으로 구성 파일에 대한 새 요소를 정의합니다. 새 요소에는 구성 섹션 처리기(즉, 인터페이스를 구현하는 <xref:System.Configuration.IConfigurationSectionHandler> 클래스)가 읽는 설정이 포함되어 있습니다. 정의하는 섹션의 특성 및 자식 요소는 설정을 읽는 데 사용하는 섹션 처리기에 따라 다릅니다.

*Machine.config* 파일에서 구성 섹션 처리기를 선언하면 **allowDefinition** 특성이 달리 지정하지 않는 한 해당 컴퓨터의 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 구성 섹션을 정의하고 해당 섹션에 대한 설정을 정의하는 방법을 보여 주며 있습니다.

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

이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
