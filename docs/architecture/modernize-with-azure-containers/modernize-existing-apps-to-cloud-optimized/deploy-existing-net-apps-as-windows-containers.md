---
title: 기존 .NET 앱을 Windows 컨테이너로 배포
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 기존 .NET 앱을 Windows 컨테이너로 배포
ms.date: 04/29/2018
ms.openlocfilehash: 28568ca363bfc8100f78b100f8a7f0242c4f04c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "73089554"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>기존 .NET 앱을 Windows 컨테이너로 배포

Windows 컨테이너를 기반으로 하는 배포는 클라우드 최적화 애플리케이션 및 클라우드 네이티브 애플리케이션에 적용됩니다.

그러나 이 가이드, 특히 다음 섹션에서는 애플리케이션을 다시 설계하지 않아도 되는 *클라우드 최적화* 애플리케이션에서 Windows 컨테이너 사용을 중점적으로 다룹니다.

## <a name="what-are-containers-linux-or-windows"></a>컨테이너란? (Linux 또는 Windows)

컨테이너는 애플리케이션을 자체 격리된 패키지로 래핑하는 방법입니다. 컨테이너에서는 애플리케이션이 컨테이너 외부에 존재하는 애플리케이션 또는 프로세스의 영향을 받지 않습니다. 애플리케이션이 프로세스로서 성공적으로 실행하기 위해 필요한 모든 것은 컨테이너 내부에 있습니다. 컨테이너가 어디로 이동하든 애플리케이션의 요구 사항이 항상 직접 종속성을 기준으로 충족됩니다. 실행해야 하는 모든 항목(라이브러리 종속성, 런타임 등)이 함께 번들되어 있기 때문입니다.

컨테이너의 주요 특징은 컨테이너 자체가 필요한 모든 종속성과 함께 제공되므로 다른 배포에서 환경을 동일하게 만든다는 것입니다. 즉, 컴퓨터에서 애플리케이션을 디버그한 다음 다른 컴퓨터에 배포하면 동일한 환경이 보장됩니다.

컨테이너는 컨테이너 이미지의 인스턴스입니다. 컨테이너 이미지는 (스냅샷과 같이) 앱 또는 서비스를 패키지로 만든 다음 안정적이고 재현 가능한 방식으로 배포하는 방법입니다. Docker는 기술일 뿐만 아니라 철학이면서 프로세스이기도 합니다.

컨테이너는 나날이 보편화되어 업계 전체에서 "배포 단위"가 되고 있습니다.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>컨테이너의 이점(Linux 또는 Windows의 Docker 엔진)

컨테이너(가벼운 빌딩 블록으로 정의할 수도 있음)를 사용하여 애플리케이션을 빌드하면 모든 인프라에서 애플리케이션을 빌드, 전달 및 실행하는 민첩성을 크게 향상시킵니다.

컨테이너를 사용하면 Microsoft 개발자 도구, 운영 체제 및 클라우드 전반의 Docker 통합 덕분에 코드를 거의 또는 전혀 변경하지 않고 앱을 개발 환경에서 프로덕션 환경으로 보낼 수 있습니다.

일반 VM에 배포하는 경우 ASP.NET 앱을 VM에 배포하는 방법은 이미 마련되어 있을 것입니다. 그러나 이러한 방법은 아마도 Puppet과 같은 배포 도구 또는 유사한 도구를 사용하여 여러 수동 단계 또는 복잡한 자동화된 프로세스를 거쳐야 합니다. 구성 항목 수정, 서버 간 애플리케이션 콘텐츠 복사, .msi 설정에 따른 대화형 설치 프로그램 실행, 후속 테스트와 같은 작업을 수행해야 할 것입니다. 이러한 모든 단계는 배포에 시간 및 위험을 추가합니다. 대상 환경에 종속성이 없을 때마다 오류가 발생합니다.

Windows 컨테이너에서는 애플리케이션 패키징 프로세스가 완전히 자동화되어 있습니다. Windows 컨테이너는 컨테이너 배포에 대한 자동 업데이트 및 롤백을 제공하는 Docker 플랫폼을 기반으로 합니다. Docker 엔진을 사용하여 얻을 수 있는 주요 개선 사항은 애플리케이션 스냅샷과 마찬가지로 모든 종속성을 포함하는 이미지를 만드는 것입니다. 이미지는 Docker 이미지(이 경우 Windows 컨테이너 이미지)입니다. 이미지는 소스 코드로 다시 이동하지 않고 컨테이너에서 ASP.NET 앱을 실행합니다. 컨테이너 스냅샷은 배포 단위가 됩니다.

많은 조직에서 다음과 같은 이유로 기존 모놀리식 애플리케이션을 컨테이너화하고 있습니다.

