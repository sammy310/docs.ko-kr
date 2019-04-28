---
title: 서버 리스 앱 아키텍처 배포 접근 방식
description: 다양 한 방법으로 엔터프라이즈 아키텍처에 대 한 가이드는 IaaS, PaaS, 컨테이너 간의 비교를 사용 하 여 클라우드로 배포 및 서버 리스입니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5477b8c4531780fdebf194e4f798564e59cd2953
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640288"
---
# <a name="architecture-deployment-approaches"></a>아키텍처 배포 접근 방식

아키텍처에 관계 없이 비즈니스 응용 프로그램, 구현, 또는 해당 응용 프로그램의 배포를 디자인 하는 데 사용 하는 방법은 다를 수 있습니다. 서버 리스 함수에 실제 하드웨어에서 모든 응용 프로그램을 호스트 하는 기업입니다.

## <a name="n-tier-applications"></a>N 계층 응용 프로그램

합니다 [N 계층 아키텍처 패턴](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) 는 완성도 높은 아키텍처 및 다양 한 논리적 계층을 별도 물리적 계층 분리는 응용 프로그램에 참조 하기만 하면 됩니다. N 계층 아키텍처는 N 계층 아키텍처의 실제 구현 합니다. 이 아키텍처의 가장 일반적인 구현에는 다음이 포함 됩니다.

* 프레젠테이션 계층, 예를 들어 웹 앱입니다.
* API 또는 데이터 액세스 REST API와 같은 계층입니다.
* SQL database와 같은 데이터 계층입니다.

![N 계층 아키텍처](./media/n-tier-architecture.png)

N 계층 솔루션에는 다음과 같은 특징이 있습니다.

* 프로젝트는 일반적으로 계층을 사용 하 여 정렬 됩니다.
* 테스트 접근할 수 다르게 계층에서.
* 예를 들어 프레젠테이션 계층은 일반적으로 데이터 계층의 구현 세부 사항을 무시, 계층 추상화 계층을 제공 합니다.
* 일반적으로 계층 으로만 인접 한 계층 상호 작용 합니다.
* 프로젝트에서 종종 관리와 따라서 계층, 수준 해제 합니다. 간단한 API 변경에는 전체 중간 계층의 새 릴리스가 필요할 수 있습니다.

이 방법은 등을 비롯 한 여러 이점을 제공 합니다.

* 데이터베이스의 격리 (종종 프런트 엔드 없는 데이터베이스 백 엔드에 대 한 직접 액세스).
* API (예를 들어, 모바일, 데스크톱 및 웹 앱 클라이언트 모든 다시 사용할 수 있도록 동일한 Api 수)를 다시 사용 합니다.
* 계층을 서로 독립적으로 확장할 수 있습니다.
* 격리를 리팩터링 합니다: 다른 계층에 영향을 주지 않고 계층을 리팩터링할 수 있습니다.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>온-프레미스 및 Infrastructure as a Service (IaaS)

응용 프로그램을 호스트 하는 기존의 방법은 하드웨어를 구입 하 고 관리 하는 모든 운영 체제를 포함 하 여 소프트웨어 설치에 필요 합니다. 원래 비용이 많이 드는 데이터 센터와 실제 하드웨어 포함 합니다. 물리적 하드웨어를 운영 하는 함께 제공 되는 문제를 많은 포함:

* "만약의 경우"에 대 한 과도 한 구매 또는 최대 수요 시나리오에 필요 합니다.
* 하드웨어에 대 한 물리적 액세스를 보호합니다.
* 하드웨어 오류 (예: 디스크 오류)에 대 한 납세 의무.
* 냉각 합니다.
* 라우터 및 부하 분산 장치를 구성 합니다.
* 전원 중복 됩니다.
* 소프트웨어 액세스를 보호합니다.

![IaaS 방식이](./media/iaas-approach.png)

"가상 머신"를 통해 하드웨어 가상화 서비스 (IaaS) 인프라를 설정합니다. 호스트 컴퓨터 자체 메모리, CPU 및 저장소에 대 한 할당을 사용 하 여 리소스 인스턴스를 제공 하려면 효과적으로 분할 됩니다. 필요한 Vm을 프로 비전 하 고 연결 된 네트워크 및 저장소에 대 한 액세스를 구성 하는 팀입니다.

자세한 내용은 [가상 머신 N 계층 참조 아키텍처](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)합니다.

