---
title: 컨테이너 및 Docker 소개
description: Docker를 사용 하는 주요 이점은의 높은 수준의 개요를 가져옵니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="8bf7e-103">컨테이너 및 Docker 소개</span><span class="sxs-lookup"><span data-stu-id="8bf7e-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="8bf7e-104">*컨테이너 화는 응용 프로그램 또는 서비스 및 해당 종속성 (배포 매니페스트 파일로 추상화) 해당 구성 된 패키지는 컨테이너 이미지로 소프트웨어 개발 방법입니다. 그런 다음 단위로 컨테이너 화 된 응용 프로그램을 테스트를 컨테이너 이미지 인스턴스로 호스트 운영 체제 (OS)를 배포 합니다.*</span><span class="sxs-lookup"><span data-stu-id="8bf7e-104">*Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image. You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system (OS).*</span></span>

<span data-ttu-id="8bf7e-105">배송 컨테이너를 사용하여 컨테이너 안에 들어있는 화물에 상관없이 상품을 배, 기차 또는 트럭으로 운반하듯이 소프트웨어 컨테이너도 다양한 코드 및 종속성을 포함할 수 있는 소프트웨어 배포의 표준 단위 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-105">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software deployment that can contain different code and dependencies.</span></span> <span data-ttu-id="8bf7e-106">이러한 방식의 소프트웨어 컨테이너화를 통해 개발자와 IT 전문가는 수정 과정을 거의 거치지 않고 모든 환경에서 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-106">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="8bf7e-107">또한 컨테이너는 공유 OS에서 애플리케이션을 서로 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-107">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="8bf7e-108">컨테이너화된 애플리케이션은 OS(Linux 또는 Windows)에서 차례대로 실행되는 컨테이너 호스트의 맨 위에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-108">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="8bf7e-109">따라서 컨테이너 가상 머신 (VM) 이미지 보다 훨씬 더 작은 공간을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-109">Containers therefore have a much smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="8bf7e-110">그림 1-1에 표시 된 것 처럼 각 컨테이너는 전체 웹 응용 프로그램 또는 서비스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-110">Each container can run a whole web application or a service, as shown in Figure 1-1.</span></span> <span data-ttu-id="8bf7e-111">이 예제에서는 Docker 호스트가 컨테이너 호스트 및 App1, App2, Svc1, 및 Svc2가 컨테이너 화 된 응용 프로그램 또는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-111">In this example, Docker host is a container host, and App1, App2, Svc1, and Svc2 are containerized applications or services.</span></span>

![VM 또는 물리적 서버의 OS에서 실행 중인 두 개의 애플리케이션 및 두 개의 서비스](./media/image1.png)

<span data-ttu-id="8bf7e-113">**그림 1-1**.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-113">**Figure 1-1**.</span></span> <span data-ttu-id="8bf7e-114">컨테이너 호스트에서 실행되는 여러 컨테이너</span><span class="sxs-lookup"><span data-stu-id="8bf7e-114">Multiple containers running on a container host</span></span>

<span data-ttu-id="8bf7e-115">컨테이너화로 얻을 수 있는 또 다른 이점은 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-115">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="8bf7e-116">단기 작업에 대한 새 컨테이너를 만들어 신속하게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-116">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="8bf7e-117">애플리케이션의 관점에서 볼 때 이미지 인스턴스화(컨테이너 생성)는 서비스 또는 웹앱과 같은 프로세스 인스턴스화와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-117">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="8bf7e-118">그러나 안정성을 생각한다면, 동일한 이미지의 여러 인스턴스를 여러 호스트 서버에서 실행할 경우 일반적으로 기본 도메인이 다른 다양한 호스트 서버 또는 VM에서 각 컨테이너(이미지 인스턴스)를 실행하려 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-118">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="8bf7e-119">즉, 컨테이너는 전체 응용 프로그램 수명 주기 워크플로에서 격리, 이식성, 민첩성, 확장성 및 컨트롤의 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-119">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application lifecycle workflow.</span></span> <span data-ttu-id="8bf7e-120">가장 중요 한 장점은 개발팀과 운영팀 간 제공 하는 환경 격리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bf7e-120">The most important benefit is the environment isolation provided between Dev and Ops.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="8bf7e-121">다음</span><span class="sxs-lookup"><span data-stu-id="8bf7e-121">Next</span></span>](what-is-docker.md)
