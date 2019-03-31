---
title: 기존.NET 앱을 Azure IaaS(클라우드 인프라 지원)로 리프트 앤 시프트 하기
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존.NET 응용 프로그램을 최신으로 변경합니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 2b987d43f476f261bfdbd1b2af6ca7f792178cf8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266626"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>기존.NET 앱을 Azure IaaS (클라우드 인프라 지원)로 리프트 앤 시프트 하기

> 목표 : 첫 번째 단계에서는 온-프레미스 투자 및 하드웨어와 네트워킹 유지 관리의 총 비용을 줄이기 위해 단순히 기존 응용 프로그램을 클라우드로 리호스팅 합니다.

기존 응용 프로그램을 Azure 서비스 형태의 인프라 (IaaS) 플랫폼으로 마이그레이션하는 *방법*을 살펴보기 전에, Azure의 IaaS로 직접 마이그레이션하려는 *이유*를 분석하는 것이 중요합니다. 이 최신화 성숙도 시나리오에서는 기본적으로 기존 온-프레미스 인프라를 사용하지 않고 클라우드의 VM을 사용합니다.

그 밖에 분석할 점은 Azure의 고급 관리 서비스를 추가하지 않고 순수 IaaS 클라우드로 마이그레이션하려는 *이유*입니다. 처음부터 IaaS가 필요한 사례를 결정하십시오.

다음 그림 2-1에서는 최신화 성숙도에서 클라우드 인프라 지원 응용 프로그램의 위치를 나타냅니다.

![클라우드 인프라 지원 응용 프로그램의 위치](./media/image2-1.png)

> **그림 2-1.** 클라우드 인프라 지원 응용 프로그램 위치

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>기존.NET 웹 응용 프로그램을 Azure IaaS로 마이그레이션하는 이유

이유는 초기 IaaS 수준에도 클라우드로 마이그레이션할 비용 절감 달성 하는 것입니다. 더 많은 관리 되는 인프라 서비스를 사용 하 여 조직의 하드웨어 유지 관리, 서버 또는 VM 프로 비전 및 배포 및 인프라 관리에 소요 된 투자를 줄일 수 있습니다.

앱을 클라우드로 이동 하도록 결정을 내리면 이유와 IaaS 처럼 PaaS는 단순히 더 많은 고급 옵션 대신 IaaS 환경 주된 이유는 더 익숙할 것입니다. 현재 유사한 환경으로 이동 하는, 온-프레미스 환경에서는 클라우드에서 가장 빠른 경로 사용 하면 낮은 학습 곡선을 제공 합니다.

그러나 클라우드에서 가장 빠른 경로로 이동 한다고 클라우드에서 실행 중인 응용 프로그램에서 대부분의 이점을 얻게 됩니다. 조직의는 클라우드 마이그레이션 도입 되었습니다. 이미 클라우드 최적화 및 클라우드-네이티브 완성도 수준에서 가장 중요 한 이점을 얻을 수 됩니다.

또한 되었기 때문에 응용 프로그램을 현대화 하 고 IaaS의 경우에 클라우드에 이미 실행 중인 경우 앞으로 아키텍처 변경 하기가 분명 합니다. 응용 프로그램 데이터 마이그레이션 이미 목표를 달성 했습니다. 또한 조직은 클라우드에서 작업 하는 데 필요한 기술을 얻을 있고 "클라우드 문화권입니다."에서 작동 하는 전환 수

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>PaaS로 대신 IaaS로 마이그레이션할 시기

다음 섹션에서는 대부분 PaaS 플랫폼 및 서비스에 기반 하는 클라우드에 최적화 된 응용 프로그램을 설명 합니다. 이러한 앱을 클라우드로 마이그레이션하면 대부분의 혜택을 제공 합니다. 

목표는 단순히 클라우드로 기존 응용 프로그램을 이동 하는, 하는 경우 먼저 Azure App Service에서 실행 하려면 상당한 수정이 필요 하지 않습니다는 기존 응용 프로그램을 식별 합니다. 이러한 앱에 대 한 첫 번째 후보 있어야 클라우드 최적화 합니다. 

그런 다음 앱에 대 한는 계속 이동할 수 없습니다 Windows 컨테이너 및 PaaS App Service 또는 Azure Service Fabric과 같은 오 케 스트레이 터는 간단한 일반 Vm (IaaS)에 마이그레이션 등. 

그러나 제대로 구성, 보호 및 Vm을 유지 관리 해야 한다는 훨씬 더 많은 시간과 IT 전문 지식을 Azure에서 PaaS 서비스를 사용 하 여 비교할 염두에서에 둡니다. Azure Virtual Machines를 고려 하는 경우를 고려해 야 패치, 업데이트 및 VM 환경을 관리 하는 데 필요한 지속적인 유지 관리 노력 해야 합니다. Azure Virtual Machines는 IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Azure Migrate을 사용 하 여 분석 하 고 Azure로 기존 응용 프로그램 마이그레이션

