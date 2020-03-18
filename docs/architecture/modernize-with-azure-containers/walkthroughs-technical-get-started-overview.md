---
title: 연습 및 기술 시작 개요
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 연습 및 기술 시작 개요
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69660893"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="50933-103">연습 및 기술 시작 개요</span><span class="sxs-lookup"><span data-stu-id="50933-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="50933-104">이 전자책의 크기를 제한하기 위해 추가 기술 문서와 전체 연습은 GitHub 리포지토리에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="50933-105">이 장에서 설명하는 온라인 연습 시리즈에서는 Windows 컨테이너 기반 다중 환경의 단계별 설정과 Azure로의 배포에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="50933-106">다음 섹션에서는 각 연습에 대한 설명, 목표 및 상위 수준 비전에 대해 설명하고 관련 작업에 대한 다이어그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="50933-107">연습 자체는 *eShopModernizing* apps GitHub repo wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki>)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="50933-108">기술 연습 목록</span><span class="sxs-lookup"><span data-stu-id="50933-108">Technical walkthrough list</span></span>

<span data-ttu-id="50933-109">다음 시작 연습에서는 컨테이너를 사용하여 리프트 앤 시프트하고 Azure에서 여러 배포 옵션을 사용하여 이동할 수 있는 샘플 앱에 대한 일관적이고 포괄적인 기술 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="50933-110">다음 각 연습은 GitHub(<https://github.com/dotnet-architecture/eShopModernizing>)에서 다운로드할 수 있는 새로운 샘플 eShopLegacy 및 eShopModernizing 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="50933-111">**eShop 레거시 앱 둘러보기(현대화할 기준 앱)**</span><span class="sxs-lookup"><span data-stu-id="50933-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="50933-112">**Windows 컨테이너를 사용하여 기존 ASP.NET 웹앱(WebForms & MVC) 컨테이너화**</span><span class="sxs-lookup"><span data-stu-id="50933-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="50933-113">**Windows 컨테이너를 사용하여 기존 WCF 서비스(N 계층 앱) 컨테이너화**</span><span class="sxs-lookup"><span data-stu-id="50933-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="50933-114">**Azure VM에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="50933-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="50933-115">**Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="50933-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="50933-116">연습 1: eShop 레거시 앱 둘러보기</span><span class="sxs-lookup"><span data-stu-id="50933-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="50933-117">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="50933-117">Technical walkthrough availability</span></span>

<span data-ttu-id="50933-118">전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="50933-119">eShopModernizing wiki walkthroughs</span><span class="sxs-lookup"><span data-stu-id="50933-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="50933-120">개요</span><span class="sxs-lookup"><span data-stu-id="50933-120">Overview</span></span>

<span data-ttu-id="50933-121">이 연습에서는 세 가지 샘플 레거시 애플리케이션의 초기 구현을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="50933-122">처음 두 샘플 웹앱은 모놀리식 아키텍처이며 클래식 ASP.NET을 사용하여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="50933-123">첫 번째 애플리케이션은 ASP.NET 4.x MVC를 기반으로 하고, 두 번째 애플리케이션은 ASP.NET 4.x Web Forms를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="50933-124">세 번째 애플리케이션은 클라이언트 WinForms 앱 및 서버 쪽 [WCF(Windows Communication Foundation)](../../framework/wcf/whats-wcf.md) 서비스로 구성된 3 계층 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="50933-125">이들 애플리케이션은 모두 [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="50933-126">목표</span><span class="sxs-lookup"><span data-stu-id="50933-126">Goals</span></span>

<span data-ttu-id="50933-127">이 연습의 주요 목표는 단순히 이러한 앱과 해당 코드 및 구성을 익히는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="50933-128">테스트를 위해 SQL 데이터베이스를 사용하지 않고 모의 데이터를 생성하고 사용하도록 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="50933-129">이 선택적 구성은 분리된 방식으로 종속성 주입을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="50933-130">시나리오 1: ASP.NET 웹앱</span><span class="sxs-lookup"><span data-stu-id="50933-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="50933-131">아래 그림에서는 원래 레거시 ASP.NET 웹 애플리케이션의 단순한 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50933-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![원래 레거시 ASP.NET 웹 애플리케이션의 단순한 아키텍처 시나리오](./media/image5-1.png)

<span data-ttu-id="50933-133">비즈니스 도메인 관점에서 두 앱은 모두 동일한 카탈로그 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="50933-134">eShop 엔터프라이즈 팀의 멤버가 이 앱을 사용하여 제품 카탈로그를 보고 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="50933-135">다음 그림은 초기 앱 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC 및 ASP.NET Web Forms 애플리케이션(기존/레거시 기술)](./media/image5-2.png)

<span data-ttu-id="50933-137">ASP.NET 4.x 이전 버전의 종속성(MVC 또는 Web Forms)은 ASP.NET Core MVC를 사용하여 코드를 완전히 다시 작성하지 않는 한 이러한 애플리케이션이 .NET Core에서 실행되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="50933-138">시나리오 2: WCF 서비스 및 WinForms 클라이언트 앱(3 계층 앱)</span><span class="sxs-lookup"><span data-stu-id="50933-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="50933-139">아래 그림에서는 원래 3 계층 레거시 애플리케이션의 단순한 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50933-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![WCF 서비스 및 WinForms 클라이언트 앱을 사용하는 원래 레거시 3 계층 앱의 단순한 아키텍처 시나리오](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="50933-141">이점</span><span class="sxs-lookup"><span data-stu-id="50933-141">Benefits</span></span>

<span data-ttu-id="50933-142">이 연습의 이점은 간단합니다. 코드 및 초기 앱에 익숙해지는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="50933-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-143">Next steps</span></span>

<span data-ttu-id="50933-144">다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="50933-145">Tour on the baseline ASP.NET MVC and Web Forms "legacy" apps</span><span class="sxs-lookup"><span data-stu-id="50933-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="50933-146">Tour on the baseline WCF service and WinForms (3-Tier) "legacy" app</span><span class="sxs-lookup"><span data-stu-id="50933-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="50933-147">연습 2: Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 컨테이너화</span><span class="sxs-lookup"><span data-stu-id="50933-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="50933-148">개요</span><span class="sxs-lookup"><span data-stu-id="50933-148">Overview</span></span>

<span data-ttu-id="50933-149">Windows 컨테이너를 사용하여 MVC, Web Forms 또는 WCF를 기반으로 하는 애플리케이션과 같은 기존 .NET 애플리케이션의 프로덕션, 개발 및 테스트 환경 배포를 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="50933-150">목표</span><span class="sxs-lookup"><span data-stu-id="50933-150">Goals</span></span>

<span data-ttu-id="50933-151">이 연습의 목표는 기존 .NET Framework 애플리케이션을 컨테이너화하기 위한 몇 가지 옵션을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="50933-152">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-152">You can:</span></span>

- <span data-ttu-id="50933-153">[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)(Visual Studio 2017 이상 버전)를 사용하여 애플리케이션을 컨테이너화합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="50933-154">수동으로 [Dockerfile](https://docs.docker.com/engine/reference/builder/)을 추가한 후 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)를 사용하여 애플리케이션을 컨테이너화합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="50933-155">[Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구(Docker의 오픈 소스 도구)를 사용하여 애플리케이션을 컨테이너화합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="50933-156">이 연습에서는 Visual Studio 2017 Tools for Docker 접근 방식에 초점을 맞추지만, 다른 두 접근 방식은 Dockerfile 사용과 관련해서는 다른 두 방법과 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="50933-157">시나리오 1: 컨테이너화된 ASP.NET 웹앱</span><span class="sxs-lookup"><span data-stu-id="50933-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="50933-158">아래 그림에서는 컨테이너화된 eShop 레거시 웹앱에 대한 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50933-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![개발 환경에서 컨테이너화된 ASP.NET 애플리케이션의 간소화된 아키텍처를 보여 주는 다이어그램](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="50933-160">시나리오 2: 컨테이너화된 WCF 서비스</span><span class="sxs-lookup"><span data-stu-id="50933-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="50933-161">아래 그림에서는 컨테이너화된 WCF 서비스를 사용하는 3 계층 앱의 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="50933-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![개발 환경에서 컨테이너화된 WCF 서비스의 간소화된 아키텍처를 보여 주는 다이어그램](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="50933-163">이점</span><span class="sxs-lookup"><span data-stu-id="50933-163">Benefits</span></span>

<span data-ttu-id="50933-164">컨테이너에서 모놀리식 애플리케이션을 실행하면 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="50933-165">먼저, 애플리케이션의 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-165">First, you create an image for the application.</span></span> <span data-ttu-id="50933-166">이 시점부터 모든 배포가 동일한 환경에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="50933-167">모든 컨테이너가 동일한 OS 버전을 사용하며, 동일한 버전의 종속성이 설치되고, 동일한 .NET 프레임워크 버전을 사용하며, 동일한 프로세스를 사용하여 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="50933-168">기본적으로 Docker 이미지를 사용하여 애플리케이션의 종속성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="50933-169">컨테이너를 배포할 때 종속성이 애플리케이션과 함께 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="50933-170">이밖에 개발자는 Windows 컨테이너에서 제공하는 일관된 환경에서 애플리케이션을 실행할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="50933-171">특정 버전에서만 나타나는 문제가 준비 또는 프로덕션 환경에서 표출되는 대신 즉시 발견될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="50933-172">애플리케이션이 컨테이너에서 실행되는 경우 개발 팀의 멤버가 사용하는 개발 환경 간 차이의 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="50933-173">컨테이너화된 애플리케이션은 보다 평탄한 수평 확장 곡선을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="50933-174">컨테이너화된 앱을 사용하면 일반적인 컴퓨터별 애플리케이션 배포와 비교할 때 VM 또는 물리적 컴퓨터에서 (컨테이너를 기반으로) 더 많은 애플리케이션 및 서비스 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="50933-175">그러면, 특히 Kubernetes와 같은 오케스트레이터를 사용할 경우, 밀도가 더욱 높아지고 필요한 리소스 수가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="50933-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="50933-176">이상적인 상황에서는 컨테이너화로 인해 애플리케이션 코드(C\#)를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="50933-177">대부분의 시나리오에서는 Docker 배포 메타데이터 파일(Dockerfile 및 Docker Compose 파일)만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="50933-178">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-178">Next steps</span></span>

<span data-ttu-id="50933-179">다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="50933-180">Windows 컨테이너 및 Docker를 사용하여 .NET Framework 웹앱을 컨테이너화하는 방법</span><span class="sxs-lookup"><span data-stu-id="50933-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="50933-181">WCF 서비스에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="50933-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="50933-182">연습 3: Azure VM에 Windows 컨테이너 기반 앱 배포</span><span class="sxs-lookup"><span data-stu-id="50933-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="50933-183">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="50933-183">Technical walkthrough availability</span></span>

<span data-ttu-id="50933-184">전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다. <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="50933-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="50933-185">개요</span><span class="sxs-lookup"><span data-stu-id="50933-185">Overview</span></span>

<span data-ttu-id="50933-186">Azure에서 Windows Server 2016 VM(가상 머신)의 Docker 호스트에 배포하면 개발/테스트/준비 환경을 신속하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="50933-187">또한 테스터 또는 비즈니스 사용자가 앱의 유효성을 검사할 수 있는 공통 위치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="50933-188">VM은 유효한 IaaS(Infrastructure as a Service) 프로덕션 환경으로도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="50933-189">목표</span><span class="sxs-lookup"><span data-stu-id="50933-189">Goals</span></span>

<span data-ttu-id="50933-190">이 연습의 목표는 Windows Server 2016 이상 버전을 기반으로 하는 Azure VM에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대안을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="50933-191">시나리오</span><span class="sxs-lookup"><span data-stu-id="50933-191">Scenarios</span></span>

<span data-ttu-id="50933-192">이 연습에서는 몇 가지 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="50933-193">시나리오 A: Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포](./media/image5-4.png)

<span data-ttu-id="50933-195">**그림 5-4.**</span><span class="sxs-lookup"><span data-stu-id="50933-195">**Figure 5-4.**</span></span> <span data-ttu-id="50933-196">Docker 엔진 연결을 통해 개발 PC에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="50933-197">시나리오 B: Docker 레지스트리를 통해 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

<span data-ttu-id="50933-199">**그림 5-5.**</span><span class="sxs-lookup"><span data-stu-id="50933-199">**Figure 5-5.**</span></span> <span data-ttu-id="50933-200">Docker 레지스트리를 통해 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="50933-201">시나리오 C: Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

<span data-ttu-id="50933-203">**그림 5-6.**</span><span class="sxs-lookup"><span data-stu-id="50933-203">**Figure 5-6.**</span></span> <span data-ttu-id="50933-204">Azure DevOps Services의 CI/CD 파이프라인에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="50933-205">Windows 컨테이너용 Azure VM</span><span class="sxs-lookup"><span data-stu-id="50933-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="50933-206">Windows 컨테이너용 Azure VM은 Windows Server 2016, Windows 10 이상 버전(모두 Docker 엔진 설정 포함)을 기반으로 하는 VM입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="50933-207">대부분의 경우 Windows Server 2016이 Azure VN에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="50933-208">현재 Azure는 **컨테이너가 포함된 Windows Server 2016**이라는 VM을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="50933-209">이 VM을 사용하여 Windows Server Core 또는 Windows Nano Server를 통해 새로운 Windows Server 컨테이너 기능을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="50933-210">컨테이너 OS 이미지를 설치하면 VM을 Docker에 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="50933-211">이점</span><span class="sxs-lookup"><span data-stu-id="50933-211">Benefits</span></span>

<span data-ttu-id="50933-212">Windows 컨테이너를 온-프레미스 Windows Server 2016 VM에 배포할 수 있지만, Azure에 배포할 경우 즉시 사용 가능한 Windows Server 컨테이너 VM으로 보다 간편하게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="50933-213">또한 테스터가 액세스할 수 있는 공통의 온라인 위치와 Azure 가상 머신 확장 집합을 통한 자동 확장성도 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="50933-214">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-214">Next steps</span></span>

<span data-ttu-id="50933-215">다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="50933-216">연습 4: ACI(Azure Container Instances)에 Windows 컨테이너 기반 앱 배포</span><span class="sxs-lookup"><span data-stu-id="50933-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="50933-217">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="50933-217">Technical walkthrough availability</span></span>

<span data-ttu-id="50933-218">전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="50933-219">[ACI(Azure Container Instances)에 앱 배포](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="50933-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="50933-220">개요</span><span class="sxs-lookup"><span data-stu-id="50933-220">Overview</span></span>

<span data-ttu-id="50933-221">[ACI(Azure Container Instances)](https://docs.microsoft.com/azure/container-instances/)는 단일 인스턴스의 컨테이너를 배포할 수 있는 컨테이너 개발/테스트/준비 환경을 확보하는 가장 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="50933-222">목표</span><span class="sxs-lookup"><span data-stu-id="50933-222">Goals</span></span>

<span data-ttu-id="50933-223">이 연습에서는 ACI(Azure Container Instances)에 Windows 컨테이너를 배포할 경우의 주요 시나리오와 ACI에 eShopModernizing 앱을 배포할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50933-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="50933-224">시나리오</span><span class="sxs-lookup"><span data-stu-id="50933-224">Scenarios</span></span>

<span data-ttu-id="50933-225">ACI에 eShopModernizing 앱을 배포할 때 앱(MVC 앱, WebForms 앱 또는 WCF 서비스) 중 하나 또는 모두를 배포하는 것과 같은 변형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="50933-226">다음 시나리오에서는 ASP.NET MVC 앱과 SQL Server 컨테이너를 ACI(Azure Container Instances)에 컨테이너로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![개발 환경에서 ACI에 배포](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="50933-228">이점</span><span class="sxs-lookup"><span data-stu-id="50933-228">Benefits</span></span>

<span data-ttu-id="50933-229">Azure Container Instances를 사용하면 가상 머신을 프로비전하거나 상위 수준 서비스를 도입하지 않고도 Azure에서 Docker 컨테이너를 쉽게 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="50933-230">ACI를 사용하면 Azure에서 Windows 컨테이너를 직접 배포하고 몇 초 내에 FQDN(정규화된 도메인 이름)을 사용하여 인터넷에 노출할 수 있습니다(Docker Hub 또는 Azure Container Registry와 같은 Docker 레지스트리에서 준비된 Windows 컨테이너 이미지가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="50933-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="50933-231">고려 사항</span><span class="sxs-lookup"><span data-stu-id="50933-231">Considerations</span></span>

<span data-ttu-id="50933-232">전체 .NET Framework/ASP.NET 또는 SQL Server를 포함하는 Windows 컨테이너를 ACI(Azure Container Instances)에 배포하는 것은 일반적인 Docker 호스트(예: Windows 컨테이너가 포함된 Server 2016)에 배포하는 것만큼 빠르지 않습니다. 매번 Docker 이미지를 다운로드해야 하고(Docker 레지스트리에서 가져옴) SQL 컨테이너 이미지(15.1GB) 및 ASP.NET 컨테이너 이미지(13.9GB)의 크기가 상당하기 때문입니다. 하지만 프로덕션 배포를 위한 훌륭한 선택인 Azure Kubernetes(AKS)와 같은 오케스트레이터는 말할 것도 없이 자체 Docker 호스트(Azure의 Windows 컨테이너가 포함된 영구 온라인 Windows Server 2016)를 보유하는 것보다 훨씬 저렴합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="50933-233">결론적으로 Azure Container Instances 사용은 개발/테스트 시나리오 및 CI/CD 파이프라인에 매우 매력적인 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50933-234">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-234">Next steps</span></span>

<span data-ttu-id="50933-235">다음 GitHub wiki에서 이 콘텐츠를 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="50933-236">연습 5: Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱 배포</span><span class="sxs-lookup"><span data-stu-id="50933-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="50933-237">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="50933-237">Technical walkthrough availability</span></span>

<span data-ttu-id="50933-238">전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="50933-239">개요</span><span class="sxs-lookup"><span data-stu-id="50933-239">Overview</span></span>

<span data-ttu-id="50933-240">Windows 컨테이너를 기반으로 하는 애플리케이션은 신속하게 플랫폼을 활용하여 IaaS VM에서 한층 더 개선되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="50933-241">이는 뛰어난 확장성과 향상된 자동 확장성을 손쉽게 구현하는 데 필요하고, 자동화된 배포 및 버전 관리를 대폭 개선하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="50933-242">이러한 목표는 [Azure Container Services](https://azure.microsoft.com/services/container-service/)에서 제공하는 오케스트레이터 [Kubernetes](https://kubernetes.io/)를 사용하여 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="50933-243">목표</span><span class="sxs-lookup"><span data-stu-id="50933-243">Goals</span></span>

<span data-ttu-id="50933-244">이 연습의 목표는 Windows 컨테이너 기반 애플리케이션을 Azure Container Service에서 Kubernetes(*K8s*라고도 함)에 배포하는 방법을 배우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="50933-245">Kubernetes를 처음부터 배포하는 과정은 다음 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50933-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="50933-246">Kubernetes 클러스터를 Azure Container Service에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="50933-247">애플리케이션 및 관련 리소스를 Kubernetes 클러스터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="50933-248">시나리오</span><span class="sxs-lookup"><span data-stu-id="50933-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="50933-249">시나리오 A: 개발 환경에서 Kubernetes 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="50933-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![개발 환경에서 Kubernetes 클러스터에 직접 배포](./media/image5-7.png)

<span data-ttu-id="50933-251">**그림 5-7.**</span><span class="sxs-lookup"><span data-stu-id="50933-251">**Figure 5-7.**</span></span> <span data-ttu-id="50933-252">개발 환경에서 Kubernetes 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="50933-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="50933-253">시나리오 B: Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포](./media/image5-8.png)

<span data-ttu-id="50933-255">**그림 5-8.**</span><span class="sxs-lookup"><span data-stu-id="50933-255">**Figure 5-8.**</span></span> <span data-ttu-id="50933-256">Azure DevOps Services의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="50933-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="50933-257">이점</span><span class="sxs-lookup"><span data-stu-id="50933-257">Benefits</span></span>

<span data-ttu-id="50933-258">Kubernetes의 클러스터에 배포하는 데는 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="50933-259">가장 큰 이점은 사용하려는 컨테이너 인스턴스 수에 따라(기존 노드의 내부 확장성) 또한 클러스터 내 노드 또는 VM 수에 따라(클러스터의 전역 확장성) 애플리케이션을 확장할 수 있는 프로덕션 준비 환경을 확보하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="50933-260">Azure Container Service는 Azure용으로 특히 인기 있는 오픈 소스 도구 및 기술을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="50933-261">컨테이너와 애플리케이션 구성 모두에 이식성을 제공하는 개방형 솔루션을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="50933-262">사용자가 크기, 호스트 수, 오케스트레이터 도구를 선택하면 Container Service에서 다른 모든 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="50933-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="50933-263">Kubernetes를 통해 개발자는 물리적 컴퓨터와 가상 머신에 대한 고려에서 다음과 같은 기능을 촉진하는 컨테이너 중심 인프라를 계획하는 과정으로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="50933-264">다중 컨테이너를 기반으로 하는 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="50933-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="50933-265">컨테이너 인스턴스 복제 및 수평 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="50933-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="50933-266">이름 지정 및 검색(예: 내부 DNS)</span><span class="sxs-lookup"><span data-stu-id="50933-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="50933-267">부하 분산</span><span class="sxs-lookup"><span data-stu-id="50933-267">Balancing loads</span></span>

- <span data-ttu-id="50933-268">롤링 업데이트</span><span class="sxs-lookup"><span data-stu-id="50933-268">Rolling updates</span></span>

- <span data-ttu-id="50933-269">비밀 배포</span><span class="sxs-lookup"><span data-stu-id="50933-269">Distributing secrets</span></span>

- <span data-ttu-id="50933-270">애플리케이션 상태 검사</span><span class="sxs-lookup"><span data-stu-id="50933-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="50933-271">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-271">Next steps</span></span>

<span data-ttu-id="50933-272">이 콘텐츠를 GitHub wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>)에서 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="50933-273">연습 6: 컨테이너용 Azure App Service에 Windows 컨테이너 기반 앱 배포</span><span class="sxs-lookup"><span data-stu-id="50933-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="50933-274">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="50933-274">Technical walkthrough availability</span></span>

<span data-ttu-id="50933-275">전체 기술 연습은 eShopModernizing GitHub repo wiki에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="50933-276">개요</span><span class="sxs-lookup"><span data-stu-id="50933-276">Overview</span></span>

<span data-ttu-id="50933-277">Windows 컨테이너를 사용하는 간단한 컨테이너화된 애플리케이션을 컨테이너용 Azure App Service에 쉽게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="50933-278">이는 대부분의 Windows 컨테이너 기반 애플리케이션에 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="50933-279">목표</span><span class="sxs-lookup"><span data-stu-id="50933-279">Goals</span></span>

<span data-ttu-id="50933-280">이 연습의 목표는 Windows 컨테이너 기반 애플리케이션을 레지스트리(Docker Hub 또는 Azure Container Registry)에서 컨테이너용 Azure App Service에 배포하는 방법을 배우는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50933-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="50933-281">시나리오</span><span class="sxs-lookup"><span data-stu-id="50933-281">Scenario</span></span>

![컨테이너용 Azure App Service에 Windows 컨테이너 기반 앱 배포](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="50933-283">이점</span><span class="sxs-lookup"><span data-stu-id="50933-283">Benefits</span></span>

<span data-ttu-id="50933-284">컨테이너용 Azure App Service에 배포하면 Azure App Service의 PaaS 이점과 쌍을 이루는 컨테이너의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="50933-285">App Service는 수직 및 수평으로 쉽게 확장할 수 있으며 자동 크기 조정을 구성하여 변화하는 수요를 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="50933-286">가동 중지 시간 없이 업데이트를 수행할 수 있으며, 레지스트리에서 지속적인 배포를 구성하는 것도 손쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="50933-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50933-287">다음 단계</span><span class="sxs-lookup"><span data-stu-id="50933-287">Next steps</span></span>

<span data-ttu-id="50933-288">이 콘텐츠를 GitHub wiki(<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>)에서 보다 심층적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="50933-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="50933-289">[이전](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [다음](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="50933-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