- **향상된 배포를 통한 릴리스 민첩성**. 컨테이너는 개발과 운영 간에 일관된 배포 계약을 제공합니다. 컨테이너를 사용할 경우 개발자가 "내 머신에서 작동하는데 왜 프로덕션 환경에서는 안 되지?"라고 말하지는 않습니다. "컨테이너로 실행되니까 프로덕션 환경에서 실행될 것입니다."라고 말할 수 있을 것입니다. 모든 종속성을 포함하는 패키지된 애플리케이션은 지원되는 모든 컨테이너 기반 환경에서 실행할 수 있습니다. 모든 배포 대상(개발, QA, 준비, 프로덕션)에서 의도한 방식으로 실행됩니다. 컨테이너는 한 단계에서 다음 단계로 이동할 때 대부분의 마찰을 제거하여 배포를 크게 개선하고 더 빠르게 제공할 수 있습니다.

- **비용 절감**. 컨테이너는 기존 하드웨어를 통합 및 제거하거나 하드웨어 단위당 더 높은 밀도에서 애플리케이션을 실행하여 비용을 절감힙니다.

- **이식성**. 컨테이너는 모듈형이며 이식 가능합니다. Docker 컨테이너는 모든 서버 운영 체제(Linux 및 Windows), 모든 주요 공용 클라우드(Microsoft Azure, Amazon AWS, Google, IBM), 그리고 온-프레미스 및 프라이빗 또는 하이브리드 클라우드 환경에서 지원됩니다.

- **제어**. 컨테이너는 컨테이너 수준에서 제어되는 유연한 보안 환경을 제공합니다. 컨테이너는 컨테이너에 실행 제약 조건 정책을 설정하여 보안을 유지하고 격리하고 제한할 수 있습니다. Windows 컨테이너에 대한 섹션에서 상술했듯이, Windows Server 2016 및 Hyper-V 컨테이너는 추가적인 엔터프라이즈 지원 옵션을 제공합니다.

애플리케이션을 개발하고 유지 관리하기 위해 컨테이너를 사용하는 경우 민첩성, 이식성 및 제어가 크게 향상되어 결과적으로 대폭의 비용 절감으로 이어집니다.

## <a name="what-is-docker"></a>Docker란?

