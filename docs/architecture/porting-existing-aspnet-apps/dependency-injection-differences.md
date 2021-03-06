---
title: ASP.NET MVC와 ASP.NET Core 간의 종속성 주입 차이
description: ASP.NET MVC 및 ASP.NET Core에서 종속성 주입이 작동 하는 방법, 차이점 및 ASP.NET MVC에서 ASP.NET Core로 마이그레이션하는 방법에 대해 살펴봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: aa1c7dd2f70e1a545352feb6560177bc6e2baa2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401778"
---
# <a name="dependency-injection-differences-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 종속성 주입 차이

ASP.NET MVC 또는 Web API에는 DI (종속성 주입)가 제공 되지 않지만 많은 앱은 IOC (반전 제어) 컨테이너를 사용 하 여 NuGet 패키지를 추가 함으로써이를 사용 하도록 설정 합니다. 이러한 경우를 종속성 주입 또는 반전에 대해 DI 컨테이너 라고도 합니다. ASP.NET MVC 앱에서 가장 많이 사용 되는 컨테이너 중 일부는 다음과 같습니다.

- [Autofac](https://www.autofac.org/)
- [Unity](https://unitycontainer.github.io/)
- [Ninject](http://www.ninject.org/)
- [StructureMap](http://structuremap.github.io/) *(사용 되지 않음)*
- [성 Windsor](http://www.castleproject.org/projects/windsor/)

ASP.NET MVC 앱에서 DI를 사용 하지 않는 경우 ASP.NET Core에서 DI에 대 한 기본 제공 지원을 조사 하는 것이 좋습니다. DI는 앱에서 모듈의 느슨한 결합을 홍보 하 고 [SOLID](https://www.weeklydevtips.com/episodes/047)와 같은 원칙을 보다 효율적으로 테스트 하 고 준수할 수 있습니다.

앱에서 DI를 사용 하는 경우 가장 좋은 조치는 사용 중인 컨테이너가 ASP.NET Core 지원 하는지 확인 하는 것입니다. 그럴 경우이를 계속 사용할 수 있으며, 형식 매핑과 수명을 설명 하는 사용자 지정 구성 규칙을 사용할 수 있습니다.

어떤 방법을 사용 하 든, 앱의 요구를 충족할 수 있으므로 ASP.NET Core와 함께 제공 되는 DI에 대 한 기본 제공 지원을 사용 하는 것이 좋습니다.

## <a name="dependency-injection-in-aspnet-core"></a>ASP.NET Core에서 종속성 주입

ASP.NET Core 앱에서 DI를 사용 한다고 가정 합니다. 이는 프레임 워크에 기본 제공 되지 않지만 프레임 워크 기능을 ASP.NET Core 앱에 대 한 지원을 제공 하기 위해 필요 합니다. 앱 시작 시 `ConfigureServices` DI 컨테이너 (서비스 컬렉션/서비스 공급자)가 앱에서 만들고 삽입할 수 있는 모든 형식을 등록 해야 하는 호출을 수행 합니다. Entity Framework Core, Id 및 MVC와 같은 기본 제공 ASP.NET Core 기능은 메서드에서 서비스로 구성 하 여 앱으로 가져옵니다 `ConfigureServices` .

앱은 기본 구현을 사용 하는 것 외에도 사용자 지정 컨테이너를 사용할 수 있습니다. [설명서에서는 기본 서비스 컨테이너를 바꾸는 방법을 설명](../../core/extensions/dependency-injection-guidelines.md#default-service-container-replacement)합니다.

DI는 ASP.NET Core의 기본입니다. 팀이이 연습에서 아직 익숙한 되지 않은 경우 앱을 포팅 하기 전에 이해 해야 합니다.

## <a name="references"></a>참조

- [.NET의 종속성 주입](../../core/extensions/dependency-injection.md)
- [ASP.NET Core의 종속성 주입](/aspnet/core/fundamentals/dependency-injection)

>[!div class="step-by-step"]
>[이전](serving-static-files.md)
>[다음](middleware-modules-handlers.md)
