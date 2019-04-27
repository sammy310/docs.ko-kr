---
title: 컨테이너화된 애플리케이션 서비스 모니터링
description: 모니터링 컨테이너 아키텍처의 몇 가지 주요 측면에 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922748"
---
# <a name="monitor-containerized-application-services"></a>컨테이너화된 애플리케이션 서비스 모니터링

이 응용 프로그램 컨테이너 및 마이크로 서비스를 여러 분할을 모니터링 하 고 전체 응용 프로그램의 동작을 분석 하는 방법이 중요 합니다.

## <a name="azure-monitor"></a>Azure Monitor

[Azure Monitor](https://azure.microsoft.com/services/monitor/) 라이브 응용 프로그램을 모니터링 하는 확장 가능한 분석 서비스입니다. 성능 문제 감지 및 진단 하는 데 실제로 할 앱을 사용 하 여 이해할 수 있습니다. 지속적으로 성능을 향상 시킬 수 있도록 의도 및 서비스 또는 응용 프로그램의 사용 편의성을 사용 하 여 개발자를 위해 설계 되었습니다. Azure Monitor는 다양 한 클라우드 또는.NET, Java, Node.js 및 기타 여러 플랫폼, 호스팅된 온-프레미스와 같은 플랫폼에서 앱을 웹/서비스와 독립 실행형을 사용 하 여 작동 합니다.

### <a name="additional-resources"></a>추가 자료

- **Azure Monitor 개요** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **Application Insights란?** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Azure Monitor 메트릭 이란?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Azure Monitor의 컨테이너 모니터링 솔루션** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>보안 및 백업 서비스

많은 응용 프로그램 및 인프라는 비즈니스 요구를 지 원하는 최상의 조건에서 확인을 처리 해야 하는 세부 정보를 사용 하 여 여러 지원 작업 되며 상황이 더 복잡해 집니다 마이크로 서비스 영역에서는 해야 하는 방법 상위 수준 및 세부 보기를 될 하 여 작업을 수행 해야 합니다.

Azure를 통해 클라우드 및 온-프레미스 리소스의 네 가지 중요 한 측면의 통합된 보기를 제공 하는 도구에 있습니다.

- **보안**합니다. 사용 하 여 [Azure Security Center](https://azure.microsoft.com/services/security-center/)합니다.
  - 완전 한 가시성과 제어권을 통해 virtual machines, 앱 및 워크 로드의 보안을 가져옵니다.
  - 보안 정책의 관리를 중앙 집중화 하 고 기존 프로세스 및 도구를 통합 합니다.
  - 고급 분석을 사용 하 여 실제 위협을 감지 합니다.

- **백업**합니다. 사용 하 여 [Azure Backup](https://azure.microsoft.com/services/backup/)합니다.
  - 비용이 많이 드는 업무 중단을 방지 하 고 규정 준수 목표를 충족 랜 섬 웨어 및 사람의 오류 로부터 데이터를 보호 합니다.
  - 전송 중 및 미사용 시 암호화 된 백업 데이터를 유지 합니다.
  - 무단된 사용을 방지 하기 위해 다단계 인증을 기반으로 하는 액세스를 확인 합니다.

- **온-프레미스 리소스**합니다. 사용 하 여 [일관 된 하이브리드 클라우드](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)합니다.

>[!div class="step-by-step"]
>[이전](manage-production-docker-environments.md)
>[다음](../key-takeaways/index.md)
