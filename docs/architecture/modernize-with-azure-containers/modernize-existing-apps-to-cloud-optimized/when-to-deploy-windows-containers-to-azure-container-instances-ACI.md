---
title: Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577936"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Azure Container Instances(ACI)에 Windows 컨테이너를 배포하는 경우

Azure Container Instances 기본 가치 제안은 사용자가 컨테이너를 바로 배포할 수 있으며 해당 환경을 유지 관리할 필요가 없고, 기본 운영 체제 또는 VM을 업그레이드/패치할 필요가 없고, 모든 것이 투명하고, 컨테이너를 즉시 사용 가능한 환경에 배포할 수 있다는 것입니다.

ACI를 사용하려는 이유 및 시나리오는 컨테이너에서 Azure VM을 사용하는 경우의 주요 시나리오와 비슷합니다. 기본적으로 Azure Container Instances 사용에 대한 주요 시나리오는 다음과 같습니다.

- **개발/테스트 시나리오**
- **작업 자동화**
- **CI/CD 에이전트**
- **소규모/대규모 일괄 처리**
- **간단한 웹앱**

간단한 웹앱 시나리오는 ACI에 타당한 시나리오이지만 ACI에서는 컨테이너 이미지당 하나의 컨테이너 인스턴스만 가능하므로 고가용성이 확보되지 않고 확장성만 제한된다는 것을 고려해야 합니다.

그러나 ACI가 단일 컨테이너 인스턴스만 제공하기 때문에 인프라로 고려되는 경우에도 Windows Server를 사용하는 일반 Azure VM에 비해 큰 이점이 있습니다. ACI를 사용하면 컨테이너를 자체 유지 관리 환경에 배포하고 해당 컨테이너에 대해서만 비용을 지불하게 됩니다. VM을 유지 관리/업데이트/패치하지 않아도 되므로 컨테이너와 함께 VM을 사용할 수 있는 대부분의 시나리오에서 훨씬 더 나은 플랫폼입니다. ACI 사용은 간단합니다. VM 환경은 만들 필요가 없이 컨테이너만 배포하면 됩니다.

Azure Container Instances(ACI)의 주요 이점은 다음과 같습니다.

- 서버를 관리하지 않고 컨테이너를 실행
- 주문형 컨테이너를 사용하여 민첩성을 향상
- 단일 명령을 사용하여 뛰어난 단순성과 속도로 클라우드에 컨테이너를 배포
- 하이퍼바이저 격리를 사용하여 애플리케이션을 보호

간단히 말해서, ACI를 사용하면 가상 머신을 관리하거나 새로운 도구를 배울 필요 없이 신속하게 앱을 개발할 수 있습니다. 단지 클라우드에서 실행되는 컨테이너의 애플리케이션일 뿐입니다.

> [!div class="step-by-step"]
> [이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [다음](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
