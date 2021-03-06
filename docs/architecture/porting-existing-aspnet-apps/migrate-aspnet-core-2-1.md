---
title: ASP.NET Core 2.1로 마이그레이션
description: .NET Framework 런타임 대상을 지원 하기 위한 마지막 .NET Core 버전으로, 일부 앱 마이그레이션 계획의 중간 단계로 .NET Core 2.1로 마이그레이션해야 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 0c478ae194c6d9118bfbca73f8933d7623246e2c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401730"
---
# <a name="migrate-to-aspnet-core-21"></a>ASP.NET Core 2.1로 마이그레이션

ASP.NET Core 2.1은 .NET Core와 .NET Framework 런타임을 모두 지원 하기 위해 현재 지원 되는 .NET Core 릴리스입니다. 따라서 앱의 모든 부분을 한 번에 .NET Core로 업그레이드 하는 것과 비교 했을 때 일부 앱에 대해 더 쉬운 업그레이드 경로를 제공할 수 있습니다. LTS 릴리스부터 .NET Core 2.1에 대 한 지원은 년 8 2021 월까지 계속 됩니다. .NET Framework에서 실행 되는 ASP.NET Core 2.1에 대 한 지원은 기본 .NET Framework 지원 되는 동안 계속 됩니다.

## <a name="should-apps-run-on-net-framework-with-aspnet-core-21"></a>앱이 ASP.NET Core 2.1를 사용 하 여 .NET Framework에서 실행 되어야 함

ASP.NET Core 2.2 이전 버전에서는 .NET Core와 .NET Framework 런타임을 모두 지원 했습니다. 전체 .NET Core로 포팅 하기 전에 앱의 일부 또는 전부를 스테핑 돌로 ASP.NET Core 2.1으로 마이그레이션하는 것이 의미가 있나요? 앱 또는 앱의 하위 집합은 비즈니스 논리 및 인프라 사용을 위해 .NET Framework 라이브러리를 계속 사용 하면서 ASP.NET Core를 사용 하기 위해 이식 된 프런트 엔드 ASP.NET 논리를 볼 수 있습니다. 이 접근 방식은 비즈니스 논리가 많지 않은 비교적 씬 UI 계층이 있고 클래스 라이브러리의 기능 집합이 훨씬 더 많은 경우에 적합할 수 있습니다.

프런트 엔드 웹 계층을 ASP.NET Core 2.1로 포팅 하는 주요 혜택은 기존 .NET 클래스 라이브러리를 초기 마이그레이션 중에 그대로 유지할 수 있다는 것입니다. 다른 .NET 앱에서 지속적으로 사용 중일 수도 있고, .NET Core로 계획 된 전체 마이그레이션의 첫 번째 반복을 위해 범위에 있을 필요가 없습니다. 대량 앱에 대 한 초기 마이그레이션의 범위를 줄이면 원하는 최종 상태에 대 한 스테핑 돌의 역할을 하는 증분 목표를 제공할 수 있습니다 .이는 일반적으로 .NET Core에 대 한 완전 한 포트입니다.

이 전략을 사용할 수 있는 기존 앱이 있는 경우 프로세스를 준비 하는 데 도움이 되는 몇 가지 작업은 ASP.NET 프로젝트에서 최대한 많은 비즈니스 논리, 데이터 액세스 및 기타 UI 이외의 논리를 가능한 한 별도의 클래스 라이브러리로 이동 하는 것입니다. 또한 시스템의 자동화 된 테스트 검사를 수행 하 여, 마이그레이션 전후에 동작이 일관 되 게 유지 되는지 확인할 수 있습니다.

앱이 너무 많아 전체 웹 앱을 한 번에 마이그레이션할 수 없는 경우 새 ASP.NET Core 앱을 기존 ASP.NET 앱과 나란히 배포할 수 있으려면이를 위해 사용할 수 있는 배포 전략이 있습니다. 이러한 [내용은 5 장: 배포 시나리오](deployment-scenarios.md)에 설명 되어 있습니다.

ASP.NET Core 2.1는 .NET Framework에서 실행을 지원 하 고 .NET Framework 라이브러리를 사용 하는 .NET Core의 마지막 LTS 릴리스입니다. 이 릴리스는 곧 지원 되지 않지만 .NET Framework (.NET Core 2.1 지원이 종료 된 후에도) .NET Framework의 ASP.NET Core 2.1가 지원 됩니다. 자세한 내용은 [.NET Framework ASP.NET Core 2.1](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)를 참조 하십시오.

## <a name="references"></a>참조

[ASP.NET에서 ASP.NET Core 2.1로 마이그레이션](/aspnet/core/migration/proper-to-2x/?preserve-view=true&view=aspnetcore-2.1)

>[!div class="step-by-step"]
>[이전](migration-considerations.md)
>[다음](choose-net-core-version.md)
