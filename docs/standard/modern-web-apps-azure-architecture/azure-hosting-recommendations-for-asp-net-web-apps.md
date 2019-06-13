---
title: ASP.NET Core 웹앱에 대한 Azure 호스팅 권장 사항
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 애플리케이션 설계 | ASP.NET 웹앱에 대한 Azure 호스팅 권장 사항
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 7cfb9ada4f963aa392a41cfb9f1b2df22f542d41
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758685"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>ASP.NET Core 웹앱에 대한 Azure 호스팅 권장 사항

> "모든 기간 업무 리더는 IT 부서를 거치지 않고 클라우드(SaaS라고도 함)에서 애플리케이션을 다운로드한 후 잡지를 구독하듯 사용료를 지불합니다. 그리고 서비스가 더 이상 필요하지 않으면 사용하지 않는 장비를 굳이 한 구석에 남겨둘 필요 없이 구독을 취소하기만 하면 됩니다.”  
> _\- Gartner 분석가 Daryl Plummer_

애플리케이션의 요구 사항 및 아키텍처가 무엇이든 Windows Azure는 이를 지원할 수 있습니다. 호스팅 요구 사항은 수십 가지 서비스로 이루어진 복잡한 애플리케이션에 대한 정적 웹 사이트처럼 간단할 수 있습니다. ASP.NET Core 모놀리식 웹 애플리케이션 및 지원 서비스에 권장되는 잘 알려진 구성이 몇 가지 있습니다. 이 문서의 권장 사항은 모든 애플리케이션, 개별 프로세스 또는 데이터에 관계없이 호스팅할 리소스의 종류에 따라 그룹화되어 있습니다.

## <a name="web-applications"></a>웹 애플리케이션

웹 애플리케이션은 다음을 통해 호스팅할 수 있습니다.

- App Service Web Apps

- 컨테이너 (몇 가지 옵션)

- VM(가상 머신)

이러한 App Service Web Apps는 간단한 컨테이너 기반 앱을 비롯 한 대부분의 시나리오에서 권장 되는 방법. 마이크로서비스 아키텍처의 경우 컨테이너 기반 접근 방식을 고려합니다. 애플리케이션을 실행하는 컴퓨터에 대한 더 세부적인 제어가 필요할 경우 Azure Virtual Machines를 고려합니다.

### <a name="app-service-web-apps"></a>App Service Web Apps

App Service Web Apps는 웹 애플리케이션 호스팅에 최적화된 완벽하게 관리되는 플랫폼을 제공합니다. 이는 비즈니스 논리에 집중할 수 있게 해주는 PaaS(Platform-as-a-service) 솔루션이며, Azure는 앱 실행 및 확장에 필요한 인프라를 관리합니다. App Service Web Apps의 몇 가지 주요 기능:

- DevOps 최적화(지속적인 통합 및 업데이트, 여러 환경, A/B 테스트, 스크립팅 지원)

- 세계적인 규모 및 고가용성

- SaaS 플랫폼 및 온-프레미스 데이터에 대한 연결

- 보안 및 규정 준수

- Visual Studio 통합

Azure App Service는 대부분의 웹앱에 가장 적합한 선택입니다. 배포 및 관리가 플랫폼에 통합되어 있고, 사이트가 높은 트래픽 부하를 처리하기 위해 빠르게 확장될 수 있으며, 기본 제공되는 부하 분산 및 트래픽 관리자가 고가용성을 제공합니다. 온라인 마이그레이션 도구를 사용하여 기존 사이트를 Azure App Service로 쉽게 이동하거나, 웹 애플리케이션 갤러리에서 오픈 소스 애플리케이션을 사용하거나, 원하는 프레임워크와 도구를 사용하여 새 사이트를 만들 수 있습니다. Webjob 기능을 사용하면 백그라운드 작업 처리를 App Service 웹앱에 쉽게 추가할 수 있습니다. 기존 ASP.NET 응용 프로그램에 온-프레미스 로컬 데이터베이스를 사용 하 여 호스트 된 경우 앱을 마이그레이션하는 Azure SQL Database (또는 원하는 경우 온-프레미스 데이터베이스 서버에 대 한 보안 액세스)를 사용 하 여 App Service 웹 앱에 명확한 경로가 있는지 합니다.

![권장된 마이그레이션 전략에 대 한 온-프레미스 Azure App Service에.NET 앱](./media/image1-6.png)

대부분의 경우에서 로컬에서 호스트 된 ASP.NET 앱에서 App Service 웹 앱을 이동은 간단한 프로세스입니다. 앱 자체의 거의 또는 전혀 수정 해야 하 고 Azure App Service Web Apps에서 제공 하는 다양 한 기능을 활용 하기 위해 빠르게 시작할 수 있습니다.

