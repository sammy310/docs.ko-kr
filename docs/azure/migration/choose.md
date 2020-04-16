---
title: 올바른 Azure 호스팅 옵션 선택
description: 어떤 Azure 마이그레이션 경로가 ASP.NET 웹 애플리케이션에 적합한지 알아봅니다.
author: CESARDELATORRE
ms.author: cesardl
ms.date: 03/01/2020
ms.openlocfilehash: a8ad946b03f97272cb8685620858af6b21a372dc
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "81433351"
---
# <a name="choose-the-right-azure-hosting-option"></a>올바른 Azure 호스팅 옵션 선택

이 문서에서는 기존 .NET Framework 응용 프로그램을 온-프레미스에서 Azure로 마이그레이션할 때 Azure에서 수행할 여러 선택 사항 간의 고려 사항과 비교를 제공합니다.

기존.NET 애플리케이션을 Azure로 마이그레이션할 때 고려해야 할 기본 영역은 다음과 같습니다.

1. 컴퓨팅 선택 항목
1. 데이터베이스 선택 항목
1. 네트워킹 및 보안 고려 사항
1. 인증 및 권한 부여 고려 사항

## <a name="compute-choices"></a>컴퓨팅 선택 항목

기존 .NET Framework 애플리케이션을 Azure로 마이그레이션하는 경우 여러 가지 선택 사항이 있습니다. 그러나 .NET Framework는 Windows에 따라 다르기 때문에 다음 선택 사항은 Windows 기반 컴퓨팅 서비스로 제한됩니다.

다음 표는 기존 .NET 애플리케이션에 적합한 컴퓨팅 마이그레이션 경로를 선택하는 데 도움이 되는 몇 가지 비교 및 권장 사항을 보여줍니다.

