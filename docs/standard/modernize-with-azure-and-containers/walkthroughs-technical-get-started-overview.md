---
title: 연습 및 기술 시작된 개요 가져오기
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램 현대화 | 연습 및 기술 시작된 개요 가져오기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 15ea074693a75aa04b4f3a03e6e5e3d7f748cea1
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674941"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="9f3cc-103">연습 및 기술 시작된 개요 가져오기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="9f3cc-104">이 전자책의 크기를 제한 하려면 추가 기술 설명서 및 연습을 전체 내용이 사용할 수 있는 GitHub 리포지토리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="9f3cc-105">이 챕터에 설명 된 연습 온라인 시리즈 Windows 컨테이너 및 Azure에 배포를 기반으로 하는 여러 환경의 단계별 설치를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="9f3cc-106">다음 섹션에서는 각 연습에 대해 해당 목표 및 고급 시각 및 관련 된 작업의 다이어그램을 제공을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="9f3cc-107">자체 연습을 가져올 수 있습니다에 *eShopModernizing* apps GitHub 리포지토리 wiki에서 [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="9f3cc-108">기술 연습 목록</span><span class="sxs-lookup"><span data-stu-id="9f3cc-108">Technical walkthrough list</span></span>

<span data-ttu-id="9f3cc-109">다음 시작 연습에서는 리프트 앤 시프트 컨테이너를 사용 하 여 및 다음 Azure에서 여러 배포 옵션을 사용 하 여 이동 하는 샘플 앱에 대 한 일관적이 고 포괄적인 기술 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="9f3cc-110">다음 연습 중 각 앱을 사용 하 여 새 샘플 eShopLegacy 및 eShopModernizing에서 GitHub에서 사용할 수 있는 [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="9f3cc-111">**EShop 레거시 앱 (기준 앱 현대화) 둘러보기**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="9f3cc-112">**Windows 컨테이너를 사용 하 여 기존 ASP.NET 웹 앱 (WebForms 및 MVC)를 컨테이너 화**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="9f3cc-113">**Windows 컨테이너를 사용 하 여 기존 WCF 서비스 (N 계층 앱)를 컨테이너 화**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="9f3cc-114">**Azure Vm에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="9f3cc-115">**Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱을 배포 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="9f3cc-116">**Azure Service Fabric에 Windows 컨테이너 기반 앱을 배포 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="9f3cc-117">연습 1: 레거시 앱 eShop 둘러보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="9f3cc-118">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="9f3cc-118">Technical walkthrough availability</span></span>

<span data-ttu-id="9f3cc-119">전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="9f3cc-120">eShopModernizing wiki 연습</span><span class="sxs-lookup"><span data-stu-id="9f3cc-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="9f3cc-121">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-121">Overview</span></span>

<span data-ttu-id="9f3cc-122">이 연습에서는 세 개의 샘플 레거시 응용 프로그램의 초기 구현을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="9f3cc-123">처음 두 개의 샘플 웹 앱 모놀리식 아키텍처에 있고 클래식 ASP.NET을 사용 하 여 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="9f3cc-124">하나의 응용 프로그램은 ASP.NET을 기반 4.x MVC; 두 번째 응용 프로그램은 ASP.NET 4.x Web Forms를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="9f3cc-125">세 번째 응용 프로그램이 클라이언트 WinForms 앱 및 서버 쪽에서 구성 된 3 계층 앱 [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="9f3cc-126">이러한 모든 응용이 프로그램에서 사용할 수는 [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-127">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-127">Goals</span></span>

<span data-ttu-id="9f3cc-128">이 연습의 기본 목적은 이러한 앱 및 해당 코드와 구성에 친숙 해지기 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="9f3cc-129">생성 하 고 모의 데이터를 사용 하 여 테스트 목적으로 SQL database를 사용 하지 않고 있는 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="9f3cc-130">이 선택적 구성은 분리 된 방식으로 종속성 주입을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="9f3cc-131">시나리오 1: ASP.NET 웹 앱</span><span class="sxs-lookup"><span data-stu-id="9f3cc-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="9f3cc-132">아래 그림에는 원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.png)

<span data-ttu-id="9f3cc-134">비즈니스 도메인 관점에서 두 앱 모두 동일한 카탈로그 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="9f3cc-135">EShop 엔터프라이즈 팀의 멤버 보기 및 편집 제품 카탈로그를 앱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="9f3cc-136">다음 그림에는 초기 앱 스크린 샷을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-136">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC 및 ASP.NET Web Forms 응용 프로그램 (기존/레거시 기술)](./media/image5-2.png)

<span data-ttu-id="9f3cc-138">종속성 ASP.NET 4.x 또는 이전 버전 (또는 MVC Web Forms) 의미 이러한 응용 프로그램 코드는 ASP.NET Core MVC를 사용 하 여 완전히 다시 작성 하지 않는 한.NET Core에서 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="9f3cc-139">시나리오 2: WCF 서비스 및 WinForms 클라이언트 앱 (3 계층 앱)</span><span class="sxs-lookup"><span data-stu-id="9f3cc-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="9f3cc-140">아래 그림에는 원래 3 계층 레거시 응용 프로그램의 간단한 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![WCF 서비스를 사용 하 여 원래 레거시 3 계층 응용 프로그램 및 WinForms 클라이언트 앱의 간단한 아키텍처 시나리오](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="9f3cc-142">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-142">Benefits</span></span>

<span data-ttu-id="9f3cc-143">이 연습의 혜택은 간단 합니다. 초기 앱 코드와 친숙 한 효과만 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="9f3cc-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-144">Next steps</span></span>

<span data-ttu-id="9f3cc-145">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-145">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="9f3cc-146">둘러보기 기준을 설정한 ASP.NET MVC 및 Web Forms "레거시" 앱</span><span class="sxs-lookup"><span data-stu-id="9f3cc-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
-   [<span data-ttu-id="9f3cc-147">기본 WCF 서비스 및 WinForms (3 계층) "레거시" 앱에 대 한 둘러보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="9f3cc-148">연습 2: Windows 컨테이너를 사용 하 여 기존.NET 응용 프로그램을 컨테이너 화</span><span class="sxs-lookup"><span data-stu-id="9f3cc-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="9f3cc-149">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-149">Overview</span></span>

<span data-ttu-id="9f3cc-150">Windows 컨테이너를 사용 하 여 MVC, Web Forms, WCF, 프로덕션, 개발 및 테스트 환경에 기반 하는 것과 같은 기존.NET 응용 프로그램을 배포 기술 향상.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-151">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-151">Goals</span></span>

<span data-ttu-id="9f3cc-152">이 연습의 목적은 기존.NET Framework 응용 프로그램을 컨테이너 화 하기 위한 몇 가지 옵션을 표시할 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="9f3cc-153">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-153">You can:</span></span>

- <span data-ttu-id="9f3cc-154">사용 하 여 응용 프로그램을 컨테이너 화 [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 또는 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="9f3cc-155">수동으로 추가 하 여 응용 프로그램을 컨테이너 화를 [Dockerfile](https://docs.docker.com/engine/reference/builder/), 한 다음 사용 하는 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="9f3cc-156">사용 하 여 응용 프로그램을 컨테이너 화 합니다 [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구 (Docker의 오픈 소스 도구).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="9f3cc-157">이 연습에서는 Docker 접근 방식에 대 한 Visual Studio 2017 도구를 중점적으로 다루지만 나머지 두 방식의 Dockerfile을 사용 하 여 인증과 관련 하 여 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="9f3cc-158">시나리오 1: 컨테이너 화 된 ASP.NET 웹 앱</span><span class="sxs-lookup"><span data-stu-id="9f3cc-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="9f3cc-159">아래 그림에는 컨테이너 화 된 eShop 레거시 웹 앱 응용 프로그램에 대 한 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![개발 환경에서 ASP.NET 응용 프로그램을 컨테이너 화 된 간소화 된 아키텍처 다이어그램](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="9f3cc-161">시나리오 2: 컨테이너 화 된 WCF 서비스</span><span class="sxs-lookup"><span data-stu-id="9f3cc-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="9f3cc-162">아래 그림에는 컨테이너 화 된 WCF 서비스를 사용 하 여 3 계층 응용 프로그램 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![간소화 된 개발 환경에서 컨테이너 화 된 WCF 서비스의 아키텍처 다이어그램](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="9f3cc-164">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-164">Benefits</span></span>

<span data-ttu-id="9f3cc-165">컨테이너의 모놀리식 응용 프로그램을 실행 하면 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="9f3cc-166">먼저, 응용 프로그램에 대 한 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-166">First, you create an image for the application.</span></span> <span data-ttu-id="9f3cc-167">해당 지점에서 모든 배포가 동일한 환경에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="9f3cc-168">모든 컨테이너 동일한 OS 버전을 사용 하 여 동일한 버전의 종속성이 설치, 동일한.NET framework 버전을 사용 하 고 동일한 프로세스를 사용 하 여 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="9f3cc-169">기본적으로 Docker 이미지를 사용 하 여 응용 프로그램의 종속성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="9f3cc-170">종속성을 컨테이너를 배포 하는 경우 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="9f3cc-171">또 다른 이점은 개발자가 Windows 컨테이너에서 제공 하는 일관 된 환경에서 응용 프로그램 실행 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="9f3cc-172">스테이징 또는 프로덕션 환경에서 표시 하는 대신 특정 버전에만 표시 되는 문제를 즉시 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="9f3cc-173">개발 팀의 멤버에서 사용 하는 개발 환경에 차이가 덜 중요 해 집니다 컨테이너에서 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="9f3cc-174">컨테이너 화 된 응용 프로그램에는 스케일 아웃 곡선을 flatter 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="9f3cc-175">컨테이너 화 된 앱 VM 또는 물리적 컴퓨터 컴퓨터당 일반 응용 프로그램 배포에 비해 더 많은 응용 프로그램 및 서비스 인스턴스 (컨테이너 기반) 할 수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="9f3cc-176">밀도가 높아지고 필요한 변환이 Kubernetes 또는 Service Fabric과 같은 오 케 스트레이 터를 사용 하는 경우에 특히 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="9f3cc-177">이상적인 상황에서는 컨테이너 화 응용 프로그램 코드 변경 필요 하지 않습니다 (C\#).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="9f3cc-178">대부분의 시나리오에서 하기만 하면 Docker 배포 메타 데이터 파일 (Dockerfiles 및 Docker Compose 파일).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="9f3cc-179">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-179">Next steps</span></span>

<span data-ttu-id="9f3cc-180">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-180">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="9f3cc-181">Windows 컨테이너 및 Docker를 사용 하 여.NET Framework 웹 앱 컨테이너 화 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9f3cc-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="9f3cc-182">WCF 서비스에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="9f3cc-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="9f3cc-183">연습 3: Azure Vm에 Windows 컨테이너 기반 앱 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="9f3cc-184">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="9f3cc-184">Technical walkthrough availability</span></span>

<span data-ttu-id="9f3cc-185">전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다. [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="9f3cc-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="9f3cc-186">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-186">Overview</span></span>

<span data-ttu-id="9f3cc-187">Windows Server 2016 가상 머신 (VM) Azure에서 Docker 호스트에 배포할 개발/테스트/스테이징 환경에 신속 하 게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="9f3cc-188">또한, 테스터 또는 비즈니스 사용자가 앱의 유효성을 검사 하는 일반적인 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="9f3cc-189">또한 Vm 서비스 (IaaS) 프로덕션 환경으로 유효한 인프라를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-189">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-190">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-190">Goals</span></span>

<span data-ttu-id="9f3cc-191">이 연습의 목표는 Windows Server 2016 또는 이후 버전을 기반으로 하는 Azure Vm에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대체 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="9f3cc-192">시나리오</span><span class="sxs-lookup"><span data-stu-id="9f3cc-192">Scenarios</span></span>

<span data-ttu-id="9f3cc-193">몇 가지 시나리오는이 연습에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="9f3cc-194">시나리오 a: Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포](./media/image5-4.png)

<span data-ttu-id="9f3cc-196">**그림 5-4.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-196">**Figure 5-4.**</span></span> <span data-ttu-id="9f3cc-197">Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="9f3cc-198">시나리오 b: Docker 레지스트리를 통해 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

<span data-ttu-id="9f3cc-200">**그림 5-5.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-200">**Figure 5-5.**</span></span> <span data-ttu-id="9f3cc-201">Docker 레지스트리를 통해 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="9f3cc-202">시나리오: c: Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

<span data-ttu-id="9f3cc-204">**그림 5-6.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-204">**Figure 5-6.**</span></span> <span data-ttu-id="9f3cc-205">Azure DevOps 서비스의 CI/CD 파이프라인에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-205">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="9f3cc-206">Windows 컨테이너에 대 한 azure Vm</span><span class="sxs-lookup"><span data-stu-id="9f3cc-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="9f3cc-207">Windows 컨테이너에 대 한 azure Vm은 Windows Server 2016, Windows 10 또는 이상 버전에 따라 Vm, Docker 엔진을 사용 하 여 둘 다 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="9f3cc-208">대부분의 경우에서 Windows Server 2016 Azure Vm에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="9f3cc-209">Azure는 현재 이라는 VM을 제공 **컨테이너를 사용 하 여 Windows Server 2016**합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="9f3cc-210">Windows Server Core 또는 Windows Nano Server를 사용 하 여 새 Windows Server 컨테이너 기능을 사용이 VM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="9f3cc-211">컨테이너 OS 이미지를 설치한 하 고 VM이 Docker를 사용 하 여 사용할 준비가 다음 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="9f3cc-212">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-212">Benefits</span></span>

<span data-ttu-id="9f3cc-213">Azure에 배포할 때 온-프레미스 Windows Server 2016 Vm에 Windows 컨테이너를 배포할 수 있습니다, 있지만 Windows Server 컨테이너 Vm 사용 준비를 사용 하 여 시작 하는 간단한 방법인을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="9f3cc-214">테스터 및 Azure 가상 머신 확장 집합을 통해 자동 확장성에 액세스할 수 있는 공통 온라인 위치를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="9f3cc-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-215">Next steps</span></span>

<span data-ttu-id="9f3cc-216">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-216">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="9f3cc-217">연습 4: Azure Container Instances (ACI)에 Windows 컨테이너 기반 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="9f3cc-218">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="9f3cc-218">Technical walkthrough availability</span></span>

<span data-ttu-id="9f3cc-219">전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="9f3cc-220">[ACI (Azure Container Instances)에 앱 배포](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="9f3cc-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="9f3cc-221">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-221">Overview</span></span>

<span data-ttu-id="9f3cc-222">[Azure ACI (Container Instances)](https://docs.microsoft.com/azure/container-instances/) 는 컨테이너의 단일 인스턴스를 배포할 수 있는 컨테이너 개발/테스트/준비 환경을 사용 하는 가장 빠른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-223">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-223">Goals</span></span>

<span data-ttu-id="9f3cc-224">이 연습에서는 Windows 컨테이너를 Azure ACI (Container Instances) ACI를 eShopModernizing 앱을 배포 하는 방법을 배포 하는 경우 주요 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="9f3cc-225">시나리오</span><span class="sxs-lookup"><span data-stu-id="9f3cc-225">Scenarios</span></span>

<span data-ttu-id="9f3cc-226">ACI에 하나 또는 모든 앱 (MVC 앱, WebForms 앱 또는 WCF 서비스) 배포와 같은 eShopModernizing 앱을 배포 하는 방법에 대 한 변형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="9f3cc-227">아래에 표시 된 다음 시나리오에서 ACI (Azure Container Instances)으로 ASP.NET MVC 앱과 배포 둘 다 SQL Server 컨테이너 컨테이너로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![ACI에 개발 환경에서 배포](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="9f3cc-229">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-229">Benefits</span></span>

<span data-ttu-id="9f3cc-230">Azure Container Instances를 사용 하면 쉽게 만들고 가상 머신을 프로 비전 하거나 상위 수준 서비스를 채택 하지 않고도 Azure에서 Docker 컨테이너를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="9f3cc-231">ACI를 사용 하 여 직접 Azure에 Windows 컨테이너를 배포 하는 인터넷에 공개 된 정규화 된 도메인 이름 (FQDN)을 사용 하 여 몇 초에서에서 (있는 경우 Windows 컨테이너 이미지를 Docker 허브 또는 Azure 컨테이너와 같은 Docker 레지스트리에 레지스트리)입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="9f3cc-232">고려 사항</span><span class="sxs-lookup"><span data-stu-id="9f3cc-232">Considerations</span></span>

<span data-ttu-id="9f3cc-233">전체.NET Framework 중 하나를 사용 하 여 Windows 컨테이너를 배포 / ASP.NET 또는 SQL Server에 Azure ACI (Container Instances)는 매우 빨리 Docker 이미지 수 있으므로 (예: Windows 컨테이너를 사용 하 여 Windows Server 2016) 일반 Docker 호스트에 배포 하지만 될 때마다 (Docker 레지스트리에서 끌어온) 다운로드 하 고 (영구적으로 온라인 사용자 고유의 docker 호스트를 유지 관리 보다 훨씬 저렴 SQL 컨테이너 이미지 (15.1 GB) 및 ASP.NET 컨테이너 이미지 (13.9 GB)의 크기는 훨씬 큰 경우 Azure에서 VM에 Windows 컨테이너를 사용 하 여 Windows Server 2016) 인 반면에 유리한 프로덕션 배포에는 Azure (AKS/ACS) 또는 Azure Service Fabric에서 Kubernetes와 같은 전체 orchestrator 말할 것도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="9f3cc-234">주 결론으로 Azure Container Instances를 사용 하 여는 CI/CD 파이프라인 및 개발/테스트 시나리오에 대 한 매우 매력적인 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f3cc-235">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-235">Next steps</span></span>

<span data-ttu-id="9f3cc-236">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-236">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="9f3cc-237">연습 5: Azure Container Service에서 Kubernetes에 Windows 컨테이너 기반 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="9f3cc-238">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="9f3cc-238">Technical walkthrough availability</span></span>

<span data-ttu-id="9f3cc-239">전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="9f3cc-240">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-240">Overview</span></span>

<span data-ttu-id="9f3cc-241">Windows 컨테이너를 기반으로 하는 응용 프로그램 플랫폼에서 멀리 더욱 IaaS Vm에서 사용 하 여 신속 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="9f3cc-242">이 쉽게 높은 확장성을 달성 하는 데 필요한 더 확장성, 자동화 된 및의 향상에 대 한 배포 및 버전 관리를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="9f3cc-243">오 케 스트레이 터를 사용 하 여 이러한 목표를 달성할 수 있습니다 [Kubernetes](https://kubernetes.io/)에 사용 가능 [Azure Container Services](https://azure.microsoft.com/services/container-service/)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-244">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-244">Goals</span></span>

<span data-ttu-id="9f3cc-245">Kubernetes에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 방법을 알아보려면이 연습의 목적은 (라고도 *K8s*) Azure Container Service에서.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="9f3cc-246">부터 Kubernetes에 배포 하는 2 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="9f3cc-247">Azure Container Service에 Kubernetes 클러스터를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="9f3cc-248">Kubernetes 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="9f3cc-249">시나리오</span><span class="sxs-lookup"><span data-stu-id="9f3cc-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="9f3cc-250">시나리오 a: 개발 환경에서 Kubernetes 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![개발 환경에서 Kubernetes 클러스터에 직접 배포](./media/image5-7.png)

<span data-ttu-id="9f3cc-252">**그림 5-7.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-252">**Figure 5-7.**</span></span> <span data-ttu-id="9f3cc-253">개발 환경에서 Kubernetes 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="9f3cc-254">시나리오 b: Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포](./media/image5-8.png)

<span data-ttu-id="9f3cc-256">**그림 5-8.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-256">**Figure 5-8.**</span></span> <span data-ttu-id="9f3cc-257">Azure DevOps 서비스의 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="9f3cc-258">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-258">Benefits</span></span>

<span data-ttu-id="9f3cc-259">Kubernetes 클러스터를 배포 하는 다음과 같은 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="9f3cc-260">가장 큰 장점은는 확장할 수 있습니다 (내부-확장성 있는 기존 노드에)를 사용 하 고 클러스터 (에서 노드 또는 Vm의 수를 기준으로 컨테이너 인스턴스 수를 기준으로 응용 프로그램을 프로덕션 준비 환경 표시 글로벌 확장성 클러스터)입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="9f3cc-261">Azure Container Service는 인기 있는 오픈 소스 도구 및 기술을 특별히 Azure 용으로 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="9f3cc-262">컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="9f3cc-263">크기, 호스트의 수를 선택 하 고 다른 모든 항목을 처리 하는 오 케 스트레이 터 도구-컨테이너 서비스 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="9f3cc-264">Kubernetes를 사용 하 여 개발자 수행해 볼 수 있습니다 실제 및 가상 컴퓨터에 대 한 생각은 다음 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라를 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="9f3cc-265">여러 컨테이너 기반 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9f3cc-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="9f3cc-266">Container instances 및 수평적 자동 크기 조정을 복제</span><span class="sxs-lookup"><span data-stu-id="9f3cc-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="9f3cc-267">이름 지정 및 검색 (예를 들어 내부 DNS)</span><span class="sxs-lookup"><span data-stu-id="9f3cc-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="9f3cc-268">부하 분산</span><span class="sxs-lookup"><span data-stu-id="9f3cc-268">Balancing loads</span></span>

- <span data-ttu-id="9f3cc-269">롤링 업데이트</span><span class="sxs-lookup"><span data-stu-id="9f3cc-269">Rolling updates</span></span>

- <span data-ttu-id="9f3cc-270">암호를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-270">Distributing secrets</span></span>

- <span data-ttu-id="9f3cc-271">응용 프로그램 상태 검사</span><span class="sxs-lookup"><span data-stu-id="9f3cc-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f3cc-272">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-272">Next steps</span></span>

<span data-ttu-id="9f3cc-273">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기 [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="9f3cc-273">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="9f3cc-274">연습 6: Azure Service Fabric에 Windows 컨테이너 기반 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="9f3cc-275">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="9f3cc-275">Technical walkthrough availability</span></span>

<span data-ttu-id="9f3cc-276">전체 기술 연습 eShopModernizing GitHub 리포지토리 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="9f3cc-277">개요</span><span class="sxs-lookup"><span data-stu-id="9f3cc-277">Overview</span></span>

<span data-ttu-id="9f3cc-278">Windows 컨테이너를 신속 하 게 기반 응용 프로그램 플랫폼에서 IaaS Vm에서 지금 이동 더욱 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="9f3cc-279">이 쉽게 높은 확장성을 달성 하는 데 필요한 더 확장성, 자동화 된 및의 향상에 대 한 배포 및 버전 관리를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="9f3cc-280">다른 공용 클라우드 또는 오 케 스트레이 터 인 Azure 클라우드에서 사용할 수 있지만 사용할 수 있는 온-프레미스 Azure Service Fabric을 사용 하 여 이러한 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="9f3cc-281">목표</span><span class="sxs-lookup"><span data-stu-id="9f3cc-281">Goals</span></span>

<span data-ttu-id="9f3cc-282">이 연습의 목표는 Azure에서 Service Fabric 클러스터에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 방법을 알아보려면입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="9f3cc-283">부터 Service Fabric에 배포 하는 2 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1. <span data-ttu-id="9f3cc-284">Azure로 (또는 다른 환경으로) Service Fabric 클러스터를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2. <span data-ttu-id="9f3cc-285">Service Fabric 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="9f3cc-286">시나리오</span><span class="sxs-lookup"><span data-stu-id="9f3cc-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="9f3cc-287">시나리오 a: 개발 환경에서 Service Fabric 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![개발 환경에서 Service Fabric 클러스터에 직접 배포](./media/image5-9.png)

> <span data-ttu-id="9f3cc-289">**그림 5-9.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-289">**Figure 5-9.**</span></span> <span data-ttu-id="9f3cc-290">개발 환경에서 Service Fabric 클러스터에 직접 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="9f3cc-291">시나리오 b: Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포](./media/image5-10.png)

<span data-ttu-id="9f3cc-293">**그림 5-10.**</span><span class="sxs-lookup"><span data-stu-id="9f3cc-293">**Figure 5-10.**</span></span> <span data-ttu-id="9f3cc-294">Azure DevOps 서비스의 CI/CD 파이프라인에서 Service Fabric 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="9f3cc-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

## <a name="benefits"></a><span data-ttu-id="9f3cc-295">이점</span><span class="sxs-lookup"><span data-stu-id="9f3cc-295">Benefits</span></span>

<span data-ttu-id="9f3cc-296">Service Fabric에서 클러스터에 배포 하는 이점을 Kubernetes를 사용 하는 이점은 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="9f3cc-297">한 가지 차이점 그러나은 Service Fabric Windows 컨테이너 버전 1.9로 Kubernetes에 대 한 베타 단계에는 Kubernetes에 비해 Windows 응용 프로그램에 대 한 더 완성도 높은 프로덕션 환경 (2017 년 12 월).</span><span class="sxs-lookup"><span data-stu-id="9f3cc-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="9f3cc-298">Kubernetes에 Linux에 대 한 보다 성숙한 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="9f3cc-299">Azure Service Fabric을 사용 하는 주요 이점은는 확장할 수 있습니다 (내부-확장성 있는 기존 노드에)를 사용 하 고의 수를 기준으로 컨테이너 인스턴스 수를 기준으로 응용 프로그램을 프로덕션이 준비 된 환경을 제공 하는 노드 또는 클러스터 (클러스터의 글로벌 확장성)의 Vm입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="9f3cc-300">Azure Service Fabric은 컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="9f3cc-301">Service Fabric 클러스터에 Azure 또는 고유한 데이터 센터에 온-프레미스 설치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="9f3cc-302">다른 클라우드에서 Service Fabric 클러스터와 같은 설치도 [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="9f3cc-303">Service Fabric을 사용 하 여 개발자 수행해 볼 수 있습니다 실제 및 가상 컴퓨터에 대 한 생각은 다음 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라를 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="9f3cc-304">여러 컨테이너 기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="9f3cc-305">Container instances 및 수평적 자동 크기 조정을 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="9f3cc-306">이름 지정 및 (예를 들어 내부 DNS)를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="9f3cc-307">부하를 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-307">Balancing loads.</span></span>

- <span data-ttu-id="9f3cc-308">롤링 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-308">Rolling updates.</span></span>

- <span data-ttu-id="9f3cc-309">비밀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-309">Distributing secrets.</span></span>

- <span data-ttu-id="9f3cc-310">응용 프로그램 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-310">Application health checks.</span></span>

<span data-ttu-id="9f3cc-311">다음 기능은 다른 오 케 스트레이 터와 비교 하는 Service Fabric에서 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="9f3cc-312">상태 저장 Reliable Services 응용 프로그램 모델을 통해 기능을 서비스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="9f3cc-313">Reliable Actors 응용 프로그램 모델을 통해 행위자 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="9f3cc-314">Windows 또는 Linux 컨테이너 외에도 틀 프로세스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="9f3cc-315">고급 롤링 업데이트 및 상태 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3cc-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="9f3cc-316">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9f3cc-316">Next steps</span></span>

<span data-ttu-id="9f3cc-317">GitHub wiki의이 콘텐츠를 더 자세히 살펴보기</span><span class="sxs-lookup"><span data-stu-id="9f3cc-317">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

> [!div class="step-by-step"]
> <span data-ttu-id="9f3cc-318">[이전](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [다음](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="9f3cc-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
