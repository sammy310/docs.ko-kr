---
title: <configuration>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: f5992a6085c32d37f56319cf8b2c361542c441e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674833"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding > 요소에 대 한 \<구성 >

구성 수준에서 어셈블리 바인딩 정책을 지정합니다.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp; **\<assemblyBinding>**

## <a name="syntax"></a>구문

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **xmlns** | 필수 특성입니다.<br><br>어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다. 문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-element"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [ **\<linkedConfiguration>** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | 포함할 구성 파일을 지정합니다. |

## <a name="remarks"></a>설명

합니다 [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) 어셈블리를 포함 하도록 응용 프로그램 구성 파일의 구성 파일을 허용 하 여 구성 요소 어셈블리의 관리를 간소화 하는 요소 잘 알려진 위치 대신 복제 어셈블리 구성 설정.

> [!NOTE]
> 합니다  **\<linkedConfiguration >** Windows side-by-side-매니페스트를 사용 하 여 응용 프로그램에 대 한 요소가 지원 되지 않습니다.

## <a name="example"></a>예제

다음 예제에서는 로컬 하드 디스크의 구성 파일을 포함 하는 방법을 보여 줍니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
