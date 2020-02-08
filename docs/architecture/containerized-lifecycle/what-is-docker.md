---
title: Docker란?
description: Docker에 대해 좀 더 깊이 생각해 보세요. 여기서 간단한 비유가 도움이 될 수 있습니다.
ms.date: 02/15/2019
ms.openlocfilehash: e3b3685f2fc6d5a9d33bb176d04ca910f0289344
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919872"
---
# <a name="what-is-docker"></a><span data-ttu-id="018ed-103">Docker란?</span><span class="sxs-lookup"><span data-stu-id="018ed-103">What is Docker?</span></span>

<span data-ttu-id="018ed-104">[Docker](https://www.docker.com/)는 클라우드 또는 온-프레미스로 실행될 수 있는 이식 가능하고 문제를 스스로 해결할 수 있는 컨테이너로서 애플리케이션 배포를 자동화하기 위한 [오픈 소스 프로젝트](https://github.com/docker/docker)입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.</span></span> <span data-ttu-id="018ed-105">Docker는 Microsoft를 비롯한 클라우드, Linux 및 Windows 공급 업체와 협업하여 이 기술을 장려하고 발전시키는 [회사](https://www.docker.com/)이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-105">Docker is also a [company](https://www.docker.com/) that promotes and evolves this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![Docker 컨테이너를 실행할 수 있는 위치를 보여 주는 다이어그램](./media/what-is-docker/docker-containers-run-anywhere.png)

<span data-ttu-id="018ed-107">**그림 1-2**.</span><span class="sxs-lookup"><span data-stu-id="018ed-107">**Figure 1-2**.</span></span> <span data-ttu-id="018ed-108">Docker는 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포</span><span class="sxs-lookup"><span data-stu-id="018ed-108">Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="018ed-109">위 다이어그램에 나와 있듯이 Docker 컨테이너는 고객 데이터 센터의 온-프레미스, 외부 서비스 공급자 또는 Azure의 클라우드에서, 어디서나 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-109">As shown in the above diagram, Docker containers can run anywhere, on-premises in the customer datacenter, in an external service provider or in the cloud, on Azure.</span></span> <span data-ttu-id="018ed-110">또한 Docker 이미지 컨테이너는 Linux 및 Windows에서 기본적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-110">Docker image containers can also run natively on Linux and Windows.</span></span> <span data-ttu-id="018ed-111">그러나 Windows 이미지는 Windows 호스트에서만 실행할 수 있고 Linux 이미지는 Linux 호스트 및 Windows 호스트(지금까지 Hyper-V Linux VM 사용)에서 실행할 수 있습니다. 여기서 호스트는 서버 또는 VM을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-111">However, Windows images can run only on Windows hosts and Linux images can run on Linux hosts and Windows hosts (using a Hyper-V Linux VM, so far), where host means a server or a VM.</span></span>

<span data-ttu-id="018ed-112">개발자는 Windows, Linux 또는 macOS에서 개발 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-112">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="018ed-113">개발자는 개발 컴퓨터에서 앱 및 해당 종속성을 비롯하여 Docker 이미지가 배포된 Docker 호스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-113">On the development computer, the developer runs a Docker host where Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="018ed-114">Linux 또는 Mac에서 작업하는 개발자는 Linux 기반의 Docker 호스트를 사용하고 Linux 컨테이너용 이미지만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-114">Developers who work on Linux or on the Mac, use a Docker host that's Linux-based, and they can only create images for Linux containers.</span></span> <span data-ttu-id="018ed-115">(Mac에서 작업하는 개발자는 macOS에서 코드를 편집하거나 Docker CLI를 실행할 수 있지만 이 문서를 작성하는 시점에는 컨테이너가 macOS에서 직접 실행되지 않습니다.) Windows에서 작업하는 개발자는 Linux 또는 Windows 컨테이너용 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-115">(Developers working on the Mac can edit code or run the Docker CLI from macOS, but as of this writing, containers don't run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="018ed-116">개발 환경에서 컨테이너를 호스트하고 추가 개발자 도구를 제공하기 위해 Docker는 Windows 또는 macOS용 [Docker CE(Community Edition)](https://www.docker.com/community-edition)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-116">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="018ed-117">이러한 제품은 컨테이너를 호스트하는 데 필요한 VM(Docker 호스트)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-117">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="018ed-118">Docker는 기업 개발용으로 설계되고 프로덕션 환경에서 대규모의 업무상 중요한 애플리케이션을 빌드, 제공 및 실행하는 IT 팀에서 사용되는 [Docker EE(Enterprise Edition)](https://www.docker.com/enterprise-edition)도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-118">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="018ed-119">[Windows 컨테이너](/virtualization/windowscontainers/about/)를 실행하기 위해 다음 두 가지 유형의 런타임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-119">To run [Windows Containers](/virtualization/windowscontainers/about/), there are two types of runtimes:</span></span>

- <span data-ttu-id="018ed-120">**Windows Server 컨테이너**는 프로세스 및 네임스페이스 격리 기술을 통해 애플리케이션 격리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-120">**Windows Server Containers** provide application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="018ed-121">Windows Server 컨테이너는 컨테이너 호스트와 호스트에서 실행 중인 모든 컨테이너와 커널을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-121">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

- <span data-ttu-id="018ed-122">**Hyper-V 컨테이너**는 고도로 최적화된 가상 머신에서 각 컨테이너를 실행하여 Windows Server 컨테이너가 제공하는 격리를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-122">**Hyper-V Containers** expand on the isolation provided by Windows Server Containers by running each container in a highly optimized virtual machine.</span></span> <span data-ttu-id="018ed-123">이 구성에서 컨테이너 호스트의 커널은 Hyper-V 컨테이너와 공유되지 않으므로 격리 기능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-123">In this configuration, the kernel of the container host isn't shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="018ed-124">이러한 컨테이너의 이미지가 생성되고 동일한 방식으로만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-124">The images for these containers are created and work just the same way.</span></span> <span data-ttu-id="018ed-125">차이점은 이미지에서 컨테이너가 생성되는 방식에 있으며, Hyper-V 컨테이너를 실행하려면 추가 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-125">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="018ed-126">자세한 내용은 [Hyper-V 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="018ed-126">For details, see [Hyper-V Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).</span></span>

## <a name="comparing-docker-containers-with-virtual-machines"></a><span data-ttu-id="018ed-127">Docker 컨테이너와 가상 머신 비교</span><span class="sxs-lookup"><span data-stu-id="018ed-127">Comparing Docker containers with virtual machines</span></span>

<span data-ttu-id="018ed-128">그림 1-3은 VM과 Docker 컨테이너 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-128">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

![VM 및 컨테이너 환경을 비교하는 다이어그램](./media/what-is-docker/comparison-vms-docker-conatiners.png)

<span data-ttu-id="018ed-130">**그림 1-3**.</span><span class="sxs-lookup"><span data-stu-id="018ed-130">**Figure 1-3**.</span></span> <span data-ttu-id="018ed-131">기존의 가상 머신과 Docker 컨테이너 비교</span><span class="sxs-lookup"><span data-stu-id="018ed-131">Comparison of traditional virtual machines to Docker containers</span></span>

<span data-ttu-id="018ed-132">위 다이어그램에 나와 있듯이 VM에는 호스트 서버에 3개의 기본 레이어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-132">As shown in the above diagram, for VMs, there are three base layers in the host server.</span></span> <span data-ttu-id="018ed-133">아래부터 위로 순서대로 인프라, 호스트 운영 체제 및 하이퍼바이저입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-133">From the bottom-up: Infrastructure, Host Operating System, and a Hypervisor.</span></span> <span data-ttu-id="018ed-134">그 위로 각 VM에 고유 OS와 모든 필요한 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-134">On top of all that, each VM has its own OS and all necessary libraries.</span></span> <span data-ttu-id="018ed-135">반면, Docker의 경우 호스트 서버에는 인프라와 OS만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-135">On the other hand, for Docker, the host server only has the Infrastructure and the OS.</span></span> <span data-ttu-id="018ed-136">그 위에서 컨테이너 엔진은 컨테이너를 격리된 상태로 유지하지만 단일 기본 OS 서비스를 공유할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-136">On top of that, the container engine keeps containers isolated, but lets them share the single base OS's services.</span></span>

<span data-ttu-id="018ed-137">컨테이너는 훨씬 적은 리소스를 필요로 하므로(예: 전체 OS가 필요하지 않음) 보다 쉽고 빠르게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-137">Because containers require far fewer resources (for example, they don't need a full OS), they're easy to deploy and they start fast.</span></span> <span data-ttu-id="018ed-138">따라서 밀도가 높아지고, 이는 동일한 하드웨어 장치에서 더 많은 서비스를 실행할 수 있어 비용을 절감할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-138">This allows you to have higher density, meaning that it allows you to run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="018ed-139">동일한 커널에서 실행되는 부작용으로 VM보다 격리성은 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-139">As a side effect of running on the same kernel, you get less isolation than VMs.</span></span>

<span data-ttu-id="018ed-140">이미지의 주요 목표는 서로 다른 배포에서 동일한 환경(종속성)을 보장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-140">The main goal of an image is to ensure the same environment (dependencies) across different deployments.</span></span> <span data-ttu-id="018ed-141">즉, 머신에서 이를 디버깅한 다음, 동일한 환경의 다른 머신에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-141">This means that you can debug it on your machine and then deploy it to another machine, the same environment guaranteed.</span></span>

<span data-ttu-id="018ed-142">컨테이너 이미지는 앱 또는 서비스를 패키지로 만들고 이를 안정적이고 재현 가능한 방식으로 배포하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-142">A container image is a way to package an app or service and deploy it in a reliable and reproducible way.</span></span> <span data-ttu-id="018ed-143">Docker는 기술일 뿐만 아니라 철학이면서 프로세스이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-143">You could say that Docker isn't only a technology but also a philosophy and a process.</span></span>

<span data-ttu-id="018ed-144">Docker를 사용할 때 개발자는 “내 머신에서 작동하는데 왜 프로덕션 환경에서는 안 되지?”라고 말하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-144">When using Docker, you won't hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="018ed-145">패키지된 Docker 애플리케이션은 지원되는 모든 Docker 환경에서 실행될 수 있기 때문에 "Docker에서 실행"되고 모든 배포 대상(예: 개발, QA, 스테이징 및 프로덕션)에서 의도된 방식으로 실행된다고 말할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-145">They can just say, "It runs on Docker", because the packaged Docker application can be executed on any supported Docker environment, and it runs the way it was intended to on all deployment targets (such as Dev, QA, staging, and production).</span></span>

## <a name="a-simple-analogy"></a><span data-ttu-id="018ed-146">간단한 비유</span><span class="sxs-lookup"><span data-stu-id="018ed-146">A simple analogy</span></span>

<span data-ttu-id="018ed-147">간단한 비유는 Docker의 핵심 개념을 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-147">Perhaps a simple analogy can help getting the grasp of the core concept of Docker.</span></span>

<span data-ttu-id="018ed-148">잠시 시간을 1950년대로 되돌려 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-148">Let's go back in time to the 1950s for a moment.</span></span> <span data-ttu-id="018ed-149">워드 프로세서가 없었고 모든 곳에서 일종의 복사기가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-149">There were no word processors, and the photocopiers were used everywhere (well, kind of).</span></span>

<span data-ttu-id="018ed-150">각 고객의 주소에 물리적으로 배달되도록 실제 종이와 봉투를 사용하여 고객에게 편지를 우편으로 보내기 위해 필요에 따라 여러 묶음의 편지를 신속하게 발송하는 일을 담당한다고 가정해 보겠습니다(그 당시에는 전자 메일이 없었음).</span><span class="sxs-lookup"><span data-stu-id="018ed-150">Imagine you're responsible for quickly issuing batches of letters as required, to mail them to customers, using real paper and envelopes, to be delivered physically to each customer's address (there was no email back then).</span></span>

<span data-ttu-id="018ed-151">문득, 편지는 편지의 목적에 맞게 필요에 따라 선택 및 정렬된 많은 단락 집합으로 구성될 뿐이라는 사실을 인식하고, 두둑한 월급 인상을 기대하며 편지를 신속하게 발송하는 시스템을 고안합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-151">At some point, you realize the letters are just a composition of a large set of paragraphs, which are picked and arranged as needed, according to the purpose of the letter, so you devise a system to issue letters quickly, expecting to get a hefty raise.</span></span>

<span data-ttu-id="018ed-152">시스템은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-152">The system is simple:</span></span>

1. <span data-ttu-id="018ed-153">각각 하나의 단락을 포함하는 한 데크의 투명 시트로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-153">You begin with a deck of transparent sheets containing one paragraph each.</span></span>

2. <span data-ttu-id="018ed-154">편지 집합을 발송하려면 필요한 단락이 포함된 시트를 선택한 후 잘 보고 읽을 수 있도록 시트를 쌓고 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-154">To issue a set of letters, you pick the sheets with the paragraphs you need, then you stack and align them so they look and read fine.</span></span>

3. <span data-ttu-id="018ed-155">마지막으로 해당 집합을 복사기에 놓고 시작을 눌러 필요한 만큼 편지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-155">Finally, you place the set in the photocopier and press start to produce as many letters as required.</span></span>

<span data-ttu-id="018ed-156">이것은 Docker의 핵심 아이디어를 단순화한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-156">So, simplifying, that's the core idea of Docker.</span></span>

<span data-ttu-id="018ed-157">Docker에서 각 계층은 프로그램 설치 등의 명령을 실행한 후 파일 시스템에 발생하는 변경 내용의 결과 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-157">In Docker, each layer is the resulting set of changes that happen to the filesystem after executing a command, such as, installing a program.</span></span>

<span data-ttu-id="018ed-158">따라서 계층이 복사된 후 파일 시스템을 “표시”하면 프로그램 설치 시 계층을 포함한 모든 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-158">So, when you "look" at the filesystem after the layer has been copied, you see all the files, included the layer when the program was installed.</span></span>

<span data-ttu-id="018ed-159">이미지는 운영 체제가 이미 설치된 “컴퓨터”에 설치할 준비가 된 보조 읽기 전용 하드 디스크라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-159">You can think of an image as an auxiliary read-only hard disk ready to be installed in a "computer" where the operating system is already installed.</span></span>

<span data-ttu-id="018ed-160">마찬가지로 컨테이너는 이미지 하드 디스크가 설치된 “컴퓨터”로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-160">Similarly, you can think of a container as the "computer" with the image hard disk installed.</span></span> <span data-ttu-id="018ed-161">컴퓨터처럼 컨테이너의 전원을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="018ed-161">The container, just like a computer, can be powered on or off.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="018ed-162">[이전](index.md)
>[다음](docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="018ed-162">[Previous](index.md)
[Next](docker-terminology.md)</span></span>
