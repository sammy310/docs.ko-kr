---
title: 기존 .NET 앱을 Windows 컨테이너로 배포
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 기존 .NET 앱을 Windows 컨테이너로 배포
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: ad0da9f7f0412c14b5362e3f631a7aa4af1f8260
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61812061"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>기존 .NET 앱을 Windows 컨테이너로 배포

Windows 컨테이너를 기반으로 하는 배포는 클라우드에 최적화된 응용 프로그램과 클라우드 네이티브 응용 프로그램에 적용할 수 있습니다.

그러나 이 가이드와 특히 다음 절에서는 응용 프로그램을 재설계하지 않아도 되는 *클라우드에 최적화*된 응용 프로그램에 대한 Windows 컨테이너 사용을 중점적으로 설명합니다.

## <a name="what-are-containers-linux-or-windows"></a>컨테이너 란? (Linux 또는 Windows)

컨테이너는 응용 프로그램을 격리된 자체 패키지로 마무리하는 방법입니다. 해당 컨테이너에서 응용 프로그램은 컨테이너 외부에 있는 응용 프로그램 또는 프로세스의 영향을 받지 않습니다. 응용 프로그램이 하나의 프로세스로 성공적으로 실행되는 데 의존하는 모든 것이 컨테이너 내부에 있습니다. 컨테이너가 이동할 수 있는 곳이라면, 직접 종속성 측면에서 응용 프로그램의 요구사항이 충족됩니다.실행에 필요한 모든 항목(라이브러리 종속성, 런타임 등)이 함께 번들되기 때문입니다.

컨테이너의 주요 특징 한다는 점입니다 환경 같은 서로 다른 배포에서 필요한 모든 종속성이 있는 컨테이너 자체 제공 되기 때문입니다. 컴퓨터에 응용 프로그램을 디버그할 수 있으며 동일한 환경의 사용 하 여 다른 컴퓨터에 배포할 수 있습니다.

컨테이너는 컨테이너 이미지의 인스턴스입니다. 컨테이너 이미지는 앱 또는 서비스 (예: snapshot)에 패키지를 안정적이 고 재현 가능한 방식으로 배포 하는 방법을 합니다. Docker는 기술 it만의 개념 및 프로세스 또한 말할 수 있습니다.

이러한 업계 전반의 "배포 단위입니다." 점점 컨테이너에는 매일 더 일반적이 있을 경우

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>컨테이너 (Linux 또는 Windows에서 Docker 엔진)의 이점

컨테이너는을 사용 하 여 응용 프로그램을 빌드할 수도 있습니다 민첩성을 빌드, 제공 되는 경우 및 인프라에서 모든 응용 프로그램을 실행 한에서 크게 향상을 간단한 구성 요소 제품으로 정의 합니다.

컨테이너를 사용 하 여 모든 앱 개발에서 프로덕션으로 거의 변경 하지 않고 코드를 통해 Microsoft 개발자 도구, 운영 체제와 클라우드의 Docker 통합 덕분를 사용 하 여 수행할 수 있습니다.

일반 Vm에 배포할 때 이미 있는 메서드를 Vm에 ASP.NET 앱을 배포 합니다. 것, 그러나 Puppet와 같은 배포 도구 또는 유사한 도구를 사용 하 여 메서드는 여러 수동 단계 또는 복잡 한 자동화 된 프로세스는입니다. 구성 항목 수정, 서버 간에 응용 프로그램 콘텐츠를 복사 및.msi 설치 과정에서 테스트 하 여 다음을 기반으로 하는 대화형 설치 프로그램을 실행 하는 같은 태스크를 수행 해야 합니다. 배포에서 이러한 모든 단계는 배포 시간 및 위험을 추가합니다. 대상 환경에서 종속성 없을 때마다 오류가 발생 합니다.

