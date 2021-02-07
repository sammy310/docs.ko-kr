---
description: '다음에 대 한 자세한 정보: <linkedConfiguration> 요소'
title: <linkedConfiguration> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: e4312cf788784241efc35304b632dfe1fdef1bc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698663"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration> 요소

포함할 구성 파일을 지정합니다.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a>Syntax

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>attribute

|           | 설명 |
| --------- | ----------- |
| **href**  | 필수 특성입니다.<br><br>포함할 구성 파일의 URL입니다. **Href** 특성에 대해 지원 되는 유일한 형식은 `file://` 입니다. 로컬 파일 및 UNC 파일이 지원 됩니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<assemblyBinding>** 요소](assemblybinding-element-for-configuration.md) | 구성 수준에서 어셈블리 바인딩 정책을 지정합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

**\<linkedConfiguration>** 요소는 구성 요소 어셈블리에 대 한 서비스를 단순화 합니다. 하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일이 있는 어셈블리를 사용 하는 경우 해당 어셈블리를 사용 하는 응용 프로그램의 구성 파일은 **\<linkedConfiguration>** 구성 정보를 직접 포함 하는 대신 요소를 사용 하 여 어셈블리 구성 파일을 포함할 수 있습니다. 구성 요소 어셈블리를 서비스할 때 공통 구성 파일을 업데이트 하면 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보가 제공 됩니다.

> [!NOTE]
> **\<linkedConfiguration>** Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에서는 요소가 지원 되지 않습니다.

다음 규칙은 연결 된 구성 파일의 사용을 제어 합니다.

- 포함 된 구성 파일의 설정은 로더 바인딩 정책에만 영향을 주며 로더에서 사용 됩니다. 포함 된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 이러한 설정은 적용 되지 않습니다.

- 특성에 대해 지원 되는 유일한 형식은 `href` `file://` 입니다. 로컬 파일 및 UNC 파일이 지원 됩니다.

- 구성 파일당 연결 된 구성 수에는 제약 조건이 없습니다.

- 모든 연결 된 구성 파일은 `#include` C/c + +의 지시문 동작과 유사 하 게 하나의 파일을 구성 하기 위해 병합 됩니다.

- **\<linkedConfiguration>** 요소는 응용 프로그램 구성 파일 에서만 허용 되며 *Machine.config* 에서는 무시 됩니다.

- 순환 참조가 감지 되 고 종료 됩니다. 즉, **\<linkedConfiguration>** 일련의 구성 파일 요소가 루프를 구성 하면 루프가 검색 되 고 중지 됩니다.

## <a name="example"></a>예제

다음 예제에서는 로컬 하드 디스크의 구성 파일을 포함 하는 방법을 보여 줍니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [**\<assemblyBinding>** 요소](assemblybinding-element-for-configuration.md)
- [.NET Framework에 대 한 구성 파일 스키마](index.md)
