---
title: 컨테이너화된 앱을 위한 Microsoft 플랫폼 및 도구 소개
description: Docker 응용 프로그램 수명 주기를 지원 하기 위해 Microsoft의 제품을 알아야 가져옵니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Microsoft 플랫폼 및 컨테이너 화 된 앱에 대 한 도구를 소개

*Vision: 만들 적응력이 엔터프라이즈급, 컨테이너 화 된 응용 프로그램 수명 주기 개발, IT 작업자 및 프로덕션 관리에 걸쳐 있는 합니다.*

그림 3-1 (응용 프로그램 개발, DevOps 인프라 프로세스 및 IT 관리 및 작업) 여러 팀에서 제공 하는 작업의 유형에 따라 분류 Docker 앱의 수명 주기에서 주요 사항 보여 줍니다. 일반적으로 기업에서 각 영역을 담당하는 "가상 사용자"의 프로필은 다릅니다. 기술도 마찬가지입니다.

![Microsoft 도구입니다. 개발 및 설계 작업: Windows, VS 및 VS 코드를.NET Core, Azure Kubernetes Service에 대 한 docker 엔진입니다. 빌드/테스트/배송 워크 로드: Azure DevOps, Team Foundation Server에서 Docker CLI, Azure Kubernetes Service. 실행/모니터링/관리 작업: Azure Monitor, Azure 포털 Azure Kubernetes 서비스를 Service Fabric에서 다른 오 케 스트레이 터입니다.](./media/image1.png)

**그림 3-1.** Microsoft 플랫폼 및 도구를 사용 하 여 컨테이너 화 된 Docker 응용 프로그램에 대 한 수명 주기에서 주요 사항

컨테이너 화 된 Docker 수명 주기 워크플로 수 규범적인 처음 선택에 따라 "기본적으로 제품을" 개발자가 더 빠르게 시작 하는 데 쉽게 이지만 내부적 있어야 함을 개방형 프레임 워크가 됩니다 있도록 기본적인를 각 조직이 나 기업의 다양 한 상황에 맞게 조정할 수 있는 유연한 워크플로. 워크플로 인프라(구성 요소와 제품)는 각 회사에서 나중에 보유하게 될 환경에 맞출 수 있을 만큼 충분히 유연해야 합니다. 개발 또는 DevOps 제품을 다른 사람과 맞바꿀 수 있을 정도여야 합니다. 플랫폼 및 인프라의 이러한 유연성, 개방성 및 광범위한 기술 옵션은 다음에 나오는 챕터에 설명된 것처럼 컨테이너화된 Docker 애플리케이션에 대한 Microsoft의 우선 순위입니다.

표 3-1에서는 컨테이너화된 Docker 애플리케이션에 대한 Microsoft DevOps의 의도는 사용자가 각 단계에 사용할 제품(Microsoft 또는 타사 제품)을 선택할 수 있도록 개방적인 DevOps 워크플로를 제공하는 한편, 이미 연결된 "기본 제품"을 제공하는 간소화된 워크플로를 제공함으로써 Docker 앱을 위한 기업 차원의 DevOps 워크플로를 빠르게 시작할 수 있게 하는 것임을 보여줍니다.

**테이블 3-1입니다.** 모든 기술에 DevOps 워크플로 열려면

| 호스트 | Microsoft 기술 | 타사-Azure 플러그형 |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Docker 앱용 플랫폼   | • Microsoft Visual Studio 및 Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • 모든 코드 편집기(예: Sublime)<br /> • 모든 언어(Node.js, Java, Go 등)<br /> • 모든 오케스트레이터 및 스케줄러<br /> • 모든 Docker 레지스트리<br /> |
| Docker 앱용 DevOps     | • Azure DevOps 서비스<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion 등<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI 등<br /> • 온-프레미스 Docker Datacenter, Docker Swarm, Mesos DC/OS, Kubernetes 등<br /> |
| 관리 및 모니터링  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos 등<br />

표 3-1에 정의된 컨테이너화된 Docker 앱을 위한 Microsoft 플랫폼 및 도구는 다음과 같은 구성 요소로 이루어집니다.

- **Docker 앱 개발용 플랫폼** "앱"을 구성하는 서비스나 서비스 컬렉션의 개발을 말합니다. 이 개발 플랫폼은 개발자가 공유 코드 리포지토리에 코드를 게시하기 전에 필요한 모든 작업을 제공합니다. 컨테이너로 배포 된 서비스를 동일한 앱 이나 Docker 없이 서비스를 개발 하는 것과 비슷합니다. 사용자 기본 설정된 언어 (.NET, Node.js, Go 등) 및 원하는 편집기 또는 Visual Studio 또는 Visual Studio Code 같은 IDE를 사용 하 여 계속 있습니다. 그러나 Docker를 배포 대상으로 고려하기보다는 Docker 환경에서 서비스를 개발하세요. 컨테이너에서 로컬로 코드를 빌드, 실행, 테스트 및 디버그하여 개발 시 대상 환경을 제공할 수 있습니다. 대상 환경을 로컬로 제공하면 Docker 컨테이너에서 DevOps 수명 주기를 개선하는 데 큰 도움이 될 수 있는 요소를 설정합니다. Visual Studio 및 Visual Studio Code에는 개발 프로세스 내에서 Docker 컨테이너를 통합하는 확장 기능이 있습니다.