Windows 컨테이너에서 응용 프로그램 패키징 프로세스 자동화 완벽 하 게 됩니다. Windows 컨테이너는 컨테이너 배포에 대 한 롤백 및 자동 업데이트를 제공 하는 Docker 플랫폼을 기반으로 합니다. Docker 엔진을 사용에서 얻는 주요 향상은 응용 프로그램의 스냅숏, 이미지, 모든 종속 항목과 함께 만드는 경우 이미지는 Docker 이미지 (이 경우: Windows 컨테이너 이미지)입니다. 이미지를 사용 하면 컨테이너에서 ASP.NET 앱을 실행 하는 소스 코드를 다시 이동 하지 않고도 합니다. 컨테이너 스냅샷이 배포 단위입니다.

대부분의 조직에서는 다음과 같은 이유로 모놀리식 기존 응용 프로그램을 컨테이너 화 됩니다.

-   **향상 된 배포를 통해 민첩성을 릴리스**합니다. 컨테이너는 개발 및 운영 간의 일관 된 배포 계약을 제공합니다. 컨테이너를 사용 하면 예를 들어 개발자 들리지 않습니다에서는 "작동 내 컴퓨터에서 없습니까 프로덕션 환경에서?" 이러한 수 예를 들어 "실행을 컨테이너로 되므로 프로덕션 환경에서 실행 됩니다." 모든 지원 되는 컨테이너 기반 환경에서 모든 종속 항목과 함께 패키지 된 응용 프로그램을 실행할 수 있습니다. 모든 배포 대상 (개발, QA, 스테이징, 프로덕션)에서 실행 되도록 의도 된 방식으로 실행 됩니다. 컨테이너 배포를 크게 향상 하는 다음 한 단계에서 벗어날 경우 대부분의 마찰을 제거 하 고 더 빠르게 제공할 수 있습니다.

-   **비용 절감**합니다. 컨테이너를 통합 하 고 기존 하드웨어 또는 하드웨어 단위당 높은 밀도로 실행 중인 응용 프로그램에서 제거 하거나 비용 절감 시킬 했습니다.

-   **이식성**합니다. 컨테이너는 모듈식 및 이식 가능한입니다. Docker 컨테이너는 모든 서버 운영 체제 (Linux 및 Windows) (Microsoft Azure, Amazon AWS, Google, IBM) 모든 메이저 공용 클라우드 및 온-프레미스에서에 개인 또는 하이브리드 클라우드 환경에서 지원 됩니다.

-   **컨트롤**합니다. 컨테이너는 컨테이너 수준에서 제어 되는 유연한 보안 환경을 제공 합니다. 컨테이너 보안 격리, 고도 컨테이너에서 실행 제약 조건 정책을 설정 하 여 제한 될 수 있습니다. Windows 컨테이너에 대 한 섹션에서 자세히 설명, Windows Server 2016 및 Hyper-v 컨테이너 추가 엔터프라이즈 지원 옵션을 제공합니다.

민첩성, 이식성 및 컨트롤에서 상당한 개선 사항을 궁극적으로 비용을 상당히 절감 컨테이너를 사용 하 여 개발 하 고 응용 프로그램을 관리 하는 경우.

## <a name="what-is-docker"></a>Docker란?

