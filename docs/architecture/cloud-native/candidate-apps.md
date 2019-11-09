---
title: 클라우드 네이티브 용 후보 앱
description: 클라우드 기본 방법의 이점을 활용 하는 응용 프로그램의 유형 알아보기
author: robvet
ms.date: 08/20/2019
ms.openlocfilehash: 127dca45ce8a5e025ca7511e6513afffe64e592d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841860"
---
# <a name="candidate-apps-for-cloud-native"></a>클라우드 네이티브 용 후보 앱

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

포트폴리오에서 앱을 확인 합니다. 클라우드 기본 아키텍처에 대해 얼마나 많은 자격이 있나요? 다? 무엇 인가요?

비용/혜택 분석을 적용 하는 경우 클라우드 네이티브로 필요한 hefty price 태그를 지원 하지 않는 것이 좋습니다. 클라우드 기본이 되는 비용은 응용 프로그램의 비즈니스 가치를 초과할 것입니다.

Cloud native의 후보가 될 수 있는 응용 프로그램의 유형은 무엇입니까?

- 비즈니스 기능/기능을 지속적으로 개선 해야 하는 거 대 한 전략적인 엔터프라이즈 시스템

- 높은 안정적인 릴리스 속도를 필요로 하는 응용 프로그램

- 전체 시스템의 전체 재배포 *없이* 개별 기능이 출시 되어야 하는 시스템

- 다른 기술 스택의 전문 지식이 있는 팀에서 개발한 응용 프로그램

- 독립적으로 크기를 조정 해야 하는 구성 요소를 포함 하는 응용 프로그램

그러면 레거시 시스템이 있습니다. 새 응용 프로그램을 구축 하는 것이 전부 이지만 비즈니스에 중요 한 레거시 워크 로드를 현대화 해야 하는 경우가 많습니다. 시간이 지남에 따라 레거시 응용 프로그램은 마이크로 서비스, 컨테이너 화 된 및 궁극적으로 "replatformed"으로 클라우드 기본 아키텍처로 분해할 수 있습니다.

### <a name="modernizing-legacy-apps"></a>현대화 레거시 앱

무료 Microsoft e-learning [현대화 Azure 클라우드 및 Windows 컨테이너를 사용 하는 기존 .net 응용 프로그램](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) 은 온-프레미스 워크 로드를 클라우드로 마이그레이션하기 위한 지침을 제공 합니다. 그림 1-10에서는 레거시 응용 프로그램을 현대화 하는 단일 크기에 맞는 단일 전략이 없다는 것을 보여 줍니다.

![레거시 작업을 마이그레이션하기 위한 전략](./media/strategies-for-migrating-legacy-workloads.png)

**그림 1-10**. 레거시 작업을 마이그레이션하기 위한 전략

심각 하지 않은 모놀리식 앱은 빠른 리프트 앤 시프트 ([클라우드 인프라 지원](https://docs.microsoft.com/dotnet/standard/modernize-with-azure-and-containers/lift-and-shift-existing-apps-azure-iaas)) 마이그레이션을 통해 주로 이점을 누릴 수 있습니다. 여기서 온-프레미스 워크 로드는 변경 없이 클라우드 기반 VM에 다시 호스트 됩니다. 이 방법은 [IaaS (Infrastructure as a Service) 모델](https://azure.microsoft.com/overview/what-is-iaas/)을 사용 합니다. Azure에는 ([Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)및 [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/))와 같은 몇 가지 도구를 사용 하 여 이러한 이동을 보다 쉽게 수행할 수 있습니다. 이 전략은 몇 가지 비용 절감 효과를 얻을 수 있지만, 이러한 응용 프로그램은 일반적으로 클라우드 컴퓨팅의 이점을 활용 하기 위해 설계 되지 않았습니다.

비즈니스에 중요 한 모놀리식 앱은 향상 된 리프트 앤 시프트 (*클라우드 최적화*) 마이그레이션을 활용 하는 것이 좋습니다. 이 접근 방식에는 응용 프로그램의 핵심 아키텍처를 변경 하지 않고도 핵심 클라우드 서비스를 사용할 수 있도록 하는 배포 최적화가 포함 됩니다. 예를 들어 응용 프로그램을 [컨테이너 화](https://docs.microsoft.com/virtualization/windowscontainers/about/) 하 고이 책의 뒷부분에서 설명 하는 [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/)와 같은 컨테이너 orchestrator에 배포할 수 있습니다. 클라우드에서 응용 프로그램은 데이터베이스, 메시지 큐, 모니터링 및 분산 캐싱과 같은 다른 클라우드 서비스를 사용할 수 있습니다.

마지막으로, 전략적 엔터프라이즈 기능을 수행 하는 모놀리식 apps는이 책의 일부인 *클라우드 기본* 접근 방식을 활용 하는 것이 가장 좋습니다. 이 방법은 민첩성과 속도를 제공 합니다. 그러나 코드를 다시 작성 하 고, 다시 작성 하 고, 다시 작성 하는 비용이 듭니다.

사용자 및 팀이 클라우드 기본 접근 방식이 적절 하다 고 생각 되는 경우 조직에 따라 결정을 합리화 behooves 합니다. 클라우드 기본 방법으로 해결할 수 있는 비즈니스 문제는 정확히 무엇 인가요? 비즈니스 요구 사항에 어떻게 부합 하나요?

- 신뢰도가 향상 된 기능의 신속한 릴리스

- 세분화 된 확장성-리소스를 보다 효율적으로 사용 하 고 있습니까?

- 시스템 복원 력이 향상 되었습니까?

- 향상 된 시스템 성능

- 작업에 대 한 가시성 향상

- Blend 개발 플랫폼과 데이터 저장소가 작업에 가장 적합 한 도구에 도착 하나요?

- 향후 응용 프로그램 투자가 있나요?

올바른 마이그레이션 전략은 대상으로 하는 시스템 및 조직의 우선 순위에 따라 달라 집니다. 대부분의 경우 모놀리식 응용 프로그램을 클라우드 최적화 하거나 N 계층 앱에 정교 하지 않은 서비스를 추가 하는 것이 더 비용 효율적일 수 있습니다. 이러한 경우에도 Azure App Service에서 제공 하는 것과 같은 클라우드 PaaS 기능을 완전히 사용할 수 있습니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 기본 컴퓨팅을 소개 했습니다. 클라우드 네이티브 응용 프로그램을 구동 하는 핵심 기능과 함께 정의를 제공 했습니다. 이러한 투자와 노력을 정당화할 수 있는 응용 프로그램의 유형을 살펴보았습니다.

소개를 통해 이제 클라우드 네이티브에 대해 훨씬 더 자세히 살펴보겠습니다.

### <a name="references"></a>참조 항목

- [클라우드 기본 컴퓨팅 기반](https://www.cncf.io/)

- [.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Cornelia Davis의 클라우드 기본 패턴](https://www.manning.com/books/cloud-native-patterns)

- [12 단계 응용 프로그램 이상](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [코드로 서의 인프라 란?](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Uber 엔지니어링의 마이크로 배포: 안심 하 고 매일 배포](https://eng.uber.com/micro-deploy/)

- [Netflix에서 코드를 배포 하는 방법](https://www.infoq.com/news/2013/06/netflix/)

- [WeChat 마이크로 서비스 크기 조정에 대 한 오버 로드 컨트롤](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

- [RayGun-사례 연구](https://raygun.com/case-study/ovation)

>[!div class="step-by-step"]
>[이전](definition.md)
>[다음](introduce-eshoponcontainers-reference-app.md)