- **Docker 앱 용 DevOps** Docker 응용 프로그램을 작성 하는 개발자가 사용할 수 있습니다 [Azure DevOps 서비스](https://azure.microsoft.com/services/devops/) 또는 포괄적인 자동화 된 응용 프로그램 수명 주기를 Jenkins와 같은 기타 다른 타사 제품 관리 (ALM)입니다.

  Azure DevOps 서비스를 사용 하면 개발자가 컨테이너에 초점을 맞춘 만들 수 있습니다 (Azure DevOps 서비스-Git, GitHub, 모든 원격 Git 리포지토리 또는 Subversion) 어디에서 나 컨트롤 소스 코드를 포함 하는 빠르고 반복적인 프로세스에 대 한 DevOps CI (지속적인 통합) 내부 단위 테스트, 내부 container/서비스 통합 테스트, CD (지속적인 업데이트), 및 릴리스 관리 (RM). 또한 개발자는 개발 환경에서 준비 및 프로덕션 환경까지 Azure Container Service로의 Docker 애플리케이션 릴리스를 자동화할 수 있습니다.

- **관리 및 모니터링** IT 관리 및 프로덕션 응용 프로그램 및 통합된 환경에서 모두 큐브 뷰를 통합 하는 여러 가지 방법으로 서비스를 모니터링할 수 있습니다.

  - **Azure portal** 오픈 소스 오 케 스트레이 터를 사용 하는 경우 Azure Kubernetes Service (AKS), Service Fabric 및 다른 오 케 스트레이 터 수 있도록 설정 하 고 Docker 환경을 유지 관리 합니다. Azure Service Fabric을 사용 중인 경우 Service Fabric Explorer를 통해 클러스터를 시각화하고 구성할 수 있습니다.

  - **Docker 도구** 익숙한 도구를 사용하여 컨테이너 응용 프로그램을 관리할 수 있습니다. 컨테이너 작업을 클라우드로 이동하기 위해 기존 Docker 관리 방법을 변경할 필요가 없습니다. 이미 익숙한 애플리케이션 관리 도구를 사용하고 원하는 오케스트레이터를 위한 표준 API 엔드포인트를 통해 연결하세요. 또한 다른 타사 도구를 사용하여 Docker Datacenter 또는 CLI Docker 도구와 같은 Docker 애플리케이션을 관리할 수도 있습니다. 

    Linux 명령에 익숙한 경우에 Microsoft Windows 및 PowerShell을 사용한 Linux 하위 시스템 명령줄 및 제품 (Docker, Kubernetes...)를 사용 하 여이 Linux 하위 시스템 기능은에서 실행 중인 클라이언트 컨테이너 응용 프로그램을 관리할 수 있습니다. 즐겨 찾는 Microsoft Windows OS를 사용 하 여이 가이드의 뒷부분에 나오는 Linux 하위 시스템에서 이러한 도구를 사용 하는 방법에 대 한 더 알아봅니다 됩니다.

  - **오픈 소스 도구** 하므로 AKS는 오케스트레이션 엔진에 대 한 표준 API 끝점을 노출 하 고 가장 인기 있는 도구가 AKS와 호환 되는, 대부분의 경우 기본적으로 작동 합니다-시각화, 모니터링, 포함 명령줄 도구 및 사용 가능 해지면 향후 도구입니다.

  - **Azure Monitor** 프로덕션 환경의 모든 각도 모니터링 하는 Azure의 솔루션입니다. 응용 프로그램에서 시스템 생성 로그 데이터를 받을 수 있도록 방금 서비스에 해당 SDK를 설정 하 여 프로덕션 Docker 응용 프로그램을 모니터링할 수 있습니다.

따라서 Microsoft는 컨테이너화된 Docker 애플리케이션의 전체 수명 주기에 대한 완벽한 기반을 제공합니다. 그러나 *컬렉션의 제품 및 기술 필요에 따라 선택 하 고 기존 통합할 수 있도록 하는 도구 및 프로세스가*합니다. 광범위한 접근법의 유연성과 심층적인 기능의 강력함은 컨테이너화된 Docker 애플리케이션 개발 분야에서 Microsoft가 유리한 위치를 점할 수 있게 해줍니다.

>[!div class="step-by-step"]
>[이전](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[다음](../design-develop-containerized-apps/index.md)
