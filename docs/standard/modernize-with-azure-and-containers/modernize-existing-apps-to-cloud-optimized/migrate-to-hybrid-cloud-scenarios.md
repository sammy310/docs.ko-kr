---
title: 하이브리드 클라우드로 마이그레이션 시나리오
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 하이브리드 클라우드 시나리오로 마이그레이션
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 6cba29ad654b09b01f9b6969fa6688dd5f165fbb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636583"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>하이브리드 클라우드로 마이그레이션 시나리오

일부 조직과 기업에서는 자체 규정이나 정책으로 인해 일부 응용 프로그램을 Microsoft Azure나 그 밖에 공용 클라우드로 마이그레이션할 수 없습니다. 하지만 조직에서 응용 프로그램의 일부를 공용 클라우드에 두고 나머지 응용 프로그램을 온-프레미스에 두게 되면 이점을 얻을 가능성이 높습니다. 하지만 혼재된 환경은 공용 클라우드와 온-프레미스에서 사용된 다양한 플랫폼과 기술로 인해 지나치게 복잡해질 수 있습니다.

Microsoft에서는 Azure 하이브리드 클라우드에서 일관성을 유지하면서  온-프레미스와 공용 클라우드의 기존 자산을 최적화할 수 있는 최상의 하이브리드 클라우드 솔루션을 제공합니다. Azure Stack(온-프레미스)과 Azure(공용 클라우드) 덕분에, 클라우드나 온-프레미스에서 동작하는 응용 프로그램을 만들 수 있는, 기존 기술을 극대화하고 유연하고 통일된 접근 방식을 사용할 수 있습니다.

보안에 있어 보안과 관리를 중앙 집중화할 수 있습니다 하이브리드 클라우드에서 합니다. 온-프레미스에서 single sign-on을 제공 하 여 모든 자산에 대 한 제어를 클라우드로 데이터 센터에서 가져올 수 있으며 클라우드 앱 수 있습니다. Active Directory 하이브리드 클라우드로 확장 하 여 및 id 관리를 사용 하 여이 작업을 수행할 합니다.

마지막으로, 배포 및 수 있습니다 및 데이터를 원활 하 게 분석, 동일한 쿼리 언어를 사용 하 여 클라우드 및 온-프레미스 자산에 대 한 분석 및 딥 러닝 해당 소스에 관계 없이 데이터를 보강 하는 Azure에 적용 합니다.

## <a name="azure-stack"></a>Azure Stack

Azure Stack은 하이브리드 클라우드 플랫폼을 사용 하면 조직의 데이터 센터에서 Azure 서비스를 제공할 수 있습니다. Azure Stack은 가장자리와 연결 되지 않은 환경 또는 특정 보안 및 규정 준수 요구 사항을 충족 하는 등의 주요 시나리오에서 최신 응용 프로그램에 대 한 새 옵션을 지원 하도록 설계 되었습니다.

그림 4-13 Microsoft에서 제공 하는 진정한 하이브리드 클라우드 플랫폼의 개요를 보여 줍니다.

![Azure Stack 및 Azure를 사용 하 여 Microsoft 하이브리드 클라우드 플랫폼](./media/image13.jpg)

> **그림 4-13입니다.** Azure Stack 및 Azure를 사용 하 여 Microsoft 하이브리드 클라우드 플랫폼

Azure Stack 사용자의 요구를 충족 하기 위해 두 가지 배포 옵션으로 제공 됩니다.

- Azure Stack 통합 시스템

- Azure Stack 개발 키트

### <a name="azure-stack-integrated-systems"></a>Azure Stack 통합 시스템

Azure Stack 통합 시스템은 Microsoft 및 하드웨어 파트너의 파트너 관계를 통해 제공 됩니다. 파트너 관계 관리에서는 간단 하 게 사용 하 여 분산 되는 클라우드 주도적 혁신을 제공 하는 솔루션을 만듭니다. Azure Stack 하드웨어 및 소프트웨어의 통합된 시스템으로 제공 하기 때문에 여전히 클라우드에서 혁신을 채택 하는 동안 적절 한 양의 유연성과 컨트롤을 가져옵니다. Azure Stack 통합 시스템 12 노드로 4 이르는 및 하드웨어 파트너와 Microsoft에서 지원 됩니다. 프로덕션 워크 로드에 대 한 새 시나리오를 구현 하려면 Azure Stack 통합 시스템을 사용 합니다.

### <a name="azure-stack-development-kit"></a>Azure Stack 개발 키트

Microsoft Azure Stack 개발 키트에는 평가 하 고 Azure Stack에 대해 알아보기에 사용할 수 있는 Azure Stack의 단일 노드 배포입니다. 또한 여기서 Api를 사용 하 여 개발할 수 있습니다 하 고 Azure와 일치 하는 도구는 개발자 환경으로 Azure Stack 개발 키트를 사용할 수 있습니다. Azure Stack 개발 키트 프로덕션 환경으로 사용할 수 없습니다.

### <a name="additional-resources"></a>추가 자료

- **Azure 하이브리드 클라우드**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Windows 컨테이너에 대 한 active Directory 서비스 계정**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Active Directory 지원을 통해 컨테이너 만들기**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Azure 하이브리드 혜택 라이선스**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[이전](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[다음](../walkthroughs-technical-get-started-overview.md)
