---
title: 연습 및 기술 시작 개요
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 연습 및 기술 시작 개요
ms.date: 12/21/2020
ms.openlocfilehash: 6bfa25e3eeeecf5a936f378df3ae548d6fa37a30
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025279"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>연습 및 기술 시작 개요

이 전자책의 크기를 제한하기 위해 추가 기술 문서와 전체 연습은 GitHub 리포지토리에서 제공됩니다. 이 장에서 설명하는 온라인 연습 시리즈에서는 Windows 컨테이너 기반 다중 환경의 단계별 설정과 Azure로의 배포에 대해 설명합니다.

다음 섹션에서는 각 연습에 대한 설명, 목표 및 상위 수준 비전에 대해 설명하고 관련 작업에 대한 다이어그램을 제공합니다. 연습 자체는 *eShopModernizing* apps GitHub repo wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki>)에서 다운로드할 수 있습니다.

## <a name="technical-walkthrough-list"></a>기술 연습 목록

다음 시작 연습에서는 컨테이너를 사용하여 리프트 앤 시프트하고 Azure에서 여러 배포 옵션을 사용하여 이동할 수 있는 샘플 앱에 대한 일관적이고 포괄적인 기술 지침을 제공합니다.

다음 각 연습은 GitHub(<https://github.com/dotnet-architecture/eShopModernizing>)에서 다운로드할 수 있는 새로운 샘플 eShopLegacy 및 eShopModernizing 앱을 사용합니다.

- **eShop 레거시 앱 둘러보기(현대화할 기준 앱)**

- **Windows 컨테이너를 사용하여 기존 ASP.NET 웹앱(WebForms & MVC) 컨테이너화**

- **Windows 컨테이너를 사용하여 기존 WCF 서비스(N 계층 앱) 컨테이너화**

- **Azure VM에 Windows 컨테이너 기반 앱 배포**

- **Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱 배포**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>연습 1: eShop 레거시 앱 둘러보기

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.

[eShopModernizing wiki walkthroughs](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>개요

이 연습에서는 세 가지 샘플 레거시 애플리케이션의 초기 구현을 탐색할 수 있습니다. 처음 두 샘플 웹앱은 모놀리식 아키텍처이며 클래식 ASP.NET을 사용하여 만들었습니다. 첫 번째 애플리케이션은 ASP.NET 4.x MVC를 기반으로 하고, 두 번째 애플리케이션은 ASP.NET 4.x Web Forms를 기반으로 합니다.
세 번째 애플리케이션은 클라이언트 WinForms 앱 및 서버 쪽 [WCF(Windows Communication Foundation)](../../framework/wcf/whats-wcf.md) 서비스로 구성된 3 계층 앱입니다.

이들 애플리케이션은 모두 [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing)에서 다운로드할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 주요 목표는 단순히 이러한 앱과 해당 코드 및 구성을 익히는 것입니다. 테스트를 위해 SQL 데이터베이스를 사용하지 않고 모의 데이터를 생성하고 사용하도록 앱을 구성할 수 있습니다. 이 선택적 구성은 분리된 방식으로 종속성 주입을 기반으로 합니다.

### <a name="scenario-1-aspnet-web-apps"></a>시나리오 1: ASP.NET 웹앱

아래 그림에서는 원래 레거시 ASP.NET 웹 애플리케이션의 단순한 시나리오를 보여줍니다.

![원래 레거시 ASP.NET 웹 애플리케이션의 단순한 아키텍처 시나리오](./media/image5-1.png)

비즈니스 도메인 관점에서 두 앱은 모두 동일한 카탈로그 관리 기능을 제공합니다. eShop 엔터프라이즈 팀의 멤버가 이 앱을 사용하여 제품 카탈로그를 보고 편집합니다.

다음 그림은 초기 앱 스크린샷입니다.

![ASP.NET MVC 및 ASP.NET Web Forms 애플리케이션(기존/레거시 기술)](./media/image5-2.png)

ASP.NET 4.x 이하 버전의 종속성(MVC 또는 Web Forms)은 ASP.NET Core MVC를 사용하여 코드를 완전히 다시 작성하지 않는 한 해당 애플리케이션이 .NET Core에서 실행되지 않음을 의미합니다.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>시나리오 2: WCF 서비스 및 WinForms 클라이언트 앱(3 계층 앱)

아래 그림에서는 원래 3 계층 레거시 애플리케이션의 단순한 시나리오를 보여줍니다.

![WCF 서비스 및 WinForms 클라이언트 앱을 사용하는 원래 레거시 3 계층 앱의 단순한 아키텍처 시나리오](./media/image5-1.5.png)

### <a name="benefits"></a>이점

이 연습의 이점은 간단합니다. 코드 및 초기 앱에 익숙해지는 것입니다.

### <a name="next-steps"></a>다음 단계

다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.

- [기준 ASP.NET MVC 및 Web Forms “레거시” 앱 둘러보기](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [기준 WCF 서비스 및 WinForms(3계층) “레거시” 앱](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>연습 2: Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 컨테이너화

### <a name="overview"></a>개요

Windows 컨테이너를 사용하여 MVC, Web Forms 또는 WCF를 기반으로 하는 애플리케이션과 같은 기존 .NET 애플리케이션의 프로덕션, 개발 및 테스트 환경 배포를 개선합니다.

### <a name="goals"></a>목표

이 연습의 목표는 기존 .NET Framework 애플리케이션을 컨테이너화하기 위한 몇 가지 옵션을 보여 주는 것입니다. 다음과 같은 작업을 수행할 수 있습니다.

- [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)(Visual Studio 2017 이상 버전)를 사용하여 애플리케이션을 컨테이너화합니다.

- 수동으로 [Dockerfile](https://docs.docker.com/engine/reference/builder/)을 추가한 후 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)를 사용하여 애플리케이션을 컨테이너화합니다.

- [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구(Docker의 오픈 소스 도구)를 사용하여 애플리케이션을 컨테이너화합니다.

이 연습에서는 Visual Studio 2017 Tools for Docker 접근 방식에 초점을 맞추지만, 다른 두 접근 방식은 Dockerfile 사용과 관련해서는 다른 두 방법과 매우 유사합니다.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>시나리오 1: 컨테이너화된 ASP.NET 웹앱

아래 그림에서는 컨테이너화된 eShop 레거시 웹앱에 대한 시나리오를 보여줍니다.

![개발 환경에서 컨테이너화된 ASP.NET 애플리케이션의 간소화된 아키텍처를 보여 주는 다이어그램](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>시나리오 2: 컨테이너화된 WCF 서비스

아래 그림에서는 컨테이너화된 WCF 서비스를 사용하는 3 계층 앱의 시나리오를 보여줍니다.

![개발 환경에서 컨테이너화된 WCF 서비스의 간소화된 아키텍처를 보여 주는 다이어그램](./media/image5-3.5.png)

### <a name="benefits"></a>이점

컨테이너에서 모놀리식 애플리케이션을 실행하면 이점이 있습니다. 먼저, 애플리케이션의 이미지를 만들 수 있습니다. 이 시점부터 모든 배포가 동일한 환경에서 실행됩니다. 모든 컨테이너가 동일한 OS 버전을 사용하며, 동일한 버전의 종속성이 설치되고, 동일한 .NET 프레임워크 버전을 사용하며, 동일한 프로세스를 사용하여 빌드됩니다. 기본적으로 Docker 이미지를 사용하여 애플리케이션의 종속성을 제어합니다. 컨테이너를 배포할 때 종속성이 애플리케이션과 함께 이동합니다.

이밖에 개발자는 Windows 컨테이너에서 제공하는 일관된 환경에서 애플리케이션을 실행할 수 있다는 이점이 있습니다. 특정 버전에서만 나타나는 문제가 준비 또는 프로덕션 환경에서 표출되는 대신 즉시 발견될 수 있습니다. 애플리케이션이 컨테이너에서 실행되는 경우 개발 팀의 멤버가 사용하는 개발 환경 간 차이의 문제가 완화됩니다.

컨테이너화된 애플리케이션은 보다 평탄한 수평 확장 곡선을 갖습니다. 컨테이너화된 앱을 사용하면 일반적인 컴퓨터별 애플리케이션 배포와 비교할 때 VM 또는 물리적 컴퓨터에서 (컨테이너를 기반으로) 더 많은 애플리케이션 및 서비스 인스턴스를 사용할 수 있습니다. 이 접근법을 사용하면 특히 Kubernetes와 같은 오케스트레이터를 사용할 경우, 밀도가 더욱 높아지고 필요한 리소스 수가 줄어듭니다.

이상적인 상황에서는 컨테이너화로 인해 애플리케이션 코드(C\#)를 변경할 필요가 없습니다. 대부분의 시나리오에서는 Docker 배포 메타데이터 파일(Dockerfile 및 Docker Compose 파일)만 필요합니다.

### <a name="next-steps"></a>다음 단계

다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.

- [Windows 컨테이너 및 Docker를 사용하여 .NET Framework 웹앱을 컨테이너화하는 방법](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [WCF 서비스에 Docker 지원 추가](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>연습 3: Azure VM에 Windows 컨테이너 기반 앱 배포

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다. <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>개요

Azure에서 Windows Server 2016 VM(가상 머신)의 Docker 호스트에 배포하면 개발/테스트/준비 환경을 신속하게 설정할 수 있습니다. 또한 테스터 또는 비즈니스 사용자가 앱의 유효성을 검사할 수 있는 공통 위치를 제공합니다. VM은 유효한 IaaS(Infrastructure as a Service) 프로덕션 환경으로도 사용할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows Server 2016 이상 버전을 기반으로 하는 Azure VM에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대안을 보여 주는 것입니다.

### <a name="scenarios"></a>시나리오

이 연습에서는 몇 가지 시나리오에 대해 설명합니다.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>시나리오 A: Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포

![Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포](./media/image5-4.png)

**그림 5-4.** Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>시나리오 B: Docker 레지스트리를 통해 Azure VM에 배포

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

**그림 5-5.** Docker 레지스트리를 통해 Azure VM에 배포

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>시나리오 C: Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포

![Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

**그림 5-6.** Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포

### <a name="azure-vms-for-windows-containers"></a>Windows 컨테이너용 Azure VM

Windows 컨테이너용 Azure VM은 Windows Server 2016, Windows 10 이상 버전(모두 Docker 엔진 설정 포함)을 기반으로 하는 VM입니다. 대부분의 경우 Windows Server 2016이 Azure VN에 사용됩니다.

현재 Azure는 **컨테이너가 포함된 Windows Server 2016** 이라는 VM을 제공합니다. 이 VM을 사용하여 Windows Server Core 또는 Windows Nano Server를 통해 새로운 Windows Server 컨테이너 기능을 사용해 볼 수 있습니다. 컨테이너 OS 이미지를 설치하면 VM을 Docker에 사용할 준비가 된 것입니다.

### <a name="benefits"></a>이점

Windows 컨테이너를 온-프레미스 Windows Server 2016 VM에 배포할 수 있지만, Azure에 배포할 경우 즉시 사용 가능한 Windows Server 컨테이너 VM으로 보다 간편하게 시작할 수 있습니다. 또한 테스터가 액세스할 수 있는 공통의 온라인 위치와 Azure 가상 머신 확장 집합을 통한 자동 확장성도 얻을 수 있습니다.

### <a name="next-steps"></a>다음 단계

다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>연습 4: ACI(Azure Container Instances)에 Windows 컨테이너 기반 앱 배포

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.

[ACI(Azure Container Instances)에 앱 배포](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>개요

[ACI(Azure Container Instances)](/azure/container-instances/)는 단일 인스턴스의 컨테이너를 배포할 수 있는 컨테이너 개발/테스트/준비 환경을 확보하는 가장 빠른 방법입니다.

### <a name="goals"></a>목표

이 연습에서는 ACI(Azure Container Instances)에 Windows 컨테이너를 배포할 경우의 주요 시나리오와 ACI에 eShopModernizing 앱을 배포할 수 있는 방법을 보여 줍니다.

### <a name="scenarios"></a>시나리오

ACI에 eShopModernizing 앱을 배포할 때 앱(MVC 앱, WebForms 앱 또는 WCF 서비스) 중 하나 또는 모두를 배포하는 것과 같은 변형이 있을 수 있습니다. 다음 시나리오에서는 ASP.NET MVC 앱과 SQL Server 컨테이너를 ACI(Azure Container Instances)에 컨테이너로 배포합니다.

![개발 환경에서 ACI에 배포](./media/image5-3.5.6.png)

### <a name="benefits"></a>이점

Azure Container Instances를 사용하면 가상 머신을 프로비전하거나 상위 수준 서비스를 도입하지 않고도 Azure에서 Docker 컨테이너를 쉽게 만들고 관리할 수 있습니다. ACI를 사용하면 Azure에서 Windows 컨테이너를 직접 배포하고 몇 초 내에 FQDN(정규화된 도메인 이름)을 사용하여 인터넷에 노출할 수 있습니다(Docker Hub 또는 Azure Container Registry와 같은 Docker 레지스트리에서 준비된 Windows 컨테이너 이미지가 있는 경우).

### <a name="considerations"></a>고려 사항

전체 .NET Framework/ASP.NET 또는 SQL Server를 포함하는 Windows 컨테이너를 ACI(Azure Container Instances)에 배포하는 것은 일반적인 Docker 호스트(예: Windows 컨테이너가 포함된 Server 2016)에 배포하는 것만큼 빠르지 않습니다. 매번 Docker 이미지를 다운로드해야 하고(Docker 레지스트리에서 가져옴) SQL 컨테이너 이미지(15.1GB) 및 ASP.NET 컨테이너 이미지(13.9GB)의 크기가 상당하기 때문입니다. 하지만 프로덕션 배포를 위한 훌륭한 선택인 Azure Kubernetes(AKS)와 같은 오케스트레이터는 말할 것도 없이 자체 Docker 호스트(Azure의 Windows 컨테이너가 포함된 영구 온라인 Windows Server 2016)를 보유하는 것보다 훨씬 저렴합니다.

결론적으로 Azure Container Instances 사용은 개발/테스트 시나리오 및 CI/CD 파이프라인에 매우 매력적인 옵션입니다.

### <a name="next-steps"></a>다음 단계

다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>연습 5: Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱 배포

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>개요

Windows 컨테이너를 기반으로 하는 애플리케이션은 신속하게 플랫폼을 활용하여 IaaS VM에서 한층 더 개선되어야 합니다. 이 접근법은 뛰어난 스케일링 성능과 향상된 자동 스케일링 성능을 손쉽게 구현하는 데 필요하고 자동화된 배포 및 버전 관리를 대폭 개선하는 데 필요합니다. 이러한 목표는 [Azure Container Services](https://azure.microsoft.com/services/container-service/)에서 제공하는 오케스트레이터 [Kubernetes](https://kubernetes.io/)를 사용하여 달성할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows 컨테이너 기반 애플리케이션을 Azure Container Service에서 Kubernetes(*K8s* 라고도 함)에 배포하는 방법을 배우는 것입니다. Kubernetes를 처음부터 배포하는 과정은 다음 두 단계로 진행됩니다.

1. Kubernetes 클러스터를 Azure Container Service에 배포합니다.

2. 애플리케이션 및 관련 리소스를 Kubernetes 클러스터에 배포합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>시나리오 A: 개발 환경에서 Kubernetes 클러스터에 직접 배포

![개발 환경에서 Kubernetes 클러스터에 직접 배포](./media/image5-7.png)

**그림 5-7.** 개발 환경에서 Kubernetes 클러스터에 직접 배포

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>시나리오 B: Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포

![Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포](./media/image5-8.png)

**그림 5-8.** Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포

### <a name="benefits"></a>이점

Kubernetes의 클러스터에 배포하는 데는 많은 이점이 있습니다. 가장 큰 이점은 사용하려는 컨테이너 인스턴스 수에 따라(기존 노드의 내부 확장성) 또한 클러스터 내 노드 또는 VM 수에 따라(클러스터의 전역 확장성) 애플리케이션을 확장할 수 있는 프로덕션 준비 환경을 확보하는 것입니다.

Azure Container Service는 Azure용으로 특히 인기 있는 오픈 소스 도구 및 기술을 최적화합니다. 컨테이너와 애플리케이션 구성 모두에 이식성을 제공하는 개방형 솔루션을 얻을 수 있습니다. 사용자가 크기, 호스트 수, 오케스트레이터 도구를 선택하면 Container Service에서 다른 모든 작업을 처리합니다.

Kubernetes를 통해 개발자는 물리적 컴퓨터와 가상 머신에 대한 고려에서 다음과 같은 기능을 촉진하는 컨테이너 중심 인프라를 계획하는 과정으로 진행할 수 있습니다.

- 다중 컨테이너를 기반으로 하는 애플리케이션

- 컨테이너 인스턴스 복제 및 수평 자동 크기 조정

- 이름 지정 및 검색(예: 내부 DNS)

- 부하 분산

- 롤링 업데이트

- 비밀 배포

- 애플리케이션 상태 검사

### <a name="next-steps"></a>다음 단계

이 콘텐츠를 GitHub wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>)에서 보다 심층적으로 살펴봅니다.

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>연습 6: 컨테이너용 Azure App Service에 Windows 컨테이너 기반 앱 배포

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>개요

Windows 컨테이너를 사용하는 간단한 컨테이너화된 애플리케이션을 컨테이너용 Azure App Service에 쉽게 배포할 수 있습니다. 이 접근법은 대부분의 Windows 컨테이너 기반 애플리케이션에 권장되는 방법입니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows 컨테이너 기반 애플리케이션을 레지스트리(Docker Hub 또는 Azure Container Registry)에서 컨테이너용 Azure App Service에 배포하는 방법을 배우는 것입니다.

### <a name="scenario"></a>시나리오

![컨테이너용 Azure App Service에 Windows 컨테이너 기반 앱 배포](./media/image5-11.png)

### <a name="benefits"></a>이점

컨테이너용 Azure App Service에 배포하면 Azure App Service의 PaaS 이점과 쌍을 이루는 컨테이너의 이점을 얻을 수 있습니다. App Service는 수직 및 수평으로 쉽게 확장할 수 있으며 자동 크기 조정을 구성하여 변화하는 수요를 충족할 수 있습니다. 가동 중지 시간 없이 업데이트를 수행할 수 있으며, 레지스트리에서 지속적인 배포를 구성하는 것도 손쉽습니다.

### <a name="next-steps"></a>다음 단계

이 콘텐츠를 GitHub wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>)에서 보다 심층적으로 살펴봅니다.

> [!div class="step-by-step"]
> [이전](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [다음](conclusions.md) <!-- Next Chapter -->
