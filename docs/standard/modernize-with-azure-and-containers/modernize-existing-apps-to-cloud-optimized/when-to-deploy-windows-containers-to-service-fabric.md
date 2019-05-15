---
title: Service Fabric에 Windows 컨테이너를 배포하는 경우
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | Service Fabric에 Windows 컨테이너를 배포하는 경우
ms.date: 04/30/2018
ms.openlocfilehash: d29a358fb039eb3390910958b1b1080698d730e0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643352"
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Service Fabric에 Windows 컨테이너를 배포하는 경우

Windows 컨테이너를 기반으로하는 응용 프로그램은 IaaS VM에서 훨씬 더 멀리 이동하는 플랫폼을 빠르게 사용해야 할 것입니다. 이는 향상된 높고 자동화된 확장성을 제공하고 배포, 업그레이드, 버전 관리, 롤백 및 상태 모니터링에 대한 완벽한 관리 경험을 크게 향상시킵니다. Microsoft Azure 클라우드뿐만 아니라 온-프레미스나 그 밖에 클라우드에서도 사용할 수 있는 오케스트레이터 Azure Service Fabric을 사용하여 이러한 목표를 달성할 수 있습니다.

많은 조직에서 다음 두 가지 이유 때문에 모놀리식의 기존 응용 프로그램을 컨테이너로 옮깁니다.

- 기존 하드웨어의 통합 및 제거 또는 더 높은 밀도의 응용 프로그램 실행으로 인한 비용 절감.

- 개발 및 운영 간의 일관된 배포 약속.

비용 절감을 추구 하는 것은 이해할 수 있도록 하 고 모든 조직 목표를 추적 되는 것입니다. 일관 된 배포를 평가 하려면 어렵습니다 이지만 중요 한 동일 하 게 합니다. 일관 된 배포 계약을 선택 하면 적합 한 기술을 사용 하 여 개발자는 운영 팀 배포 및 응용 프로그램을 관리 하는 단일 방법을 가져옵니다 코드 의미 합니다. 본이 계약은 특정 기술만 사용 하는 개발자를 강제 하거나 다양 한 기술의 복잡성을 처리 하는 작업의 어려움을 완화 합니다. 기본적으로, 각 응용 프로그램은 자체 포함된 배포 이미지에 컨테이너 화 된.

일부 조직에서는 마이크로 서비스 (클라우드 네이티브 응용 프로그램)를 추가 하 여 현대화 계속할 수 있지만 여러 다른 조직이 여기 (클라우드에 최적화 된 응용 프로그램) 중지 됩니다. 그림 4-8에서와 같이 하지 해야 할 수도 있으므로 이러한 조직에서는 마이크로 서비스 아키텍처를 이동 하지 않습니다. 어떤 경우 든, 이미 받게는 컨테이너와 Service Fabric을 사용 하 여 배포를 포함 하는 전체 관리를 제공 환경을 업그레이드 하는 혜택, 버전 관리, 롤백 및 상태 모니터링 합니다.

> ![리프트 앤 시프트를 Service Fabric 응용 프로그램](./media/image8.png)
>
> **그림 4-8입니다.** 리프트 앤 시프트를 Service Fabric 응용 프로그램

Service Fabric의 주요 방법은 기존 코드를 재사용 하 고 리프트 앤 시프트 하는 것입니다. 따라서 Windows 컨테이너를 사용 하 여 현재.NET Framework 응용 프로그램을 마이그레이션할 수 있으며 Service Fabric에 배포 합니다. 쉽게 이동 현대화, 결국 새 마이크로 서비스를 추가 하 여 유지 됩니다.

다른 오 케 스트레이 터를 Service Fabric을 비교할 때 Service Fabric에서 Windows 기반 응용 프로그램 및 서비스를 실행 하는 완성도 높은 임을 강조 표시 하는 것이 반드시 합니다. Windows 기반 서비스 및 응용 프로그램을 오랫동안 계층 1, 업무상 중요 한 Microsoft 제품을 포함 하 여 Service Fabric이 실행 되었습니다. Windows 컨테이너에 대 한 일반 공급을 할 첫 번째 오 케 스트레이 터 있었습니다. Kubernetes, DC/OS 및 Docker Swarm과 같은 다른 컨테이너를 Service Fabric에 대 한 Windows 기반 응용 프로그램 및 Windows 컨테이너 보다 더 새롭고 완성도 낮음 하지만 Linux에서 더욱 진보를

Service Fabric의 궁극적인 목표는 마이크로 서비스 접근 방식을 사용 하 여 응용 프로그램 구축의 복잡성을 줄이는 것입니다. 결국 마이크로 서비스에 대해 원하는 특정 유형의 비용이 많이 드는 다시 하지 않으려면 응용 프로그램입니다. 작은 규모로 시작할 필요에 따라 확장, 서비스의 사용을 중단, 새 서비스를을 추가한 고객 사용을 사용 하 여 응용 프로그램을 진화 합니다. 아직 대부분의 개발자를 위한 마이크로 서비스를 보다 쉽게 수행할 확인을 해결 해야 할 수 있는 다른 많은 문제가 있습니다. 현재는 방금 변환 하 고 Windows 컨테이너를 사용 하 여 응용 프로그램을 이동 하지만 향후 컨테이너 기반 마이크로 서비스를 추가 하는 방법을 고려 하는 경우 Service Fabric 최적입니다.

>[!div class="step-by-step"]
>[이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
>[다음](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
