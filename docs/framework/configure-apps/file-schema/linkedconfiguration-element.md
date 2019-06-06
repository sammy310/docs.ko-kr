---
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
ms.openlocfilehash: 909ee7cbb7cd31cf213f305b23237cb69e295882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674651"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > 요소

포함할 구성 파일을 지정합니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<assemblyBinding>** ](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration>**

## <a name="syntax"></a>구문

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **href**  | 필수 특성입니다.<br><br>포함할 구성 파일의 URL입니다. 형식만 지원 합니다 **href** 특성이 `file://`합니다. 로컬 파일 및 UNC 파일 지원 됩니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<assemblyBinding >** 요소](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | 구성 수준에서 어셈블리 바인딩 정책을 지정합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

합니다  **\<linkedConfiguration >** 요소 구성 요소 어셈블리에 대 한 서비스를 단순화 합니다. 하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일을 포함 하는 어셈블리를 사용 하는 경우 어셈블리를 사용 하는 응용 프로그램의 구성 파일에 사용할 수는  **\<linkedConfiguration >** 구성 정보를 직접 포함 하지 않고 어셈블리 구성 파일을 포함 하는 요소입니다. 서비스는 구성 요소 어셈블리를 제공 하는 경우 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보를 제공 공용 구성 파일을 업데이트 합니다.

> [!NOTE]
> 합니다  **\<linkedConfiguration >** Windows side-by-side-매니페스트를 사용 하 여 응용 프로그램에 대 한 요소가 지원 되지 않습니다.

다음 규칙은 연결 된 구성 파일의 사용을 통제:

- 포함 된 구성 파일에만 로더 바인딩 정책에 영향을 설정과 로더만 사용 됩니다. 포함 된 구성 파일 설정 바인딩 정책 이외의 수 있지만 이러한 설정이 아무런 효과가 없습니다.

- 형식만 지원 합니다 `href` 특성은 `file://`합니다. 로컬 파일 및 UNC 파일 지원 됩니다.

- 구성 파일 마다 연결 된 구성 수에 제한이 없습니다.

- 모든 연결 된 구성 파일의 동작과 비슷하게 하나의 파일로 병합 되는 `#include` c에서 지시문 /C++합니다.

- 합니다  **\<linkedConfiguration >** 요소를 응용 프로그램 구성 파일에만 사용할 수는;에서 무시 됩니다 *Machine.config*합니다.

- 순환 참조가 검색 하 고 종료 됩니다. 즉, 경우 합니다  **\<linkedConfiguration >** 루프를 형성 하는 일련의 구성 파일의 요소, 루프 검색 되 고 중지 됩니다.

## <a name="example"></a>예제

다음 예제에서는 구성 파일을 로컬 하드 디스크를 포함 하는 방법을 보여 줍니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고자료

- [ **\<assemblyBinding >** 요소](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
