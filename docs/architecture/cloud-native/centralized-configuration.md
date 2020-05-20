---
title: 중앙 집중식 구성
description: Azure 앱 구성 및 AzureKey Vault를 사용 하 여 클라우드 네이티브 응용 프로그램에 대 한 구성을 중앙 집중화 합니다.
ms.date: 05/13/2020
ms.openlocfilehash: d389d29dcdb1db5162d95370d181ab5a85d72dc8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614229"
---
# <a name="centralized-configuration"></a>중앙 집중식 구성

모든 항목이 단일 인스턴스 내에서 실행 되는 모놀리식 앱과 달리 클라우드 네이티브 응용 프로그램은 가상 컴퓨터, 컨테이너 및 지리적 지역에 걸쳐 분산 된 독립적인 서비스로 구성 됩니다. 수십 개의 상호 의존적인 서비스에 대 한 구성 설정을 관리 하는 것은 어려울 수 있습니다. 서로 다른 위치에 있는 구성 설정의 중복 복사본은 오류가 발생 하기 쉬우며 관리가 어렵습니다. 중앙 집중식 구성은 분산 클라우드 네이티브 응용 프로그램에 대 한 중요 한 요구 사항입니다.

[1 장](introduction.md)에서 설명한 바와 같이 12 단계 앱 권장 사항은 코드와 구성 사이에 엄격한 분리가 필요 합니다. 구성을 응용 프로그램 외부에서 외부에 저장 하 고 필요에 따라 읽어야 합니다. 코드에 구성 값을 상수 또는 리터럴 값으로 저장 하는 것은 위반입니다. 같은 응용 프로그램의 여러 서비스에서 동일한 구성 값을 사용 하는 경우가 많습니다. 또한 개발, 테스트 및 프로덕션과 같은 여러 환경에서 동일한 값을 지원 해야 합니다. 모범 사례는 중앙 집중식 구성 저장소에 저장 하는 것입니다.

Azure 클라우드는 여러 가지 유용한 옵션을 제공 합니다.

## <a name="azure-app-configuration"></a>Azure App Configuration

[Azure 앱 구성은](https://docs.microsoft.com/azure/azure-app-configuration/overview) 안전 하 고 중앙 위치에서 비밀 없는 구성 설정을 저장 하는 완전히 관리 되는 Azure 서비스입니다. 저장 된 값은 여러 서비스와 응용 프로그램 간에 공유할 수 있습니다.

서비스는 간단 하 게 사용할 수 있으며 다음과 같은 몇 가지 이점을 제공 합니다.

- 유연한 키/값 표현 및 매핑
- Azure 레이블로 태그 지정
- 관리용 전용 UI
- 중요 한 정보 암호화
- 쿼리 및 일괄 처리 검색

Azure 앱 구성은 키-값 설정에 대 한 변경 내용을 7 일 동안 유지 합니다. 지정 시간 스냅숏 기능을 사용 하면 설정 기록을 다시 생성 하 고 실패 한 배포에 대해서도 롤백할 수 있습니다.

앱 구성은 구성 저장소에 대 한 과도 한 호출을 방지 하기 위해 각 설정을 자동으로 캐시 합니다. 구성 저장소에서 값이 변경되는 경우에도 새로 고침 작업은 설정의 캐시된 값이 만료될 때까지 기다린 후에 해당 설정을 업데이트합니다. 기본 캐시 만료 시간은 30초입니다. 만료 시간을 재정의할 수 있습니다.

앱 구성은 전송 및 휴지 상태의 모든 구성 값을 암호화 합니다. 키 이름과 레이블은 구성 데이터 검색을 위한 인덱스로 사용 되며 암호화 되지 않습니다.

앱 구성에서 강화 된 보안을 제공 하지만 Azure Key Vault은 여전히 응용 프로그램 비밀을 저장 하는 가장 좋은 장소입니다. Key Vault 하드웨어 수준 암호화, 세부적인 액세스 정책 및 인증서 회전과 같은 관리 작업을 제공 합니다. Key Vault에 저장 된 암호를 참조 하는 앱 구성 값을 만들 수 있습니다.

## <a name="azure-key-vault"></a>Azure Key Vault

Key Vault는 비밀을 안전 하 게 저장 하 고 액세스 하기 위한 관리 되는 서비스입니다. 비밀은 API 키, 암호 또는 인증서 등에 대한 액세스를 엄격하게 제어하려는 항목입니다. 자격 증명 모음은 암호의 논리적 그룹입니다.

Key Vault를 사용하면 비밀이 우발적으로 유출될 가능성이 대폭 감소합니다. Key Vault를 사용하면 애플리케이션 개발자가 더 이상 애플리케이션에 보안 정보를 저장할 필요가 없습니다. 이 방법을 통해 코드 내에이 정보를 저장할 필요가 없습니다. 예를 들어 애플리케이션이 데이터베이스에 연결해야 할 수 있습니다. 연결 문자열을 앱 코드에 저장하는 대신 Key Vault에 안전하게 저장할 수 있습니다.

애플리케이션은 URI를 사용하여 필요한 정보에 안전하게 액세스할 수 있습니다. 이러한 URI를 사용하면 애플리케이션이 특정 버전의 비밀을 검색할 수 있습니다. Key Vault에 저장 된 비밀 정보를 보호 하기 위해 사용자 지정 코드를 작성할 필요가 없습니다.

Key Vault에 액세스 하려면 적절 한 호출자 인증 및 권한 부여가 필요 합니다. 일반적으로 각 클라우드 기본 마이크로 서비스는 ClientId/ClientSecret 조합을 사용 합니다. 이러한 자격 증명은 소스 제어 외부에 보관 하는 것이 중요 합니다. 응용 프로그램 환경에서 설정 하는 것이 가장 좋습니다. AKS에서의 Key Vault에 대 한 직접 액세스는 [Key Vault의 볼륨](https://github.com/Azure/kubernetes-keyvault-flexvol)을 사용 하 여 달성할 수 있습니다.

## <a name="configuration-in-eshop"></a>EShop의 구성

EShopOnContainers 응용 프로그램에는 각 마이크로 서비스를 사용 하는 로컬 응용 프로그램 설정 파일이 포함 됩니다. 이러한 파일은 소스 제어에 체크 인 되지만 연결 문자열 또는 API 키와 같은 프로덕션 암호는 포함 되지 않습니다. 프로덕션에서 개별 설정은 서비스별 환경 변수를 사용 하 여 덮어쓸 수 있습니다. 환경 변수에 비밀을 삽입 하는 것은 호스팅된 응용 프로그램의 일반적인 방법 이지만 중앙 구성 저장소는 제공 하지 않습니다. 구성 설정에 대 한 중앙 집중식 관리를 지원 하기 위해 각 마이크로 서비스에는 로컬 설정 사용 또는 Azure Key Vault 설정 사이를 전환 하는 설정이 포함 됩니다.

## <a name="references"></a>참조

- [EShopOnContainers 아키텍처](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Architecture)
- [높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 애플리케이션 오케스트레이션](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/scalable-available-multi-container-microservice-applications)
- [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)
- [Azure SQL Database 개요](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)
- [Azure Cache for Redis](https://azure.microsoft.com/services/cache/)
- [Azure Cosmos DB의 API for MongoDB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Monitor 개요](https://docs.microsoft.com/azure/azure-monitor/overview)
- [eShopOnContainers: AKS에서 Kubernetes 클러스터 만들기](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev 공간](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[이전](deploy-eshoponcontainers-azure.md)
>[다음](scale-applications.md)
