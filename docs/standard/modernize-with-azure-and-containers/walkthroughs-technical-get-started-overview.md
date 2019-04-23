---
title: 기술 개요와 실습
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 기술 개요와 실습
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 2202e2f972951e4074ed1941f0a0cfe352ab4b85
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612955"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>기술 개요와 실습

이 전자책의 분량이 너무 방대해지는 것을 피하고자, 추가적인 기술 설명서와 실습의 전체 내용은 GitHub 리포지토리를 활용하도록 구성되어 있습니다. 이 장에서 설명하는 실습 온라인 시리즈에서는 Windows 컨테이너를 기반으로 하는 다양한 환경의 단계별 설치와 Azure 배포에 대해 설명합니다.

다음 섹션에서는 각 연습에 대해 해당 목표 및 고급 시각 및 관련 된 작업의 다이어그램을 제공을 설명 합니다. 자체 연습을 가져올 수 있습니다에 *eShopModernizing* apps GitHub 리포지토리 wiki에서 <https://github.com/dotnet-architecture/eShopModernizing/wiki>합니다.

## <a name="technical-walkthrough-list"></a>기술 연습 목록

다음 시작 연습에서는 리프트 앤 시프트 컨테이너를 사용 하 여 및 다음 Azure에서 여러 배포 옵션을 사용 하 여 이동 하는 샘플 앱에 대 한 일관적이 고 포괄적인 기술 지침을 제공 합니다.

다음 연습 중 각 앱을 사용 하 여 새 샘플 eShopLegacy 및 eShopModernizing에서 GitHub에서 사용할 수 있는 <https://github.com/dotnet-architecture/eShopModernizing>합니다.

- **EShop 레거시 앱 (기준 앱 현대화) 둘러보기**

- **Windows 컨테이너를 사용 하 여 기존 ASP.NET 웹 앱 (WebForms 및 MVC)를 컨테이너 화**

- **Windows 컨테이너를 사용 하 여 기존 WCF 서비스 (N 계층 앱)를 컨테이너 화**

- **Azure Vm에 Windows 컨테이너 기반 앱 배포**

- **Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱을 배포 합니다.**

- **Azure Service Fabric에 Windows 컨테이너 기반 앱을 배포 합니다.**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>연습 1: 레거시 앱 eShop 둘러보기

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.

