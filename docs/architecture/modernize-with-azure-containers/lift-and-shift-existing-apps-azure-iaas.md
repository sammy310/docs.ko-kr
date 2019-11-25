---
title: 기존 .NET 앱을 Azure IaaS(클라우드 인프라 지원)로 리프트 앤 시프트
description: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션을 현대화합니다.
ms.date: 04/28/2018
ms.openlocfilehash: c7638a034dbb27baea1b097bdb66175bfb5a71f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73089632"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>기존 .NET 앱을 Azure IaaS(클라우드 인프라 지원)로 리프트 앤 시프트

> 비전: 첫 번째 단계로, 온-프레미스 투자액과 하드웨어 및 네트워킹 유지 관리에 소요되는 전체 비용을 절감하기 위해 기존 애플리케이션을 클라우드로 재호스팅합니다.

기존 애플리케이션을 Azure IaaS (infrastructure as a service) 플랫폼으로 마이그레이션하는 *방법*을 확인하기에 앞서 Azure의 IaaS로 직접 마이그레이션해야 하는 *이유*를 분석하는 것이 중요합니다. 현재의 현대화 완성도에서 그려 볼 시나리오는 기본적으로 현재의 온-프레미스 인프라를 계속 사용하는 대신 클라우드에서 VM 사용을 시작하는 것입니다.

또 다른 분석 포인트는 Azure에 고급 관리 서비스를 추가만 할 것이 아니라 순수형 IaaS 클라우드로 마이그레이션해야 하는 *이유*입니다. 먼저 IaaS가 필요할 만한 사례를 확인합니다.

그림 2-1에서는 클라우드 인프라 지원 애플리케이션의 위치가 현대화 완성도 수준에서 지정됩니다.

![클라우드 인프라 지원 애플리케이션 위치 지정](./media/image2-1.png)

**그림 2-1.** 클라우드 인프라 지원 애플리케이션 위치 지정

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Azure IaaS로 기존 .NET 웹 애플리케이션을 마이그레이션하는 이유

초기 IaaS 수준에서도 클라우드로 마이그레이션하는 주된 이유는 비용 절감에 있습니다. 조직에서는 관리형 인프라 서비스를 추가로 사용하여 하드웨어 유지 관리, 서버나 VM의 프로비전과 배포, 인프라 관리에 대한 투자 부담을 줄일 수 있습니다.

앱을 클라우드로 옮기기로 결정한 후, PaaS와 같은 고급 옵션 대신 IaaS를 선택할 수 있는 주된 이유는 IaaS 환경이 더 친숙하다는 데 있습니다. 현재 사용 중인 온-프레미스 환경과 유사한 환경으로 이동하면 학습 곡선 자체가 낮아져 클라우드로 가장 빠르게 접근할 수 있게 됩니다.

하지만 클라우드에 가장 빠르게 접근할 수 있다고 해서 클라우드에서 실행 중인 애플리케이션으로 이점을 극대화할 수 있다고 보장하기는 어렵습니다. 모든 조직은 이미 도입된 클라우드 최적화 및 클라우드 기본 완성도를 기반으로 하는 클라우드 마이그레이션에서 가장 큰 이점을 얻을 수 있습니다.

또한 애플리케이션이 이미 클라우드에서(IaaS에서도) 실행 중일 때 향후 애플리케이션 현대화와 재설계가 더 쉽다는 것이 명확해졌습니다. 애플리케이션 데이터 마이그레이션은 이미 수행되었습니다. 또한 사용자의 조직에서는 클라우드에서 작업하는 데 필요한 기술을 획득하고 "클라우드 문화권"에서의 운영을 위해 이동을 완료했습니다.

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>PaaS가 아닌 IaaS로 마이그레이션하는 경우

다음 섹션에서는 주로 PaaS 플랫폼과 서비스를 기반으로 하는 클라우드 최적화 애플리케이션에 대해 설명합니다. 이러한 앱에서는 클라우드로의 마이그레이션을 통한 이익을 극대화할 수 있습니다.

먼저, 단순히 기존 애플리케이션을 클라우드로 이동하려는 경우에는 Azure App Service에서 실행하기 위해 크게 수정하지 않아도 되는 기존 애플리케이션을 식별합니다. 이러한 앱이 클라우드 최적화를 위한 최초의 후보여야 합니다.

그런 다음 여전히 Windows 컨테이너 및 PaaS로 옮길 수 없는 앱(예: Azure Kubernetes Service 같은 오케스트레이터 또는 App Service)의 경우에는 이러한 앱을 단순한 일반 VM(IaaS)으로 마이그레이션합니다.

