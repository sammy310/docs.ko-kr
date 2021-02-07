---
description: '에 대 한 자세한 정보: <assemblyBinding> 요소 <configuration>'
title: <configuration>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 5cc3fc7cccd4b9dc7b62815734ff76e32e2243d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730111"
---
# <a name="assemblybinding-element-for-configuration"></a>\<configuration>에 대한 \<assemblyBinding> 요소

구성 수준에서 어셈블리 바인딩 정책을 지정합니다.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Syntax

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | 설명 |
| --------- | ----------- |
| **xmlns** | 필수 특성입니다.<br><br>어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다. 문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-element"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | 포함할 구성 파일을 지정합니다. |

## <a name="remarks"></a>설명

[**\<linkedConfiguration>**](linkedconfiguration-element.md)요소는 응용 프로그램 구성 파일이 어셈블리 구성 설정을 복제 하는 대신 잘 알려진 위치에 어셈블리 구성 파일을 포함 하도록 허용 하 여 구성 요소 어셈블리의 관리를 간소화 합니다.

> [!NOTE]
> **\<linkedConfiguration>** Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에서는 요소가 지원 되지 않습니다.

## <a name="example"></a>예제

다음 예제에서는 로컬 하드 디스크에 구성 파일을 포함 하는 방법을 보여 줍니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [.NET Framework에 대 한 구성 파일 스키마](index.md)
