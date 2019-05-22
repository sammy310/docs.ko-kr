---
title: ASP.NET Core 웹앱에 대한 Azure 호스팅 권장 사항
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 애플리케이션 설계 | ASP.NET 웹앱에 대한 Azure 호스팅 권장 사항
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 136ad9992ea94b027f095f47df0388408029f24e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638912"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a><span data-ttu-id="460d7-103">ASP.NET Core 웹앱에 대한 Azure 호스팅 권장 사항</span><span class="sxs-lookup"><span data-stu-id="460d7-103">Azure hosting recommendations for ASP.NET Core web apps</span></span>

> <span data-ttu-id="460d7-104">"모든 기간 업무 리더는 IT 부서를 거치지 않고 클라우드(SaaS라고도 함)에서 애플리케이션을 다운로드한 후 잡지를 구독하듯 사용료를 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-104">"Line-of-business leaders everywhere are bypassing IT departments to get applications from the cloud (aka SaaS) and paying for them like they would a magazine subscription.</span></span> <span data-ttu-id="460d7-105">그리고 서비스가 더 이상 필요하지 않으면 사용하지 않는 장비를 굳이 한 구석에 남겨둘 필요 없이 구독을 취소하기만 하면 됩니다.”</span><span class="sxs-lookup"><span data-stu-id="460d7-105">And when the service is no longer required, they can cancel the subscription with no equipment left unused in the corner."</span></span>  
> <span data-ttu-id="460d7-106">_\- Gartner 분석가 Daryl Plummer_</span><span class="sxs-lookup"><span data-stu-id="460d7-106">_\- Daryl Plummer, Gartner analyst_</span></span>

<span data-ttu-id="460d7-107">애플리케이션의 요구 사항 및 아키텍처가 무엇이든 Windows Azure는 이를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-107">Whatever your application's needs and architecture, Windows Azure can support it.</span></span> <span data-ttu-id="460d7-108">호스팅 요구 사항은 수십 가지 서비스로 이루어진 복잡한 애플리케이션에 대한 정적 웹 사이트처럼 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-108">Your hosting needs can be as simple as a static website to a sophisticated application made up of dozens of services.</span></span> <span data-ttu-id="460d7-109">ASP.NET Core 모놀리식 웹 애플리케이션 및 지원 서비스에 권장되는 잘 알려진 구성이 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-109">For ASP.NET Core monolithic web applications and supporting services, there are several well-known configurations that are recommended.</span></span> <span data-ttu-id="460d7-110">이 문서의 권장 사항은 모든 애플리케이션, 개별 프로세스 또는 데이터에 관계없이 호스팅할 리소스의 종류에 따라 그룹화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-110">The recommendations on this article are grouped based on the kind of resource to be hosted, whether full applications, individual processes, or data.</span></span>

## <a name="web-applications"></a><span data-ttu-id="460d7-111">웹 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="460d7-111">Web applications</span></span>

<span data-ttu-id="460d7-112">웹 애플리케이션은 다음을 통해 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-112">Web applications can be hosted with:</span></span>

- <span data-ttu-id="460d7-113">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="460d7-113">App Service Web Apps</span></span>

- <span data-ttu-id="460d7-114">컨테이너</span><span class="sxs-lookup"><span data-stu-id="460d7-114">Containers</span></span>

- <span data-ttu-id="460d7-115">VM(가상 머신)</span><span class="sxs-lookup"><span data-stu-id="460d7-115">Virtual Machines (VMs)</span></span>

<span data-ttu-id="460d7-116">이 중에서 App Service Web Apps는 대부분의 시나리오에 권장되는 접근 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-116">Of these, App Service Web Apps is the recommended approach for most scenarios.</span></span> <span data-ttu-id="460d7-117">마이크로서비스 아키텍처의 경우 컨테이너 기반 접근 방식을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-117">For microservice architectures, consider a container-based approach.</span></span> <span data-ttu-id="460d7-118">애플리케이션을 실행하는 컴퓨터에 대한 더 세부적인 제어가 필요할 경우 Azure Virtual Machines를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-118">If you need more control over the machines running your application, consider Azure Virtual Machines.</span></span>

