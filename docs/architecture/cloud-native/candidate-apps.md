---
title: 클라우드 네이티브용 후보 앱
description: 클라우드 네이티브 접근 방식의 이점을 누리는 응용 프로그램 유형 알아보기
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805617"
---
# <a name="candidate-apps-for-cloud-native"></a>클라우드 네이티브용 후보 앱

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

포트폴리오의 앱을 살펴보십시오. 클라우드 네이티브 아키텍처를 받을 자격이 있는 사람은 몇 명입니까? 위 운영 체제 모두 아마도 일부?

비용/이점 분석을 적용하면 대부분의 경우 클라우드 네이티브에 필요한 막대한 가격 표를 지원하지 않을 가능성이 높습니다. 클라우드 네이티브인 비용은 응용 프로그램의 비즈니스 가치를 훨씬 초과합니다.

클라우드 네이티브의 후보가 될 수 있는 응용 프로그램 유형은 무엇입니까?

- 비즈니스 기능/기능을 지속적으로 발전시켜야 하는 대규모의 전략적 엔터프라이즈 시스템

- 높은 릴리스 속도를 요구하는 응용 프로그램 - 높은 신뢰도

- 전체 시스템을 완전히 *재배포하지 않고* 개별 기능을 릴리스해야 하는 시스템

- 다양한 기술 스택에 대한 전문 지식을 갖춘 팀이 개발한 애플리케이션

- 독립적으로 확장해야 하는 구성 요소가 있는 응용 프로그램

그런 다음 레거시 시스템이 있습니다. 모두 새 응용 프로그램을 빌드하고 싶지만 비즈니스에 중요한 레거시 워크로드를 현대화하는 경우가 많습니다. 시간이 지남에 따라 레거시 응용 프로그램을 마이크로 서비스로 분해하고 컨테이너화하여 궁극적으로 클라우드 네이티브 아키텍처로 "다시 플랫폼화"할 수 있습니다.

### <a name="modernizing-legacy-apps"></a>레거시 앱 현대화

무료 Microsoft 전자책은 [Azure 클라우드 및 Windows 컨테이너를 통해 기존 .NET 응용 프로그램을 현대화하여](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) 온-프레미스 워크로드를 클라우드로 마이그레이션하기 위한 지침을 제공합니다. 그림 1-10은 레거시 응용 프로그램을 현대화하기 위한 단일 한 가지 전략이 없다는 것을 보여줍니다.

![레거시 워크로드 마이그레이션 전략](./media/strategies-for-migrating-legacy-workloads.png)

**그림 1-10 .** 레거시 워크로드 마이그레이션 전략