클라우드에 대 한 최적화 되지 않은 앱 외에도 Azure App Service Web Apps는 간단한 모놀리식 (비분산) 같은 많은 응용 프로그램이, 대부분의 ASP.NET Core 앱에 대 한는 훌륭한 솔루션입니다. 이 방법에서는 아키텍처를 기본으로 간편 하 게 이해 하 고 관리 합니다.

![기본 Azure 아키텍처](./media/image1-5.png)

소수의 단일 리소스 그룹의 리소스는 일반적으로 이러한 앱을 관리 하는 데 충분 합니다. 일반적으로 하나의 단위로 배포 되는 앱이 아닌 별도 프로세스 대부분의 구성 된 해당 앱은이 대 한 좋은 후보 [기본 아키텍처 접근 방법을](https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app)합니다. 이 방법을 (노드당 더 많은 리소스)를 모두 확장 및 축소 호스팅된 응용 프로그램 계속 사용 하면 구조적으로 간단 하지만 (더 호스트 노드) 수요에서 증가 충족 하도록 합니다. 자동 크기 조정 등을 사용 하 여 노드 간에 요청 및 평균 부하에 따라 앱을 호스트 하는 노드의 수를 자동으로 조정 하도록 앱을 구성할 수 있습니다.

### <a name="app-service-web-apps-for-containers"></a>App Service Web Apps for Containers

