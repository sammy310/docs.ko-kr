---
title: <configuration>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155481"
---
# <a name="assemblybinding-element-for-configuration"></a>\<구성> 위한 \<어셈블리 바인딩> 요소

구성 수준에서 어셈블리 바인딩 정책을 지정합니다.

구성 &nbsp; &nbsp;>[** \<**](configuration-element.md) **어셈블리바인딩 \<>**

## <a name="syntax"></a>구문

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | Description |
| --------- | ----------- |
| **xmlns** | 필수 특성입니다.<br><br>어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다. 문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다. |

## <a name="parent-element"></a>부모 요소

|     | Description |
| --- | ----------- |
| [**\<구성>**](configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-element"></a>자식 요소

|     | Description |
| --- | ----------- |
| [**\<링크된 구성>**](linkedconfiguration-element.md) | 포함할 구성 파일을 지정합니다. |

## <a name="remarks"></a>설명

연결된Configuration>요소는 어셈블리 구성 설정을 복제하는 대신 응용 프로그램 구성 파일이 잘 알려진 위치에 어셈블리 구성 파일을 포함하도록 허용하여 구성 요소 어셈블리관리를 단순화합니다. [** \<**](linkedconfiguration-element.md)

> [!NOTE]
> ** \<링크된Configuration>** 요소는 Windows 나란히 매니페스트가 있는 응용 프로그램에 대해 지원되지 않습니다.

## <a name="example"></a>예제

다음 예제에서는 로컬 하드 디스크에 구성 파일을 포함하는 방법을 보여 주십습니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [.NET Framework의 구성 파일 스키마](index.md)
