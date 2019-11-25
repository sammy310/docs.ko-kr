---
title: 하이브리드 클라우드로 마이그레이션 시나리오
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 하이브리드 클라우드 시나리오로 마이그레이션
ms.date: 04/30/2018
ms.openlocfilehash: 4348a9b538042fee7ebd9c08f480491f17425937
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "72394541"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>하이브리드 클라우드로 마이그레이션 시나리오

일부 조직 및 기업은 규정 또는 자체 정책으로 인해 일부 애플리케이션을 Microsoft Azure와 같은 공용 클라우드로 마이그레이션할 수 없습니다. 그러나 모든 조직은 일부 애플리케이션을 공용 클라우드에 배치하고 다른 애플리케이션을 온-프레미스에 배치하는 것이 유용할 수 있습니다. 다만 혼합 환경에서는 공용 클라우드와 온-프레미스 환경에 사용되는 다양한 플랫폼 및 기술로 인해 환경에서 과도한 복잡성이 발생할 수 있습니다.

Microsoft는 Azure 하이브리드 클라우드에서 일관성을 유지하면서 기존 자산을 온-프레미스 및 공용 클라우드에서 최적화할 수 있는 최상의 하이브리드 클라우드 솔루션을 제공합니다. Azure Stack(온-프레미스) 및 Azure(공용 클라우드) 덕분에 기존 역량을 극대화하고 클라우드 또는 온-프레미스에서 실행할 수 있는 앱을 빌드하는 유연하고 통합된 접근 방식을 활용할 수 있습니다.

보안과 관련하여 하이브리드 클라우드를 통해 관리 및 보안을 중앙 집중화할 수 있습니다. 온-프레미스 및 클라우드 앱에 대한 Single Sign-On을 제공하여 데이터 센터에서 클라우드까지 모든 자산에 대한 제어를 확보할 수 있습니다. 이는 Active Directory를 하이브리드 클라우드로 확장하고 ID 관리를 사용하여 달성합니다.

마지막으로, 데이터를 원활하게 배포 및 분석하고, 클라우드 및 온-프레미스 자산에 대해 동일한 쿼리 언어를 사용하고, Azure에서 분석 및 딥 러닝을 적용하여 원본에 관계없이 데이터를 보강할 수 있습니다.

## <a name="azure-stack"></a>Azure Stack

Azure Stack은 조직의 데이터 센터에서 Azure 서비스를 제공할 수 있게 해주는 하이브리드 클라우드 플랫폼입니다. Azure Stack은 에지 및 연결되지 않은 환경과 같은 주요 시나리오에서 최신 애플리케이션에 대한 새로운 옵션을 지원하거나 특정 보안 및 규정 준수 요구 사항을 충족하도록 디자인되었습니다.

그림 4-13에서는 Microsoft가 제공하는 진정한 하이브리드 클라우드 플랫폼에 대한 개요를 보여줍니다.

![Azure Stack과 Azure를 사용하는 Microsoft 하이브리드 클라우드 플랫폼의 다이어그램](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

**그림 4-13.** Azure Stack 및 Azure를 사용하는 Microsoft 하이브리드 클라우드 플랫폼

Azure Stack은 사용자 요구 사항을 충족하기 위해 두 가지 배포 옵션으로 제공됩니다.

- Azure Stack 통합 시스템

- Azure Stack Development Kit

### <a name="azure-stack-integrated-systems"></a>Azure Stack 통합 시스템

Azure Stack 통합 시스템은 Microsoft와 하드웨어 파트너 간 파트너 관계를 통해 제공됩니다. 이 파트너 관계는 관리 단순성과 균형을 이루는 클라우드 지향 혁신을 제공하는 솔루션을 만듭니다. Azure Stack은 하드웨어와 소프트웨어의 통합 시스템으로 제공되므로 유동적으로 활용하고 제어하는 동시에 클라우드의 혁신 기능도 도입할 수 있습니다. Azure Stack 통합 시스템은 4~12개 노드를 포함하며 하드웨어 파트너와 Microsoft를 통해 공동으로 지원됩니다. 프로덕션 워크로드용으로 새로운 시나리오를 구현하려면 Azure Stack 통합 시스템을 사용하세요.

### <a name="azure-stack-development-kit"></a>Azure Stack Development Kit

Microsoft Azure Stack 개발 키트는 Azure Stack을 평가 및 파악하는 데 사용할 수 있는 Azure Stack의 단일 노드 배포입니다. Azure Stack Development Kit를 개발자 환경으로 활용해 Azure와 동일한 API와 도구를 사용하여 개발 작업을 수행할 수도 있습니다. Azure Stack 개발 키트를 프로덕션 환경으로 사용할 수는 없습니다.

### <a name="additional-resources"></a>추가 자료

- **Azure 하이브리드 클라우드**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Windows 컨테이너용 Active Directory 서비스 계정**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Active Directory 지원으로 컨테이너 만들기**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Azure 하이브리드 혜택 라이선스**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[이전](life-cycle-ci-cd-pipelines-devops-tools.md)
>[다음](../walkthroughs-technical-get-started-overview.md)
