---
title: Docker란?
description: Docker에 대해 좀 더 깊이 생각해 보세요. 여기서 간단한 비유가 도움이 될 수 있습니다.
ms.date: 02/15/2019
ms.openlocfilehash: 7fd3c599afda2d59e0d56756bd61495f2d0370a0
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770712"
---
# <a name="what-is-docker"></a><span data-ttu-id="0ad4c-103">Docker란?</span><span class="sxs-lookup"><span data-stu-id="0ad4c-103">What is Docker?</span></span>

<span data-ttu-id="0ad4c-104">[Docker](https://www.docker.com/)는 클라우드 또는 온-프레미스로 실행될 수 있는 이식 가능하고 문제를 스스로 해결할 수 있는 컨테이너로서 애플리케이션 배포를 자동화하기 위한 [오픈 소스 프로젝트](https://github.com/docker/docker)입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.</span></span> <span data-ttu-id="0ad4c-105">Docker는 Microsoft를 비롯한 클라우드, Linux 및 Windows 공급 업체와 협업하여 이 기술을 장려하고 발전시키는 [회사](https://www.docker.com/)이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-105">Docker is also a [company](https://www.docker.com/) that promotes and evolves this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![Docker 컨테이너는 고객 데이터 센터의 온-프레미스, 외부 서비스 공급자 또는 Azure의 클라우드에서, 어디서나 실행할 수 있습니다.](./media/image2.png)

<span data-ttu-id="0ad4c-107">**그림 1-2**.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-107">**Figure 1-2**.</span></span> <span data-ttu-id="0ad4c-108">Docker는 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포</span><span class="sxs-lookup"><span data-stu-id="0ad4c-108">Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="0ad4c-109">Docker 이미지 컨테이너는 Linux 및 Windows에서 기본적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-109">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="0ad4c-110">그러나 Windows 이미지는 Windows 호스트에서만 실행할 수 있고 Linux 이미지는 Linux 호스트 및 Windows 호스트(지금까지 Hyper-V Linux VM 사용)에서 실행할 수 있습니다. 여기서 호스트는 서버 또는 VM을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-110">However, Windows images can run only on Windows hosts and Linux images can run on Linux hosts and Windows hosts (using a Hyper-V Linux VM, so far), where host means a server or a VM.</span></span>

<span data-ttu-id="0ad4c-111">개발자는 Windows, Linux 또는 macOS에서 개발 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-111">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="0ad4c-112">개발자는 개발 컴퓨터에서 앱 및 해당 종속성을 비롯하여 Docker 이미지가 배포된 Docker 호스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-112">On the development computer, the developer runs a Docker host where Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="0ad4c-113">Linux 또는 Mac에서 작업하는 개발자는 Linux 기반의 Docker 호스트를 사용하고 Linux 컨테이너용 이미지만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-113">Developers who work on Linux or on the Mac, use a Docker host that's Linux-based, and they can only create images for Linux containers.</span></span> <span data-ttu-id="0ad4c-114">(Mac에서 작업하는 개발자는 macOS에서 코드를 편집하거나 Docker CLI(명령줄 인터페이스)를 실행할 수 있지만, 이 작성 시 컨테이너가 macOS에서 직접 실행되지 않습니다.) Windows에서 작업하는 개발자는 Linux 또는 Windows 컨테이너용 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-114">(Developers working on the Mac can edit code or run the Docker command-line interface (CLI) from macOS, but as of this writing, containers don't run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="0ad4c-115">개발 환경에서 컨테이너를 호스트하고 추가 개발자 도구를 제공하기 위해 Docker는 Windows 또는 macOS용 [Docker CE(Community Edition)](https://www.docker.com/community-edition)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-115">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="0ad4c-116">이러한 제품은 컨테이너를 호스트하는 데 필요한 VM(Docker 호스트)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-116">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="0ad4c-117">Docker는 기업 개발용으로 설계되고 프로덕션 환경에서 대규모의 업무상 중요한 애플리케이션을 빌드, 제공 및 실행하는 IT 팀에서 사용되는 [Docker EE(Enterprise Edition)](https://www.docker.com/enterprise-edition)도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-117">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="0ad4c-118">[Windows 컨테이너](/virtualization/windowscontainers/about/)를 실행하기 위해 다음 두 가지 유형의 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-118">To run [Windows Containers](/virtualization/windowscontainers/about/), there are two types of runtimes:</span></span>

- <span data-ttu-id="0ad4c-119">**Windows Server 컨테이너**는 프로세스 및 네임스페이스 격리 기술을 통해 애플리케이션 격리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-119">**Windows Server Containers** provide application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="0ad4c-120">Windows Server 컨테이너는 컨테이너 호스트와 호스트에서 실행 중인 모든 컨테이너와 커널을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-120">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

- <span data-ttu-id="0ad4c-121">**Hyper-V 컨테이너**는 고도로 최적화된 가상 머신에서 각 컨테이너를 실행하여 Windows Server 컨테이너가 제공하는 격리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-121">**Hyper-V Containers** expand on the isolation provided by Windows Server Containers by running each container in a highly optimized virtual machine.</span></span> <span data-ttu-id="0ad4c-122">이 구성에서 컨테이너 호스트의 커널은 Hyper-V 컨테이너와 공유되지 않으므로 격리 기능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-122">In this configuration, the kernel of the container host isn't shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="0ad4c-123">이러한 컨테이너의 이미지가 생성되고 동일한 방식으로만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-123">The images for these containers are created and work just the same way.</span></span> <span data-ttu-id="0ad4c-124">차이점은 이미지에서 컨테이너가 생성되는 방식에 있으며, Hyper-V 컨테이너를 실행하려면 추가 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-124">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="0ad4c-125">자세한 내용은 [Hyper-V 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-125">For details, see [Hyper-V Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).</span></span>

## <a name="comparing-docker-containers-with-virtual-machines"></a><span data-ttu-id="0ad4c-126">Docker 컨테이너와 가상 머신 비교</span><span class="sxs-lookup"><span data-stu-id="0ad4c-126">Comparing Docker containers with virtual machines</span></span>

<span data-ttu-id="0ad4c-127">그림 1-3은 VM과 Docker 컨테이너 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-127">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

![VM의 경우 기본적으로 호스트 서버에 세 가지 기본 계층인 인프라, 호스트 운영 체제 및 하이퍼바이저가 있고, 이들 계층 위에서 각 VM에는 고유한 OS 및 모든 필요한 라이브러리가 포함됩니다.](./media/image3.png)

<span data-ttu-id="0ad4c-130">**그림 1-3**.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-130">**Figure 1-3**.</span></span> <span data-ttu-id="0ad4c-131">기존의 가상 머신과 Docker 컨테이너 비교</span><span class="sxs-lookup"><span data-stu-id="0ad4c-131">Comparison of traditional virtual machines to Docker containers</span></span>

<span data-ttu-id="0ad4c-132">컨테이너는 훨씬 적은 리소스를 필요로 하므로(예: 전체 OS가 필요하지 않음) 보다 쉽고 빠르게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-132">Because containers require far fewer resources (for example, they don't need a full OS), they're easy to deploy and they start fast.</span></span> <span data-ttu-id="0ad4c-133">따라서 밀도가 높아지고, 이는 동일한 하드웨어 장치에서 더 많은 서비스를 실행할 수 있어 비용을 절감할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-133">This allows you to have higher density, meaning that it allows you to run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="0ad4c-134">동일한 커널에서 실행되는 부작용으로 VM보다 격리성은 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-134">As a side effect of running on the same kernel, you get less isolation than VMs.</span></span>

<span data-ttu-id="0ad4c-135">이미지의 주요 목표는 서로 다른 배포에서 동일한 환경(종속성)을 보장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-135">The main goal of an image is to ensure the same environment (dependencies) across different deployments.</span></span> <span data-ttu-id="0ad4c-136">즉, 머신에서 이를 디버깅한 다음, 동일한 환경의 다른 머신에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-136">This means that you can debug it on your machine and then deploy it to another machine, the same environment guaranteed.</span></span>

<span data-ttu-id="0ad4c-137">컨테이너 이미지는 앱 또는 서비스를 패키지로 만들고 이를 안정적이고 재현 가능한 방식으로 배포하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-137">A container image is a way to package an app or service and deploy it in a reliable and reproducible way.</span></span> <span data-ttu-id="0ad4c-138">Docker는 기술일 뿐만 아니라 철학이면서 프로세스이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-138">You could say that Docker isn't only a technology but also a philosophy and a process.</span></span>

<span data-ttu-id="0ad4c-139">Docker를 사용할 때 개발자는 “내 머신에서 작동하는데 왜 프로덕션 환경에서는 안 되지?”라고 말하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-139">When using Docker, you won't hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="0ad4c-140">패키지된 Docker 애플리케이션은 지원되는 모든 Docker 환경에서 실행될 수 있기 때문에 "Docker에서 실행"되고 모든 배포 대상(예: 개발, QA, 스테이징 및 프로덕션)에서 의도된 방식으로 실행된다고 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-140">They can just say, "It runs on Docker", because the packaged Docker application can be executed on any supported Docker environment, and it runs the way it was intended to on all deployment targets (such as Dev, QA, staging, and production).</span></span>

## <a name="a-simple-analogy"></a><span data-ttu-id="0ad4c-141">간단한 비유</span><span class="sxs-lookup"><span data-stu-id="0ad4c-141">A simple analogy</span></span>

<span data-ttu-id="0ad4c-142">간단한 비유는 Docker의 핵심 개념을 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-142">Perhaps a simple analogy can help getting the grasp of the core concept of Docker.</span></span>

<span data-ttu-id="0ad4c-143">잠시 시간을 1950년대로 되돌려 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-143">Let's go back in time to the 1950s for a moment.</span></span> <span data-ttu-id="0ad4c-144">워드 프로세서가 없었고 모든 곳에서 일종의 복사기가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-144">There were no word processors, and the photocopiers were used everywhere (well, kind of).</span></span>

<span data-ttu-id="0ad4c-145">각 고객의 주소에 물리적으로 배달되도록 실제 종이와 봉투를 사용하여 고객에게 편지를 우편으로 보내기 위해 필요에 따라 여러 묶음의 편지를 신속하게 발송하는 일을 담당한다고 가정해 보겠습니다(그 당시에는 전자 메일이 없었음).</span><span class="sxs-lookup"><span data-stu-id="0ad4c-145">Imagine you're responsible for quickly issuing batches of letters as required, to mail them to customers, using real paper and envelopes, to be delivered physically to each customer's address (there was no email back then).</span></span>

<span data-ttu-id="0ad4c-146">문득, 편지는 편지의 목적에 맞게 필요에 따라 선택 및 정렬된 많은 단락 집합으로 구성될 뿐이라는 사실을 인식하고, 두둑한 월급 인상을 기대하며 편지를 신속하게 발송하는 시스템을 고안합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-146">At some point, you realize the letters are just a composition of a large set of paragraphs, which are picked and arranged as needed, according to the purpose of the letter, so you devise a system to issue letters quickly, expecting to get a hefty raise.</span></span>

<span data-ttu-id="0ad4c-147">시스템은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-147">The system is simple:</span></span>

1. <span data-ttu-id="0ad4c-148">각각 하나의 단락을 포함하는 한 데크의 투명 시트로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-148">You begin with a deck of transparent sheets containing one paragraph each.</span></span>

2. <span data-ttu-id="0ad4c-149">편지 집합을 발송하려면 필요한 단락이 포함된 시트를 선택한 후 잘 보고 읽을 수 있도록 시트를 쌓고 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-149">To issue a set of letters, you pick the sheets with the paragraphs you need, then you stack and align them so they look and read fine.</span></span>

3. <span data-ttu-id="0ad4c-150">마지막으로 해당 집합을 복사기에 놓고 시작을 눌러 필요한 만큼 편지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-150">Finally, you place the set in the photocopier and press start to produce as many letters as required.</span></span>

<span data-ttu-id="0ad4c-151">이것은 Docker의 핵심 아이디어를 단순화한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-151">So, simplifying, that's the core idea of Docker.</span></span>

<span data-ttu-id="0ad4c-152">Docker에서 각 계층은 프로그램 설치 등의 명령을 실행한 후 파일 시스템에 발생하는 변경 내용의 결과 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-152">In Docker, each layer is the resulting set of changes that happen to the filesystem after executing a command, such as, installing a program.</span></span>

<span data-ttu-id="0ad4c-153">따라서 계층이 복사된 후 파일 시스템을 “표시”하면 프로그램 설치 시 계층을 포함한 모든 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-153">So, when you "look" at the filesystem after the layer has been copied, you see all the files, included the layer when the program was installed.</span></span>

<span data-ttu-id="0ad4c-154">이미지는 운영 체제가 이미 설치된 “컴퓨터”에 설치할 준비가 된 보조 읽기 전용 하드 디스크라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-154">You can think of an image as an auxiliary read-only hard disk ready to be installed in a "computer" where the operating system is already installed.</span></span>

<span data-ttu-id="0ad4c-155">마찬가지로 컨테이너는 이미지 하드 디스크가 설치된 “컴퓨터”로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-155">Similarly, you can think of a container as the "computer" with the image hard disk installed.</span></span> <span data-ttu-id="0ad4c-156">컴퓨터처럼 컨테이너의 전원을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-156">The container, just like a computer, can be powered on or off.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0ad4c-157">[이전](index.md)
>[다음](docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="0ad4c-157">[Previous](index.md)
[Next](docker-terminology.md)</span></span>
