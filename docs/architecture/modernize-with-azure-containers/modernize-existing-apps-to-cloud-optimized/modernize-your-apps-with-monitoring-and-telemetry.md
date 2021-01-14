---
title: 모니터링 및 원격 분석을 사용하여 앱 현대화
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 모니터링 및 원격 분석을 사용하여 앱 현대화
ms.date: 12/21/2020
ms.openlocfilehash: c79a16400ce9dadca50fabb6c7df2859e4519a41
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025240"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>모니터링 및 원격 분석을 사용하여 앱 현대화

프로덕션 환경에서 애플리케이션을 실행하는 경우 애플리케이션 작동 방식에 대한 정보를 파악하는 것이 중요합니다. 애플리케이션이 상위 수준에서 실행되나요? 애플리케이션이 안정적이고 신뢰할 수 있나요, 아니면 사용자에게 오류가 발생하나요? 애플리케이션을 사용할 수 있고 예상대로 작동하는지 확인하는 데 도움이 되는 다양한 성능 모니터링, 강력한 경고 및 대시보드가 필요합니다. 또한 문제가 있는지 신속하게 확인하고, 얼마나 많은 고객이 영향을 받는지 확인하고, 근본 원인 분석을 수행하여 문제를 찾고 해결할 수 있어야 합니다.

## <a name="monitor-your-application-with-application-insights"></a>Application Insights를 사용하여 애플리케이션 모니터링

Application Insights는 여러 플랫폼에서 작업하는 웹 개발자를 위한 확장 가능한 APM(애플리케이션 성능 관리) 서비스입니다. 이를 사용하여 라이브 웹 애플리케이션을 모니터링합니다. Application Insights는 자동으로 성능 이상을 검색합니다. 문제를 진단하고 사용자들이 앱을 사용하여 실제로 수행할 작업을 이해할 수 있도록 돕는 강력한 분석 도구를 포함합니다. Application Insights는 성능 및 유용성을 지속적으로 향상시킬 수 있도록 설계되었습니다. 온-프레미스 또는 클라우드에서 호스팅되는지 여부에 관계없이 .NET, Node.js 및 J2EE를 포함하여 다양한 플랫폼의 응용 프로그램에서 작동합니다. Application Insights는 DevOps 프로세스와 통합되며, 다양한 개발 도구와의 연결점을 갖고 있습니다.

그림 4-10에서는 Application Insights가 애플리케이션을 모니터링하는 방법과 해당 인사이트를 대시보드에 표시하는 방법을 보여줍니다.

![Application Insights 모니터링 대시보드의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

**그림 4-10.** Application Insights 모니터링 대시보드

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Log Analytics 및 해당 컨테이너 모니터링 솔루션을 사용하여 Docker 인프라 모니터링

[Azure Log Analytics](/azure/log-analytics/log-analytics-overview)는 [Microsoft Azure 전체 모니터링 솔루션](/azure/monitoring-and-diagnostics/monitoring-overview)의 일부입니다. 또한 [OMS(Operations Management Suite)](/azure/operations-management-suite/operations-management-suite-overview)의 서비스입니다. Log Analytics는 클라우드 및 온-프레미스 환경(온-프레미스용 OMS)을 모니터링하여 가용성과 성능을 유지합니다. 이 서비스는 클라우드 및 온-프레미스 환경에서 리소스에 의해 생성되고 여러 원본에 대한 분석을 제공하는 다른 모니터링 도구에서 생성된 데이터를 수집합니다.

Azure 인프라 로그와 관련하여, Log Analytics는 Azure 서비스로서 다른 Azure 서비스([Azure Monitor](/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)를 통해), Azure VM, Docker 컨테이너 및 온-프레미스 또는 기타 클라우드 인프라에서 로그 및 메트릭 데이터를 수집합니다. Log Analytics는 이 데이터를 기반으로 하는 유연한 로그 검색과 기본 분석을 제공합니다. 소스에서 데이터를 분석하는 데 사용할 수 있는 다양한 도구를 제공하고, 모든 로그에서 복잡한 쿼리를 허용하며, 지정된 조건을 기반으로 사전에 경고할 수 있습니다. 중앙 Log Analytics 리포지토리에서 사용자 지정 데이터를 수집하여 쿼리하고 시각화할 수도 있습니다. Log Analytics의 기본 제공 솔루션을 활용하여 인프라의 보안 및 기능을 즉시 파악할 수도 있습니다.

수집된 데이터를 분석 및 조작하기 위해 모든 브라우저에서 실행되고 구성 설정 및 여러 도구에 대한 액세스를 제공하는 OMS 포털 또는 Azure Portal을 통해 Log Analytics에 액세스할 수 있습니다.

Log Analytics의 [컨테이너 모니터링 솔루션](/azure/log-analytics/log-analytics-containers)을 사용하여 단일 위치에서 Docker 및 Windows 컨테이너 호스트를 보고 관리할 수 있습니다. 솔루션은 어떤 컨테이너가 실행 중인지, 실행 중인 컨테이너 이미지 및 컨테이너가 실행 중인 위치를 표시합니다. 컨테이너에 사용되는 명령을 포함하여 자세한 감사 정보를 볼 수 있습니다. 중앙화된 로그를 보고 검색하면 원격으로 Docker 또는 Windows 호스트를 보지 않고도 컨테이너의 문제를 해결할 수도 있습니다. 호스트에서 방해가 되고 과도한 리소스를 사용하는 컨테이너를 검색할 수 있습니다. 또한 컨테이너에 대해 중앙화된 CPU 메모리, 스토리지, 네트워크 사용 및 성능 정보를 확인할 수 있습니다. Windows를 실행하는 컴퓨터에서 Windows Server, Hyper-V, Docker 컨테이너에서 로그를 중앙 집중화 및 비교할 수 있습니다. 솔루션은 다음과 같은 컨테이너 오케스트레이터를 지원합니다.

- Docker Swarm

- DC/OS

- Kubernetes

- Red Hat OpenShift

그림 4-11에서는 다양한 컨테이너 호스트와 에이전트 및 OMS 간의 관계를 보여줍니다.

![Log Analytics 컨테이너 모니터링 솔루션의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

**그림 4-11.** Log Analytics 컨테이너 모니터링 솔루션

Log Analytics 컨테이너 모니터링 솔루션을 다음과 같이 사용할 수 있습니다.

- 단일 위치의 모든 컨테이너 호스트에 대한 정보를 확인

- 실행 중인 컨테이너, 실행 중인 이미지 및 실행 중인 위치를 확인

- 컨테이너에 대한 작업 감사 내역을 확인

- Docker 호스트에 원격 로그인하지 않고 중앙 집중식 로그를 보고 검색하여 문제 해결

- 호스트에서 “방해가 되고” 과도한 리소스를 소모하는 컨테이너를 검색

- 컨테이너에 대한 CPU 메모리, 저장소, 네트워크 사용 및 성능 정보를 중앙 집중식으로 확인

### <a name="additional-resources"></a>추가 자료

- **Microsoft Azure 모니터링 개요**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **Application Insights란?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **Log Analytics란?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Azure Monitor의 컨테이너 모니터링 솔루션**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Azure Monitor 개요**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **OMS(Operations Management Suite)란?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[다음](life-cycle-ci-cd-pipelines-devops-tools.md)