중요하지 않은 모놀리식 앱은 빠른 리프트 앤 시프트(클라우드[인프라 지원)](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)마이그레이션의 이점을 크게 활용합니다. 여기서 온-프레미스 워크로드는 변경 없이 클라우드 기반 VM으로 다시 호스팅됩니다. 이 방법은 [IaaS(인프라 서비스로서의 인프라) 모델을](https://azure.microsoft.com/overview/what-is-iaas/)사용합니다. Azure에는 이러한 이동을 더 쉽게 하기 위해 [Azure 마이그레이션,](https://azure.microsoft.com/services/azure-migrate/) [Azure 사이트 복구](https://azure.microsoft.com/services/site-recovery/)및 Azure 데이터베이스 마이그레이션 [서비스와](https://azure.microsoft.com/campaigns/database-migration/) 같은 몇 가지 도구가 포함되어 있습니다. 이 전략은 일부 비용 절감효과를 가져올 수 있지만, 이러한 애플리케이션은 일반적으로 클라우드 컴퓨팅의 이점을 활용하고 잠금을 해제하고 활용하기 위해 설계되지 않았습니다.

비즈니스에 중요한 모놀리식 앱은 향상된 리프트 앤 시프트(클라우드*최적화)* 마이그레이션의 이점을 자주 누릴 수 있습니다. 이 접근 방식에는 응용 프로그램의 핵심 아키텍처를 변경하지 않고 주요 클라우드 서비스를 활성화하는 배포 최적화가 포함됩니다. 예를 들어 응용 프로그램을 [컨테이너화하고](https://docs.microsoft.com/virtualization/windowscontainers/about/) 이 설명서의 후반부에서 설명하는 [Azure Kubernetes 서비스(Azure Kubernetes Services)와](https://azure.microsoft.com/services/kubernetes-service/)같은 컨테이너 오케스트레이터에 배포할 수 있습니다. 클라우드에 들어가면 응용 프로그램은 데이터베이스, 메시지 큐, 모니터링 및 분산 캐싱과 같은 다른 클라우드 서비스를 사용할 수 있습니다.

마지막으로, 전략적 엔터프라이즈 기능을 수행하는 모놀리식 앱은 이 책의 주제인 *클라우드 네이티브* 접근 방식의 이점을 가장 잘 활용할 수 있습니다. 이 접근 방식은 민첩성과 속도를 제공합니다. 그러나 코드를 다시 플랫포밍하고 다시 작성해야 합니다.

귀하와 귀하의 팀이 클라우드 네이티브 접근 방식이 적절하다고 생각되면 조직과의 결정을 합리화하는 것이 좋습니다. 클라우드 네이티브 접근 방식이 해결할 비즈니스 문제는 정확히 무엇입니까? 비즈니스 요구 사항에 어떻게 부합할까요?

- 자신감을 높이는 기능의 신속한 출시?

- 세분화된 확장성 - 리소스의 보다 효율적인 사용?

- 시스템 복원력 향상?

- 시스템 성능이 향상되었습니다.

- 운영에 대한 가시성을 높이고 있습니까?

- 개발 플랫폼과 데이터 저장소를 혼합하여 작업에 가장 적합한 도구에 도달하고 있습니까?

- 미래 지향적인 애플리케이션 투자?

올바른 마이그레이션 전략은 조직의 우선 순위와 대상으로 하는 시스템에 따라 달라집니다. 대부분의 경우 모놀리식 응용 프로그램을 클라우드로 최적화하거나 N-Tier 앱에 거친 서비스를 추가하는 것이 더 비용 효율적일 수 있습니다. 이러한 경우 Azure 앱 서비스에서 제공하는 것과 같은 클라우드 PaaS 기능을 최대한 활용할 수 있습니다.

## <a name="summary"></a>요약

이 장에서는 클라우드 네이티브 컴퓨팅을 소개했습니다. 클라우드 네이티브 응용 프로그램을 구동하는 주요 기능과 함께 정의를 제공했습니다. 우리는 이 투자와 노력을 정당화할 수 있는 응용 프로그램의 유형을 살펴보았습니다.

뒤에 소개와 함께, 우리는 지금 클라우드 네이티브에 훨씬 더 자세한 모습으로 다이빙.

### <a name="references"></a>참조

- [클라우드 네이티브 컴퓨팅 기반](https://www.cncf.io/)

- [.NET 마이크로 서비스: 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Azure 클라우드 및 Windows 컨테이너를 통해 기존 .NET 응용 프로그램을 현대화](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [코넬리아 데이비스의 클라우드 네이티브 패턴](https://www.manning.com/books/cloud-native-patterns)

- [12단계 응용 프로그램 을 넘어서](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [인프라가 코드로 이란?](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [동네 짱 엔지니어링의 마이크로 배포: 자신감을 가진 매일 배포](https://eng.uber.com/micro-deploy/)

- [넷플릭스가 코드를 배포하는 방법](https://www.infoq.com/news/2013/06/netflix/)

- [WeChat 마이크로 서비스 확장을 위한 과부하 제어](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[이전](definition.md)
>[다음](introduce-eshoponcontainers-reference-app.md)
