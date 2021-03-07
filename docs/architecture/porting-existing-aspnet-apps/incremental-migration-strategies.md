---
title: 증분 마이그레이션 전략
description: 팀이 채택할 수 있는 전략은 증분 방식으로 ASP.NET MVC의 많은 앱을 .NET Core로 마이그레이션할 수 있도록 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: dc500fa71188c472f78ef4df95d79434208552c3
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401886"
---
# <a name="strategies-for-migrating-incrementally"></a>증분 마이그레이션 전략

큰 앱을 마이그레이션하는 가장 큰 문제는 프로세스를 더 작은 작업으로 분리 하는 방법을 결정 하는 것입니다. 이 목적을 위해 응용 프로그램을 UI, 데이터 액세스, 비즈니스 논리 등의 가로 계층으로 분리 하거나 앱을 별도의 작은 앱으로 나누는 등 여러 가지 전략을 적용할 수 있습니다. 또 다른 전략은 최신 .NET Core 릴리스를 위해 일부 또는 모든 앱을 다른 프레임 워크 버전으로 업그레이드 하는 것입니다. 사용할 수 있는 한 가지 방법은 한 번에 하나의 가로 계층을 마이그레이션하도록 시도 하는 대신 앱의 [수직 조각을](https://deviq.com/practices/vertical-slices) 마이그레이션하는 것입니다. 각각의 서로 다른 방법을 살펴보겠습니다.

큰 ASP.NET 4.5 앱을 마이그레이션할 때의 문제를 고려 합니다. 한 가지 방법은 .NET Framework 4.5에서 .NET Core 3.1로 전체 앱을 직접 마이그레이션하는 것입니다. 그러나이 방법은 두 프레임 워크와 버전 간의 주요 변경 내용이 모두 고려 되어야 합니다.

## <a name="migrating-layer-by-layer"></a>계층 별로 계층 마이그레이션

여러 .NET framework 간의 상호 운용성을 지 원하는 .NET 에코 시스템에 대 한 최근 추가 기능을 [.NET Standard](https://dotnet.microsoft.com/platform/dotnet-standard)합니다. .NET Standard를 사용 하면 공용 Api의 합의 된 집합에 대해 라이브러리를 빌드하여 .NET 앱에서 사용할 수 있습니다. .NET Standard 2.0은 대부분의 .NET Framework 및 .NET Core 앱에서 사용 하는 대부분의 기본 클래스 라이브러리 기능을 포함 하기 때문에 주목할 만한 것입니다. 아쉽게도 .NET Standard 2.0를 지 원하는 가장 이른 버전의 .NET은 4.6.1 .NET Framework 이며 초기 업그레이드에 적합 한 여러 업데이트를 .NET Framework 4.8에 있습니다.

.NET Framework 4.5 시스템 계층을 증분 방식으로 업그레이드 하는 한 가지 방법은 먼저 클래스 라이브러리 종속성을 .NET Framework 4.8로 업데이트 하는 것입니다. 그런 다음 이러한 라이브러리를 .NET Standard 클래스 라이브러리로 수정 합니다. 필요한 경우 다중 대상 지정 및 조건부 컴파일을 사용 합니다. 이 단계는 앱 종속성이 .NET Framework 필요 하 고 .NET Standard 및 .NET Core를 사용 하기 위해 직접 이식할 수 없는 시나리오에서 유용할 수 있습니다. .NET Framework 라이브러리는 ASP.NET Core 2.1 앱에서 사용할 수 있기 때문에 다음 단계는 앱의 웹 기능 일부 또는 전부를 ASP.NET Core 2.1 ( [이전 장에](choose-net-core-version.md)설명 된 대로)로 마이그레이션하는 것입니다. 이는 낮은 수준의 클래스 라이브러리 종속성으로 시작 하 고 웹 앱 진입점으로 작업 하는 "상향식" 방식입니다.

ASP.NET Core 2.1에서 앱이 실행 되 고 있으면 격리에서 ASP.NET Core 3.1로 마이그레이션하는 것은 비교적 간단 합니다. 이 단계에서 발생 하는 가장 큰 문제는 .NET Core를 지원 하기 위해 호환 되지 않는 종속성을 업데이트 하는 것이 고 더 높은 버전의 .NET Standard .NET Framework 전용 라이브러리에 대해 문제가 있는 종속성이 없는 앱의 경우 ASP.NET Core 2.1로 업그레이드할 이유가 거의 없습니다. ASP.NET Core 3.1로 직접 포팅 하는 것이 더 합리적 이며, 더 짧은 노력이 필요 합니다.

앱이 .NET Core 3.1에서 실행 되는 시점에는 현재 .NET 5 릴리스로 마이그레이션하는 것은 비교적 간편 합니다. 프로세스에는 주로 프로젝트 파일의 대상 프레임 워크와 관련 된 NuGet 패키지 종속성 업데이트가 포함 됩니다. 고려해 야 할 몇 가지 [주요 변경 사항이](../../core/compatibility/5.0.md)있지만 대부분의 앱은 .net Core 3.1에서 .net 5로 이동 하기 위한 상당한 수정이 필요 하지 않습니다. [.Net Core 3.1 및 .net 5 중에서 선택 하](choose-net-core-version.md)는 기본 결정 요인은 지원 될 수 있습니다.

"상향식" 접근 방식 대신 웹 앱 (또는 전체 솔루션)에서 시작 하 고 자동화 된 도구를 사용 하 여 업그레이드를 지원할 수도 있습니다. [.Net 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant) 를 사용 하 여 .NET Framework 앱을 .net Core/.net 5로 업그레이드할 수 있습니다. 프로젝트 파일 형식 수정, 적절 한 대상 프레임 워크 설정, NuGet 종속성 업데이트 등 앱 업그레이드와 관련 된 여러 가지 일반적인 작업을 자동화 합니다.

"상향식" 접근 방식 대신 웹 앱 (또는 전체 솔루션)에서 시작 하 고 자동화 된 도구를 사용 하 여 업그레이드를 지원할 수도 있습니다. [.Net 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant) 를 사용 하 여 .NET Framework 앱을 .net Core/.net 5로 업그레이드할 수 있습니다. 프로젝트 파일 형식 수정, 적절 한 대상 프레임 워크 설정, NuGet 종속성 업데이트 등 앱 업그레이드와 관련 된 여러 가지 일반적인 작업을 자동화 합니다.

## <a name="migrating-slice-by-slice"></a>조각 별로 조각 마이그레이션

마이그레이션의 또 다른 방법은 기능의 세로 조각을 식별 하 고 대상 플랫폼으로 하나씩 마이그레이션하는 것입니다. 첫 번째 단계는 새 ASP.NET Core 3.1 또는 5 앱을 만드는 것입니다. 그런 다음, 먼저 마이그레이션되는 개별 페이지 또는 API 끝점을 식별 합니다. ASP.NET Core 앱에서이 한 경로를 지 원하는 데 필요한 기능만 빌드 하세요. 그런 다음 HTTP 다시 쓰기 및/또는 역방향 프록시를 사용 하 여 이러한 페이지 또는 끝점에 대 한 요청을 ASP.NET 앱이 아닌 새 앱으로 보내기 시작 합니다.

IIS를 사용 하 여이 전략을 수행 하는 방법에 대 한 몇 가지 특정 지침은 [5 장 배포 시나리오](deployment-scenarios.md)에 설명 되어 있습니다.

## <a name="references"></a>참조

- [.NET Standard란?](https://dotnet.microsoft.com/platform/dotnet-standard)
- [.NET 5 소개](https://devblogs.microsoft.com/dotnet/introducing-net-5/)
- [ASP.NET Core 3.1에서 5.0로 마이그레이션](/aspnet/core/migration/31-to-50)
- [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)

>[!div class="step-by-step"]
>[이전](choose-net-core-version.md)
>[다음](migrate-web-forms.md)