### <a name="app-service-web-apps"></a><span data-ttu-id="460d7-119">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="460d7-119">App Service Web Apps</span></span>

<span data-ttu-id="460d7-120">App Service Web Apps는 웹 애플리케이션 호스팅에 최적화된 완벽하게 관리되는 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-120">App Service Web Apps offers a fully managed platform optimized for hosting web applications.</span></span> <span data-ttu-id="460d7-121">이는 비즈니스 논리에 집중할 수 있게 해주는 PaaS(Platform-as-a-service) 솔루션이며, Azure는 앱 실행 및 확장에 필요한 인프라를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-121">It's a platform as a service (PaaS) offering that lets you focus on your business logic, while Azure takes care of the infrastructure needed to run and scale the app.</span></span> <span data-ttu-id="460d7-122">App Service Web Apps의 몇 가지 주요 기능:</span><span class="sxs-lookup"><span data-stu-id="460d7-122">Some key features of App Service Web Apps:</span></span>

- <span data-ttu-id="460d7-123">DevOps 최적화(지속적인 통합 및 업데이트, 여러 환경, A/B 테스트, 스크립팅 지원)</span><span class="sxs-lookup"><span data-stu-id="460d7-123">DevOps optimization (continuous integration and delivery, multiple environments, A/B testing, scripting support).</span></span>

- <span data-ttu-id="460d7-124">세계적인 규모 및 고가용성</span><span class="sxs-lookup"><span data-stu-id="460d7-124">Global scale and high availability.</span></span>

- <span data-ttu-id="460d7-125">SaaS 플랫폼 및 온-프레미스 데이터에 대한 연결</span><span class="sxs-lookup"><span data-stu-id="460d7-125">Connections to SaaS platforms and your on-premises data.</span></span>

- <span data-ttu-id="460d7-126">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="460d7-126">Security and compliance.</span></span>

- <span data-ttu-id="460d7-127">Visual Studio 통합</span><span class="sxs-lookup"><span data-stu-id="460d7-127">Visual Studio integration.</span></span>

