---
title: Docker 애플리케이션에 대한 외부 루프 DevOps 워크플로의 단계
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 2cd769ce9013a8521c53f36b44ea260ceccd48b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795383"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="a1db9-103">Azure DevOps 서비스에서 컨테이너의 .NET Core 2.0 애플리케이션에 대한 CI/CD 파이프라인 만들기 및 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="a1db9-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="a1db9-104">그림 5-12에서 다루는 코드 관리, 코드 컴파일 엔드-투-엔드 DevOps 시나리오를 볼 수 있습니다, Docker 이미지 빌드, Docker 이미지 푸시 Docker 레지스트리를 마지막으로 Azure에서 Kubernetes 클러스터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![워크플로: 개발 컴퓨터에서 시작합니다.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="a1db9-107">**그림 5-12**.</span><span class="sxs-lookup"><span data-stu-id="a1db9-107">**Figure 5-12**.</span></span> <span data-ttu-id="a1db9-108">Docker 이미지를 만들고 Azure에서 Kubernetes 클러스터에 배포 하는 CI/CD 시나리오</span><span class="sxs-lookup"><span data-stu-id="a1db9-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="a1db9-109">두 개의 파이프라인, / CI, 빌드 및 릴리스/CD (예: Docker 허브 또는 Azure Container Registry) Docker 레지스트리를 통해 연결 되어 있는지를 강조 표시 하는 것이 반드시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="a1db9-110">Docker 레지스트리에 Docker 없이 기존 CI/CD 프로세스에 비해 주요 차이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="a1db9-111">그림 5-13에서와 같이 첫 번째 단계는 빌드/CI 파이프라인.</span><span class="sxs-lookup"><span data-stu-id="a1db9-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="a1db9-112">Azure DevOps 서비스에서 코드를 컴파일하려면 코드, Docker 이미지를 만들고 Docker 허브 또는 Azure Container Registry와 같은 Docker 레지스트리로 푸시하는 빌드/CD 파이프라인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-112">In Azure DevOps Services you can create build/CD pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Azure DevOps, 빌드 프로세스 작업 정의의 브라우저 보기입니다.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="a1db9-114">**그림 5-13**.</span><span class="sxs-lookup"><span data-stu-id="a1db9-114">**Figure 5-13**.</span></span> <span data-ttu-id="a1db9-115">Azure DevOps Docker 이미지를 빌드하고 Docker 레지스트리에 이미지 푸시하기 빌드/CI 파이프라인</span><span class="sxs-lookup"><span data-stu-id="a1db9-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="a1db9-116">두 번째 단계는 배포/릴리스 파이프라인을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="a1db9-117">Azure DevOps 서비스에서는 그림 5-14에 나와 있는 것 처럼 Azure DevOps 서비스에 대 한 Kubernetes 작업을 사용 하 여 Kubernetes 클러스터를 대상으로 하는 배포 파이프라인을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Azure DevOps의 브라우저 보기 Kubernetes 작업 정의를 배포 합니다.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="a1db9-119">**그림 5-14**.</span><span class="sxs-lookup"><span data-stu-id="a1db9-119">**Figure 5-14**.</span></span> <span data-ttu-id="a1db9-120">Azure DevOps 서비스 Kubernetes 클러스터에 배포할 릴리스/CD 파이프라인</span><span class="sxs-lookup"><span data-stu-id="a1db9-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [! 연습]<span data-ttu-id="a1db9-121"> eShopModernized Kubernetes에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1db9-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="a1db9-122">Azure DevOps CI/CD 파이프라인의 자세한 연습에 대 한이 게시물을 참조 Kubernetes에 배포 합니다. \\</span><span class="sxs-lookup"><span data-stu-id="a1db9-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="a1db9-123">[이전](docker-application-outer-loop-devops-workflow.md)
>[다음](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="a1db9-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