클라우드로의 마이그레이션은 어렵지 없습니다. 하지만 대부분의 조직에서는 환경 및 응용 프로그램, 작업 및 데이터 간의 긴밀 하 게 상호 종속성에 대 한 심층 파악을 시작 하는 데 있습니다. 해당 표시 하지 않고 앞으로 경로 계획 하는 것이 어려울 수 있습니다. 성공적인 마이그레이션에 필요한 항목에 대 한 자세한 내용은 없이 조직 내에서 올바른 대화를 할 수 없습니다. 잠재적 비용 이점에 대해 알 수 없는 워크 로드만 리프트 앤 시프트 수 또는 성공적으로 마이그레이션하려면 상당한 재작업 해야 하는지 여부 또는 합니다. 대부분의 조직에서는 언제 든 지 당연 합니다.

[Azure Migrate](https://aka.ms/azuremigrate) 는 지침, insights 및 Azure로 마이그레이션하는 데 도움이 하는 데 필요한 메커니즘을 제공 하는 새로운 서비스입니다. Azure Migrate는 다음을 제공합니다.

- 검색 및 온-프레미스 가상 컴퓨터에 대 한 평가

- 다중 계층 응용 프로그램의 높은 정확도 검색에 대 한 기본 제공된 종속성 매핑

- Azure virtual machines에 지능형 오른쪽 크기 조정

- 호환성 수정 잠재적인 문제에 대 한 지침을 사용 하 여 보고

- 데이터베이스 검색 및 마이그레이션에 대 한 Azure 데이터베이스 관리 서비스와의 통합

Azure Migrate는 비즈니스에 영향을 최소화 하면서 워크 로드 수 마이그레이션하고 Azure에서 예상 대로 실행 하는 확신을 줍니다. 적절 한 도구 및 지침을 사용 하 여 최대는 중요 한 성능 보장 하는 동안 투자 수익률을 얻을 수 있습니다 및 안정성 요구 사항이 충족 됩니다.

그림 2-2 Azure Migrate에서 수행 하는 모든 서버 및 응용 프로그램 연결에 대 한 기본 제공 종속성 매핑을 보여 줍니다.

![클라우드 인프라 지원 응용 프로그램 위치 지정](./media/image2-2.png)

> **그림 2-2입니다.** 클라우드 인프라 지원 응용 프로그램 위치 지정

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Azure Site Recovery를 사용 하 여 Azure Vm에 기존 Vm을 마이그레이션하려면

엔드-투-엔드의 일부로 [Azure Migrate](https://aka.ms/azuremigrate)하십시오 [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) 쉽게 Azure에서 Vm에 웹 앱을 마이그레이션 하는 데 사용할 수 있는 도구입니다. 보조 온-프레미스 위치에 복제 또는 온-프레미스 Vm 및 물리적 서버를 Azure로 복제에 Site Recovery를 사용할 수 있습니다. 온-프레미스는 지원 되는 Azure VM에서 실행 되는 워크 로드도 복제할 수 있습니다 *Hyper-v* VM의는 *VMware* VM 또는 Windows 나 Linux 물리적 서버. Azure로 복제를 보조 데이터 센터를 유지 관리 하 고 비용을 제거 합니다.

Site Recovery에도 부분적으로 하이브리드 환경에 맞게 이루어집니다 온-프레미스 및 Azure에서 부분적으로 합니다. Site Recovery Vm에서 실행 되는 앱을 유지 하 여 비즈니스 연속성을 보장 하는 데 도움이 됩니다 및 온-프레미스 물리적 서버를 사용할 수 있는 사이트 다운 합니다. 되도록 사용할 수 있는 보조 위치에서 기본 사이트를 사용할 수 없는 경우 Vm 및 물리적 서버에서 실행 되는 워크 로드를 복제 합니다. 워크 로드 되 면 기본 사이트를 다시 실행 복구 합니다.

그림 2-3 Azure Site Recovery를 사용 하 여 여러 VM 마이그레이션 실행을 보여 줍니다.

![클라우드 인프라 지원 응용 프로그램 위치 지정](./media/image2-3.png)

> **그림 2-3입니다.** 클라우드 인프라 지원 응용 프로그램 위치 지정

### <a name="additional-resources"></a>추가 자료

- **Azure Migrate 데이터 시트**

    [https://aka.ms/azuremigration\_datasheet](https://aka.ms/azuremigration\_datasheet)

- **Azure Migrate**

    [https://aka.ms/azuremigrate](https://aka.ms/azuremigrate)

- **Azure 마이그레이션 센터**

    [https://azure.microsoft.com/migration/](https://azure.microsoft.com/migration/)

- **Site Recovery 사용 하 여 Azure로 마이그레이션**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- **Azure Site Recovery 서비스 개요**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- **Azure Vm에 AWS에서 Vm 마이그레이션**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
>[이전](index.md)
>[다음](migrate-your-relational-databases-to-azure.md)