[Docker](https://www.docker.com/) 되는 [오픈 소스 프로젝트](https://github.com/docker/docker) 클라우드 또는 온-프레미스에서 실행할 수 있는 자체 충족 적 이동식 컨테이너를 응용 프로그램의 배포를 자동화 하 합니다. Docker는 이 기술을 장려하고 발전시키는 [회사](https://www.docker.com/)이기도 합니다. 회사는 클라우드, Linux 및 Windows 공급 업체를 비롯 하 여 Microsoft와 공동 작업에서 작동합니다.

![](./media/image6.png)

> **그림 4 ~ 6입니다.** Docker는 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포

다른 사람에 게 virtual machines를 사용 하 여 친숙 한 컨테이너 나타날 매우 유사 합니다. 컨테이너 운영 체제를 실행 하 고 파일 시스템에 물리적 또는 가상 컴퓨터 시스템에서와 마찬가지로 네트워크를 통해 액세스할 수 있습니다. 그러나 기술 및 개념 컨테이너는 가상 컴퓨터와 크게 다릅니다. 개발자의 관점에서 단일 프로세스와 같은 컨테이너를 더 처리 해야 합니다. 사실, 컨테이너는 하나의 프로세스에 대 한 단일 진입점입니다.

Docker 컨테이너 (편의상 *컨테이너*) Linux 및 Windows에서 기본적으로 실행할 수 있습니다. Windows 컨테이너 (호스트 서버 또는 VM) Windows 호스트 에서만 실행할 수 있습니다 일반 컨테이너를 실행 하는 경우 및 Linux 컨테이너는 Linux 호스트에만 실행할 수 있습니다. 그러나 Windows Server 및 Hyper-v 컨테이너의 최신 버전의 Linux 컨테이너도 기본적으로 서버에서 실행할 수 Windows 현재는 Windows Server 컨테이너에만 사용할 수 있는 Hyper-v 격리 기술을 사용 하 여 합니다.

가까운 미래에 Linux 및 Windows 컨테이너에 있는 혼합된 환경을 가능 하 고 일반적인 됩니다.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>기존.NET 응용 프로그램에 대 한 Windows 컨테이너의 혜택

Windows 컨테이너를 사용 하 여의 이점은 기본적으로 동일한 얻을 수 있는 혜택 컨테이너에서 일반적입니다. Windows 컨테이너를 사용 하는 것은 크게 민첩성, 이식성 및 제어를 개선 하는 방법에 대 한입니다.

기존.NET 응용 프로그램은.NET Framework를 사용 하 여 만든 응용 프로그램을 가리킵니다. 예를 들어 기존의 ASP.NET 웹 응용 프로그램 수 있습니다-최신 이며 플랫폼 간 실행 하는.NET Core를 사용 하지 않는 Linux, Windows, MacOS에서 합니다.

.NET Framework의 기본 종속성이 Windows. 또한 기존 ASP.NET에 IIS 및 System.Web와 같은 보조 종속성도 있습니다.

기간.NET Framework 응용 프로그램을 Windows를 실행 해야 합니다. 기존.NET Framework 응용 프로그램을 컨테이너 화 하려는 고 처리할 수 없거나.NET Core로 마이그레이션에 투자 하지 않으려는 "(제대로 작동 하지 않습니다" 마이그레이션 것), Windows 컨테이너를 사용 하는 컨테이너에 대 한 유일한 선택 합니다.

즉, Windows 컨테이너의 주요 장점 중 하나를 제공 하면 컨테이너 화를 통한 Windows에서 실행 되는 기존.NET Framework 응용 프로그램을 현대화 하는 방법입니다. 궁극적으로 Windows 컨테이너에서는 컨테이너 민첩성, 휴대성 및 더 나은 제어를 사용 하 여 찾고자 하는 이점입니다.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>대상으로 지정할 OS를 선택 합니다. NET 기반 컨테이너

