---
title: Azure 클라우드를 사용하여 기존.NET 응용 프로그램과 Windows 컨테이너를 최신으로 변경하기 (2 판)
description: 리프트 앤 시프트 및 Azure 클라우드 및 이 전자책을 사용하여 컨테이너에 기존 응용 프로그램을 최신으로 변경하는 방법을 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 7e56238e129cadd128240d51f03a5926e6de3e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628421"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Azure 클라우드와 Windows 컨테이너를 사용하여 기존.NET 응용 프로그램을 최신으로 변경하기 (2 판)

![표지 이미지 현대화.NET 응용 프로그램 가이드입니다.](./media/index/web-application-guide-cover-image.png)

게시자:  
Microsoft Press 및 Microsoft DevDiv  
Microsoft Corporation의 사업부  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 by Microsoft Corporation  

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제할 수 없습니다.

이 책은 <https://dot.net/architecture>와 같은 다양한 Microsoft 채널을 통해 전자책(e-book)의 형태로 제공되며 무료로 사용할 수 있습니다.

이 책에 관한 질문은 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 이메일을 보내 주세요.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. 이러한 견해와 의견, URL, 기타 인터넷 웹 사이트 참조를 비롯한 이 책에 표시된 정보는 통보 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

"상표" 웹 페이지의 <https://www.microsoft.com>에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다. 기타 모든 표시는 해당 소유자의 자산입니다.

만든 이:
> **Cesar de la Torre**, 수석 PM.NET 제품 팀, Microsoft Corp.

참가자 및 검토자:
> **Scott Hunter**, 파트너 PM 책임자, Microsoft .NET 팀  
> **Paul Yuknewicz**, 수석 PM 관리자, Microsoft Visual Studio Tools 팀  
> **Lisa Guthrie**, 수석 PM, Microsoft Visual Studio Tools 팀  
> **Ankit Asthana**, 수석 PM 관리자, Microsoft .NET 팀  
> **Unai Zorrilla**, 수석 개발자, Plain Concepts  
> **Javier Valero**, 최고 운영 책임자, Grupo Solutio  

## <a name="introduction"></a>소개

웹 응용 프로그램 또는 서비스를 최신으로 변경하고 클라우드로 이동하기위해 앱 아키텍처를 완전히 변경해야 하는 것은 아닙니다. 제한된 시간과 비용 때문에 마이크로 서비스 같은 향상된 방법으로 응용 프로그램을 재설계하는 것을 항상 선택할 수는 없습니다. 응용 프로그램의 유형에 따라 앱의 아키텍처를 변경하지 않을 수도 있습니다. 조직의 클라우드 마이그레이션 전략을 비용 효과적으로 최적화하려면 비즈니스와 앱의 요구 사항을 고려해야 합니다. 다음 사항을 파악해야 합니다.

- 아키텍처를 재설계하거나 변경이 필요한 앱.

- 일부분만 최신으로 변경해야 하는 앱.

- 클라우드에 바로 "리프트 앤 시프트(통째로 들어 올리는)"할 수 있는 앱.

## <a name="about-this-guide"></a>이 가이드의 내용

이 가이드는 주로 기존 MICROSOFT.NET Framework 웹이나 서비스 지향 응용 프로그램의 기본 아키텍처와 응용 프로그램의 코드를 크게 변경하지 않고 최신의 새로운 환경으로 워크로드를 옮기는 작업을 뜻하는 초기의 최신화에 중점을 둡니다. 

이 가이드에서는 클라우드로 앱을 옮기는 것의 이득과 Windows 컨테이너와 Windows 컨테이너를 지원하는 Azure의 관련된 계산 플랫폼과 같은 새로운 기술과 방법을 사용하여 앱을 부분적으로 최신화하는 것에 대한 이점을 강조합니다.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>기존.NET 애플리케이션을 클라우드로 이동하는 경로

조직에서는 일반적으로 응용 프로그램이 민첩성과 속도를 갖게 하기 위해 클라우드로 옮기는 것을 선택합니다. 클라우드에서는 몇 분 안에 수천 대의 서버(VM)를 설치할 수 있는데 비해 온프레미스에 직접 서버를 구축하는 데는 몇 주의 시간이 걸리는 것이 일반적입니다.