[Docker](https://www.docker.com/)는 클라우드 또는 온-프레미스로 실행될 수 있는 이식 가능하고 스스로 문제를 해결할 수 있는 컨테이너로서 애플리케이션 배포를 자동화하는 [오픈 소스 프로젝트](https://github.com/docker/docker)입니다. Docker는 이 기술을 장려하고 발전시키는 [회사](https://www.docker.com/)이기도 합니다. 이 회사는 Microsoft를 비롯한 클라우드, Linux 및 Windows 공급 업체와 공동으로 작업합니다.

![Docker가 하이브리드 클라우드에서 컨테이너를 배포하는 방법을 보여 주는 다이어그램](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**그림 4-6.** Docker는 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포

가상 머신에 익숙한 사람이라면 컨테이너가 매우 비슷하게 보일 수 있습니다. 컨테이너는 운영 체제를 실행하며, 파일 시스템을 보유하고, 물리적 또는 가상 컴퓨터 시스템과 마찬가지로 네트워크에서 액세스할 수 있습니다. 하지만 컨테이너의 바탕이 되는 기술 및 개념은 가상 머신과는 상당한 차이가 있습니다. 개발자 관점에서 볼 때 컨테이너는 단일 프로세스처럼 취급해야 합니다. 실제로 컨테이너마다 한 프로세스에 대한 단일 진입점이 있습니다.

Docker 컨테이너(간단히 *컨테이너*)는 Linux 및 Windows에서 기본적으로 실행할 수 있습니다. 일반 컨테이너를 실행하는 경우 Windows 컨테이너는 Windows 호스트(호스트 서버 또는 VM)에서만 실행할 수 있고 Linux 컨테이너는 Linux 호스트에서만 실행할 수 있습니다. 그러나 최신 버전의 Windows Server 및 Hyper-V 컨테이너에서는 Linux 컨테이너가 현재 Windows Server 컨테이너에서만 제공되는 Hyper-V 격리 기술을 사용하여 Windows Server에서도 기본적으로실행될 수 있습니다.

가까운 장래에 Linux 및 Windows 컨테이너를 모두 포함하는 혼합 환경도 가능하고 보다 일반화될 것입니다.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>기존 .NET 애플리케이션에 대한 Windows 컨테이너의 이점

Windows 컨테이너를 사용하는 이점은 일반적으로 컨테이너에서 얻을 수 있는 그것과 기본적으로 동일합니다. Windows 컨테이너를 사용한다는 것은 민첩성, 이식성 및 제어를 크게 개선하는 것입니다.

기존 .NET 애플리케이션은 .NET Framework를 사용하여 만든 애플리케이션을 참조합니다. 예를 들어 기존 ASP.NET 웹 애플리케이션일 수 있습니다. 즉, Linux, Windows 및 MacOS에서 플랫폼 간에 실행되는 최신 버전인 .NET Core를 사용하지 않습니다.

.NET Framework의 주요 종속성은 Windows입니다. 또한 IIS, 그리고 기존 ASP.NET의 System.Web과 같은 보조 종속성도 있습니다.

.NET Framework 애플리케이션은 Windows에서 실행되어야 합니다. 그뿐입니다. 기존 .NET Framework 애플리케이션을 컨테이너화기 원하지만 .NET Core로 마이그레이션하는 데 투자할 여력 또는 의사가 없는 경우("제대로 작동한다면 마이그레이션하지 마세요"), 컨테이너에 대한 유일한 선택은 Windows 컨테이너를 사용하는 것입니다.

따라서 Windows 컨테이너의 주요 이점 중 하나는 컨테이너화를 통해 Windows에서 실행되는 기존 .NET Framework 애플리케이션을 현대화하는 방법을 제공한다는 것입니다. 궁극적으로 Windows 컨테이너는 컨테이너를 사용함으로써 추구하는 이점, 즉 민첩성, 이식성 및 향상된 제어를 선사합니다.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>.NET 기반 컨테이너에서 대상으로 지정할 OS 선택

Docker에서 지원하는 운영 체제의 다양함과 .NET Framework 및 .NET Core 간 차이를 고려해 보면 사용하는 프레임워크를 기반으로 특정 OS와 특정 버전을 목표로 해야 합니다.

Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다. 이러한 Windows 버전은 .NET Framework 또는 .NET Core 애플리케이션에 필요할 수 있는 다양한 특성(예: IIS 또는 Kestrel과 같은 자체 호스팅 웹 서버)을 제공합니다.

Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.

그림 4-7에서는 앱의 .NET Framework 버전에 따라 대상으로 지정할 수 있는 OS 버전을 보여줍니다.

![.NET Framework 버전을 기반으로 대상으로 지정할 OS를 보여 주는 다이어그램](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**그림 4-7.** .NET Framework 버전을 기반으로 대상으로 지정할 운영 체제

.NET Framework 애플리케이션을 기반으로 하는 기존 또는 레거시 애플리케이션의 마이그레이션 시나리오에서 기본 종속성은 Windows 및 IIS입니다. 유일한 옵션은 Windows Server Core 및 .NET Framework를 기반으로 Docker 이미지를 사용하는 것입니다.

.NET Framework 기반 Windows 컨테이너 이미지에 대한 다음 예제와 같이, Dockerfile 파일에 이미지 이름을 추가할 때 태그를 사용하여 운영 체제 및 버전을 선택할 수 있습니다.

> | **Tag** | **시스템 및 버전** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | Windows Server Core의 .NET Framework 4.x |
> | **microsoft/aspnet:4.x-windowsservercore** | Windows Server Core의 .NET Framework 4.x(추가 ASP.NET 사용자 지정 포함) |

.NET Core(Linux 및 Windows 플랫폼 간)의 경우 태그는 다음과 같습니다.

> | **Tag** | **시스템 및 버전**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | Linux의 .NET Core 2.0 런타임 전용 |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | Windows Nano Server의 .NET Core 2.0 런타임 전용 |

### <a name="multi-arch-images"></a>다중 아키텍처 이미지

2017년 중반부터 [다중 아키텍처](https://github.com/moby/moby/issues/15866) 이미지라는 Docker의 새 기능도 사용할 수 있습니다. .NET Core Docker 이미지는 다중 아키텍처 태그를 사용할 수 있습니다. Dockerfile 파일은 더 이상 대상 운영 체제를 정의할 필요가 없습니다. 다중 아키텍처 기능을 사용하면 여러 컴퓨터 구성에서 단일 태그를 사용할 수 있습니다. 예를 들어 다중 아키텍처 기능을 사용하는 경우 하나의 공통 태그를 사용할 수 있습니다. **microsoft/dotnet:2.0.0-runtime**. Linux 컨테이너 환경에서 이 태그를 가져올 경우 Debian 기반 이미지를 얻습니다. Windows 컨테이너 환경에서 이 태그를 가져올 경우 Nano Server 기반 이미지를 얻습니다.

.NET Framework 이미지의 경우 기존 .NET Framework는 Windows만 지원하기 때문에 다중 아키텍처 기능을 사용할 수 없습니다.

## <a name="windows-container-types"></a>Windows 컨테이너 형식

Linux 컨테이너와 마찬가지로, Windows Server 컨테이너는 Docker 엔진을 사용하여 관리됩니다. Linux 컨테이너와 달리 Windows 컨테이너에는 두 가지 컨테이너 유형(즉 런타임) Windows Server 컨테이너 및 Hyper-V 격리가 포함됩니다.

**Windows Server 컨테이너** 프로세스 및 네임스페이스 격리 기술을 통해 애플리케이션 격리를 제공합니다. Windows Server 컨테이너는 컨테이너 호스트와 해당 호스트에서 실행 중인 모든 컨테이너와 커널을 공유합니다. 이러한 컨테이너는 악의적인 보안 경계를 제공하지 않으므로 신뢰할 수 없는 코드를 격리하는 데 사용하면 안 됩니다. 공유된 커널 공간 때문에 이러한 컨테이너에는 동일한 커널 버전 및 구성이 필요합니다.

**Hyper-V 격리**: 최적화된 VM에서 각 컨테이너를 실행하여 Windows Server 컨테이너에서 제공하는 격리를 확장합니다. 이 구성에서 컨테이너 호스트의 커널은 동일한 호스트의 다른 컨테이너와 공유되지 않습니다. 이러한 컨테이너는 악의적인 다중 테넌트 호스팅 때문에 디자인되었으며, VM의 보안 보증은 동일 합니다. 이러한 컨테이너는 호스트 또는 동일한 호스트의 다른 컨테이너와 커널을 공유하지 않기 때문에 서로 다른 버전 및 구성을 사용하여 커널을 실행할 수 있습니다(지원되는 버전). 예를 들어 Windows 10의 모든 Windows 컨테이너는 Hyper-V 격리를 사용하여 Windows Server 커널 버전 및 구성을 활용합니다.

Windows에서 컨테이너를 실행할 때 Hyper-V 격리를 사용할지 여부는 런타임 결정입니다. 처음에 Hyper-V 격리를 사용하여 컨테이너를 만들었다가 런타임에 Windows Server 컨테이너로 실행하도록 선택할 수 있습니다.

### <a name="additional-resources"></a>추가 자료

- **Windows 컨테이너 설명서**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Windows 컨테이너 기본 사항**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **인포그래픽: Microsoft 및 컨테이너**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Azure의 컨테이너 에코시스템

이전 섹션에서는 Docker 컨테이너의 이점을 알아보고 .NET 애플리케이션용 특정 컨테이너 이미지에 대해 자세히 설명했습니다. 애플리케이션을 개발 또는 컨테이너화하려면 이러한 일반 정보는 모두 기본 사항입니다.
그러나 프로덕션 배포 환경 또는 QA 및 개발/테스트 환경을 고려하여 Microsoft Azure는 개방적이고 광범위한 선택지, 즉 종합적인 클라우드 컨테이너 에코시스템을 제공합니다(아래 다이어그램 참조). 특정 애플리케이션의 요구 사항에 따라 Azure 제품을 선택해야 합니다.

![Azure의 컨테이너 에코시스템을 보여 주는 다이어그램](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**그림 4-7.5.** Azure의 컨테이너 에코시스템

Azure의 컨테이너 에코시스템에서 인프라로 간주되는 컨테이너를 지원하는 제품은 다음과 같습니다.

- **ACI(Azure Container Instances)**
- **Azure Virtual Machines**(컨테이너에서 지원)
- **Azure Virtual Machine Scale Sets**(컨테이너에서 지원)

이 세 제품 중에서 ACI는 기본 OS를 유지 관리할 필요가 없고, 업그레이드/패치를 수행할 필요가 없는 등 상당한 이점을 선사하지만, 이 책의 다른 섹션에서 곧 자세히 설명하듯이 ACI는 여전히 인프라 수준에서 배치됩니다.

PaaS(Platform as a Service) 수준에서 동시에 배치되는 컨테이너를 지원하는 Azure 제품은 다음과 같습니다.

- **Azure App Service**
- **Azure Kubernetes Service(AKS 및 ACS)**
- **Azure Batch**

Azure Container Registry는 Azure에서 호스트되는 뛰어난 확장성의 컨테이너 레지스트리로, 사용자 지정 컨테이너 이미지를 등록 및 배포할 때 이전의 모든 제품에서 사용할 수 있습니다.

또한 컨테이너에서 Azure SQL Database, Azure Redis cache, Azure Cosmos DB 등 다른 Azure 관리형 서비스를 사용할 수 있습니다. 이밖에 Azure Marketplace에는 Cloud Foundry 및 OpenShift와 같이 Azure 내에서 컨테이너를 사용할 수도 있는 타사 솔루션/플랫폼이 있습니다.

다음 섹션에서는 Windows 컨테이너를 대상으로 지정할 경우 이러한 Azure 제품 및 솔루션을 사용하는 시기에 대한 Microsoft 권장 사항을 살펴볼 수 있습니다.

>[!div class="step-by-step"]
>[이전](what-about-cloud-native-applications.md)
>[다음](when-not-to-deploy-to-windows-containers.md)
