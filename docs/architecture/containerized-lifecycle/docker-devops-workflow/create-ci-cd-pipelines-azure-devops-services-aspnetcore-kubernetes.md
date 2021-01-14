---
title: Azure DevOps Services에서 컨테이너의 .NET 애플리케이션에 대한 CI/CD 파이프라인 만들기 및 Kubernetes 클러스터에 배포
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기
ms.date: 01/06/2021
ms.openlocfilehash: ef994f132716547ee402237016ee71013528d779
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970488"
---
# <a name="create-cicd-pipelines-in-azure-devops-services-for-a-net-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="19b24-103">Azure DevOps Services에서 컨테이너의 .NET 애플리케이션에 대한 CI/CD 파이프라인 만들기 및 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="19b24-103">Create CI/CD pipelines in Azure DevOps Services for a .NET application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="19b24-104">그림 5-12에서는 코드 관리, 코드 컴파일, Docker 이미지 빌드, Docker 레지스트리로 Docker 이미지 푸시, 마지막으로 Azure의 Kubernetes 클러스터에 배포하는 과정을 다루는 엔드투엔드 DevOps 시나리오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![워크플로: 개발 머신에서 시작합니다.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="19b24-107">**그림 5-12**.</span><span class="sxs-lookup"><span data-stu-id="19b24-107">**Figure 5-12**.</span></span> <span data-ttu-id="19b24-108">Docker 이미지를 만들어서 Azure의 Kubernetes 클러스터에 배포하는 CI/CD 시나리오</span><span class="sxs-lookup"><span data-stu-id="19b24-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="19b24-109">두 파이프라인(빌드/CI 및 릴리스/CD)이 Docker 레지스트리(예: Docker Hub 또는 Azure Container Registry)를 통해 연결되는 것을 강조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="19b24-110">Docker가 없는 기존 CI/CD 프로세스와 다른 주요 차이점 중 하나는 Docker 레지스트리입니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="19b24-111">그림 5-13처럼 첫 번째 단계는 빌드/CI 파이프라인입니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="19b24-112">Azure DevOps Services에서 코드를 컴파일하고, Docker 이미지를 만들고, Docker Hub 또는 Azure Container Registry 같은 Docker 레지스트리로 푸시하는 빌드/CI 파이프라인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Azure DevOps의 브라우저 보기, 빌드 프로세스 작업 정의](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="19b24-114">**그림 5-13**.</span><span class="sxs-lookup"><span data-stu-id="19b24-114">**Figure 5-13**.</span></span> <span data-ttu-id="19b24-115">Docker 이미지를 빌드하여 Docker 레지스트리로 푸시하는 Azure DevOps의 빌드/CI 파이프라인</span><span class="sxs-lookup"><span data-stu-id="19b24-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="19b24-116">두 번째 단계는 배포/릴리스 파이프라인을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="19b24-117">Azure DevOps Services에서는 그림 5-14처럼 Azure DevOps Services에 대한 Kubernetes 작업을 사용하여 Kubernetes 클러스터를 대상으로 하는 배포 파이프라인을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19b24-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Azure DevOps의 브라우저 보기, Kubernetes에 배포 작업 정의](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="19b24-119">**그림 5-14**.</span><span class="sxs-lookup"><span data-stu-id="19b24-119">**Figure 5-14**.</span></span> <span data-ttu-id="19b24-120">Kubernetes 클러스터에 배포하는 Azure DevOps Services의 릴리스/CD 파이프라인</span><span class="sxs-lookup"><span data-stu-id="19b24-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> <span data-ttu-id="19b24-121">[!연습] Kubernetes에 eShopModernized 배포:</span><span class="sxs-lookup"><span data-stu-id="19b24-121">[!Walkthrough] Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="19b24-122">Kubernetes에 배포하는 Azure DevOps CI/CD 파이프라인의 구체적인 연습은 다음 게시물을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="19b24-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: </span></span>\
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="19b24-123">[이전](docker-application-outer-loop-devops-workflow.md)
>[다음](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="19b24-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