가상화 및 인프라 (IaaS) 서비스로 많은 문제를 해결 하지만 여전히 담당자가 많은 책임 인프라 팀의 손에 있습니다. 팀에 운영 체제 버전을 유지 관리, 보안 패치를 적용 및 대상 컴퓨터에서 타사 종속성을 설치 합니다. 또한 테스트 환경에 비해 프로덕션 컴퓨터에서 앱 종종 다르게 동작 합니다. 서로 다른 종속성 버전 및/또는 OS SKU 수준으로 인해 문제가 발생 합니다. 대부분의 회사와 같은 더 많은 클라우드 네이티브 모델에 배포에서 이점을 얻을 수 있지만 대부분의 조직에서는 이러한 대상에 N 계층 응용 프로그램을 배포 하는 경우 [Platform-as-a-service](#platform-as-a-service-paas)합니다. 마이크로 서비스 아키텍처는 탄력성 및 복구 기능에 대 한 확장 요구 사항으로 인해 좀 더 어렵습니다.

자세한 내용은 [가상 머신](https://docs.microsoft.com/azure/virtual-machines/)합니다.

## <a name="platform-as-a-service-paas"></a>Platform as a Service (PaaS)

플랫폼 (PaaS) 서비스에서 제공 솔루션 개발자에 직접 연결할 수 있는 구성입니다. PaaS는 관리 되는 호스팅에 대 한 다른 용어입니다. 기본 운영 체제를 관리할 필요가, 보안 패치 및 대부분의 경우 타사 종속성입니다. 플랫폼의 예로 데이터베이스, 웹 응용 프로그램 및 모바일 백 엔드입니다.

PaaS는 IaaS로 일반적인 문제를 해결합니다. PaaS는 개발자를 배포 되는 방법 보다는 코드 또는 데이터베이스 스키마에 집중할 수 있습니다. PaaS의 이점은 다음과 같습니다.

* 유휴 컴퓨터에 투자 하는 오버 헤드를 제거 하는 사용 하 여 모델에 대 한 요금을 지불 합니다.
* 배포 및 향상 된 DevOps, 연속 통합 (CI) 및 CD (지속적인 업데이트) 파이프라인을 지시 합니다.
* 자동 업그레이드, 업데이트 및 보안 패치 합니다.
* 누름 규모 확장 및 수직 확장 (탄력적인).

일반적으로 PaaS의 주요 단점은 공급 업체에 되었습니다. 예를 들어, 일부 PaaS 공급자 ASP.NET, Node.js 또는 다른 특정 언어 및 플랫폼에만 지원합니다. Azure App Service와 같은 제품 여러 플랫폼을 해결 하 고 웹 앱을 호스트 하는 것에 대 한 다양 한 언어 및 프레임 워크를 지원 하도록 발전 했습니다.

![서비스 아키텍처와 플랫폼](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software as a Service (SaaS)

서비스 또는 SaaS 소프트웨어 인지 중앙에서 호스 티 드 및 로컬 설치 없이 사용할 수 있는 프로 비전 합니다. SaaS 종종 위에 호스팅되는 PaaS 소프트웨어를 배포 하기 위한 플랫폼으로 합니다. SaaS 제공 서비스를 실행 하 고 기존 소프트웨어를 사용 하 여 연결 합니다. SaaS는 산업 및 수직 특정 경우가 많습니다. SaaS는 자주 사용이 허가 됩니다 하 고 일반적으로 클라이언트/서버 모델을 제공 합니다. 대부분의 최신 SaaS 제품을 클라이언트에 대 한 웹 기반 앱을 사용합니다. 일반적으로 회사는 비즈니스 솔루션 라이선스 제품으로 SaaS를 고려합니다. 이 확장성 및 응용 프로그램의 유지 관리에 대 한 아키텍처 고려 사항으로 자주 구현 되지 않습니다. 실제로 대부분의 SaaS 솔루션은 IaaS, PaaS 및/또는 서버 리스 백 엔드에 빌드됩니다.

통해 SaaS에 대 한 자세한 정보를 [샘플 응용 프로그램](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)합니다.

## <a name="containers-and-functions-as-a-service-faas"></a>컨테이너 및 Functions as a Service (FaaS)

컨테이너는 IaaS 오버 헤드 없이 PaaS 같은 혜택을 사용 하도록 설정 하는 흥미로운 솔루션입니다. 컨테이너는 기본적으로 고유한 응용 프로그램을 실행 하는 데 필요한 완전 한 필수 정보를 포함 하는 런타임. 호스트 운영 체제 및 저장소와 같은 서비스의 일부 커널 또는 core 호스트 간에 공유 됩니다. 공유 커널 간단 하 게 컨테이너를 사용 하도록 설정 (일부는 크기, 일반적인 가상 머신의 기가바이트 크기에 비해 단순한 메가바이트)입니다. 이미 실행 중인 호스트를 사용 하 여 컨테이너 시작할 수 있습니다 신속 하 게 고가용성을 지원 합니다. 또한 컨테이너를 빠르게 스핀업 하는 기능 복원 력의 추가 계층을 제공 합니다. Docker는 컨테이너의 많이 구현 중 하나입니다.

컨테이너의 이점은 다음과 같습니다.

* 간단 하 고 이식 가능
* 자체 포함 된 종속성을 설치할 필요가 없습니다
* 호스트 (클라우드 서버에서 랩톱에서 정확히 동일한 실행)에 관계 없이 일관 된 환경을 제공 합니다.
* 스케일 아웃에 대 한 신속 하 게 프로비저닝할 수 있습니다.
* 다시 시작할 수 있습니다 신속 하 게 오류를 복구 하려면

컨테이너 (에 운영 체제 미 설치 컴퓨터 또는 가상 컴퓨터에서 실행할 수 있습니다)는 컨테이너 호스트에서 실행 됩니다. 여러 컨테이너 또는 같은 컨테이너의 인스턴스는 단일 호스트에서 실행할 수 있습니다. 완벽 한 장애 조치 및 복구 기능에 대 한 호스트에서 컨테이너를 확장 해야 합니다.

Docker 컨테이너에 대 한 자세한 내용은 참조 하세요. [Docker 란](../microservices-architecture/container-docker-introduction/docker-defined.md)?

일반적으로 호스트에서 컨테이너를 관리 Kubernetes 같은 오케스트레이션 도구에 필요 합니다. 구성 및 오케스트레이션 솔루션을 관리 프로젝트에 추가 오버 헤드와 복잡성을 추가할 수 있습니다. 다행 스럽게도 대부분의 클라우드 공급자는 컨테이너의 관리를 단순화 하려면 PaaS 솔루션을 통해 오케스트레이션 서비스를 제공 합니다.

다음 이미지에서는 Kubernetes 설치 예제를 보여 줍니다. 설치에 대 한 노드 규모 확장 및 장애 조치를 해결합니다. 마스터 서버에 의해 관리 되는 컨테이너 인스턴스에 Docker 실행 됩니다. 합니다 *kubelet* Kubernetes에서 Docker 명령을 릴레이 클라이언트입니다.

![Kubernetes](./media/kubernetes-example.png)

오케스트레이션에 대 한 자세한 내용은 참조 하세요. [Azure의 Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)합니다.

서비스로 (FaaS) 함수는 서버 리스 유사한 특수 한 컨테이너 서비스입니다. FaaS, 호출의 특정 구현을 [OpenFaaS](https://github.com/openfaas/faas), 서버 리스 기능을 제공 하는 컨테이너 기반으로 합니다. OpenFaaS는 컨테이너 종속성 코드 조각을 실행 하는 데 필요한 모든 패키지는 템플릿을 제공 합니다. 템플릿을 사용 하 여 하나의 기능 단위로 코드를 배포 하는 과정을 간소화 합니다. OpenFaaS 기존 인프라를 사용할 수 있기 때문에 컨테이너 및 오 케 스트레이 터를 이미 포함 하는 아키텍처를 대상으로 합니다. 서버 리스 기능을 제공 하지만 특히 해야 Docker 및 오 케 스트레이 터를 사용 합니다.

## <a name="serverless"></a>서버 리스

서버 리스 아키텍처를 코드와 호스팅 환경 간의 분리를 제공합니다. 코드를 구현 하는 *함수* 하 여 호출 되는 *트리거*합니다. 해당 함수 종료 된 후 필요한 모든 리소스를 해제 될 수 있습니다. 트리거는 수동, 시간 제한 프로세스, HTTP 요청 또는 파일 업로드 수 있습니다. 트리거의 결과 코드를 실행 합니다. 서버 리스 플랫폼 다르지만 가장 액세스할 미리 정의 된 Api 및 바인딩의 데이터베이스 또는 큐 결과를 작성 하는 등 작업을 간소화 합니다.

서버 리스는 코드를 중점적으로 호스트 환경 추상화에 크게 의존 하는 아키텍처입니다. 으로 생각할 수 있습니다 *서버가*합니다.

컨테이너 솔루션 개발자가 기존 빌드 서버 리스 준비 이미지에 코드를 게시 하는 스크립트를 제공 합니다. 다른 구현과 확장 가능한 아키텍처를 제공 합니다. 기존 PaaS 솔루션을 사용 합니다.

추상화는 DevOps 팀 프로 비전 또는 관리 서버 또는 특정 컨테이너에 없는 것을 의미 합니다. 서버 리스 플랫폼 호스트 코드, 스크립트 또는 패키지에 포함 된 실행 파일을 관련된 SDK를 사용 하 여 작성 하 고 코드의 크기를 조정 하는 데 필요한 리소스를 할당 합니다.

다음 그림에서는 4 개의 서버가 없는 구성 요소 다이어그램입니다. HTTP 요청에서 체크 아웃 API 코드를 실행 하면 됩니다. 체크 아웃 API 데이터베이스에 코드를 삽입 하 고 삽입 컴퓨팅 작업 처리 등의 작업을 수행 하기 위해 실행 하는 여러 다른 함수를 트리거합니다.

![서버 리스 구현](./media/serverless-implementation.png)

서버 리스의 장점은 다음과 같습니다.

* **높은 밀도입니다.** 대부분의 서버 리스 코드는 컨테이너 또는 가상 컴퓨터에 비해 동일한 호스트에서 실행할 수 있습니다. 여러 호스트 규모 확장 및 복원 력 인스턴스 소수 자릿수입니다.
* **Micro 청구**합니다. 대부분의 서버 리스 공급자 청구서를 기반으로 특정 시나리오에 대규모 비용 절감을 사용 하도록 설정 하는 서버 리스 실행 합니다.
* **즉시 확장**합니다. 서버는 자동으로 하 고 빠르게 워크 로드에 맞게 확장할 수 있습니다.
* **출시 시간 단축** 개발자가 코드에 집중 하 고 서버 리스 플랫폼에 직접 배포 합니다. 구성 요소는 서로 독립적으로 릴리스할 수 있습니다.

서버 계산 컨텍스트의 가장 자주 설명 되어 있지만 데이터에 적용할 수도 있습니다. 예를 들어 [Azure SQL](https://docs.microsoft.com/azure/sql-database) 하 고 [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) 모두 호스트 컴퓨터 또는 클러스터를 구성할 필요가 없는 클라우드 데이터베이스를 제공 합니다. 이 가이드는 서버 리스 계산에 중점을 둡니다.

## <a name="summary"></a>요약

아키텍처의 경우 하이브리드 방식을 포함 하 여 사용 가능한 선택 항목까지 다양 한 방법이 있습니다. 서버를 사용 방법, 관리 및 응용 프로그램 기능 제어 및 이식성 희생 원가 간소화합니다. 그러나 많은 서버 리스 플랫폼 솔루션을 미세 조정 하는 데 구성을 표시지 않습니다. 이식성이 높은 코드를 줄이고 서버 리스 플랫폼 잠금에 바람직한 프로그래밍 방식도 발생할 수도 있습니다. 다음 표에서 아키텍처 접근 방법을 나란히 보여 줍니다. 서버 리스 기준으로 선택 하 여 확장 요구 사항, 런타임, 관리 하려는 여부 및 얼마나 잘 작은 구성 요소로으로 워크 로드를 나눌 수 있습니다. 서버 리스를 사용 하 여 잠재적인 문제 및 다른 의사 결정 지점 다음 장에서에 대해 알아봅니다.

|         |IaaS     |PaaS     |컨테이너|서버 리스|
|---------|---------|---------|---------|----------|
|**배율**|VM       |인스턴스 |앱      |함수  |
|**Abstracts**|하드웨어|플랫폼|호스트 OS|런타임   |
|**Unit** |VM       |프로젝트  |이미지    |코드      |
|**수명(lifetime)**|개월|개월 기간 (일)|일 분|분 시간 (밀리초)|
|**책임**|응용 프로그램, 종속성, 런타임 및 운영 체제|응용 프로그램 및 종속성|응용 프로그램, 종속성 및 런타임|함수

* **확장** 응용 프로그램을 확장 하는 데 사용 되는 장치를 말합니다
* **추상화** 구현에 의해 추상화 되는 계층에 대 한 참조
* **단위** 는 배포 된 범위를 가리킵니다.
* **수명** 특정 인스턴스의 일반적인 런타임 참조
* **책임** 오버 헤드를 빌드, 배포 및 응용 프로그램 유지 관리 참조

다음 장에서 서버 리스 아키텍처에 집중, 사용 사례 및 디자인 패턴

## <a name="recommended-resources"></a>권장 되는 리소스

* [Azure 응용 프로그램 아키텍처 가이드](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [Azure SQL](https://docs.microsoft.com/azure/sql-database)
* [N 계층 아키텍처 패턴](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Azure의 Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [마이크로 서비스](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [가상 머신 N 계층 참조 아키텍처](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [가상 컴퓨터](https://docs.microsoft.com/azure/virtual-machines/)
* [Docker란?](../microservices-architecture/container-docker-introduction/docker-defined.md)
* [Wingtip Tickets SaaS 응용 프로그램](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[이전](architecture-approaches.md)
>[다음](serverless-architecture.md)