.NET Framework 및.NET Core 간의 차이점 뿐만 아니라 Docker에서 지원 되는 운영 체제의 다양성을 고려할 때, 특정 OS와 사용 중인 framework를 기반으로 하는 특정 버전을 대상 해야 있습니다.

Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다. 이러한 Windows 버전.NET Framework 또는.NET Core 응용 프로그램에서 필요할 수 있는 다른 특성 (예: IIS와 Kestrel 같은 자체 호스팅된 웹 서버 ()를 제공 합니다.

Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.

그림 4-7 OS 버전의.NET Framework 앱의 버전에 따라 대상 수를 보여 줍니다.

![](./media/image7.png)

> **그림 4-7입니다.** .NET Framework 버전을 기반으로 하는 대상 운영 체제

.NET Framework 응용 프로그램을 기반으로 하는 기존 또는 레거시 응용 프로그램에 대 한 마이그레이션 시나리오의 경우 기본 종속성 Windows 및 IIS에 있습니다. 유일한 방법은 Windows Server Core 및.NET Framework를 기반으로 하는 Docker 이미지를 사용 하는 것입니다.

Dockerfile 파일에 이미지 이름을 추가한 경우 Windows.NET Framework 기반 컨테이너 이미지에 대 한 다음 예와 같이 태그를 사용 하 여 운영 체제 및 버전을 선택할 수 있습니다.

> | **Tag** | **시스템 및 버전** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x를 Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x Windows Server Core에서 추가 ASP.NET 사용자 지정 |

.NET Core (플랫폼 간 Linux 및 Windows 용)에 대 한 태그를 다음과 같이 보입니다.

> | **Tag** | **시스템 및 버전**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET core 2.0 런타임 전용 linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET core 2.0 런타임 전용 Windows Nano Server에서 |

### <a name="multi-arch-images"></a>다중 아키텍처 이미지

2017 년 중반부터 사용할 수도 있습니다 새로운 기능을 호출 하는 Docker에서 [다중 아키텍처](https://github.com/moby/moby/issues/15866) 이미지입니다. .NET core Docker 이미지는 다중 아키텍처 태그를 사용할 수 있습니다. Dockerfile 파일 대상으로 하는 운영 체제를 정의할 필요가 없습니다. 다중 아키텍처 기능을 단일 태그를 다중 컴퓨터 구성에서 사용할 수 있습니다. 예를 들어 다중 아키텍처를 사용 하 여 사용할 수 있습니다 하나 일반적인 태그: **microsoft/dotnet:2.0.0-runtime**합니다. Linux 컨테이너 환경에서 이러한 태그를 끌어오는 경우 Debian 기반 이미지를 가져옵니다. Windows 컨테이너 환경에서 이러한 태그를 끌어오는 경우 Nano 서버 기반 이미지를 가져옵니다.

기존.NET Framework만 Windows를 지원 하기 때문에.NET Framework 이미지에 대 한 다중 아키텍처 기능을 사용할 수 없습니다.

## <a name="windows-container-types"></a>Windows 컨테이너 형식

Linux 컨테이너와 같은 Windows Server 컨테이너는 Docker 엔진을 사용 하 여 관리 됩니다. Linux 컨테이너와 달리 Windows 컨테이너 두 개의 서로 다른 컨테이너 형식에 포함 하거나 시간-Windows Server 컨테이너와 Hyper-v 격리를 실행 합니다.

**Windows Server 컨테이너**: 프로세스 및 네임 스페이스 격리 기술을 통해 응용 프로그램 격리를 제공합니다. Windows Server 컨테이너를 컨테이너 호스트 및 호스트에서 실행 되는 모든 컨테이너와 커널을 공유 합니다. 이러한 컨테이너는 적대적인 보안 경계를 제공 하지 않습니다와 신뢰할 수 없는 코드를 격리 하려면 쓰일 수 없습니다. 이러한 컨테이너에는 공유 커널 공간이 같은 커널 버전 및 구성이 필요합니다.

**Hyper-v 격리**: 각 컨테이너를 고도로 최적화 된 VM에서 실행 하 여 Windows Server 컨테이너에서 제공 하는 격리를 확장 합니다. 이 구성에서는 컨테이너 호스트의 커널은 동일한 호스트에 다른 컨테이너와 공유 되지 않습니다. 이러한 컨테이너는 적대적인 다중 테 넌 트 호스팅의 경우 VM의 동일한 보안 보증을 사용 하 여 설계 되었습니다. 이러한 컨테이너 호스트 또는 호스트의 다른 컨테이너와 커널을 공유 하지 않습니다, 때문에 다른 버전 및 구성 (사용 하 여 지원 되는 버전)를 사용 하 여 커널을 실행할 수 있습니다. 예를 들어, Windows 10에서 모든 Windows 컨테이너 구성과 커널 버전의 Windows Server를 활용 하려면 Hyper-v 격리를 사용 합니다.

Hyper-v 격리 없이 Windows 컨테이너를 실행 하는 것은 런타임에 결정 합니다. 처음에 Hyper-v 격리를 사용 하 여 컨테이너를 만들도록 선택할 수도 있으며 런타임 시 대신 Windows Server 컨테이너로 서 실행 하도록 선택할 수 있습니다.

### <a name="additional-resources"></a>추가 자료

-   **Windows 컨테이너 설명서**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

-   **Windows 컨테이너 기본 사항**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

-   **인포 그래픽: Microsoft 및 컨테이너**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Azure에서 컨테이너 에코 시스템

이전 섹션에서이 설명 했습니다.NET 응용 프로그램에 대 한 특정 컨테이너 이미지에 대 한 세부 정보 뿐만 아니라는 Docker 컨테이너의 이점을 제공 합니다. 모든 일반 정보는 개발 또는 응용 프로그램을 컨테이너 화 하기 위해 기본입니다.
그러나 프로덕션 배포 환경 또는 QA 및 개발/테스트 환경에 대 한 생각을 하는 경우에 Microsoft Azure를 개방적이 고 광범위 한 다양 한 선택 항목 (아래 다이어그램에 표시 됨)는 클라우드에서 전체 컨테이너 생태계를 제공 합니다. 특정 응용 프로그램의 요구에 따라 하나 또는 다른 Azure 제품을 선택 해야 합니다.

![](./media/image7.5.png)

> **그림 4-7.5입니다.** Azure에서 컨테이너 에코 시스템

인프라를 간주 되는 컨테이너를 지 원하는 다음 제품을 Azure에서 컨테이너 에코 시스템:
-   **Azure Container Instances (ACI)**
-   **Azure Virtual Machines** (지원과 컨테이너의)
-   **Azure Virtual Machine Scale Sets** (지원과 컨테이너의)

세 가지 해당에서 ACI 사실은 기본 OS 필요가 없습니다를 업그레이드/패치 등을 유지 하기 위해 필요는 없지만 여전히 ACI 향상이 가이드의 다음 섹션에 설명 된 대로, 인프라 수준에 배치 되는 훌륭한 혜택을 제공 합니다.

Azure 지원 컨테이너 수준 동시에 보다 PaaS (Platform as a Service)에 배치 되는 제품은 다음과 같습니다.

-   **Azure App Service**
-   **Azure Kubernetes Service (AKS 및 ACS)**
-   **Azure Service Fabric** 
-   **Azure Batch** 

그런 다음 Azure Container Registry는 모든 이전 제품의 등록 및 사용자 지정 컨테이너 이미지를 배포할 때 사용할 수 있는 Azure에서 호스트 되는 높은 확장성이 뛰어난 컨테이너 레지스트리입니다.

또한 사용자 컨테이너에서 사용할 수 있습니다 다른 관리 서비스에서 Azure SQL Database, Azure Redis cache에 Azure Cosmos DB와 같은 Azure 등. 또한 Cloud Foundry 등 OpenShift Azure 내에서 컨테이너를도 사용할 수 있는 Azure Marketplace의 타사 솔루션/플랫폼이 됩니다. 

다음 섹션에서는 Windows 컨테이너를 대상으로 하는 경우에 특히 각 해당 Azure 제품 및 솔루션을 사용 하는 경우에 대 한 Microsoft의 권장 사항을 탐색할 수 있습니다.

>[!div class="step-by-step"]
>[이전](what-about-cloud-native-applications.md)
>[다음](when-not-to-deploy-to-windows-containers.md)
