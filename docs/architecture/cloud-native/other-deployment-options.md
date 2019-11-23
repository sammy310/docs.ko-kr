---
title: 기타 컨테이너 배포 옵션
description: Azure를 사용 하는 다른 컨테이너 배포 옵션
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841164"
---
# <a name="other-container-deployment-options"></a>기타 컨테이너 배포 옵션

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

AKS에 배포 하는 것 외에도 컨테이너 및 Azure Container Instances에 대 한 Azure App Service 컨테이너를 배포할 수 있습니다.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>컨테이너의 App Service에 배포 하는 것이 적합 한가요?

오케스트레이션을 필요로 하지 않는 간단한 프로덕션 응용 프로그램은 컨테이너에 Azure App Service 하는 데 적합 합니다.

## <a name="how-to-deploy-to-app-service-for-containers"></a>컨테이너의 App Service에 배포 하는 방법

[컨테이너의 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)에 배포 하려면 ACR (Azure Container Registry) 및 액세스를 위한 자격 증명을 구성 해야 합니다. 호스트로 만들려는 컨테이너를 Azure App Service으로 끌어올 수 있도록 푸시합니다. 일단 만들어지면 ACR에서 해당 이미지를 업데이트할 때마다 앱에 업데이트를 자동으로 배포 하는 연속 배포에 대해 앱을 구성할 수 있습니다.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Azure Container Instances에 배포 하는 것이 적합 한가요?

Azure Container Instances는 테스트 시나리오에 가장 적합 합니다. 응용 프로그램을 클라우드로 호스트 된 컨테이너 인스턴스에 빠르게 배포 하는 간단한 방법을 제공 합니다. Azure Kubernetes 서비스에서 제공 하는 크기 조정 및 오케스트레이션 기능이 필요 하지 않은 경우 응용 프로그램을 테스트 하는 데 사용 합니다.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Azure Container Instances에 앱을 배포 하는 방법

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)에 배포 하려면 AZURE CONTAINER REGISTRY (ACR) 및 액세스를 위한 자격 증명을 구성 해야 합니다. 또한 이전에 컨테이너 이미지를 레지스트리에 푸시 했으므로 ACI로 풀 하는 데 사용할 수 있습니다. Azure CLI 또는 포털을 통해 ACI를 사용 하 여 작업할 수 있습니다. 그림 3-14에 표시 된 것 처럼 Azure Container registry를 사용 하면 레지스트리 내에서 직접 개별 컨테이너 인스턴스를 ACI에 쉽게 배포할 수 있습니다.

![Azure Container Registry 실행 인스턴스](./media/acr-runinstance-contextmenu.png)

**그림 3-14**. Azure Container Registry 실행 인스턴스

레지스트리에서 컨테이너 인스턴스를 만들려면 일반적인 Azure 설정 (이름, 구독, 리소스 그룹 및 위치), 컨테이너에 할당할 메모리 양 및 수신 대기 해야 하는 포트를 지정 해야 합니다. 이 [빠른 시작에서는 Azure Portal를 사용 하 여 ACI에 컨테이너 인스턴스를 배포 하는 방법을 보여 줍니다](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

배포가 완료 되 면 새로 배포 된 컨테이너의 IP 주소를 찾아 지정 된 포트를 통해 통신 합니다.

Azure Container Instances은 Azure에서 컨테이너를 실행 하는 가장 빠르고 가장 간단한 방법을 제공 합니다. App service 또는 orchestrator를 구성 하거나 가상 머신을 처리 하지 않아도 됩니다. 그러나 편의를 위해 ACI는 주로 테스트 목적으로 사용 되어야 합니다. 응용 프로그램에 자동 확장성이 필요한 경우 여러 컨테이너가 함께 작동 하도록 구성 된 경우 또는 추가 복잡 한 기능을 사용 하는 경우 앱을 호스트 하는 데 더 적합 한 다른 Azure 서비스가 있습니다.

## <a name="references"></a>참조

- [문서 Azure Container Instances](https://docs.microsoft.com/azure/container-instances/)
- [ACR에서 컨테이너 인스턴스 배포](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[이전](scale-containers-serverless.md)
>[다음](communication-patterns.md)
