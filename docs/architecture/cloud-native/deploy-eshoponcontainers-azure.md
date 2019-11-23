---
title: Azure에 eShopOnContainers 배포
description: Azure Kubernetes Service, 투구 및 DevSpaces를 사용 하 여 eShopOnContainers 응용 프로그램을 배포 합니다.
ms.date: 06/30/2019
ms.openlocfilehash: 21033cc904dc595193c69f3452ce2522740f8ff6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840492"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Azure에 eShopOnContainers 배포

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Azure에서 다양 한 서비스를 사용 하 여 eShopOnContainers 응용 프로그램을 지 원하는 논리를 지원할 수 있습니다. Azure Kubernetes Service (AKS)를 사용 하 여 Kubernetes를 활용 하는 것이 좋습니다. 쉽게 반복 되는 인프라 구성을 보장 하기 위해이를 투구 배포와 결합할 수 있습니다. 개발자는 필요에 따라 개발 프로세스의 일환으로 Kubernetes에 대 한 Azure Dev Spaces 활용할 수 있습니다. 또 다른 옵션은 Azure Functions 및 Azure Logic Apps와 같은 Azure 서버 리스 기능을 사용 하 여 앱의 기능을 호스트 하는 것입니다.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

자신의 AKS 클러스터에서 eShopOnContainers 응용 프로그램을 호스트 하려는 경우 첫 번째 단계는 클러스터를 만드는 것입니다. 필요한 단계를 안내 하는 Azure Portal을 사용 하 여이 작업을 수행할 수 있습니다 .이 작업을 수행 하는 경우 Azure CLI를 사용 하 여 RBAC (역할 기반 Access Control) 및 응용 프로그램 라우팅을 사용 하도록 설정할 수 있습니다. EShopOnContainers ' 설명서에서는 고유한 AKS 클러스터를 만드는 데 필요한 단계에 대해 설명 합니다. 클러스터가 만들어지면 Kubernetes 대시보드에 대 한 액세스를 사용 하도록 설정 해야 합니다 .이 시점에서 클러스터를 관리 하기 위해 Kubernetes 대시보드로 이동할 수 있어야 합니다.

클러스터를 만들고 구성한 후에는 투구 및 Tiller를 사용 하 여 응용 프로그램을 배포할 수 있습니다.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>투구를 사용 하 여 Azure Kubernetes Service에 배포

AKS에 대 한 기본 배포에서는 사용자 지정 CLI 스크립트 또는 간단한 배포 파일을 사용할 수 있지만 더 복잡 한 응용 프로그램은 투구와 같은 종속성 관리 도구를 사용 해야 합니다. 투구는 클라우드 기본 컴퓨팅 기반에서 유지 관리 되며 Kubernetes 응용 프로그램을 정의, 설치 및 업그레이드 하는 데 도움이 됩니다. 투구는 투구 차트를 사용 하는 Tiller 및 클러스터 내 구성 요소를 사용 하는 명령줄 클라이언트 (투구)로 구성 됩니다. 투구 차트는 표준 YAML 형식 파일을 사용 하 여 관련 된 Kubernetes 리소스 집합을 설명 하 고 일반적으로 설명 하는 응용 프로그램과 함께 버전을 지정 합니다. 투구 차트는 설명 하는 설치 요구 사항에 따라 단순에서 복잡 하 게 됩니다.

/K8s/helm 폴더에서 eShopOnContainers 투구 차트를 찾을 수 있습니다. 그림 2-6에서는 응용 프로그램의 다양 한 구성 요소가 투구에서 사용 되는 폴더 구조로 구성 되 고, 관리 되는 배포를 정의 하는 방법을 보여 줍니다.

![eShopOnContainers 아키텍처](./media/eshoponcontainers-helm-folder.png)
**그림 2-6**. EShopOnContainers 투구 폴더입니다.

