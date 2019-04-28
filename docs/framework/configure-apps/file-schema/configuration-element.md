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
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705417"
---
# <a name="configuration-element"></a>\<구성 > 요소

공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.

**\<구성>**

## <a name="syntax"></a>구문

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a>특성

없음

## <a name="parent-element"></a>부모 요소

없음

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | 구성 수준에서 어셈블리 바인딩 정책을 지정합니다.|
| [**\<시작 >** 설정 스키마](~/docs/framework/configure-apps/file-schema/startup/index.md) | 시작 설정 스키마의 모든 요소입니다. |
| [**\<런타임 >** 설정 스키마](~/docs/framework/configure-apps/file-schema/runtime/index.md) | 런타임 설정 스키마의 모든 요소입니다. |
| [**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) | 원격 설정 스키마의 모든 요소입니다. |
| [**\<system.Net>** Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) | 네트워크 설정 스키마의 모든 요소입니다. |
| [**\<cryptographySettings >** 설정 스키마](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | 암호화 설정 스키마의 모든 요소입니다. |
| [**\<구성 >** 섹션 스키마](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | 구성 섹션 설정 스키마의 모든 요소입니다. |
| [추적 및 디버그 설정 스키마](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | 추적 및 디버그 설정 스키마의 모든 요소입니다. |
| [ASP.NET 구성 설정 스키마](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) | ASP.NET 웹 사이트 및 응용 프로그램을 구성 하기 위한 요소를 포함 하는 ASP.NET 구성 스키마의 모든 요소입니다. 레지스트리에 *Web.config* 파일입니다. |
| [**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) | 웹 서비스 설정 스키마의 모든 요소입니다. |
| [웹 설정 스키마](~/docs/framework/configure-apps/file-schema/web/index.md) | ASP.NET이 IIS와 같은 호스트 응용 프로그램과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다. 레지스트리에 *aspnet.config* 파일입니다. |

## <a name="remarks"></a>설명

각 구성 파일 하나만 있어야  **\<구성 >** 요소입니다.

## <a name="see-also"></a>참고자료

- [.NET Framework의 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
