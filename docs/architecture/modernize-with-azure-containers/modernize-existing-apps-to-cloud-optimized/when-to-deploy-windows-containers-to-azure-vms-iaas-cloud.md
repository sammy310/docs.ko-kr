---
title: Azure VM에 Windows 컨테이너를 배포해야 하는 경우(IaaS 클라우드)
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | Azure VM(IaaS 클라우드)에 Windows 컨테이너를 배포하는 경우
ms.date: 12/21/2020
ms.openlocfilehash: 64ba53fa56227266ee0e61a128d18373a2dbbc93
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025096"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Azure VM에 Windows 컨테이너를 배포해야 하는 경우(IaaS 클라우드)

조직에서 Azure VM을 사용하는 경우 Windows 컨테이너도 사용하더라도 여전히 IaaS를 처리하는 것입니다. 즉, 부하가 분산된 인프라에서 여러 VM에 배포하는 경우 스케일링 성능이 뛰어난 애플리케이션에 대한 인프라 작업, VM OS 패치 및 인프라 복잡성을 처리한다는 의미입니다. Azure VM에서 Windows 컨테이너를 사용하는 주요 시나리오는 다음과 같습니다.

- **개발/테스트 환경**: 클라우드의 VM은 클라우드에서 개발하고 테스트하는 데 매우 적합합니다. 요구 사항에 따라 신속하게 환경을 만들거나 중지할 수 있습니다.

- **중소 규모의 확장성 요구 사항**: 프로덕션 환경에 두 개의 VM만 필요할 수 있는 시나리오에서는 오케스트레이터 같은 고급 PaaS 환경으로 전환할 수 있을 때까지 소수의 VM을 관리하는 것이 경제적일 수 있습니다.

- **기존 배포 도구를 사용하는 프로덕션 환경**: VM 또는 운영 체제 미설치 서버(예: Puppet 또는 유사한 도구)에 대한 복잡 한 배포를 수행하기 위해 도구에 투자한 온-프레미스 환경에서 이동할 수 있습니다. 프로덕션 환경 배포 절차를 최소한으로 변경하여 클라우드로 이동하려면 이러한 도구를 계속 사용하여 Azure VM에 배포할 수 있습니다. 그러나 배포 단위로 Windows 컨테이너를 사용하여 배포 환경을 개선하는 것이 좋습니다.

>[!div class="step-by-step"]
>[이전](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[다음](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