[eShopModernizing wiki 연습](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>개요

이 연습에서는 세 개의 샘플 레거시 응용 프로그램의 초기 구현을 탐색할 수 있습니다. 처음 두 개의 샘플 웹 앱 모놀리식 아키텍처에 있고 클래식 ASP.NET을 사용 하 여 만든 합니다. 하나의 응용 프로그램은 ASP.NET을 기반 4.x MVC; 두 번째 응용 프로그램은 ASP.NET 4.x Web Forms를 기반으로 합니다.
세 번째 응용 프로그램이 클라이언트 WinForms 앱 및 서버 쪽에서 구성 된 3 계층 앱 [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) 서비스입니다.

이러한 모든 응용이 프로그램에서 사용할 수는 [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)합니다.

### <a name="goals"></a>목표

이 연습의 기본 목적은 이러한 앱 및 해당 코드와 구성에 친숙 해지기 하기만 하면 됩니다. 생성 하 고 모의 데이터를 사용 하 여 테스트 목적으로 SQL database를 사용 하지 않고 있는 앱을 구성할 수 있습니다. 이 선택적 구성은 분리 된 방식으로 종속성 주입을 기반으로 합니다.

### <a name="scenario-1-aspnet-web-apps"></a>시나리오 1: ASP.NET 웹 앱

아래 그림에는 원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 시나리오를 보여 줍니다.

![원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.png)

비즈니스 도메인 관점에서 두 앱 모두 동일한 카탈로그 관리 기능을 제공합니다. EShop 엔터프라이즈 팀의 멤버 보기 및 편집 제품 카탈로그를 앱을 사용 합니다.

다음 그림에는 초기 앱 스크린 샷을 보여 줍니다.

![ASP.NET MVC 및 ASP.NET Web Forms 응용 프로그램 (기존/레거시 기술)](./media/image5-2.png)

종속성 ASP.NET 4.x 또는 이전 버전 (또는 MVC Web Forms) 의미 이러한 응용 프로그램 코드는 ASP.NET Core MVC를 사용 하 여 완전히 다시 작성 하지 않는 한.NET Core에서 실행 되지 않습니다.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>시나리오 2: WCF 서비스 및 WinForms 클라이언트 앱 (3 계층 앱)

아래 그림에는 원래 3 계층 레거시 응용 프로그램의 간단한 시나리오를 보여 줍니다.

![WCF 서비스를 사용 하 여 원래 레거시 3 계층 응용 프로그램 및 WinForms 클라이언트 앱의 간단한 아키텍처 시나리오](./media/image5-1.5.png)

### <a name="benefits"></a>이점

이 연습의 혜택은 간단 합니다. 초기 앱 코드와 친숙 한 효과만 합니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기

- [둘러보기 기준을 설정한 ASP.NET MVC 및 Web Forms "레거시" 앱](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [기본 WCF 서비스 및 WinForms (3 계층) "레거시" 앱에 대 한 둘러보기](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>연습 2: Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램을 컨테이너 화

### <a name="overview"></a>개요

Windows 컨테이너를 사용 하 여 MVC, Web Forms, WCF, 프로덕션, 개발 및 테스트 환경에 기반 하는 것과 같은 기존.NET 응용 프로그램을 배포 기술 향상.

### <a name="goals"></a>목표

이 연습의 목적은 기존.NET Framework 응용 프로그램을 컨테이너 화 하기 위한 몇 가지 옵션을 표시할 하는 것입니다. 다음과 같은 작업을 수행할 수 있습니다.

- 사용 하 여 응용 프로그램을 컨테이너 화 [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 또는 이상 버전).

- 수동으로 추가 하 여 응용 프로그램을 컨테이너 화를 [Dockerfile](https://docs.docker.com/engine/reference/builder/), 한 다음 사용 하는 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)합니다.

- 사용 하 여 응용 프로그램을 컨테이너 화 합니다 [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구 (Docker의 오픈 소스 도구).

이 연습에서는 Docker 접근 방식에 대 한 Visual Studio 2017 도구를 중점적으로 다루지만 나머지 두 방식의 Dockerfile을 사용 하 여 인증과 관련 하 여 매우 비슷합니다.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>시나리오 1: 컨테이너 화 된 ASP.NET 웹 앱

아래 그림에는 컨테이너 화 된 eShop 레거시 웹 앱 응용 프로그램에 대 한 시나리오를 보여 줍니다.

![개발 환경에서 ASP.NET 응용 프로그램을 컨테이너 화 된 간소화 된 아키텍처 다이어그램](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>시나리오 2: 컨테이너 화 된 WCF 서비스

아래 그림에는 컨테이너 화 된 WCF 서비스를 사용 하 여 3 계층 응용 프로그램 시나리오를 보여 줍니다.

![간소화 된 개발 환경에서 컨테이너 화 된 WCF 서비스의 아키텍처 다이어그램](./media/image5-3.5.png)

### <a name="benefits"></a>이점

컨테이너의 모놀리식 응용 프로그램을 실행 하면 이점이 있습니다. 먼저, 응용 프로그램에 대 한 이미지를 만듭니다. 해당 지점에서 모든 배포가 동일한 환경에서 실행 됩니다. 모든 컨테이너 동일한 OS 버전을 사용 하 여 동일한 버전의 종속성이 설치, 동일한.NET framework 버전을 사용 하 고 동일한 프로세스를 사용 하 여 빌드됩니다. 기본적으로 Docker 이미지를 사용 하 여 응용 프로그램의 종속성을 제어 합니다. 종속성을 컨테이너를 배포 하는 경우 응용 프로그램으로 이동 합니다.

또 다른 이점은 개발자가 Windows 컨테이너에서 제공 하는 일관 된 환경에서 응용 프로그램 실행 수입니다. 스테이징 또는 프로덕션 환경에서 표시 하는 대신 특정 버전에만 표시 되는 문제를 즉시 확인할 수 있습니다. 개발 팀의 멤버에서 사용 하는 개발 환경에 차이가 덜 중요 해 집니다 컨테이너에서 응용 프로그램을 실행 합니다.

컨테이너 화 된 응용 프로그램에는 스케일 아웃 곡선을 flatter 수도 있습니다. 컨테이너 화 된 앱 VM 또는 물리적 컴퓨터 컴퓨터당 일반 응용 프로그램 배포에 비해 더 많은 응용 프로그램 및 서비스 인스턴스 (컨테이너 기반) 할 수를 사용 합니다. 밀도가 높아지고 필요한 변환이 Kubernetes 또는 Service Fabric과 같은 오 케 스트레이 터를 사용 하는 경우에 특히 리소스입니다.

이상적인 상황에서는 컨테이너 화 응용 프로그램 코드 변경 필요 하지 않습니다 (C\#). 대부분의 시나리오에서 하기만 하면 Docker 배포 메타 데이터 파일 (Dockerfiles 및 Docker Compose 파일).

### <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기

- [Windows 컨테이너 및 Docker를 사용 하 여.NET Framework 웹 앱 컨테이너 화 하는 방법](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [WCF 서비스에 Docker 지원 추가](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>연습 3: Azure Vm에 Windows 컨테이너 기반 앱 배포

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다. <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>개요

Windows Server 2016 가상 머신 (VM) Azure에서 Docker 호스트에 배포할 개발/테스트/스테이징 환경에 신속 하 게 설정할 수 있습니다. 또한, 테스터 또는 비즈니스 사용자가 앱의 유효성을 검사 하는 일반적인 위치를 제공 합니다. 또한 Vm 서비스 (IaaS) 프로덕션 환경으로 유효한 인프라를 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows Server 2016 또는 이후 버전을 기반으로 하는 Azure Vm에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대체 방법을 보여 줍니다.

### <a name="scenarios"></a>시나리오

몇 가지 시나리오는이 연습에 포함 됩니다.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>시나리오 a: Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포

![Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포](./media/image5-4.png)

**그림 5-4.** Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>시나리오 b: Docker 레지스트리를 통해 Azure VM에 배포

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

**그림 5-5.** Docker 레지스트리를 통해 Azure VM에 배포

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>시나리오: c: Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

**그림 5-6.** Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포

### <a name="azure-vms-for-windows-containers"></a>Windows 컨테이너에 대 한 azure Vm

Windows 컨테이너에 대 한 azure Vm은 Windows Server 2016, Windows 10 또는 이상 버전에 따라 Vm, Docker 엔진을 사용 하 여 둘 다 설정 합니다. 대부분의 경우에서 Windows Server 2016 Azure Vm에서 사용 됩니다.

Azure는 현재 이라는 VM을 제공 **컨테이너를 사용 하 여 Windows Server 2016**합니다. Windows Server Core 또는 Windows Nano Server를 사용 하 여 새 Windows Server 컨테이너 기능을 사용이 VM을 사용할 수 있습니다. 컨테이너 OS 이미지를 설치한 하 고 VM이 Docker를 사용 하 여 사용할 준비가 다음 키를 누릅니다.

### <a name="benefits"></a>이점

Azure에 배포할 때 온-프레미스 Windows Server 2016 Vm에 Windows 컨테이너를 배포할 수 있습니다, 있지만 Windows Server 컨테이너 Vm 사용 준비를 사용 하 여 시작 하는 간단한 방법인을 얻게 됩니다. 테스터 및 Azure 가상 머신 확장 집합을 통해 자동 확장성에 액세스할 수 있는 공통 온라인 위치를 가져올 수도 있습니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기

<https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>연습 4: Azure Container Instances (ACI)에 Windows 컨테이너 기반 앱을 배포 합니다.

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.

[ACI (Azure Container Instances)에 앱 배포](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>개요

[Azure ACI (Container Instances)](https://docs.microsoft.com/azure/container-instances/) 는 컨테이너의 단일 인스턴스를 배포할 수 있는 컨테이너 개발/테스트/준비 환경을 사용 하는 가장 빠른 방법입니다.

### <a name="goals"></a>목표

이 연습에서는 Windows 컨테이너를 Azure ACI (Container Instances) ACI를 eShopModernizing 앱을 배포 하는 방법을 배포 하는 경우 주요 시나리오를 보여줍니다.

### <a name="scenarios"></a>시나리오

ACI에 하나 또는 모든 앱 (MVC 앱, WebForms 앱 또는 WCF 서비스) 배포와 같은 eShopModernizing 앱을 배포 하는 방법에 대 한 변형이 있을 수 있습니다. 아래에 표시 된 다음 시나리오에서 ACI (Azure Container Instances)으로 ASP.NET MVC 앱과 배포 둘 다 SQL Server 컨테이너 컨테이너로 볼 수 있습니다.

![ACI에 개발 환경에서 배포](./media/image5-3.5.6.png)

### <a name="benefits"></a>이점

Azure Container Instances를 사용 하면 쉽게 만들고 가상 머신을 프로 비전 하거나 상위 수준 서비스를 채택 하지 않고도 Azure에서 Docker 컨테이너를 관리 합니다. ACI를 사용 하 여 직접 Azure에 Windows 컨테이너를 배포 하는 인터넷에 공개 된 정규화 된 도메인 이름 (FQDN)을 사용 하 여 몇 초에서에서 (있는 경우 Windows 컨테이너 이미지를 Docker 허브 또는 Azure 컨테이너와 같은 Docker 레지스트리에 레지스트리)입니다.

### <a name="considerations"></a>고려 사항

전체.NET Framework 중 하나를 사용 하 여 Windows 컨테이너를 배포 / ASP.NET 또는 SQL Server에 Azure ACI (Container Instances)는 매우 빨리 Docker 이미지 수 있으므로 (예: Windows 컨테이너를 사용 하 여 Windows Server 2016) 일반 Docker 호스트에 배포 하지만 될 때마다 (Docker 레지스트리에서 끌어온) 다운로드 하 고 (영구적으로 온라인 사용자 고유의 docker 호스트를 유지 관리 보다 훨씬 저렴 SQL 컨테이너 이미지 (15.1 GB) 및 ASP.NET 컨테이너 이미지 (13.9 GB)의 크기는 훨씬 큰 경우 Azure에서 VM에 Windows 컨테이너를 사용 하 여 Windows Server 2016) 인 반면에 유리한 프로덕션 배포에는 Azure (AKS/ACS) 또는 Azure Service Fabric에서 Kubernetes와 같은 전체 orchestrator 말할 것도 없습니다.

주 결론으로 Azure Container Instances를 사용 하 여는 CI/CD 파이프라인 및 개발/테스트 시나리오에 대 한 매우 매력적인 옵션입니다.

## <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>연습 5: Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱을 배포 합니다.

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

### <a name="overview"></a>개요

Windows 컨테이너를 기반으로 하는 응용 프로그램 플랫폼에서 멀리 더욱 IaaS Vm에서 사용 하 여 신속 하 게 해야 합니다. 이 쉽게 높은 확장성을 달성 하는 데 필요한 더 확장성, 자동화 된 및의 향상에 대 한 배포 및 버전 관리를 자동화 합니다. 오 케 스트레이 터를 사용 하 여 이러한 목표를 달성할 수 있습니다 [Kubernetes](https://kubernetes.io/)에 사용 가능 [Azure Container Services](https://azure.microsoft.com/services/container-service/)합니다.

### <a name="goals"></a>목표

Kubernetes에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 방법을 알아보려면이 연습의 목적은 (라고도 *K8s*) Azure Container Service에서. 부터 Kubernetes에 배포 하는 2 단계 프로세스입니다.

1. Azure Container Service에 Kubernetes 클러스터를 배포 합니다.

2. Kubernetes 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>시나리오 a: 개발 환경에서 Kubernetes 클러스터에 직접 배포

![개발 환경에서 Kubernetes 클러스터에 직접 배포](./media/image5-7.png)

**그림 5-7.** 개발 환경에서 Kubernetes 클러스터에 직접 배포

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>시나리오 b: Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포](./media/image5-8.png)

**그림 5-8.** Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포

### <a name="benefits"></a>이점

Kubernetes 클러스터를 배포 하는 다음과 같은 많은 이점이 있습니다. 가장 큰 장점은는 확장할 수 있습니다 (내부-확장성 있는 기존 노드에)를 사용 하 고 클러스터 (에서 노드 또는 Vm의 수를 기준으로 컨테이너 인스턴스 수를 기준으로 응용 프로그램을 프로덕션 준비 환경 표시 글로벌 확장성 클러스터)입니다.

Azure Container Service는 인기 있는 오픈 소스 도구 및 기술을 특별히 Azure 용으로 최적화합니다. 컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션을 얻게 됩니다. 크기, 호스트의 수를 선택 하 고 다른 모든 항목을 처리 하는 오 케 스트레이 터 도구-컨테이너 서비스 키를 누릅니다.

Kubernetes를 사용 하 여 개발자 수행해 볼 수 있습니다 실제 및 가상 컴퓨터에 대 한 생각은 다음 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라를 계획 합니다.

- 여러 컨테이너 기반 응용 프로그램

- Container instances 및 수평적 자동 크기 조정을 복제

- 이름 지정 및 검색 (예를 들어 내부 DNS)

- 부하 분산

- 롤링 업데이트

- 암호를 배포합니다.

- 응용 프로그램 상태 검사

## <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기 <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>연습 6: Azure Service Fabric에 Windows 컨테이너 기반 앱을 배포 합니다.

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

### <a name="overview"></a>개요

Windows 컨테이너를 신속 하 게 기반 응용 프로그램 플랫폼에서 IaaS Vm에서 지금 이동 더욱 사용 해야 합니다. 이 쉽게 높은 확장성을 달성 하는 데 필요한 더 확장성, 자동화 된 및의 향상에 대 한 배포 및 버전 관리를 자동화 합니다. 다른 공용 클라우드 또는 오 케 스트레이 터 인 Azure 클라우드에서 사용할 수 있지만 사용할 수 있는 온-프레미스 Azure Service Fabric을 사용 하 여 이러한 목표를 달성할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Azure에서 Service Fabric 클러스터에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 방법을 알아보려면입니다. 부터 Service Fabric에 배포 하는 2 단계 프로세스입니다.

1. Azure로 (또는 다른 환경으로) Service Fabric 클러스터를 배포 합니다.

2. Service Fabric 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>시나리오 a: 개발 환경에서 Service Fabric 클러스터에 직접 배포

![개발 환경에서 Service Fabric 클러스터에 직접 배포](./media/image5-9.png)

> **그림 5-9.** 개발 환경에서 Service Fabric 클러스터에 직접 배포

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a>시나리오 b: Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포](./media/image5-10.png)

**그림 5-10.** Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포

## <a name="benefits"></a>이점

Service Fabric에서 클러스터에 배포 하는 이점을 Kubernetes를 사용 하는 이점은 비슷합니다. 한 가지 차이점 그러나은 Service Fabric Windows 컨테이너 버전 1.9로 Kubernetes에 대 한 베타 단계에는 Kubernetes에 비해 Windows 응용 프로그램에 대 한 더 완성도 높은 프로덕션 환경 (2017 년 12 월). Kubernetes에 Linux에 대 한 보다 성숙한 환경입니다.

Azure Service Fabric을 사용 하는 주요 이점은는 확장할 수 있습니다 (내부-확장성 있는 기존 노드에)를 사용 하 고의 수를 기준으로 컨테이너 인스턴스 수를 기준으로 응용 프로그램을 프로덕션이 준비 된 환경을 제공 하는 노드 또는 클러스터 (클러스터의 글로벌 확장성)의 Vm입니다.

Azure Service Fabric은 컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공합니다. Service Fabric 클러스터에 Azure 또는 고유한 데이터 센터에 온-프레미스 설치를 사용할 수 있습니다. 다른 클라우드에서 Service Fabric 클러스터와 같은 설치도 [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)합니다.

Service Fabric을 사용 하 여 개발자 수행해 볼 수 있습니다 실제 및 가상 컴퓨터에 대 한 생각은 다음 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라를 계획 합니다.

- 여러 컨테이너 기반 응용 프로그램입니다.

- Container instances 및 수평적 자동 크기 조정을 복제합니다.

- 이름 지정 및 (예를 들어 내부 DNS)를 검색 합니다.

- 부하를 분산합니다.

- 롤링 업데이트 합니다.

- 비밀을 배포 합니다.

- 응용 프로그램 상태를 확인합니다.

다음 기능은 다른 오 케 스트레이 터와 비교 하는 Service Fabric에서 전용입니다.

- 상태 저장 Reliable Services 응용 프로그램 모델을 통해 기능을 서비스 합니다.

- Reliable Actors 응용 프로그램 모델을 통해 행위자 패턴입니다.

- Windows 또는 Linux 컨테이너 외에도 틀 프로세스를 배포 합니다.

- 고급 롤링 업데이트 및 상태 검사 합니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki의이 콘텐츠를 더 자세히 살펴보기

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

> [!div class="step-by-step"]
> [이전](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [다음](conclusions.md)