각 개별 구성 요소는 `helm install` 명령을 사용 하 여 설치 됩니다. 이러한 명령은 쉽게 스크립팅할 수 있으며, eShopOnContainers는 서로 다른 구성 요소를 반복 하 고 해당 하는 투구 차트를 사용 하 여 설치 하는 "모두 배포" 스크립트를 제공 합니다. 그 결과, 팀의 모든 사용자가 한 줄 스크립트 명령을 사용 하 여 AKS 클러스터에 배포할 수 있는 반복 가능한 프로세스가 소스 제어에서 응용 프로그램과 함께 사용 됩니다. 특히 Azure Dev Spaces와 함께 사용 하면 개발자가 자신의 마이크로 서비스 기반 클라우드 네이티브 앱에 대 한 개별 변경 사항을 쉽게 진단 하 고 테스트할 수 있습니다.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Azure Dev Spaces는 개별 개발자가 개발 하는 동안 Azure에서 고유한 AKS 클러스터 버전을 호스트 하는 데 도움이 됩니다. 이렇게 하면 로컬 컴퓨터 요구 사항이 최소화 되며 팀 멤버가 실제 AKS 환경에서 변경 내용을 신속 하 게 파악할 수 있습니다. Azure Dev Spaces는 개발자가 개발 공간을 관리 하 고 필요에 따라 특정 자식 개발 공간에 배포 하는 데 사용할 수 있는 CLI를 제공 합니다. 각 자식 개발 공간은 고유한 URL 하위 도메인을 사용 하 여 참조 되므로 개별 개발자가 진행 중인 작업과 충돌을 방지할 수 있도록 수정 된 클러스터의 side-by-side 배포를 허용 합니다. 그림 2-7에서 개발자 Susie 자신의 자전거 마이크로 서비스 버전을 개발 공간에 배포 하는 방법을 확인할 수 있습니다. 그런 다음 사용자의 스페이스 이름으로 시작 하는 사용자 지정 URL을 사용 하 여 변경 내용을 테스트할 수 있습니다 (susie.s.dev.myapp.eus.azds.io).

![eShopOnContainers 아키텍처](./media/azure-devspaces-one.png)
**그림 2-7**. 개발자 Susie 자신의 자전거 마이크로 서비스 버전을 배포 하 고 테스트 합니다.

동시에 개발자 John은 예약 마이크로 서비스 사용자 지정 하 고 변경 내용을 테스트 해야 합니다. 그림 2-8에 표시 된 것 처럼 Susie의 변경 내용과 충돌 하지 않고 자신의 개발자 공간에 변경 내용을 배포할 수 있습니다. 자신의 URL을 사용 하 여 변경 내용을 테스트할 수 있습니다 (john.s.dev.myapp.eus.azds.io).

![eShopOnContainers 아키텍처](./media/azure-devspaces-two.png)
**그림 2-8**. 개발자는 자신의 예약 마이크로 서비스 버전을 배포 하 고 다른 개발자와 충돌 하지 않고 테스트 합니다.

Azure Dev Spaces를 사용 하 여 팀은 변경 내용을 독립적으로 변경, 배포 및 테스트 하는 동시에 AKS를 사용 하 여 직접 작업할 수 있습니다. 이 방법은 모든 개발자가 자신의 AKS 환경을 효과적으로 사용 하기 때문에 별도의 전용 호스팅 환경에 대 한 필요성을 줄입니다. 개발자는 CLI를 사용 하 여 Azure Dev Spaces 작업 하거나 응용 프로그램을 시작 하 여 Visual Studio에서 직접 Azure Dev Spaces 수 있습니다. [Azure Dev Spaces 작동 하 고 구성 되는 방법에 대해 자세히 알아보세요.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions 및 Logic Apps (서버 리스)

EShopOnContainers 샘플에는 온라인 마케팅 캠페인을 추적 하는 기능이 포함 되어 있습니다. Azure Function은 지정 된 캠페인 ID에 대 한 마케팅 캠페인 세부 정보를 가져오는 데 사용 됩니다. 이 목적을 위해 완전 한 ASP.NET Core 응용 프로그램을 만드는 대신 단일 Azure 함수 끝점은 더 간단 하 고 충분 합니다. 특히 Kubernetes에서 실행 되도록 구성 된 경우 전체 ASP.NET Core 응용 프로그램 보다 훨씬 간단한 빌드 및 배포 모델을 Azure Functions. 함수 배포는 ARM (Azure Resource Manager) 템플릿 및 Azure CLI를 사용 하 여 스크립팅됩니다. 이 캠페인 세부 정보는 고객이 마이크로 서비스 것이 아니며 온라인 스토어와 동일한 요구 사항이 없으므로 Azure Functions 하는 것이 좋습니다. 함수를 사용 하려면 데이터베이스 연결 문자열 데이터 및 이미지 기본 URI 설정과 같은 일부 구성이 제대로 작동 해야 합니다. Azure Portal에서 Azure Functions를 구성 합니다.

## <a name="references"></a>참조

- [eShopOnContainers: AKS에서 Kubernetes 클러스터 만들기](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[이전](map-eshoponcontainers-azure-services.md)
>[다음](centralized-configuration.md)
