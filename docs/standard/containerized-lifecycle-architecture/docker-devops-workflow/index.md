---
title: Microsoft 도구를 사용하는 Docker 애플리케이션 DevOps 워크플로
description: Microsoft 도구를 사용 하 여 Microsoft 플랫폼 및 도구 DevOps 워크플로 사용 하 여 컨테이너 화 된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 80acd58d08900da8e79f6b7388da3b10f9e4e566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672305"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a><span data-ttu-id="4d6a9-103">Microsoft 도구를 사용하는 Docker 애플리케이션 DevOps 워크플로</span><span class="sxs-lookup"><span data-stu-id="4d6a9-103">Docker application DevOps workflow with Microsoft tools</span></span>

<span data-ttu-id="4d6a9-104">*Microsoft Visual Studio, Azure DevOps 서비스, Team Foundation Server 및 Azure Monitor는 포괄적인 에코 시스템 개발 및 IT 운영 팀 프로젝트를 관리 하 고 신속 하 게 구축 하는 도구를 제공 하는 테스트 및 배포에 대 한 컨테이너 화 된 제공 응용 프로그램입니다.*</span><span class="sxs-lookup"><span data-stu-id="4d6a9-104">*Microsoft Visual Studio, Azure DevOps Services, Team Foundation Server, and Azure Monitor provide a comprehensive ecosystem for development and IT operations that give your team the tools to manage projects and rapidly build, test, and deploy containerized applications.*</span></span>

<span data-ttu-id="4d6a9-105">Visual Studio 및 Team Foundation Server 온-프레미스와 클라우드의 Azure DevOps 서비스를 사용 하 여 개발 팀 수 생산적으로 빌드, 테스트 및 Windows 또는 Linux를 대상으로 하는 컨테이너 화 된 응용 프로그램을 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-105">With Visual Studio and Azure DevOps Services in the cloud, along with Team Foundation Server on-premises, development teams can productively build, test, and release containerized applications that target either Windows or Linux.</span></span>

<span data-ttu-id="4d6a9-106">Microsoft 도구는 컨테이너 화 된 응용 프로그램의 특정 구현에 대 한 파이프라인을 자동화할 수 있습니다-Docker,.NET Core 또는 다른 플랫폼 조합 등 전역 빌드 및 CI (지속적인 통합) 및 Azure DevOps 서비스 또는 팀을 사용 하 여 테스트 Foundation Server에 연속 배포 (CD) Docker 환경 (개발, 스테이징, 프로덕션)을 하는 데 Azure Monitor를 통해 개발 팀에는 서비스에 대 한 분석 정보를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-106">Microsoft tools can automate the pipeline for specific implementations of containerized applications—Docker, .NET Core, or any combination with other platforms—from global builds and Continuous Integration (CI) and tests with Azure DevOps Services or Team Foundation Server, to Continuous Deployment (CD) to Docker environments (Development, Staging, Production), and to transmit analytics information about the services to the development team through Azure Monitor.</span></span> <span data-ttu-id="4d6a9-107">모든 코드 커밋은 빌드(CI)를 시작하고 특정 컨테이너화된 환경(CD)에 자동으로 서비스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-107">Every code commit can initiate a build (CI) and automatically deploy the services to specific containerized environments (CD).</span></span>

<span data-ttu-id="4d6a9-108">개발자와 테스터는 Microsoft Azure의 템플릿을 사용하여 프로덕션 환경과 유사한 Docker 기반의 개발 및 배포 환경을 쉽고 빠르게 프로비전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-108">Developers and testers can easily and quickly provision production-like development and test environments based on Docker by using templates in Microsoft Azure.</span></span>

<span data-ttu-id="4d6a9-109">컨테이너화된 애플리케이션 개발의 복잡성은 비즈니스 복잡성 및 확장성 요구 사항에 따라 꾸준히 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-109">The complexity of containerized application development increases steadily depending on the business complexity and scalability needs.</span></span> <span data-ttu-id="4d6a9-110">이러한 복잡성의 좋은 예는 마이크로 서비스 아키텍처에 따라 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-110">A good example of this complexity are applications based on microservices architectures.</span></span> <span data-ttu-id="4d6a9-111">이러한 환경에서 성공 하려면 프로젝트가 전체 수명 주기를 자동화 해야-빌드 및 배포 작업 뿐만 아니라 것도 관리 해야 원격 분석 컬렉션과 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-111">To succeed in such an environment, your project must automate the entire life cycle—not only the build and deployment, but it also must manage versions along with the collection of telemetry.</span></span> <span data-ttu-id="4d6a9-112">Azure DevOps 서비스 및 Azure는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-112">Azure DevOps Services and Azure offer the following capabilities:</span></span>

- <span data-ttu-id="4d6a9-113">Azure DevOps Services/Team Foundation Server 소스 코드 관리 (Git 또는 Team Foundation 버전 제어에 따라), Agile 계획 (Agile, 스크럼 및 CMMI 지원 됨), CI, 릴리스 관리 및 Agile 팀을 위한 다른 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-113">Azure DevOps Services/Team Foundation Server source code management (based on Git or Team Foundation Version Control), Agile planning (Agile, Scrum, and CMMI are supported), CI, release management, and other tools for Agile teams.</span></span>

- <span data-ttu-id="4d6a9-114">Azure DevOps 서비스 및 Team Foundation Server는 강력 하 고 증가 에코 시스템 쉽게 수 CI, 빌드, 테스트, 배달, 생성 하 고 있는 릴리스 관리 파이프라인 마이크로 서비스에 대 한 첫 번째 및 타사 확장을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-114">Azure DevOps Services and Team Foundation Server include a powerful and growing ecosystem of first- and third-party extensions with which you easily can construct a CI, build, test, delivery, and release management pipeline for microservices.</span></span>

- <span data-ttu-id="4d6a9-115">Azure DevOps 서비스에서 빌드 파이프라인의 일부로 자동화 된 테스트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-115">Run automated tests as part of your build pipeline in Azure DevOps Services.</span></span>

- <span data-ttu-id="4d6a9-116">Azure DevOps 서비스를 강화할 수 있습니다 DevOps 수명 주기 여러 환경에 업데이트를 사용 하 여 프로덕션 환경 뿐만 아니라도 테스트를 위해 A를 포함 하 여 / B 실험 [카나리아 릴리스](https://martinfowler.com/bliki/CanaryRelease.html)등입니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-116">Azure DevOps Services can tighten the DevOps life cycle with delivery to multiple environments, not just for production environments, but also for testing, including A/B experimentation, [canary releases](https://martinfowler.com/bliki/CanaryRelease.html), and so on.</span></span>

- <span data-ttu-id="4d6a9-117">조직에서는 쉽게 프로 비전 할 Azure 구성 요소 (데이터, PaaS 등)에 대 한 종속성과 함께 Azure Container Registry에 저장 된 비공개 이미지에서 Docker 컨테이너 사용 하 여 이미 편한 도구를 사용 하 여 Azure Resource Manager 템플릿을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-117">Organizations easily can provision Docker containers from private images stored in Azure Container Registry along with any dependency on Azure components (Data, PaaS, etc.) using Azure Resource Manager templates with tools they're already comfortable with.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4d6a9-118">[이전](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[다음](docker-application-outer-loop-devops-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4d6a9-118">[Previous](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
[Next](docker-application-outer-loop-devops-workflow.md)</span></span>
