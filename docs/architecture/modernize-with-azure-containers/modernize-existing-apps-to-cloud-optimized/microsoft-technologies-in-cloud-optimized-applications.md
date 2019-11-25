---
title: 클라우드 최적화 애플리케이션의 Microsoft 기술
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 클라우드 최적화 애플리케이션의 Microsoft 기술
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "69578226"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>클라우드 최적화 애플리케이션의 Microsoft 기술

다음 목록에서는 클라우드 최적화 앱에 대한 요구 사항으로 인식되는 도구, 기술 및 솔루션에 대해 설명합니다. 사용자는 우선순위에 따라 클라우드 최적화 요소를 선택적으로 또는 점진적으로 도입할 수 있습니다.

- **클라우드 인프라**: 컴퓨팅 플랫폼, 운영 체제, 네트워크 및 저장소가 제공되는 인프라입니다. Microsoft Azure는 이 수준으로 위치가 지정됩니다.

- **런타임**: 이 계층에서는 애플리케이션 실행을 위한 환경이 제공됩니다. 컨테이너를 사용하는 경우, 이 계층은 일반적으로 Linux 호스트나 Windows 호스트에서 실행되는 [Docker 엔진](https://docs.docker.com/engine/)을 기반으로 합니다. ([Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/)는 Windows Server 2016부터 지원됩니다. Windows 컨테이너는 Windows에서 실행되는 기존 .NET Framework 애플리케이션에 가장 적합한 선택지입니다.

- **관리형 클라우드**: 관리형 클라우드 옵션을 선택하면 기본 인프라, VM, OS 패치, 네트워킹 구성을 관리 및 지원하는 데 따르는 비용과 복잡성의 문제를 피할 수 있습니다. IaaS를 사용한 마이그레이션을 선택하면 그 모든 작업에 대한 책임은 물론 관련 비용 부담까지 지게 됩니다. 관리형 클라우드 옵션에서는 사용자가 개발하는 애플리케이션과 서비스만 관리하면 됩니다. 그 외의 모든 사항은 일반적으로 클라우드 서비스 공급자가 관리합니다. Azure에서 관리되는 클라우드 서비스의 예로는 [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), 그리고 [VM 확장 집합](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure App Service](https://azure.microsoft.com/services/app-service/), [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/) 같은 관리형 컴퓨팅 서비스가 포함됩니다.

- **애플리케이션 개발**: 컨테이너에서 실행되는 애플리케이션을 빌드할 때는 여러 언어 중에서 원하는 언어를 선택할 수 있습니다. 이 가이드에서는 [.NET](https://www.microsoft.com/net)에 초점을 맞추고 있지만, 사용자는 Node.js, Python, Spring/Java 또는 Go와 같은 다른 언어를 사용하여 컨테이너 기반 앱을 개발할 수도 있습니다.

- **모니터링, 원격 분석, 로깅 및 감사**: 클라우드에서 실행되는 애플리케이션과 컨테이너를 모니터링하고 감사하는 기능은 클라우드 최적화 애플리케이션에 매우 중요합니다. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/)와 [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite)는 클라우드 최적화 앱을 위한 모니터링 및 감사 기능을 제공하는 주된 Microsoft 도구입니다.

- **프로비전**: 자동화 도구는 인프라를 프로비전하고 애플리케이션을 여러 환경(프로덕션, 테스트, 스테이징)으로 배포하는 데 유용합니다. 사용자는 Chef와 Puppet 같은 도구를 사용하여 애플리케이션의 구성과 환경을 관리할 수 있습니다. 이 계층은 더 단순하고 직접적인 접근법으로 구현할 수도 있습니다. 예를 들면 Azure CLI(Azure 명령줄 인터페이스) 도구를 사용하여 직접 배포를 실시한 다음 [Azure DevOps Services](https://azure.microsoft.com/services/devops/)에서 연속 배포 및 릴리스 관리 파이프라인을 사용할 수 있습니다.

- **애플리케이션 수명 주기**: [Azure DevOps Services](https://azure.microsoft.com/services/devops/) 등의 도구(예: Jenkins)는 릴리스 관리를 비롯한 CI/CD 파이프라인 구현에 유용한 빌드 자동화 서버입니다.

이 챕터의 다음 섹션과 관련 연습 자료에서는 런타임 계층(Windows 컨테이너)에 관한 세부 사항에 특히 초점을 맞춥니다. 이 지침에서는 Windows Server 2016 이상 버전의 VM 및 Azure Container Instances에 Windows 컨테이너를 배포하는 방법을 설명합니다. 또한 Azure Kubernetes Service 같은 오케스트레이터와 Azure App Service 같은 고급 PaaS 플랫폼에 대해 좀 더 자세히 설명합니다.

## <a name="monolithic-applications-can-be-cloud-optimized"></a>모놀리식 애플리케이션은 클라우드 최적화가 *가능함*

특히 강조해야 할 부분은 모놀리식 애플리케이션(마이크로 서비스 기반이 아닌 애플리케이션)이 클라우드 최적화가 *가능*하다는 점입니다. 사용자는 컨테이너, 지속적인 업데이트 및 DevOps의 조합을 사용하여 클라우드 컴퓨팅 모델을 활용하는 모놀리식 애플리케이션을 빌드 및 운영할 수 있습니다. 기존의 모놀리식 애플리케이션이 비즈니스 목표에 적합하다면 해당 앱을 현대화하고 클라우드 최적화 작업을 진행할 수 있습니다.

마찬가지로 모놀리식 애플리케이션의 클라우드 최적화가 가능하다면 n 계층 애플리케이션처럼 좀 더 복잡한 다른 아키텍처 또한 클라우드 최적화 애플리케이션으로 현대화가 가능합니다.

>[!div class="step-by-step"]
>[이전](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[다음](what-about-cloud-native-applications.md)