- <span data-ttu-id="460d7-128">[Web App for Containers](https://azure.microsoft.com/en-us/services/app-service/containers/)를 통한 통해 Linux 및 Windows 컨테이너 지원</span><span class="sxs-lookup"><span data-stu-id="460d7-128">Support for Linux and Windows containers via [Web App for Containers](https://azure.microsoft.com/en-us/services/app-service/containers/).</span></span>

<span data-ttu-id="460d7-129">Azure App Service는 대부분의 웹앱에 가장 적합한 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-129">Azure App Service is the best choice for most web apps.</span></span> <span data-ttu-id="460d7-130">배포 및 관리가 플랫폼에 통합되어 있고, 사이트가 높은 트래픽 부하를 처리하기 위해 빠르게 확장될 수 있으며, 기본 제공되는 부하 분산 및 트래픽 관리자가 고가용성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-130">Deployment and management are integrated into the platform, sites can scale quickly to handle high traffic loads, and the built-in load balancing and traffic manager provide high availability.</span></span> <span data-ttu-id="460d7-131">온라인 마이그레이션 도구를 사용하여 기존 사이트를 Azure App Service로 쉽게 이동하거나, 웹 애플리케이션 갤러리에서 오픈 소스 애플리케이션을 사용하거나, 원하는 프레임워크와 도구를 사용하여 새 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-131">You can move existing sites to Azure App Service easily with an online migration tool, use an open-source app from the Web Application Gallery, or create a new site using the framework and tools of your choice.</span></span> <span data-ttu-id="460d7-132">Webjob 기능을 사용하면 백그라운드 작업 처리를 App Service 웹앱에 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-132">The WebJobs feature makes it easy to add background job processing to your App Service web app.</span></span>

### <a name="azure-kubernetes-service"></a><span data-ttu-id="460d7-133">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="460d7-133">Azure Kubernetes Service</span></span>

<span data-ttu-id="460d7-134">AKS(Azure Kubernetes Service)는 컨테이너 오케스트레이션 전문 지식 없이도 컨테이너화된 애플리케이션을 빠르고 쉽게 배포 및 관리할 수 있도록 해주는 호스트된 Kubernetes 환경을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-134">Azure Kubernetes Service (AKS) manages your hosted Kubernetes environment, making it quick and easy to deploy and manage containerized applications without container orchestration expertise.</span></span> <span data-ttu-id="460d7-135">또한 애플리케이션을 오프라인으로 전환하지 않고 요청 시 리소스를 프로비전, 업그레이드 및 크기 조정하여 진행 중인 작업 및 유지 관리 부담을 덜어줍니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-135">It also eliminates the burden of ongoing operations and maintenance by provisioning, upgrading, and scaling resources on demand, without taking your applications offline.</span></span>

<span data-ttu-id="460d7-136">AKS는 대부분의 책임을 Azure로 오프로드함으로써 Kubernetes 클러스터 관리에 대한 복잡성 및 운영 오버헤드를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-136">AKS reduces the complexity and operational overhead of managing a Kubernetes cluster by offloading much of that responsibility to Azure.</span></span> <span data-ttu-id="460d7-137">호스트된 Kubernetes 서비스처럼, Azure는 상태 모니터링 및 유지 관리와 같은 중요 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-137">As a hosted Kubernetes service, Azure handles critical tasks like health monitoring and maintenance for you.</span></span> <span data-ttu-id="460d7-138">또한 사용자는 마스터가 아닌 사용자 클러스터 내 에이전트 노드에 대해서만 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-138">Also, you pay only for the agent nodes within your clusters, not for the masters.</span></span> <span data-ttu-id="460d7-139">관리되는 Kubernetes 서비스로서 AKS는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-139">As a managed Kubernetes service, AKS provides:</span></span>

- <span data-ttu-id="460d7-140">자동화된 Kubernetes 버전 업그레이드 및 패치.</span><span class="sxs-lookup"><span data-stu-id="460d7-140">Automated Kubernetes version upgrades and patching.</span></span>
- <span data-ttu-id="460d7-141">간편한 클러스터 크기 조정.</span><span class="sxs-lookup"><span data-stu-id="460d7-141">Easy cluster scaling.</span></span>
- <span data-ttu-id="460d7-142">자체 복구 호스팅된 컨트롤 평면(마스터).</span><span class="sxs-lookup"><span data-stu-id="460d7-142">Self-healing hosted control plane (masters).</span></span>
- <span data-ttu-id="460d7-143">비용 절감 - 실행 중인 에이전트 풀 노드에 대해서만 지불.</span><span class="sxs-lookup"><span data-stu-id="460d7-143">Cost savings - pay only for running agent pool nodes.</span></span>

<span data-ttu-id="460d7-144">이제 AKS 클러스터의 노드 관리를 처리하는 Azure를 사용하면 클러스터 업그레이드와 같은 여러 작업을 수동으로 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-144">With Azure handling the management of the nodes in your AKS cluster, you no longer need to perform many tasks manually, like cluster upgrades.</span></span> <span data-ttu-id="460d7-145">Azure가 사용자를 위해 이와 같은 중요한 유지 관리 작업을 처리하므로 AKS는 클러스터에 대한 직접 액세스를 제공하지 않습니다(예: SSH 사용).</span><span class="sxs-lookup"><span data-stu-id="460d7-145">Because Azure handles these critical maintenance tasks for you, AKS doesn't provide direct access (such as with SSH) to the cluster.</span></span>

### <a name="azure-virtual-machines"></a><span data-ttu-id="460d7-146">Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="460d7-146">Azure Virtual Machines</span></span>

<span data-ttu-id="460d7-147">App Service에서 실행하려면 상당한 수정이 필요한 기존 애플리케이션의 경우, 클라우드로의 마이그레이션을 간소화하기 위해 Virtual Machines를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-147">If you have an existing application that would require substantial modifications to run in App Service, you could choose Virtual Machines in order to simplify migrating to the cloud.</span></span> <span data-ttu-id="460d7-148">그러나 VM을 올바르게 구성, 보호 및 유지 관리하려면 Azure App Service보다 훨씬 더 많은 시간과 IT 전문 지식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-148">However, correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to Azure App Service.</span></span> <span data-ttu-id="460d7-149">Azure Virtual Machines를 고려 중이라면 VM 환경을 패치, 업데이트 및 관리하는 데 지속적인 유지 관리 노력이 필요함을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-149">If you're considering Azure Virtual Machines, make sure you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="460d7-150">Azure Virtual Machines는 IaaS(서비스 형태의 인프라)이며, App Service는 PaaS(Platform-as-a-Service)입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-150">Azure Virtual Machines is infrastructure as a service (IaaS), while App Service is PaaS.</span></span> <span data-ttu-id="460d7-151">또한 앱을 Windows 컨테이너로 Web App for Containers에 배포하는 것이 시나리오에 유용한 옵션인지도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-151">You should also consider whether deploying your app as a Windows Container to Web App for Containers might be a viable option for your scenario.</span></span>

## <a name="logical-processes"></a><span data-ttu-id="460d7-152">논리적 프로세스</span><span class="sxs-lookup"><span data-stu-id="460d7-152">Logical processes</span></span>

<span data-ttu-id="460d7-153">애플리케이션의 나머지 부분과 분리될 수 있는 개별 논리 프로세스는 "서버가 없는" 방식으로 Azure Functions에 별도로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-153">Individual logical processes that can be decoupled from the rest of the application may be deployed independently to Azure Functions in a "serverless" manner.</span></span> <span data-ttu-id="460d7-154">Azure Functions를 사용하면 코드를 실행할 애플리케이션 또는 인프라에 대한 걱정 없이 주어진 문제에 필요한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-154">Azure Functions lets you just write the code you need for a given problem, without worrying about the application or infrastructure to run it.</span></span> <span data-ttu-id="460d7-155">C\#, F\#, Node.js, Python 및 PHP를 포함하는 다양한 프로그래밍 언어 중에서 작업에 가장 생산적인 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-155">You can choose from a variety of programming languages, including C\#, F\#, Node.js, Python, and PHP, allowing you to pick the most productive language for the task at hand.</span></span> <span data-ttu-id="460d7-156">대부분의 클라우드 기반 솔루션과 마찬가지로 사용 시간만큼 요금을 지불하고 Azure Functions를 필요에 따라 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-156">Like most cloud-based solutions, you pay only for the amount of time your use, and you can trust Azure Functions to scale up as needed.</span></span>

## <a name="data"></a><span data-ttu-id="460d7-157">데이터</span><span class="sxs-lookup"><span data-stu-id="460d7-157">Data</span></span>

<span data-ttu-id="460d7-158">Azure는 다양한 데이터 저장 옵션을 제공하므로, 애플리케이션이 해당 데이터에 대해 적절한 데이터 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-158">Azure offers a wide variety of data storage options, so that your application can use the appropriate data provider for the data in question.</span></span>

<span data-ttu-id="460d7-159">트랜잭션, 관계형 데이터의 경우 Azure SQL Database가 가장 적합한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-159">For transactional, relational data, Azure SQL Databases are the best option.</span></span> <span data-ttu-id="460d7-160">대부분 읽기 전용인 고성능 데이터의 경우 Azure SQL Database에서 지원하는 Redis 캐시가 적합한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-160">For high performance read-mostly data, a Redis cache backed by an Azure SQL Database is a good solution.</span></span>

<span data-ttu-id="460d7-161">구조화되지 않은 JSON 데이터는 SQL Database 열에서 Azure Storage의 Blob 또는 테이블, DocumentDB에 이르기까지 다양한 방법으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-161">Unstructured JSON data can be stored in a variety of ways, from SQL Database columns to Blobs or Tables in Azure Storage, to DocumentDB.</span></span> <span data-ttu-id="460d7-162">이 중에서 DocumentDB는 최상의 쿼리 기능을 제공하며, 쿼리를 지원해야 하는 다수의 JSON 기반 문서에 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-162">Of these, DocumentDB offers the best querying functionality, and is the recommended option for large numbers of JSON-based documents that must support querying.</span></span>

<span data-ttu-id="460d7-163">애플리케이션 동작을 오케스트레이션하는 데 사용되는 일시적인 명령 또는 이벤트 기반 데이터는 Azure Service Bus 또는 Azure Storage Queue를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-163">Transient command- or event-based data used to orchestrate application behavior can use Azure Service Bus or Azure Storage Queues.</span></span> <span data-ttu-id="460d7-164">Azure Storage Bus는 더 많은 유연성을 제공하며 애플리케이션 내 및 애플리케이션 간의 중요한 메시징에 권장되는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-164">Azure Storage Bus offers more flexibility and is the recommended service for non-trivial messaging within and between applications.</span></span>

## <a name="architecture-recommendations"></a><span data-ttu-id="460d7-165">아키텍처 권장 사항</span><span class="sxs-lookup"><span data-stu-id="460d7-165">Architecture recommendations</span></span>

<span data-ttu-id="460d7-166">애플리케이션의 요구 사항에 따라 아키텍처가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-166">Your application's requirements should dictate its architecture.</span></span> <span data-ttu-id="460d7-167">여러 다양한 Azure 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-167">There are many different Azure services available.</span></span> <span data-ttu-id="460d7-168">적합한 서비스를 선택하는 것은 중요한 의사 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-168">Choosing the right one is an important decision.</span></span> <span data-ttu-id="460d7-169">Microsoft는 일반적인 시나리오에 최적화된 일반적인 아키텍처를 식별하는 데 도움이 되는 참조 아키텍처의 갤러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-169">Microsoft offers a gallery of reference architectures to help identify typical architectures optimized for common scenarios.</span></span> <span data-ttu-id="460d7-170">애플리케이션의 요구 사항과 밀접한 관련이 있거나 적어도 시작점을 제공하는 참조 아키텍처를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-170">You may find a reference architecture that maps closely to your application's requirements, or at least offers a starting point.</span></span>

<span data-ttu-id="460d7-171">그림 11-2는 참조 아키텍처의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-171">Figure 11-2 shows an example reference architecture.</span></span> <span data-ttu-id="460d7-172">이 다이어그램에서는 마케팅에 최적화된 Sitecore 콘텐츠 관리 시스템 웹 사이트에 권장되는 아키텍처 접근 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="460d7-172">This diagram describes a recommended architecture approach for a Sitecore content management system website optimized for marketing.</span></span>

![](./media/image11-2.png)

<span data-ttu-id="460d7-173">**그림 11-1.**</span><span class="sxs-lookup"><span data-stu-id="460d7-173">**Figure 11-1.**</span></span> <span data-ttu-id="460d7-174">Sitecore 마케팅 웹 사이트 참조 아키텍처 </span><span class="sxs-lookup"><span data-stu-id="460d7-174">Sitecore marketing website reference architecture.</span></span>

<span data-ttu-id="460d7-175">**참조 - Azure 호스팅 권장 사항**</span><span class="sxs-lookup"><span data-stu-id="460d7-175">**References – Azure hosting recommendations**</span></span>

- <span data-ttu-id="460d7-176">Azure 솔루션 아키텍처\\</span><span class="sxs-lookup"><span data-stu-id="460d7-176">Azure Solution Architectures\\</span></span>
  <https://azure.microsoft.com/solutions/architecture/>

- <span data-ttu-id="460d7-177">Azure 개발자 가이드\\</span><span class="sxs-lookup"><span data-stu-id="460d7-177">Azure Developer Guide\\</span></span>
  <https://azure.microsoft.com/campaigns/developer-guide/>

- <span data-ttu-id="460d7-178">웹앱 개요\\</span><span class="sxs-lookup"><span data-stu-id="460d7-178">Web Apps overview\\</span></span>
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- <span data-ttu-id="460d7-179">Web App for Containers\\</span><span class="sxs-lookup"><span data-stu-id="460d7-179">Web App for Containers\\</span></span>
  <https://azure.microsoft.com/en-us/services/app-service/containers/>

- <span data-ttu-id="460d7-180">AKS(Azure Kubernetes Service) 소개\\</span><span class="sxs-lookup"><span data-stu-id="460d7-180">Introduction to Azure Kubernetes Service (AKS)\\</span></span>
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[<span data-ttu-id="460d7-181">이전</span><span class="sxs-lookup"><span data-stu-id="460d7-181">Previous</span></span>](development-process-for-azure.md)
