---
title: 클라우드에 최적화된 응용 프로그램 내의 Microsoft 기술
description: 기존.NET 응용 프로그램을 Azure 클라우드와 Windows 컨테이너를 사용하여 최신화 | 클라우드에 최적화된 응용 프로그램 내의 Microsoft 기술
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 45eeee165a1dcbfc7b6dbc5146ce2c4b2be2e643
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012050"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>클라우드에 최적화된 응용 프로그램 내의 Microsoft 기술

다음 목록은 클라우드에 최적화된 앱의 요구 사항으로 인식되는 도구와 기술, 솔루션을 설명합니다. 우선 순위에 따라 클라우드 최적화 요소를 단계적 또는 선택적으로 채택할 수 있습니다.

- **클라우드 인프라**: 계산 플랫폼과 운영 체제, 네트워크, 저장소를 제공하는 인프라입니다. Microsoft Azure는 이 수준에 위치합니다.

- **런타임**: 이 계층에는 응용 프로그램 실행을 위한 환경을 제공 합니다. 이 계층에 기반 일반적으로 컨테이너를 사용 하는 경우 [Docker 엔진](https://docs.docker.com/engine/), Windows 호스트 또는 Linux 호스트에서 실행 중입니다. ([Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 은 Windows Server 2016부터 지원 합니다. Windows 컨테이너는 Windows에서 실행 되는 기존.NET Framework 응용 프로그램에 적합 합니다.)

- **클라우드 관리**: 관리 되는 클라우드 옵션을 선택 하면 비용 및 관리 하 고 기본 인프라를 Vm에 OS 패치를 지 원하는 네트워킹 구성의 복잡성을 피할 수 있습니다. IaaS를 사용 하 여 마이그레이션하도록 선택 하면 사용자는 이러한 작업을 모두에 대 한 관련 된 비용에 대 한 책임이 있습니다. 관리 되는 클라우드 옵션을 응용 프로그램 및 개발 하는 서비스를 관리 합니다. 일반적으로 클라우드 서비스 공급자를 다른 모든 항목을 관리 합니다. Azure에서 관리 되는 클라우드 서비스의 예로 [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/)합니다 [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/)를 [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/)를 [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/)를 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), 및와 같은 계산 서비스를 관리 되는 [VM 확장 설정](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)합니다 [Azure App Service](https://azure.microsoft.com/services/app-service/), 및 [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/)합니다.

- **응용 프로그램 개발**: 컨테이너에서 실행 되는 응용 프로그램을 빌드할 때 많은 언어 중에서 선택할 수 있습니다. 이 가이드에 중점을 둡니다 [.NET](https://www.microsoft.com/net)에 있지만 이동 하거나 Node.js, Python, Java/Spring와 마찬가지로 다른 언어를 사용 하 여 컨테이너 기반 앱을 개발할 수 있습니다.

- **모니터링, 원격 분석 로깅 및 감사**: 모니터링 및 감사 응용 프로그램을 클라우드에서 실행 중인 컨테이너는 클라우드에 최적화 된 응용 프로그램 중요 합니다. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 하 고 [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) 클라우드에 최적화 된 앱에 대 한 모니터링 및 감사를 제공 하는 주요 Microsoft 도구입니다.

- **프로 비전**: 자동화 도구를 사용 하 여 인프라를 프로 비전 하 고 여러 환경 (프로덕션, 테스트, 스테이징)에 응용 프로그램을 배포할 수 도움이 됩니다. 응용 프로그램의 구성 및 환경 관리에 Chef 및 Puppet과 같은 도구를 사용할 수 있습니다. 또한이 계층 보다 간단 하 고 더 직접적인 방법을 사용 하 여 구현할 수 있습니다. 예를 들어, 도구, Azure 명령줄 인터페이스 (Azure CLI)를 사용 하 여 직접 배포 하 고 다음 연속 배포를 사용 하 릴리스 관리 파이프라인에서 [Azure DevOps 서비스](https://azure.microsoft.com/services/devops/)합니다.

- **응용 프로그램 수명 주기**: [Azure DevOps 서비스](https://azure.microsoft.com/services/devops/) 및 Jenkins와 같은 다른 도구는 도움이 되는 기본 제공된 자동화 서버 구현 릴리스 관리를 비롯 하 여 CI/CD 파이프라인을 합니다.

다음 섹션에서는이 장 및 관련된 연습을 런타임 계층 (Windows 컨테이너)에 대 한 세부 정보 특히 집중합니다. 지침에는 Windows Server 2016 (및 이상 버전)에서 Windows 컨테이너 Vm 및 Azure Container Instances에 배포할 수 있습니다 하는 방법을 설명 합니다. 또한 Azure App Service와 같은 고급 PaaS 플랫폼 및 Azure Service Fabric 및 Azure Kubernetes Service와 같은 오 케 스트레이 터 다룹니다.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>모놀리식 응용 프로그램 *수* 클라우드에 최적화 수

모놀리식 응용 프로그램 (응용 프로그램 마이크로 서비스에 기반 하지 않는)는 강조 표시 해야 *수* 클라우드에 최적화 된 응용 프로그램 이어야 합니다. 빌드 수 있으며 클라우드 컨테이너, 지속적인 업데이트 및 DevOps의 조합을 사용 하 여 모델을 컴퓨팅을 활용 하는 모놀리식 응용 프로그램을 작동할 수 있습니다. 이 현대화 하 고 있도록 수 이면 기존 모놀리식 응용 프로그램을 오른쪽에서 비즈니스 목표에 맞게 클라우드 최적화 합니다.

마찬가지로, 모놀리식 응용 프로그램을 클라우드에 최적화 된 응용 프로그램 수를 N 계층 응용 프로그램과 같은 다른, 보다 복잡 한 아키텍처 클라우드에 최적화 된 응용 프로그램으로 현대화 수도 있습니다.

>[!div class="step-by-step"]
>[이전](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[다음](what-about-cloud-native-applications.md)