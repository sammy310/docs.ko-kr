---
title: 배포 전략
description: ASP.NET에서 ASP.NET Core로 마이그레이션하는 동안 팀에서 사용할 수 있는 배포 전략은 무엇 인가요? 증분 마이그레이션은 원활한 최종 사용자 환경을 제공 하 여 .NET Framework 및 .NET Core 앱의 병렬 배포를 가능 하 게 할 수 있나요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 6691a4878205d6422cf8b6153353abefd9764d18
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401771"
---
# <a name="deployment-strategies"></a>배포 전략

ASP.NET Core에 대 한 대량 ASP.NET 앱의 마이그레이션을 계획할 때 고려해 야 할 사항은 새 앱을 배포 하는 방법입니다. ASP.NET를 사용 하 여 배포 옵션은 Windows의 IIS로 제한 되었습니다. ASP.NET Core를 사용 하면 훨씬 더 광범위 한 배포 옵션을 사용할 수 있습니다.

## <a name="cross-platform-options"></a>플랫폼 간 옵션

.NET Core는 Linux에서 실행 되기 때문에 이전에 고려 하지 않은 일부 호스팅 옵션을 찾을 수 있습니다. Linux 기반 호스트는 다음과 같은 경우에 더 적합할 수 있습니다.

* 조직에 인프라 또는 전문 기술이 있습니다.
* 호스팅 공급자는 Linux 기반 호스팅을 위한 매력적인 기능 또는 가격 책정을 제공 합니다.

이러한 옵션에 대 한 도어를 위한 .NET Core가 열립니다.

## <a name="cloud-native-development"></a>클라우드 네이티브 개발

오늘날 대부분의 조직에서는 소프트웨어 기능 중 일부에 대해 클라우드 플랫폼을 사용 하 고 있습니다. 앱을 .NET Core로 마이그레이션하는 경우 앱을 클라우드 호스팅을 염두에 두면 의도적으로 작성 해야 하는지 여부를 고려 하는 것이 좋습니다. 이러한 *클라우드 네이티브* 앱은 서버를 사용 하지 않는, 마이크로 서비스 등의 클라우드 기능을 보다 효율적으로 적용할 수 있으며 배포 하는 방법 및 위치에 대 한 하위 수준 세부 정보에는 관심이 없을 수 있습니다.

[Azure에 대 한 클라우드 네이티브 .Net 응용 프로그램을 설계](../cloud-native/index.md)하 여이 무료 e-learning에서 클라우드 네이티브 앱 개발에 대해 자세히 알아보세요.

## <a name="leverage-containers"></a>컨테이너 활용

최신 앱은 호스트 환경 간의 변형을 줄이기 위해 컨테이너를 활용 하는 경우가 많습니다. 특정 컨테이너에 앱을 배포 하면 컨테이너에서 호스트 되는 앱은 개발자의 랩톱이 나 프로덕션 환경에서 실행 되는 경우와 동일 하 게 실행 됩니다. .Net Core로 마이그레이션하는 과정의 일환으로 앱이 컨테이너를 통해 컨테이너를 통해 배포 하는 것이 좋습니다. 전체 모놀리식로 또는 여러 개의 작은 컨테이너 화 된 apps로 분할 되어 있는지를 고려 하는 것이 좋을 수 있습니다.

## <a name="side-by-side-deployment-options"></a>Side-by-side 배포 옵션

큰 .NET Framework 앱을 .NET Core로 마이그레이션하려면 상당한 노력이 필요 합니다. 대부분의 조직에서는 전체 마이그레이션이 완료 되기 전에 프로덕션 환경에서 앱을 마이그레이션 및 배포할 수 있도록이 작업을 특정 방식으로 중단할 수 있습니다. 원래 ASP.NET 앱과 새로 마이그레이션된 ASP.NET Core 하위 앱을 나란히 실행 하는 것은 흔히 명시 된 목표입니다. 이는 [5 장에서](deployment-scenarios.md)설명 하는 IIS 라우팅 활용을 포함 하 여 다양 한 메커니즘을 통해 달성할 수 있습니다. 다른 옵션으로는 [프런트 엔드의 백 엔드](/azure/architecture/patterns/backends-for-frontends) 와 같은 앱 게이트웨이 또는 클라우드 디자인 패턴을 활용 하 여 ASP.NET 웹 api와 ASP.NET Core API 끝점의 집합을 관리할 수 있습니다.

## <a name="iis-on-windows"></a>Windows의 IIS

Windows에서 실행 되는 IIS에서 앱을 계속 호스트할 수 있습니다. 이 옵션은 현재 배포 모델을 변경 하지 않고 ASP.NET Core 기능을 활용 하려는 고객을 위한 적절 한 옵션입니다. ASP.NET Core로 이동 하는 것은 앱을 배포 하는 방법 및 위치와 관련 하 여 더 많은 옵션을 제공 하는 반면, Windows의 검증 된 IIS 조합을 사용 하는 상태에서 변경 하지 않아도 됩니다.

## <a name="other-options-on-windows"></a>Windows의 기타 옵션

필요한 경우 Docker 컨테이너 뿐만 아니라 Kestrel, HTTP.sys 및 IIS 호스트의 조합을 사용 하 여 Windows에서 앱 side-by-side 앱을 호스트할 수 있습니다. 응용 프로그램에 Windows 및 Linux 서비스 조합이 필요한 경우 [Wsl](/windows/wsl/about) 및/또는 linux Docker 컨테이너를 사용 하 여 windows 서버에서 호스팅하면 앱의 모든 부분을 호스트 하는 단일 서버 솔루션을 제공 합니다.

## <a name="references"></a>참조

- [호스트 및 배포 ASP.NET Core](/aspnet/core/host-and-deploy/)
- [IIS가 있는 Windows에서 ASP.NET Core 호스팅](/aspnet/core/host-and-deploy/iis/)
- [Azure App Service 및 IIS에 대 한 ASP.NET Core 문제 해결](/aspnet/core/test/troubleshoot-azure-iis)

>[!div class="step-by-step"]
>[이전](migrate-web-forms.md)
>[다음](additional-migration-resources.md)
