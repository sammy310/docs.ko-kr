---
title: .NET Framework의 구성 파일 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: ab6f12be01899f5b7e54a7ec2d9675d502d88bc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555135"
---
# <a name="configuration-file-schema-for-the-net-framework"></a>.NET Framework의 구성 파일 스키마

구성 파일은 설정을 변경하고 응용 프로그램을 위한 정책을 설정하는 데 사용할 수 있는 표준 XML 파일입니다. .NET Framework 구성 스키마는 응용 프로그램의 동작을 제어하기 위해 구성 파일에 사용할 수 있는 요소로 구성됩니다. 이 섹션의 목차에는 시작, 런타임, 네트워크 및 구성 설정의 다른 형식에 대한 스키마 계층 구조가 반영되어 있습니다.

구성 파일의 형식, 형식 및 위치에 대 한 자세한 내용은 [앱 구성](../index.md)을 참조 하세요. 구성 파일을 직접 편집하려면 먼저 XML에 익숙해야 합니다.

> [!IMPORTANT]
> 구성 파일에서 XML 태그 및 특성은 대/소문자를 구분합니다.

## <a name="in-this-section"></a>섹션 내용

[**\<configuration>** 요소인](configuration-element.md)\
모든 구성 파일의 최상위 요소입니다.

[**\<assemblyBinding>** 요소인](assemblybinding-element-for-configuration.md)\
구성 수준에서 어셈블리 바인딩 정책을 지정합니다.

[**\<linkedConfiguration>** 요소인](linkedconfiguration-element.md)\
포함할 구성 파일을 지정합니다.

[시작 설정 스키마](./startup/index.md)\
사용할 공용 언어 런타임의 버전을 지정 하는 요소입니다.

[런타임 설정 스키마](./runtime/index.md)\
어셈블리 바인딩 및 런타임 동작을 구성 하는 요소입니다.

[네트워크 설정 스키마](./network/index.md)\
.NET Framework 인터넷에 연결 하는 방법을 지정 하는 요소입니다.

[암호화 설정 스키마](./cryptography/index.md)\
암호화 알고리즘을 구현 하는 클래스에 알고리즘 이름을 매핑하는 요소입니다.

[구성 섹션 스키마](configuration-sections-schema.md)\
사용자 지정 설정에 대 한 구성 섹션을 만들고 사용 하는 데 사용 되는 요소입니다.

[추적 및 디버그 설정 스키마](./trace-debug/index.md)\
추적 스위치 및 수신기를 지정 하는 요소입니다.

[컴파일러 및 언어 공급자 설정 스키마](./compiler/index.md)\
사용 가능한 언어 공급자의 컴파일러 구성을 지정 하는 요소입니다.

[응용 프로그램 설정 스키마](application-settings-schema.md)\
Windows Forms 또는 ASP.NET 응용 프로그램에서 응용 프로그램 범위 및 사용자 범위 설정을 저장 하 고 검색 하는 데 사용할 수 있는 요소입니다.

[앱 설정 스키마](./appsettings/index.md)\
파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.

[웹 설정 스키마](./web/index.md)\
ASP.NET가 IIS와 같은 호스트 응용 프로그램과 함께 작동 하는 방법을 구성 하기 위한 요소입니다. *Aspnet.config* 파일에서 사용됩니다.

[Windows Forms 구성 스키마](winforms/index.md)\
다중 모니터 및 높은 DPI 지원과 같은 사용자 지정을 포함 하는 Windows Forms 응용 프로그램 구성 섹션의 모든 요소입니다.

[WCF 구성 스키마](./wcf/index.md)\
WCF 서비스 및 클라이언트 응용 프로그램을 구성 하는 데 사용할 수 있는 모든 요소입니다.

[WCF 지시문 구문](./wcf-directive/index.md)\
`@ServiceHost`.Svc 컴파일러에서 사용 하는 페이지 관련 특성을 정의 하는 지시문에 대해 설명 합니다.

[WIF 구성 스키마](windows-identity-foundation/index.md)\
WIF (Windows Identity Foundation) 구성 스키마의 모든 요소입니다.

## <a name="related-sections"></a>관련 단원

[원격 설정 스키마](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))\
리모팅을 구현하는 클라이언트 및 서버 응용 프로그램을 구성하는 요소에 대해 설명합니다.

[ASP.NET Settings 스키마](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))\
ASP.NET 웹 응용 프로그램의 동작을 제어하는 요소에 대해 설명합니다.

[웹 서비스 설정 스키마](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))\
ASP.NET 웹 서비스와 해당 클라이언트를 제어하는 요소에 대해 설명합니다.

[.NET Framework 앱 구성](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))\
.NET Framework에서 보안, 어셈블리 바인딩 및 리모팅을 구성하는 방법에 대해 설명합니다.