웹 앱을 직접 호스팅 지원 외에도 [App Service Web Apps for Containers](https://azure.microsoft.com/services/app-service/containers/) Windows 및 Linux에서 컨테이너 화 된 응용 프로그램 실행에 사용할 수 있습니다. 이 서비스를 사용 하 여, 있습니다 수 쉽게 배포 하 고 비즈니스에 맞게 확장 될 수 있는 컨테이너 화 된 응용 프로그램을 실행 합니다. 앱의 모든 기능 위에 나열 된 App Service Web Apps의 경우 또한 웹 앱 컨테이너 지원에 대 한 Docker 허브, Azure Container Registry 및 GitHub를 사용 하 여 CI/CD를 간소화 합니다. 레지스트리 변경 내용을 게시 하는 빌드 및 배포 파이프라인을 정의 하려면 Azure DevOps를 사용할 수 있습니다. 이러한 변경 내용은 스테이징 환경에서 테스트 고 무중단 업그레이드를 허용 하 고 배포 슬롯을 사용 하 여 프로덕션에 자동으로 배포 수 있습니다. 이전 버전으로 롤백하는 쉽게 수행할 수 있습니다.

Web Apps for Containers 적합 하 게 몇 가지 시나리오가 있습니다. Windows 또는 Linux 컨테이너에서 기존 앱을 컨테이너 화할 수 있는 경우이 도구 집합을 사용 하 여 쉽게 호스트할 수 있습니다. 단순히 컨테이너를 게시 하 고 선택한 레지스트리에서 해당 이미지의 최신 버전을 가져오려고 컨테이너용 Web Apps를 구성 합니다. 이것이 클래식 앱 호스팅 클라우드에 최적화 된 모델에 모델에서에서 마이그레이션하는 것을 "리프트 앤 시프트" 접근 방식입니다.

![Azure Web Apps for Containers에 컨테이너 화 된 온-프레미스.NET 응용 프로그램 마이그레이션](./media/image1-8.png)

이 방법은 개발 팀이 컨테이너 기반 개발 프로세스를 이동할 수 있는 경우에에 작동 합니다. 컨테이너를 사용 하 여 앱을 개발 하는 "내부 루프" 컨테이너를 사용 하 여 앱 빌드를 포함 합니다. 컨테이너 구성에 대 한도 코드 변경 내용을 소스 제어에 푸시됩니다 이며 자동화 된 빌드 같은 Docker 허브 레지스트리 또는 Azure Container Registry에 새 컨테이너 이미지를 게시 하는 일을 담당 합니다. 이러한 이미지는 다음의 기초로 사용 프로덕션에 배포 뿐만 아니라 추가 개발을 위해 다음 다이어그램에 나와 있는 것 처럼:

![종단 간 Docker DevOps 수명 주기 워크플로](./media/image1-7.png)

컨테이너를 사용 하 여 개발는 컨테이너는 프로덕션 환경에서 사용 하는 경우에 특히 많은 이점을 제공 합니다. 동일한 컨테이너 구성은 실행 되는, 빌드 및 테스트 시스템에서 프로덕션으로 로컬 개발 컴퓨터에서 각 환경에서 앱을 호스트에 사용 됩니다. 이 컴퓨터 구성 또는 소프트웨어 버전 차이로 인해 결함 가능성이 크게 줄어듭니다. 개발자는 어떤 도구 들은 운영 체제를 포함 하 여, 가장 생산적인 모든 OS에서 컨테이너를 실행할 수 있으므로 사용할 수도 있습니다. 많은 컨테이너를 포함 하는 분산된 응용 프로그램 리소스를 매우 많이 단일 개발 컴퓨터에서 실행할 수도 있습니다. 이 시나리오에서는 Kubernetes 및 다음 섹션에서 다루는 Azure 개발 공간을 사용 하 여로 업그레이드 하는 것이 해야 합니다.

대규모 응용 프로그램 부분으로 세분화 되 자신의 작은 독립적으로 *마이크로 서비스*, 앱 동작을 개선 하기 위해 추가 디자인 패턴을 사용할 수 있습니다. 개별 서비스와 직접 작업 하는 대신 한 *API 게이트웨이* 액세스를 간소화 하는 백 엔드의 클라이언트를 분리 합니다. 백 엔드 다른 프런트 엔드에 대 한 별도 서비스에 서비스를 소비자와 함께에서 발전 시킬 수 있습니다. 별도 공용 서비스에 액세스할 수 있습니다 *사이드카* 컨테이너를 사용 하 여 일반적인 클라이언트 연결 라이브러리 포함 될 수 있습니다 합니다 *특사* 패턴입니다.

![마이크로 서비스 설명 하는 몇 가지 일반적인 디자인 패턴을 사용 하 여 아키텍처를 샘플링 합니다.](./media/image1-10.png)

[마이크로 서비스 기반 시스템을 구축할 때 고려해 야 할 디자인 패턴에 대해 알아봅니다.](https://docs.microsoft.com/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

AKS(Azure Kubernetes Service)는 컨테이너 오케스트레이션 전문 지식 없이도 컨테이너화된 애플리케이션을 빠르고 쉽게 배포 및 관리할 수 있도록 해주는 호스트된 Kubernetes 환경을 관리합니다. 또한 애플리케이션을 오프라인으로 전환하지 않고 요청 시 리소스를 프로비전, 업그레이드 및 크기 조정하여 진행 중인 작업 및 유지 관리 부담을 덜어줍니다.

AKS는 대부분의 책임을 Azure로 오프로드함으로써 Kubernetes 클러스터 관리에 대한 복잡성 및 운영 오버헤드를 줄입니다. 호스트된 Kubernetes 서비스처럼, Azure는 상태 모니터링 및 유지 관리와 같은 중요 작업을 처리합니다. 또한 사용자는 마스터가 아닌 사용자 클러스터 내 에이전트 노드에 대해서만 비용을 지불합니다. 관리되는 Kubernetes 서비스로서 AKS는 다음을 제공합니다.

- 자동화된 Kubernetes 버전 업그레이드 및 패치.
- 간편한 클러스터 크기 조정.
- 자체 복구 호스팅된 컨트롤 평면(마스터).
- 비용 절감 - 실행 중인 에이전트 풀 노드에 대해서만 지불.

이제 AKS 클러스터의 노드 관리를 처리하는 Azure를 사용하면 클러스터 업그레이드와 같은 여러 작업을 수동으로 수행하지 않아도 됩니다. Azure가 사용자를 위해 이와 같은 중요한 유지 관리 작업을 처리하므로 AKS는 클러스터에 대한 직접 액세스를 제공하지 않습니다(예: SSH 사용).

AKS를 활용 하는 팀도 활용할 수 Azure 개발 공간입니다. Azure 개발 공간을 사용 하면 팀 팀이 해당 전체 마이크로 서비스 아키텍처 또는 AKS에서 실행 중인 응용 프로그램에 직접 작업할 수 있도록 하 여 마이크로 서비스 응용 프로그램 이므로 신속한 반복 개발에 집중할 수 있습니다. Azure 개발 공간에는 또한 AKS 클러스터 또는 다른 개발자의 나머지 부분에 영향을 주지 않고 독립적으로 격리 된 상태에서 마이크로 서비스 아키텍처의 일부를 업데이트 하는 방법을 제공 합니다.

![Azure 개발 공간 워크플로 예제](./media/image1-9.gif)

Azure Dev Spaces

- 로컬 컴퓨터 설치 시간 및 리소스 요구 사항을 최소화합니다
- 팀이 더 신속 하 게 반복
- 팀에 필요한 통합 환경 수 줄이기
- 제거를 개발 하 고 테스트 하는 경우 분산된 시스템에서 특정 서비스를 모의 해야 합니다.

[Azure 개발 공간에 자세히 알아보기](https://docs.microsoft.com/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

App Service에서 실행하려면 상당한 수정이 필요한 기존 애플리케이션의 경우, 클라우드로의 마이그레이션을 간소화하기 위해 Virtual Machines를 선택할 수 있습니다. 그러나 VM을 올바르게 구성, 보호 및 유지 관리하려면 Azure App Service보다 훨씬 더 많은 시간과 IT 전문 지식이 필요합니다. Azure Virtual Machines를 고려 중이라면 VM 환경을 패치, 업데이트 및 관리하는 데 지속적인 유지 관리 노력이 필요함을 염두에 두어야 합니다. Azure Virtual Machines는 IaaS(서비스 형태의 인프라)이며, App Service는 PaaS(Platform-as-a-Service)입니다. 또한 앱을 Windows 컨테이너로 Web App for Containers에 배포하는 것이 시나리오에 유용한 옵션인지도 고려해야 합니다.

## <a name="logical-processes"></a>논리적 프로세스

애플리케이션의 나머지 부분과 분리될 수 있는 개별 논리 프로세스는 "서버가 없는" 방식으로 Azure Functions에 별도로 배포할 수 있습니다. Azure Functions를 사용하면 코드를 실행할 애플리케이션 또는 인프라에 대한 걱정 없이 주어진 문제에 필요한 코드를 작성할 수 있습니다. C\#, F\#, Node.js, Python 및 PHP를 포함하는 다양한 프로그래밍 언어 중에서 작업에 가장 생산적인 언어를 선택할 수 있습니다. 대부분의 클라우드 기반 솔루션과 마찬가지로 사용 시간만큼 요금을 지불하고 Azure Functions를 필요에 따라 확장할 수 있습니다.

## <a name="data"></a>데이터

Azure는 다양한 데이터 저장 옵션을 제공하므로, 애플리케이션이 해당 데이터에 대해 적절한 데이터 공급자를 사용할 수 있습니다.

트랜잭션, 관계형 데이터의 경우 Azure SQL Database가 가장 적합한 옵션입니다. 대부분 읽기 전용인 고성능 데이터의 경우 Azure SQL Database에서 지원하는 Redis 캐시가 적합한 솔루션입니다.

구조화되지 않은 JSON 데이터는 SQL Database 열에서 Azure Storage의 Blob 또는 테이블, DocumentDB에 이르기까지 다양한 방법으로 저장할 수 있습니다. 이 중에서 DocumentDB는 최상의 쿼리 기능을 제공하며, 쿼리를 지원해야 하는 다수의 JSON 기반 문서에 권장되는 옵션입니다.

애플리케이션 동작을 오케스트레이션하는 데 사용되는 일시적인 명령 또는 이벤트 기반 데이터는 Azure Service Bus 또는 Azure Storage Queue를 사용할 수 있습니다. Azure Storage Bus는 더 많은 유연성을 제공하며 애플리케이션 내 및 애플리케이션 간의 중요한 메시징에 권장되는 서비스입니다.

## <a name="architecture-recommendations"></a>아키텍처 권장 사항

애플리케이션의 요구 사항에 따라 아키텍처가 결정됩니다. 여러 다양한 Azure 서비스를 사용할 수 있습니다. 적합한 서비스를 선택하는 것은 중요한 의사 결정입니다. Microsoft는 일반적인 시나리오에 최적화된 일반적인 아키텍처를 식별하는 데 도움이 되는 참조 아키텍처의 갤러리를 제공합니다. 애플리케이션의 요구 사항과 밀접한 관련이 있거나 적어도 시작점을 제공하는 참조 아키텍처를 찾을 수 있습니다.

그림 11-2는 참조 아키텍처의 예를 보여줍니다. 이 다이어그램에서는 마케팅에 최적화된 Sitecore 콘텐츠 관리 시스템 웹 사이트에 권장되는 아키텍처 접근 방식을 설명합니다.

![](./media/image11-2.png)

**그림 11-1.** Sitecore 마케팅 웹 사이트 참조 아키텍처

**참조 - Azure 호스팅 권장 사항**

- Azure 솔루션 아키텍처\
  <https://azure.microsoft.com/solutions/architecture/>

- Azure의 기본 웹 응용 프로그램 Architecture\
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Microservices\에 대 한 디자인 패턴
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Azure 개발자 가이드\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- 웹앱 개요\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Web App for Containers\
  <https://azure.microsoft.com/services/app-service/containers/>

- AKS(Azure Kubernetes Service) 소개\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[이전](development-process-for-azure.md)