|                 | Azure VM | Azure App Service | Windows 컨테이너 |
|-----------------|-----------|-------------------|--------------------|
|사용 시기      |<ul><li>애플리케이션은 서버 및 로컬 .msi 설치에 크게 의존합니다.</li><li>가장 쉬운 애플리케이션 마이그레이션 경로가 필요합니다.</li></ul>|앱은 서버에 의존하지 않으며, 데이터베이스 서버에 액세스하는 순수한 ASP.NET 웹앱(MVC, WebForm) 또는 N 계층 앱(Web API, WCf)입니다. |<ul><li>애플리케이션은 원본 서버에 종속되지만 이러한 종속성이 Docker Windows 이미지에도 포함될 수 있습니다.</li><li>[클라우드 DevOps-준비되도록](../../architecture/modernize-with-azure-containers/modernize-existing-apps-to-cloud-optimized/reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md) 응용 프로그램을 현대화하고 싶습니다.</li></ul>|
|장점 및 혜택  |<ul><li>가장 쉬운 마이그레이션 경로</li><li>친숙한 환경. 배포 환경은 VM이므로 온-프레미스 서버와 유사합니다.</li></ul> |지속적인 PaaS 유지 관리, Azure에서 앱을 관리하고 확장하는 가장 간단한 방법입니다. |<ul><li>미래를 위해 준비된 클라우드 DevOps-앱의 컨테이너에 포함된 종속성이 있는 클라우드 DevOps-Ready.</li><li>.NET /C# 코드를 리팩터링할 필요가 거의 없습니다.</li></ul> |
|단점             |IaaS. 유지 관리 비용이 많이 듭니다. 네트워킹, 로드 밸러너, 스케일 아웃, IIS 관리 등과 같은 VM 인프라를 관리해야 합니다. |<ul><li>모든 앱이 [지원](https://appmigration.microsoft.com/assessment)되지 않음</li><li>일부 앱은 리팩터링되고 약간 다시 설계되어야 할 수 있으므로 Azure 앱 서비스를 지원합니다.</li></ul> |<ul><li>Docker의 기술 학습 곡선</li><li>일부 코드 및 앱 구성 설정 변경</li></ul>|
|요구 사항 |온-프레미스용 앱과 동일한 요구 사항을 가진 Windows Server VM | [준비 검사에](https://github.com/Azure/App-Service-Migration-Assistant/wiki/Readiness-Checks)지정된 Azure 앱 서비스 요구 사항입니다. |<ul><li>[도커 엔진 - Windows 서버 2019용 엔터프라이즈](https://azuremarketplace.microsoft.com/marketplace/apps/cloud-infrastructure-services.docker-windows-2019)<br />또는</li><li>[Azure Container Service(AKS)](https://azure.microsoft.com/services/container-service/) (즉 Kubernetes orchestrator)<br />또는<li>[Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) 오케스트레이터</li></ul> |
|마이그레이션하는 방법 |[Azure Virtual Machines로 마이그레이션](vm.md) 참조 | [Azure App Service 마이그레이션](app-service.md) 참조 | Azure 및 [Windows 컨테이너 전자북을 사용한 기존 .NET 앱 현대화에](https://aka.ms/liftandshiftwithcontainersebook) 설명된 고려 사항, 시나리오 및 연습에 따라 |

다음 순서도 다이어그램은 기존 .NET Framework 응용 프로그램에 대한 Azure로의 마이그레이션을 계획할 때 의사 결정 트리를 보여 줍니다. 실행 가능한 경우 먼저 옵션 A를 시도하지만 옵션 B는 수행하는 가장 쉬운 경로입니다.

![호스팅 의사 결정 트리를 보여주는 순서도](../media/migration/choose/decision-tree.png)

## <a name="database-choices"></a>데이터베이스 선택 항목

관계형 데이터베이스를 Azure로 마이그레이션하는 경우 여러 가지 선택 항목이 있습니다. [Azure로 SQL Server 데이터베이스 마이그레이션](sql.md)을 참조하여 기존.NET 애플리케이션에 적합한 데이터베이스 마이그레이션 경로를 선택합니다.

## <a name="networking-and-security-considerations"></a>네트워킹 및 보안 고려 사항

Microsoft Azure와 같은 퍼블릭 클라우드에 애플리케이션을 배포하는 경우 [Azure와 온-프레미스 사이의 DMZ](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid) 또는 [Azure와 인터넷 사이의 DMZ](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz)와 같은 [네트워크 DMZ를 생성하여](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/) 특정 네트워크를 격리하고 보호할 수 있습니다. DMZ는 [Azure Virtual Network](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview)로 구현할 수 있습니다.

Azure Virtual Network를 사용하여 다음을 수행할 수 있습니다.

- 제어하는 하이브리드 인프라 구축
- 자체 IP 주소 및 DNS 서버 가져오기
- IPSec VPN 또는 ExpressRoute로 연결 보호
- 서브넷 간 트래픽에 대한 세부적인 제어 확보
- 가상 어플라이언스가 포함된 고급 네트워크 토폴로지 만들기
- 애플리케이션을 위한 격리되고 매우 안전한 환경 확보

자체 가상 네트워크 구축을 시작하려면 [Azure Virtual Network 설명서](https://docs.microsoft.com/azure/virtual-network/)를 참조하세요.

## <a name="authentication-and-authorization-considerations-when-migrating-to-azure"></a>Azure로 마이그레이션할 때 인증 및 권한 부여 고려 사항

클라우드로 이동하는 조직의 가장 큰 관심사는 보안입니다. 대부분의 기업은 보안 모델 설계 및 개발에 상당한 시간, 돈 및 엔지니어링을 투자했으며 ID 저장소 및 단일 사인온 솔루션과 같은 기존 투자를 활용할 수 있어야 합니다.

온-프레미스를 실행하는 많은 기존 엔터프라이즈 B2E .NET 애플리케이션은 인증 및 ID 관리를 위해 Active Directory를 사용합니다. Azure AD Connect는 온-프레미스 디렉터리와 Azure Active Directory를 통합하도록 해줍니다. 시작하려면 [Azure Active Directory와 온-프레미스 디렉터리 통합](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조하세요.

Azure Active Directory에 관련된 추가 계획은 [하이브리드 ID 솔루션에 대한 ID 요구 사항](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-business-needs)을 참조하세요.

다른 인증 프로토콜 선택 사항은 소비자 관련 애플리케이션에서 일반적인 [OAuth ](https://en.wikipedia.org/wiki/OAuth) 및 [OpenID](https://en.wikipedia.org/wiki/OpenID)입니다. OAuth를 사용하여 IdentityServer4로 래핑된 ASP.NET Identity SQL 데이터베이스와 같은 자율적인 ID 데이터베이스를 사용할 때는 일반적으로 온-프레미스 데이터베이스 또는 디렉토리에 대한 연결이 필요하지 않습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [ASP.NET 웹 응용 프로그램을 Azure 앱 서비스로 마이그레이션](app-service.md)