클라우드로 애플리케이션을 마이그레이션하는 방법에 대한 단일 만능 전략은 없습니다. 귀하에게 적합한 마이그레이션 전략은 귀사의 요구 사항과 우선 순위, 마이그레이션하는 애플리케이션의 종류에 따라 달라집니다. 모든 애플리케이션이 서비스 제공 플랫폼([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) 모델로의 전환이나 [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 애플리케이션 모델 개발에 대한 투자를 보증하는 것은 아닙니다. 대다수의 경우 비즈니스 요구 사항에 따라 단계식 또는 증분 접근법을 사용하여 클라우드로의 자산 전환에 투자할 수 있습니다.

최상의 장기적인 민첩성과 가치를 지닌 최신 응용 프로그램의 경우 *클라우드 네이티브* 응용 프로그램 아키텍처에 투자하는 것이 좋습니다. 그러나 기존 응용 프로그램의 경우 중요 이점을 실현하기 위해서는 클라우드로 이동하면서 최소한의 시간과 비용(재설계 또는 코드 변경 없이)을 들이는 것이 핵심입니다.

그림 1-1에서는 증분 단계로 기존.NET 응용 프로그램을 클라우드로 옮기는 경우 선택할 수 있는 방법을 보여 줍니다.

 ![기존 .NET 애플리케이션 및 서비스의 현대화 경로](./media/image1-1.png)

> **그림 1-1**. 기존 .NET 애플리케이션 및 서비스의 현대화 경로

각 마이그레이션 방법마다 이점과 사용해야 할 이유가 다릅니다. 클라우드에 앱을 마이그레이션하는 경우 단일 접근법을 선택하거나 여러 접근법 중에서 특정 구성 요소를 선택할 수 있습니다. 개별 애플리케이션이 단일 접근법이나 완성 상태로 제한되는 것은 아닙니다. 예를 들어, 일반적인 하이브리드 접근법은 특정 온-프레미스 구성 요소와 다른 클라우드 구성 요소를 사용합니다.

각 응용 프로그램 완성도에 대 한 간략 한 설명을 확인 하 고 정의는 다음과 같습니다.

**수준 1: 클라우드 인프라 지원** 응용 프로그램: 이 마이그레이션 접근법에서는 단순히 마이그레이션하거나 rehost 서비스로 인프라에 현재 온-프레미스 응용 프로그램 ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) 플랫폼입니다. 앱의 구성은 전과 거의 동일하지만 이제 클라우드의 VM에 앱을 배포합니다.
이 간단한 유형의 마이그레이션은 일반적으로 "리프트 및 시프트" 업계에 알려진

**수준 2: 클라우드 최적화** 응용 프로그램: 이 수준에서 한 여전히 재설계 나 중요 한 코드 변경 없이 컨테이너 및 추가 클라우드 관리 서비스와 같은 최신 기술 사용 하 여 클라우드에서 앱을 실행 하는 추가 이점을 얻을 수 있습니다. 기업 개발 운영(DevOps) 프로세스를 세분화하여 애플리케이션의 민첩성을 개선함으로써 더 빨리 배송할 수 있습니다. Docker 엔진을 기반으로 하는 Windows 컨테이너 같은 기술을 사용 하 여이 작업을 수행 합니다. 컨테이너는 여러 단계로 배포 하는 경우 응용 프로그램 종속성으로 발생 하는 마찰을 제거 합니다. 이 완성 모델에서 IaaS에서 컨테이너를 배포할 수 있습니다 또는 추가 사용 하는 동안 PaaS as a service, 모니터링 및 지속적인 통합/지속적인 배포 (CI/CD) 파이프라인 캐시 데이터베이스에 관련 된 클라우드 관리 서비스입니다.

세 번째 완성도는 클라우드의 궁극적 목표이지만 여러 앱에는 선택적이며 이 가이드의 주요 초점은 아닙니다.

**수준 3: 클라우드 네이티브** 응용 프로그램: 이 마이그레이션 접근법은 일반적으로 비즈니스 필요 성과 업무상 중요 한 응용 프로그램 현대화를 대상으로 하 여 결정 됩니다. 이 수준에서는 PaaS 서비스를 사용하여 PaaS 컴퓨팅 플랫폼으로 앱을 이동합니다. [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램 및 마이크로 서비스 아키텍처를 구현하여 장기적인 민첩성으로 응용 프로그램을 진화시키고 새로운 한계로 확장합니다. 이 유형의 현대화는 일반적으로 클라우드를 위한 특별한 설계가 필요합니다. 특히 클라우드 전용 애플리케이션 및 마이크로 서비스 기반 모델로 이동하는 경우 새 코드를 작성해야 하는 경우가 많습니다. 이 방법은 모놀리식 및 온-프레미스 애플리케이션 환경에서 달성하기 어려운 이점을 얻는 데 도움이 될 수 있습니다.

표 1-1에서는 각 마이그레이션 또는 현대화 방법을 선택하는 이유와 주요 이점을 설명합니다.

| **클라우드 인프라 지원** <br /> *리프트 앤 시프트* | **클라우드 최적화** <br /> *Modernize* | **Cloud-Native** <br /> *현대화 재설계 하 고 다시 작성* |
|---|---|---|
| **응용 프로그램의 계산 대상** |
| Azure의 VM에 배포된 응용 프로그램 | 컨테이너 또는 Azure Service Fabric 또는 AKS(Azure Kubernetes Service)를 사용하여 Azure App Service, Azure 컨테이너 인스턴스(ACI), VM에 배포된 모놀리식 또는 N-티어 앱 | AKS(Azure Kubernetes Service)와 Service Fabric 및 Azure 함수 기반의 서버리스 마이크로 서비스에서 컨테이너화된 마이크로 서비스. |
| **데이터 대상** |
| VM의 모든 관계형 데이터베이스나 SQL | Azure SQL Database Managed Instance 또는 클라우드에서 관리되는 그 밖의 데이터베이스. | Azure SQL Database나 Azure Cosmos DB, 그 밖의 클라우드에서 관리되는 데이터베이스기반의 마이크로 서비스당 세분화된 데이터베이스 |
| **장점**|
| <li>재설계, 새로운 코드 불필요 <li> 최소한의 작업으로 빠른 마이그레이션 가능 <li> Azure에서 지원되는 공통점 <li> 기본 가용성 보장 <li> 클라우드로 이동 후  아주 쉬운 최신화 | <li> 재설계 불필요 <li> 최소한의 코드 및 구성 변경 <li> 컨테이너로 인해 향상된 배포와 DevOps 릴리스 민첩성 <li> 밀도 증가 및 배포 비용 감소 <li> 앱 및 종속성의 이식성 <li> 호스트 대상의 유연성 : PaaS나 IaaS 방식 | <li> 클라우드용 설계, 클리우드에서 최고의 이득을 얻을 수 있으나 새로운 코드 필요 <li> 마이크로 서비스 클라우드 전용 접근법 <li> 최신 중요 업무용 응용 프로그램, 클라우드 복원력이 있는 매우 뛰어난 확장성 <li> 완벽하게 관리되는 서비스 <li> 규모에 최적화 <li> 하위 시스템에 의한 자율적인 민첩성 최적화 <li> 배포 및 DevOps 기반 |
| **당면 과제** |
| <li> 운영 비용이나 데이터 센터 폐쇄가 아닌 클라우드 가격 축소 <li> 관리가 어려움: OS나 미들웨어 패치 없음. Terraform이나 Spinnaker, Puppet 같은 인프라 솔루션을 사용할 수 있음. | <li> 컨테이너화는 개발자와 IT 운영에 대한 학습 곡선의 단계를 증가시킴 <li> DevOps 및 CI/CD 파이프라인은 일반적으로 이러한 방식에서 반드시 필요하며, 현재 조직에 없다면 추가적인 당면 과제입니다.| <li> 클라우드 네이티브 앱과 마이크로 서비스 아키텍처의 재개발이 필요하며 일반적으로 최신으로 변경하는 경우 상당한 코드 리팩터링이나 재작성이 필요합니다(시간 및 예산 증가). <li> DevOps 및 CI/CD 파이프라인은 일반적으로 이러한 방식에서 반드시 필요하며, 현재 조직에 없다면 추가적인 당면 과제입니다.|
> **표 1-1.** 기존 .NET 애플리케이션과 서비스를 최신으로 변경하는 방법의 이점 및 당면 과제

### <a name="key-technologies-and-architectures-by-maturity-level"></a>성숙도별 핵심 기술 및 아키텍처

초기 .NET Framework 애플리케이션은 2001년 후반에 출시된 .NET Framework 버전 1.0으로 시작되었습니다. 그런 다음 기업에서는 최신 버전(예: .NET 2.0과 3.5, 4.x)으로 넘어갔습니다. 이러한 응용 프로그램은 대부분 Windows Server와 인터넷 정보 서버(IIS)에서 동작하고 SQL Server나 Oracle, MySQL 또는 그 밖의 RDBMS와 같은 관계형 데이터베이스를 사용합니다.

최근 .NET 애플리케이션은 대부분 .NET Framework 4.x나 .NET Framework 3.5 기반이며, ASP.NET MVC와 ASP.NET Web Forms, ASP.NET Web API, Windows Communication Foundation(WCF), ASP.NET SignalR, ASP.NET Web Pages 같은 웹 프레임워크를 사용합니다. 이와 같은 기존의 .NET Framework 기술은 Windows에 종속됩니다. 단순히 레거시 앱만 마이그레이션하고 애플리케이션 인프라의 변경을 최소화하려면 이러한 종속성을 고려해야 합니다.

그림 1-2에서는 각각의 세 가지 클라우드 성숙도에 해당하는 주요 기술과 아키텍처 스타일을 보여 줍니다.

![각 성숙도별 기존 .NET 웹 애플리케이션을 최신으로 변경하는데 필요한 주요 기술](./media/image1-2.png)

> **그림 1-2.** 각 성숙도별로 기존 .NET 웹 애플리케이션을 최신으로 변경하는데 필요한 주요 기술

그림 1-2는 가장 일반적인 시나리오이며 아키텍처는 여러 가지 하이브리드와 혼합된 변형 형태가 가능합니다. 예를 들어 성숙도 모델은 기존 웹앱의 모놀리식 아키텍처 뿐만 아니라 서비스 지향과 N-티어, 그 밖의 아키텍처 스타일 변형에도 적용됩니다. 집중되어 있거나 비중이 높은 아키텍처 유형과 관련 기술이 응용 프로그램의 전반적인 성숙도를 결정합니다.

최신화 과정의 각 성숙도는 다음 핵심 기술 및 방법과 관련이 있습니다.

- **클라우드 인프라 지원** (재호스팅 또는 기본적인 리프트 엔 시프트): 첫 번째 단계로, 대부분의 조직에서는 신속하게 클라우드 마이그레이션 전략을 실행하려고 합니다. 이 경우 응용 프로그램은 재호스팅됩니다. 대부분의 재호스팅은 [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)와 [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) 같은 클라우드 도구 기반의 Azure 마이그레이션 가이드와 정보, 메커니즘을 제공하는 [Azure Migrate](https://aka.ms/azuremigrate) 서비스로 자동화할 수 있습니다. 레거시 앱을 클라우드로 옮길 때 자산에 대한 인프라 세부 정보를 파악할 수 있도록 수동으로 재호스팅을 설정할 수도 있습니다. 예를 들면 간단한 설정값을 변경하는 등의 최소한의 변경으로 응용 프로그램을 Azure의 VM으로 옮길 수 있습니다. 이 경우 네트워킹은 온-프레미스 환경과 비슷하며, Azure에서 가상 네트워크를 만드는 경우라면 특히 비슷합니다.

- **클라우드 최적화** (관리 서비스와 Windows 컨테이너): 이 모델은 응용 프로그램의 핵심 아키텍처를 변경 하지 않고 클라우드에서 상당한 이점을 얻는 몇 가지 중요 한 배포 최적화 합니다. 여기서 기본 단계는 기존의 .NET Framework 애플리케이션에 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 지원을 추가하는 것입니다. 이 중요 한 단계 (컨테이너 화)는 전반적인 리프트 앤 시프트 작업 light 이므로 코드를 건드리지 필요 하지 않습니다. [Image2Docker](https://github.com/docker/communitytools-image2docker-win) 또는 Visual Studio 같은 도구와 [Docker](https://www.docker.com/)용 도구를 사용할 수 있습니다. Visual Studio는 ASP.NET 애플리케이션 및 Windows 컨테이너 이미지에 대한 스마트 기본값을 자동으로 선택합니다. 이러한 도구는 신속한 내부 루프와 Azure로 컨테이너를 가져올 수 있는 빠른 경로를 제공합니다. 여러 환경에 배포할 때 민첩성이 향상됩니다. 그런 다음 프로덕션으로 전환, 배포할 수 있습니다 하 여 Windows 컨테이너에 [Azure Web App for Containers](https://azure.microsoft.com/services/app-service/containers/), [Azure ACI (Container Instances), 및 Windows Server 2016 및 IaaS 방식이 선호 하는 경우 컨테이너를 사용 하 여 Azure Vm입니다. 같은 오 케 스트레이 터에 약간 더 복잡 한 다중 컨테이너 응용 프로그램에 대 한 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) 하거나 [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/)합니다. 이 초기 현대화 중 추가할 수도 있습니다 자산와 같은 도구를 사용 하 여 모니터링 하는 등 클라우드에서 [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview); CI/CD 파이프라인을 사용 하 여 앱 수명 주기에 [Azure DevOps 서비스](https://azure.microsoft.com/services/devops/); 및 Azure에서 사용할 수 있는 많은 추가 데이터 리소스 서비스입니다. 예를 들어 원래 기존의 [ASP.NET Web Forms](https://www.asp.net/web-forms) 또는 [ASP.NET MVC](https://www.asp.net/mvc)를 사용하여 개발되었지만 이제 Windows 컨테이너를 사용하여 배포할 모놀리식 웹앱을 수정할 수 있습니다. Windows 컨테이너를 사용할 경우 애플리케이션의 핵심 아키텍처를 변경하지 않고 데이터도 [Azure SQL Database Managed Instance](https://docs.microsoft.com/azure/sql-database/)의 데이터베이스로 마이그레이션해야 합니다.

- **클라우드 네이티브**: 에 도입 된 설계 고려해 야 [클라우드 네이티브](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 수 있는 다른 마이크로 서비스에서 작업 하는 여러 독립 개발 팀을 사용 하 여 크고 복잡 한 응용 프로그램을 대상으로 할 때 응용 프로그램 개발 하 고 자율적으로 배포 합니다. 또한 마이크로 서비스 마다 granularized와 확장성 인해 이러한 아키텍처 접근 방법을 매우 중요 한 과제와 복잡 한 직면 하 고 있지만 클라우드 PaaS를 사용 하 여 크게 간소화할 수 있습니다 및 오 케 스트레이 터 [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) (managed Kubernetes), [Azure 서비스 패브릭 및 [Azure Functions](https://azure.microsoft.com/services/functions/) 서버 리스 방식에 대 한 합니다. 클라우드 용 설계 하 고 새 코드를 작성 하는 (예: 마이크로 서비스 및 서버) 이러한 모든 접근이 방법은 일반적으로 필요-특정 PaaS 플랫폼에 적용 되는 코드 또는 마이크로 서비스 같은 특정 아키텍처에 부합 하는 코드입니다.

다음 그림 1-3에서는 성숙도별로 사용할 수 있는 내부 기술을 보여줍니다.

![최신화 성숙도별 해당하는 내부 기술](./media/image1-3.png)

> **그림 1-3.** 최신화 성숙도별 내부 기술

## <a name="lift-and-shift-scenario"></a>리프트 앤 시프트 시나리오

리프트 앤 시프트 마이그레이션의 경우, 애플리케이션 시나리오에서 리프트 앤 시프트의 다양한 변형 형태를 사용할 수 있습니다. 애플리케이션을 다시 호스팅하기만 하는 경우는 애플리케이션과 데이터베이스 서버 전용의 클라우드 VM을 사용하는 그림 1-4와 같은 시나리오에 해당할 수 있습니다.

![클라우드에서 순수 IaaS 시나리오의 예](./media/image1-4.png)

> **그림 1-4**. 클라우드에서 순수 IaaS 시나리오의 예

## <a name="modernization-scenarios"></a>최신화 시나리오

최신화 시나리오의 경우 해당 성숙도의 요소만 사용하는 순수 클라우드 최적화 응용 프로그램이 있을 수 있습니다. 또는 그림 1-5와 같이 클라우드 인프라 지원(Cloud Infrastructure-Ready)의 일부 요소와 클라우드 최적화(Cloud-Optimized)의 다른 요소 ("pick and choose"나 혼합된 형태의 모델)를 사용하는 중간 상태의 응용 프로그램이 있을 수 있습니다.

![IaaS와 DevOps, 컨테이너화 자산에 있는 데이터베이스를 사용하는 "pick and choose" 시나리오의 예](./media/image1-5.png)

> **그림 1-5.** IaaS와 DevOps, 컨테이너화 자산에 있는 데이터베이스를 사용하는 "pick and choose" 시나리오의 예

다음으로 마이그레이션하려면 여러 기존.NET Framework 응용 프로그램에 이상적인 시나리오로 클라우드에 최적화 된 응용 프로그램에 약간의 작업에 상당한 이점을 활용 하려면 마이그레이션할 수 있습니다. 이 접근법은 하면 클라우드 네이티브에 대해 가능한 향후 발전 과정으로 합니다. 그림 1-6에 그 예가 나와 있습니다.

![Windows 컨테이너 및 관리 되는 서비스를 사용 하 여 예제 클라우드 최적화 앱 시나리오](./media/image1-6.png)

> **그림 1-6.** Windows 컨테이너 및 관리 되는 서비스를 사용 하 여 예제 클라우드 최적화 앱 시나리오

더 나아가서 특정 시나리오에 대 한 몇 가지 마이크로 서비스를 추가 하 여 기존 클라우드 액세스에 최적화 된 응용 프로그램을 확장할 수 있습니다. 이 이동 하면 부분적으로 현재 지침에서는의 주요 초점은 없는 클라우드 네이티브 모델 수준입니다.

## <a name="what-this-guide-does-not-cover"></a>이 가이드에서 다루지 않는 내용

이 가이드에서는 그림 1-7에 나와 있는 시나리오 예를 몇 가지 다룹니다. 이 가이드 및 궁극적으로 클라우드 최적화 모델을 리프트 앤 시프트 시나리오에만 중점을 둡니다. 클라우드 최적화 모델에서 Windows 컨테이너와 모니터링과 같은 추가 구성 요소를 사용 하 여.NET Framework 응용 프로그램을 현대화 됩니다 및 CI/CD 파이프라인. 각 구성 요소는 클라우드로 애플리케이션을 더 빨리, 민첩하게 배포하는 데 핵심적입니다.

![클라우드 네이티브가이 가이드에서는 다루지 않습니다.](./media/image1-7.png)

> **그림 1-7.** 클라우드 네이티브가이 가이드에서는 다루지 않습니다.

이 가이드는 특정 부분에 중점을 둡니다. 경로의 아키텍처를 변경 하지 않고 코드 변경 없이 리프트 앤 시프트 기존.NET 응용 프로그램을 달성 하기 위해 취할 수를 보여줍니다. 궁극적으로 하는 방법을 보여 줍니다 응용 프로그램을 쉽게 클라우드에 최적화 합니다.

이 가이드에서 마이크로 서비스 아키텍처로 진화 하는 방법 등의 클라우드 네이티브 응용 프로그램을 만드는 방법을 표시 되지 않습니다. 응용 프로그램을 재설계 하거나 마이크로 서비스를 기반으로 하는 새로운 응용 프로그램을 만드는 참조 전자책 [.NET 마이크로 서비스: 컨테이너 화 된.NET 응용 프로그램에 대 한 아키텍처](https://aka.ms/microservicesebook)합니다.

### <a name="additional-resources"></a>추가 자료

- **Microsoft 플랫폼 및 도구를 사용 하 여 Docker 응용 프로그램 수명 주기를 컨테이너 화 된** (다운로드 가능한 전자책) \
  <https://aka.ms/dockerlifecycleebook>

- **.NET 마이크로 서비스: 컨테이너 화 된.NET 응용 프로그램에 대 한 아키텍처** (다운로드 가능한 전자책) \
  <https://aka.ms/microservicesebook>

- **ASP.NET Core 및 Azure를 사용 하 여 현대식 웹 응용 프로그램 설계** (다운로드 가능한 전자책) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드는 개발자와 배송 및 응용 프로그램 출시 민첩성 향상된을 위해.NET Framework를 기반으로 하는 WCF 서비스 또는 기존 ASP.NET 웹 응용 프로그램을 현대화 하려는 솔루션 설계자를 위한 작성 되었습니다.

또한 Windows 컨테이너를 사용하고, Microsoft Azure 사용 시 클라우드로 배포하여 얻을 수 있는 이점을 간략히 살펴보고자 하는 기업 설계자 또는 개발 책임자/이사와 같은 기술 의사 결정권자일 경우 이 가이드가 유용할 수 있습니다.

## <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드에서는 "이유"를 설명합니다. 기존 애플리케이션을 현대화하려는 이유, 클라우드로 앱 이동 시 Windows 컨테이너 사용으로 얻을 수 있는 구체적인 이점을 설명합니다. 이 가이드에서 처음 몇 챕터의 내용은 개요를 알고 싶지만 구현과 기술적인 단계별 세부 정보에 대해 중점을 둘 필요가 없는 설계자와 기술 의사 결정권자를 위해 고안되었습니다.

이 가이드의 마지막 챕터에서는 특정 배포 시나리오에 초점을 맞춘 여러 안내를 소개합니다. 이 가이드에서는 시나리오를 요약 하 고 해당 이점을 중점적 짧은 버전의 안내를 제공 합니다. 자세한 안내는 설치 및 구현에 대한 세부 정보를 설명하고, 관련 샘플 앱이 있는 동일한 공개 [GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)에 일련의 [Wiki 게시물](https://github.com/dotnet-architecture/eShopModernizing/wiki)로 게시되어 있습니다(다음 섹션에서 설명). 마지막 챕터와 GitHub의 단계별 Wiki 안내는 구현 세부 정보를 중점적으로 파악하고자 하는 개발자와 설계자에게 더 많은 관심을 받을 것입니다.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>레거시 앱 현대화에 대한 샘플 앱: eShopModernizing

GitHub의 [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) 리포지토리는 레거시 모놀리식 웹 애플리케이션을 시뮬레이션하는 두 가지 샘플 애플리케이션을 제공합니다. ASP.NET MVC;를 사용 하 여 하나의 웹 앱 개발 ASP.NET Web Forms를 사용 하 여 두 번째 웹 앱을 개발 하 고 세 번째 앱은 WCF 서비스 백 엔드를 사용 하는 WinForms 클라이언트 데스크톱 앱을 사용 하 여 N 계층 앱입니다. 이러한 모든 앱은 기존.NET Framework를 기반으로 합니다. 이러한 샘플은 현대화해야 하는 기존/레거시 .NET Framework 애플리케이션이어야 하기 때문에 .NET Core 또는 ASP.NET Core를 사용하지 않습니다.

이러한 샘플 앱 현대화 된 코드를 사용 하 여 두 번째 버전이 매우 간단 합니다. 앱 버전 간의 가장 중요한 차이점은 두 번째 버전에서 배포 옵션으로 Windows 컨테이너를 사용한다는 것입니다. 또한 두 번째 버전에는 이미지 관리를 위한 Azure Storage Blob, 보안 관리를 위한 Azure Active Directory, 애플리케이션 모니터링 및 감사를 위한 Azure Application Insights 같은 몇 가지 기능이 추가되었습니다.

## <a name="send-your-feedback"></a>피드백 보내기

이 가이드는 개선 하 고 기존.NET 웹 응용 프로그램을 현대화 하기 위한 옵션을 이해할 수 있도록 작성 되었습니다. 가이드와 관련 샘플 애플리케이션은 개선되고 있습니다. 사용자 의견을 보내주세요! 이 가이드의 개선 방향에 대한 의견이 있으시면 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 보내 주세요.

>[!div class="step-by-step"]
>[다음](lift-and-shift-existing-apps-azure-iaas.md)
