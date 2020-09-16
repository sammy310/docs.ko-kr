---
title: <configuration> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544692"
---
# <a name="configuration-element"></a>\<configuration> 요소

공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.

**\<configuration>**

## <a name="syntax"></a>구문

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>특성

None

## <a name="parent-element"></a>부모 요소

None

## <a name="child-elements"></a>자식 요소

|     | Description |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | 구성 수준에서 어셈블리 바인딩 정책을 지정합니다.|
| [**\<startup>** 설정 스키마](./startup/index.md) | 시작 설정 스키마의 모든 요소입니다. |
| [**\<runtime>** 설정 스키마](./runtime/index.md) | 런타임 설정 스키마의 모든 요소입니다. |
| [**\<system.runtime.remoting>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | 원격 설정 스키마의 모든 요소입니다. |
| [**\<system.Net>** 설정 스키마](./network/index.md) | 네트워크 설정 스키마의 모든 요소입니다. |
| [**\<cryptographySettings>** 설정 스키마](./cryptography/index.md) | 암호화 설정 스키마의 모든 요소입니다. |
| [**\<configuration>** 섹션 스키마](configuration-sections-schema.md) | 구성 섹션 설정 스키마의 모든 요소입니다. |
| [추적 및 디버그 설정 스키마](./trace-debug/index.md) | 추적 및 디버그 설정 스키마의 모든 요소입니다. |
| [ASP.NET 구성 설정 스키마](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | ASP.NET 웹 사이트 및 응용 프로그램을 구성 하기 위한 요소를 포함 하는 ASP.NET 구성 스키마의 모든 요소입니다. *Web.config* 파일에 사용 됩니다. |
| [**\<webServices>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | 웹 서비스 설정 스키마의 모든 요소입니다. |
| [웹 설정 스키마](./web/index.md) | ASP.NET이 IIS와 같은 호스트 애플리케이션과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다. *aspnet.config* 파일에 사용 됩니다. |

## <a name="remarks"></a>설명

각 구성 파일에는 정확히 하나의 요소만 포함 되어야 합니다 **\<configuration>** .

## <a name="see-also"></a>참조

- [.NET Framework의 구성 파일 스키마](index.md)
