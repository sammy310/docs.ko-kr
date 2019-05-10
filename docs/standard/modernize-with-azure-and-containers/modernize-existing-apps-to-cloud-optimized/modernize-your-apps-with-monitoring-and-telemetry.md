---
title: 모니터링 및 원격 분석을 사용하여 앱을 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 모니터링 및 원격 분석을 사용하여 앱을 최신화
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: a8135031d2879ff377881d246c532573a2149fe7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611652"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>모니터링 및 원격 분석을 사용하여 앱을 최신화

프로덕션 환경에서 응용 프로그램을 실행하는 경우 응용 프로그램 성능에 대한 통찰력이 중요합니다. 높은 수준으로 실행되고 있읍니까? 사용자에게 오류를 발생시키거나 아니면 안정적이고 신뢰할 수 있는 응용 프로그램입니까? 다양한 성능 모니터링과 강력한 알림, 대시보드가 있어야 응용 프로그램이 사용할 수 있고 기대한 대로 실행되는지 확인할 수 있습니다. 또한 문제가 있다면 신속하게 확인하여 얼마나 많은 고객이 영향을 받는지 확인하고, 문제를 찾아서 해결하기 위해 근본 원인을 분석하는 작업을 해야 합니다.

## <a name="monitor-your-application-with-application-insights"></a>Application Insights를 사용 하 여 응용 프로그램 모니터링

Application Insights는 여러 플랫폼에서 작업 하는 웹 개발자를 위한 확장 가능한 응용 프로그램 성능 관리 (APM) 서비스. 라이브 웹 응용 프로그램을 모니터링 하는 데 사용할. Application Insights는 성능 이상을 자동으로 검색 합니다. 문제 진단을 도와주 고 실제로 할 앱을 사용 하 여 이해를 돕는 강력한 분석 도구를 포함 합니다. Application Insights는 성능 및 유용성을 지속적으로 향상 시킬 수 있도록 설계 되었습니다. 다양 한.NET, Node.js 및 J2EE, 여부를 포함 하는 플랫폼에서 앱에 대 한 작동 호스팅된 온-프레미스 또는 클라우드에서 합니다. Application Insights는 DevOps 프로세스를 통합 하 고 다양 한 개발 도구에 대 한 연결 지점이 있습니다.

그림 4-10 Application Insights에서 응용 프로그램을 모니터링 하는 방법 및 이러한 insights 대시보드에 처럼 하는 방법의 예를 보여 줍니다.

![Application Insights 모니터링 대시보드](./media/image10.png)

> **그림 4-10 합니다.** Application Insights 모니터링 대시보드

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Log Analytics와 해당 컨테이너 모니터링 솔루션을 사용 하 여 Docker 인프라 모니터링

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) 의 일부인 합니다 [Microsoft Azure 모니터링 솔루션 전체](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)합니다. 이기도 서비스 [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)합니다. Log Analytics 모니터링 하는 클라우드 및 온-프레미스 환경 (온-프레미스에 대 한 OMS) 가용성과 성능을 유지 하기 위해. 여러 원본에서 분석 기능을 제공 하려면 다른 모니터링 도구에서 한 클라우드 및 온-프레미스 환경의 리소스로 생성 된 데이터를 수집 합니다.

Azure 인프라 로그와 관련 하 여 Log Analytics는 Azure 서비스로 서 수집 하 여 다른 Azure 서비스의 로그 및 메트릭 데이터 (통해 [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure Vm, Docker 컨테이너 및 온-프레미스 또는 기타 클라우드 인프라입니다. Log Analytics는 유연한 로그 검색 및이 데이터를 기반으로 아웃은 분석을 제공합니다. 지정 된 조건에 따라 원본에서 데이터를 분석 하 여, 모든 로그에서 복잡 한 쿼리를 사용 하면을 사전에 경고할 수 다양 한 도구를 제공 합니다. 쿼리 및 시각화할 수 있는 중앙 Log Analytics 리포지토리에서 사용자 지정 데이터도 수집할 수 있습니다. Log Analytics 기본 제공 솔루션 보안에 즉시 통찰력을 활용 하 고 인프라의 기능 또한 취할 수입니다.

OMS 포털 또는 모든 브라우저에서 실행 하는 Azure portal을 통해 Log Analytics에 액세스할 수 있으며 구성 설정에 대 한 액세스를 사용 하 여 및 여러 도구 제공을 분석 하 고 수집 된 데이터를 작업할 수 있습니다.

합니다 [컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) 사용 하면 Log Analytics에에서 보고 하 고이 단일 위치에서 Docker 및 Windows 컨테이너 호스트를 관리 합니다. 솔루션은를 실행 하는 및 실행 중인 컨테이너는 컨테이너 이미지를 실행 합니다. 컨테이너를 사용 하 여 사용 중인 명령을 포함 하 여 자세한 감사 정보를 볼 수 있습니다. 원격 Docker 또는 Windows 호스트를 확인 하지 않고도 중앙 집중식된 로그를 검색 하 여 컨테이너를 해결할 수도 있습니다. 컨테이너 호스트에서 성가 시 고 소비 과도 한 리소스 수를 확인할 수 있습니다. 또한 중앙화 된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 볼 수 있습니다. Windows를 실행 하는 컴퓨터에 중앙 집중화를 Windows Server에서 로그를 비교 합니다. Hyper-v 및 Docker 컨테이너입니다. 솔루션에서는 다음과 같은 컨테이너 오 케 스트레이 터를 지원합니다.

- Docker Swarm

- DC/OS

- Kubernetes

- Service Fabric

- Red Hat OpenShift

그림 4-11 다양 한 컨테이너 호스트와 에이전트와 OMS 간의 관계를 보여 줍니다.

![Log Analytics 컨테이너 모니터링 솔루션](./media/image11.png)

> **그림 4-11 합니다.** Log Analytics 컨테이너 모니터링 솔루션

Log Analytics 컨테이너 모니터링 솔루션을 사용할 수 있습니다.

- 단일 위치에서 모든 컨테이너 호스트에 대 한 정보를 참조 하세요.

- 알고 있는 컨테이너를 실행 하는 어떤 이미지를 실행 및 실행 하는 것입니다.

- 컨테이너에 대 한 작업에 대 한 감사 내역을 참조 하세요.

- Docker 호스트에 원격 로그인이 없는 중앙 집중식된 로그를 검색 하 여이 문제를 해결 합니다.

- "시끄러운 이웃" 수 있으며 과도 한 리소스를 호스트에서 사용 하는 컨테이너를 찾습니다.

- 중앙화 된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 봅니다.

### <a name="additional-resources"></a>추가 자료

- **Microsoft Azure의 모니터링 개요**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Application Insights란?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Log Analytics 란?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Azure Monitor의 컨테이너 모니터링 솔루션**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Azure Monitor 개요**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Operations Management Suite (OMS) 란?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- **OMS 사용 하 여 Service Fabric에서 Windows Server 컨테이너 모니터링**

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
>[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[다음](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