그러나 VM을 올바르게 구성, 보호 및 유지 관리하려면 Azure의 PaaS 서비스 사용보다 더 많은 시간과 IT 전문 지식이 필요합니다. Azure Virtual Machines를 고려 중인 경우 VM 환경 패치/업데이트/관리에 필요한 지속적인 유지 관리 활동을 고려해야 합니다. Azure Virtual Machines는 IaaS입니다.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Azure Migrate를 사용하여 기존 애플리케이션을 분석하고 Azure로 마이그레이션

클라우드로의 마이그레이션은 어렵지 않습니다. 그러나 많은 조직에서는 이를 시작하는 데 있어, 즉 그 환경은 물론 애플리케이션과 워크로드, 데이터 간의 긴밀한 상호 종속성을 심층적으로 파악하는 데 있어 어려움을 겪습니다. 그처럼 명확하게 파악이 되지 않으면 향후 진행이 어려울 수 있습니다. 성공적인 마이그레이션에 필요한 사항을 자세히 알지 못하면 조직 내의 올바른 대화 진행이 불가능합니다. 잠재적인 비용 혜택에 관해, 또는 워크로드의 리프트 앤 시프트가 간편히 될 수 있는지 성공적인 마이그레이션에 상당한 재작업이 필요할지에 관해 자세히 알기 어렵습니다. 많은 조직이 마이그레이션을 주저하는 것도 놀랄 일이 아닙니다.

[Azure Migrate](https://aka.ms/azuremigrate)는 Azure로 마이그레이션하는 데 유용한 지침, 통찰력 및 메커니즘을 제공하는 신규 서비스입니다. Azure Migrate 제공:

- 온-프레미스 가상 머신 검색 및 평가

- 다중 계층 애플리케이션의 신뢰도 높은 검색을 위한 기본 제공 종속성 매핑

- Azure 가상 머신에 맞춘 지능적이고 올바른 크기 조정

- 잠재적 문제 수정 관련 지침이 포함된 호환성 보고서

- 데이터베이스 검색 및 마이그레이션을 위한 Azure Database Management Service 통합

Azure Migrate를 통해 비즈니스에 미치는 영향을 최소화하는 가운데 워크로드의 마이그레이션이 가능하며 Azure에서 예상대로 실행할 수 있습니다. 도구와 지침이 적절하다면 중요한 성능 및 안정성 요건을 충족하는 동시에 투자 수익률을 극대화할 수 있습니다.

그림 2-2는 Azure Migrate에서 수행되는 모든 서버 및 애플리케이션 연결에 대한 기본 제공 종속성 매핑을 보여줍니다.

![클라우드 인프라 지원 애플리케이션 위치 지정](./media/image2-2.png)

**그림 2-2.** 클라우드 인프라 지원 애플리케이션 위치 지정

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Azure Site Recovery를 사용하여 기존 VM을 Azure VM으로 마이그레이션

엔드투엔드 [Azure Migrate](https://aka.ms/azuremigrate)에 포함된 [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)는 사용자의 웹 애플리케이션을 Azure의 VM으로 간편히 마이그레이션하는 데 사용 가능한 도구입니다. 사용자는 Site Recovery를 사용하여 온-프레미스 VM과 물리 서버를 Azure로 복제하거나 보조 온-프레미스 위치로 복제할 수 있습니다. 또는 지원 대상 Azure VM이나 온-프레미스 *Hyper-V* VM, *VMware* VM, 또는 Windows나 Linux의 물리 서버에서 실행 중인 워크로드를 복제할 수도 있습니다. Azure에 복제하면 보조 데이터 센터를 유지하는 비용과 복잡성을 제거할 수 있습니다.

Site Recovery는 일부분은 온-프레미스로, 일부는 Azure로 구성된 하이브리드 환경에 특히 적합합니다. Site Recovery는 사이트의 작동이 중단된 경우에도 VM 및 온-프레미스 물리 서버에서 실행 중인 앱을 계속 사용할 수 있도록 하여 비즈니스 연속성을 보장하는 데 도움이 됩니다. 그리고 VM 및 물리 서버에서 실행 중인 워크로드를 복제하여 기본 사이트를 사용할 수 없게 될 경우 보조 위치에서 계속 사용할 수 있도록 합니다. 사이트가 복구되어 다시 실행되면 워크로드를 기본 사이트로 복구합니다.

그림 2-3은 Azure Site Recovery를 사용하여 여러 VM 마이그레이션을 실행하는 방법을 보여줍니다.

![클라우드 인프라 지원 애플리케이션 위치 지정](./media/image2-3.png)

**그림 2-3.** 클라우드 인프라 지원 애플리케이션 위치 지정

### <a name="additional-resources"></a>추가 자료

- **Azure Migrate 데이터시트**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure 마이그레이션 센터**

    <https://azure.microsoft.com/migration/>

- **Site Recovery를 사용하여 Azure에 마이그레이션**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Azure Site Recovery 서비스 개요**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **AWS의 VM을 Azure VM으로 마이그레이션**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
