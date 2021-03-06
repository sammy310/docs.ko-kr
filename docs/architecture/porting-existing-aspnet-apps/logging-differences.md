---
title: ASP.NET MVC와 ASP.NET Core 간의 로깅 차이점
description: ASP.NET MVC와 Web API apps 및 ASP.NET Core apps 간에는 어떻게 서로 다르게 로그인 하나요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0ad12463c8d13d13516ab027e56f809b67f713e4
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401736"
---
# <a name="logging-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 로깅 차이점

응용 프로그램 로깅은 특히 프로덕션 환경에서 실행 되는 앱에 중요 한 진단 정보를 제공 합니다. ASP.NET Core에는 모든 앱에 표준화 된 로깅을 추가 하기 위한 새로운 시스템이 도입 되었습니다. 기존 ASP.NET MVC 및 Web API apps는 ASP.NET Core에서 계속 지원 될 가능성이 높은 타사 로깅 솔루션을 사용 하는 경우가 많습니다.

## <a name="aspnet-mvc-logging"></a>ASP.NET MVC 로깅

ASP.NET MVC 및 Web API apps에는 기본 제공 로깅 솔루션이 없습니다. 대신, 대부분의 앱은 [log4net](https://www.nuget.org/packages/log4net/), [Nlog](https://www.nuget.org/packages/NLog/)또는 [Serilog](https://www.nuget.org/packages/Serilog)와 같은 타사 로깅 솔루션을 사용 합니다. 많은 팀은 자신의 로깅 솔루션을 롤아웃할 수도 있습니다. 로깅 프레임 워크는 일반적으로 텍스트 파일, 데이터베이스 또는 전자 메일 같은 로그 출력에 대해 여러 "싱크" (또는 대상 또는 어 펜더)를 지원 합니다. 구성을 사용 하 여 시스템의 일부가 다른 싱크로 라우팅되는 로그 메시지 수준을 결정 합니다. 앱의 로깅을 .NET Core로 마이그레이션하는 방법을 고려할 때 앱에서 로깅을 수행 하 고 [구성](configuration-differences.md) 하는 방법을 검토 합니다.

## <a name="aspnet-core-logging"></a>ASP.NET Core 로깅

ASP.NET Core에서 로깅은 앱이 시작 될 때 구성 및 확장할 수 있는 [기본 제공 기능](/aspnet/core/fundamentals/logging/) 입니다. 위에서 언급 한 것을 비롯 한 타사로 거는 기능을 향상 시키기 위해 ASP.NET Core와 통합할 수 있습니다.

ASP.NET Core 로깅은 범주 및 수준을 사용 하 여 로깅되는 내용 및 방법을 제어 합니다. 일반적으로 클래스는 `ILogger<T>` 제네릭 형식으로 사용 되는 클래스의 형식을 사용 하 여 인터페이스 인스턴스를 사용 `T` 합니다. 이 시나리오에서는 클래스의 정규화 된 이름이 범주로 사용 됩니다. 를 사용 하 여 사용자 지정 범주를 사용 하 여로 거를 만들 수도 있습니다 `ILoggerFactory` . 로그 수준이 가장 자세한 범위에서 가장 중요 한으로 범위가 가장 `Trace` 중요 합니다 `Critical` . 구성을 사용 하 여 앱은 범주 별 (와일드 카드) 기준으로 포함 해야 하는 최소 로깅 수준을 지정할 수 있습니다.

일반적인 로깅 구성은 `Information` 기본적으로 정보를 로그할 수 있지만 앞 `Warning` 에서 설명한 범주에만 해당 됩니다 `Microsoft` .

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning"
    }
  }
}
```

ASP.NET Core의 로깅에 대 한 지원은 광범위 하 고 유연 합니다. 자세한 내용은 [문서를 참조](/aspnet/core/fundamentals/logging/)하세요.

## <a name="migrate-logging"></a>로깅 마이그레이션

.NET Framework 앱의 로깅을 .NET Core로 마이그레이션하는 방법은 앱이 지금 로깅하는 방법에 따라 달라 집니다. 타사 NuGet 패키지를 사용 하는 경우 해당 패키지에 대 한 업그레이드 설명서를 참조 하세요. 가장 간단한 업그레이드 경로를 사용할 수 있습니다. 사용자 고유의 로깅 솔루션을 사용 하는 경우 다음 작업 중 하나를 수행 합니다.

1. 직접 로깅 솔루션 마이그레이션
1. 타사 로깅 솔루션으로 마이그레이션
1. ASP.NET Core에서 기본 제공 로깅 지원 사용

`Microsoft.Extensions.Logging`NuGet 4.3 이상을 사용 하 고 .NET Framework 4.6.1 이상에 있는 .NET Framework 앱에서 패키지를 참조할 수 있습니다. 앱이이 패키지를 참조 한 후에는 앱을 .NET Core로 마이그레이션하기 전에 새 확장을 사용 하도록 로깅 문을 변환할 수 있습니다. 최신 확장 패키지를 사용 하 여 로그인 하는 동안 앱이 계속 해 서 실행 될 수 있으므로이는 전체 마이그레이션에 .NET Framework 대 한 단계별 석재를 제공할 수 있습니다.

## <a name="references"></a>참조

- [.NET Core 및 ASP.NET Core 로그인](/aspnet/core/fundamentals/logging/)
- [Microsoft Extensions. 로깅 NuGet 패키지](https://www.nuget.org/packages/microsoft.extensions.logging/)

>[!div class="step-by-step"]
>[이전](middleware-modules-handlers.md)
>[다음](routing-differences.md)
