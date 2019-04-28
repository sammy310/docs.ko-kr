---
title: Docker 컨테이너, 이미지 및 레지스트리
description: 레지스트리에 Docker 방식으로 응용 프로그램 배포의 전체 재생는 중요 한 역할에 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795327"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="38520-103">Docker 컨테이너, 이미지 및 레지스트리</span><span class="sxs-lookup"><span data-stu-id="38520-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="38520-104">Docker를 사용 하는 경우 만든 앱 또는 서비스 및 패키지를 하 고 컨테이너 이미지에 종속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38520-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="38520-105">이미지는 앱 또는 서비스와 그 구성 및 종속성을 정적으로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="38520-106">앱 또는 서비스를 실행하려면 앱의 이미지가 인스턴스화되어 Docker 호스트에서 실행되는 컨테이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38520-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="38520-107">컨테이너는 개발 환경 또는 PC에서 초기에 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="38520-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="38520-108">레지스트리에 이미지 라이브러리로 사용 되는 이미지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-108">You store images in a registry, that acts as a library of images.</span></span> <span data-ttu-id="38520-109">프로덕션 오 케 스트레이 터에 배포할 때 레지스트리를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="38520-110">Docker는 [Docker 허브](https://hub.docker.com/)를 통해 공용 레지스트리를 관리합니다. 다른 공급업체는 다른 이미지 컬렉션을 위한 [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) 등의 레지스트리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="38520-111">또는 기업에서는 자체 Docker 이미지를 위해 개인 레지스트리 온-프레미스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38520-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="38520-112">그림 1-4의 Docker 이미지와 레지스트리가 다른 구성 요소에 연결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38520-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="38520-113">그것은 또한 공급업체로부터 제공되는 여러 레지스트리를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="38520-113">It also shows the multiple registry offerings from vendors.</span></span>

![Docker에서 기본 분류: 이미지 저장 및 서비스 또는 웹 앱을 실행할 컨테이너를 빌드하기 위한 가져올 수 있게 되는 관련 서적 등 레지스트리는.](./media/image4.png)

<span data-ttu-id="38520-118">**그림 1-4**.</span><span class="sxs-lookup"><span data-stu-id="38520-118">**Figure 1-4**.</span></span> <span data-ttu-id="38520-119">Docker 용어 및 개념의 분류</span><span class="sxs-lookup"><span data-stu-id="38520-119">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="38520-120">레지스트리에 이미지를 배치 하 여 모든 프레임 워크 수준 종속성을 포함 하 여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38520-120">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="38520-121">하면 다음 버전 및 여러 환경에서 이미지를 배포한 따라서 일관 된 배포 단위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-121">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="38520-122">온-프레미스 또는 클라우드에서 호스팅되는 개인 이미지 레지스티리는 다음과 같은 경우에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="38520-122">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="38520-123">기밀로 인해 이미지를 공개적으로 공유해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="38520-123">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="38520-124">이미지와 선택한 배포 환경 사이에는 최소 네트워크 대기 시간이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="38520-124">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="38520-125">예를 들어 프로덕션 환경의 Azure 인 경우 아마도 하려는에서 이미지를 저장할 [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) 네트워크 대기 시간이 최소화 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38520-125">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="38520-126">프로덕션 환경이 동일한 로컬 네트워크 내에서 사용 가능한 온-프레미스 Docker Trusted Registry인 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="38520-126">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="38520-127">[이전](docker-terminology.md)
>[다음](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="38520-127">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
