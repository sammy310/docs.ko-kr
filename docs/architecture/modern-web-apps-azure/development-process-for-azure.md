---
title: Azure 개발 프로세스
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 애플리케이션 설계 | Azure 개발 프로세스
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 830271d76e5a87ed782d81fa9491328c580f0f87
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849580"
---
# <a name="development-process-for-azure"></a><span data-ttu-id="29de4-103">Azure 개발 프로세스</span><span class="sxs-lookup"><span data-stu-id="29de4-103">Development process for Azure</span></span>

> <span data-ttu-id="29de4-104">_"클라우드를 사용하면 개인과 소규모 기업은 손가락만으로 엔터프라이즈급 서비스를 즉시 설정할 수 있습니다."_</span><span class="sxs-lookup"><span data-stu-id="29de4-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="29de4-105">_- Roy Stephan_</span><span class="sxs-lookup"><span data-stu-id="29de4-105">_- Roy Stephan_</span></span>

## <a name="vision"></a><span data-ttu-id="29de4-106">비전</span><span class="sxs-lookup"><span data-stu-id="29de4-106">Vision</span></span>

> <span data-ttu-id="29de4-107">*Visual Studio 또는 dotnet CLI와 Visual Studio Code 또는 원하는 편집기를 사용하여 원하는 방식으로 잘 설계된 ASP.NET Core 애플리케이션을 개발합니다.*</span><span class="sxs-lookup"><span data-stu-id="29de4-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="29de4-108">ASP.NET Core 앱 개발 환경</span><span class="sxs-lookup"><span data-stu-id="29de4-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="29de4-109">개발 도구 선택: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="29de4-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="29de4-110">개발자가 완전하고 강력한 IDE를 선호하든 아니면 가볍고 민첩한 편집기를 선호하든, Microsoft에서는 ASP.NET Core 애플리케이션 개발에 필요한 모든 것을 제공해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="29de4-111">**Visual Studio 2017.**</span><span class="sxs-lookup"><span data-stu-id="29de4-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="29de4-112">*Visual Studio 2017*을 사용하는 경우 *.NET Core 플랫폼 간 개발* 워크로드가 설치되어 있다면 ASP.NET Core 애플리케이션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="29de4-113">그림 10-1은 Visual Studio 2017 설정 대화 상자에서 필요한 워크로드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![Visual Studio 2017에 .NET Core 워크로드 설치](./media/image10-1.png)

<span data-ttu-id="29de4-115">**그림 10-1.**</span><span class="sxs-lookup"><span data-stu-id="29de4-115">**Figure 10-1.**</span></span> <span data-ttu-id="29de4-116">Visual Studio 2017에 .NET Core 워크로드 설치.</span><span class="sxs-lookup"><span data-stu-id="29de4-116">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="29de4-117">Visual Studio 2017 다운로드</span><span class="sxs-lookup"><span data-stu-id="29de4-117">Download Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

<span data-ttu-id="29de4-118">**Visual Studio Code 및 dotnet CLI**(Mac, Linux 및 Windows용 플랫폼 간 도구).</span><span class="sxs-lookup"><span data-stu-id="29de4-118">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="29de4-119">모든 개발 언어를 지원하는 가벼운 플랫폼 간 편집기를 선호하는 경우 Microsoft Visual Studio Code 및 docker CLI를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-119">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="29de4-120">이러한 제품은 간단하지만 강력한 환경을 제공하여 개발자 워크플로를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-120">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="29de4-121">또한 Visual Studio Code는 C\# 확장 및 웹 개발을 지원하며, 편집기 내에서 인텔리전스 및 바로 가기 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-121">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="29de4-122">.NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="29de4-122">Download the .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

[<span data-ttu-id="29de4-123">Visual Studio Code 다운로드</span><span class="sxs-lookup"><span data-stu-id="29de4-123">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="29de4-124">Azure에서 호스트되는 ASP.NET Core 앱의 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="29de4-124">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="29de4-125">애플리케이션 개발 수명 주기는 각 개발자의 컴퓨터에서 시작되며, 개발자는 선호하는 언어를 사용하여 로컬로 앱을 코딩하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-125">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="29de4-126">개발자는 빌드 서버를 사용하여 또는 기본 제공 Azure 기능을 기반으로 선호하는 소스 제어 시스템을 선택하고 CI(연속 통합) 및/또는 CD(지속적인 업데이트/지속적인 배포)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-126">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="29de4-127">CI/CD를 사용하여 ASP.NET Core 애플리케이션 개발을 시작하려면 Azure DevOps Services 또는 조직에서 소유한 TFS(Team Foundation Server)를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-127">To get started with developing an ASP.NET Core application using CI/CD, you can use Azure DevOps Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="29de4-128">초기 설정</span><span class="sxs-lookup"><span data-stu-id="29de4-128">Initial setup</span></span>

<span data-ttu-id="29de4-129">앱에 대한 릴리스 파이프라인을 만들려면 소스 제어에 애플리케이션 코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-129">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="29de4-130">로컬 리포지토리를 설정하고 팀 프로젝트의 원격 리포지토리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-130">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="29de4-131">다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-131">Follow these instructions:</span></span>

- <span data-ttu-id="29de4-132">[Git 및 Visual Studio와 코드 공유](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs) 또는</span><span class="sxs-lookup"><span data-stu-id="29de4-132">[Share your code with Git and Visual Studio](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs) or</span></span>

- [<span data-ttu-id="29de4-133">TFVC 및 Visual Studio와 코드 공유</span><span class="sxs-lookup"><span data-stu-id="29de4-133">Share your code with TFVC and Visual Studio</span></span>](https://docs.microsoft.com/azure/devops/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="29de4-134">애플리케이션을 배포할 Azure App Service를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-134">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="29de4-135">Azure Portal에서 App Services 블레이드로 이동하여 웹앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-135">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="29de4-136">+추가를 클릭하고, 웹앱 템플릿을 선택하고, 만들기를 클릭하고, 이름과 기타 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-136">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="29de4-137">웹앱은 {name}.azurewebsites.net에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-137">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="29de4-139">**그림 10-2.**</span><span class="sxs-lookup"><span data-stu-id="29de4-139">**Figure 10-2.**</span></span> <span data-ttu-id="29de4-140">Azure Portal에서 새 Azure App Service 웹앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-140">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="29de4-141">CI 빌드 프로세스는 프로젝트의 소스 제어 리포지토리에 새 코드가 커밋될 때마다 자동화된 빌드를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-141">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="29de4-142">이렇게 하면 코드에서 빌드하고(그리고 이상적으로 자동화된 테스트를 전달하고) 잠재적으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-142">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="29de4-143">이 CI 빌드는 웹 배포 패키지 아티팩트를 생성하고 CD 프로세스에서 사용할 수 있도록 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-143">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="29de4-144">CI 빌드 프로세스 정의</span><span class="sxs-lookup"><span data-stu-id="29de4-144">Define your CI build process</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#ci)

<span data-ttu-id="29de4-145">팀원 중 누군가가 새 코드를 커밋할 때마다 시스템이 빌드를 대기열에 추가하도록 연속 통합을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-145">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="29de4-146">빌드가 아티팩트 중 하나로 웹 배포 패키지를 생성하는지 빌드를 테스트 및 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-146">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="29de4-147">빌드에 성공하면 CD 프로세스에서 CI 빌드 결과를 Azure 웹앱에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-147">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="29de4-148">이렇게 구성하려면 Azure App Service에 배포하는 *릴리스*를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-148">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="29de4-149">CD 릴리스 프로세스 정의</span><span class="sxs-lookup"><span data-stu-id="29de4-149">Define your CD release process</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#cd)

<span data-ttu-id="29de4-150">CI/CD 파이프라인이 구성되면 간단하게 웹앱을 업데이트하고 소스 제어에 커밋하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-150">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="29de4-151">Azure에서 호스트되는 ASP.NET Core 애플리케이션을 개발하는 워크플로</span><span class="sxs-lookup"><span data-stu-id="29de4-151">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="29de4-152">Azure 계정 및 CI/CD 프로세스 구성이 완료되면 Azure에서 호스트되는 ASP.NET Core 애플리케이션을 간단하게 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-152">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="29de4-153">다음은 그림 10-3처럼 Azure App Service에 웹앱으로 호스트되는 ASP.NET Core 앱을 빌드할 때 수행하는 기본 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-153">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="29de4-155">**그림 10-3.**</span><span class="sxs-lookup"><span data-stu-id="29de4-155">**Figure 10-3.**</span></span> <span data-ttu-id="29de4-156">ASP.NET Core 앱을 빌드하고 Azure에서 호스팅하기 위한 단계별 워크플로</span><span class="sxs-lookup"><span data-stu-id="29de4-156">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="29de4-157">1단계:</span><span class="sxs-lookup"><span data-stu-id="29de4-157">Step 1.</span></span> <span data-ttu-id="29de4-158">로컬 개발 환경 내부 루프</span><span class="sxs-lookup"><span data-stu-id="29de4-158">Local dev environment inner loop</span></span>

<span data-ttu-id="29de4-159">Azure에 배포할 ASP.NET Core 애플리케이션 개발은 일반적인 애플리케이션 개발과 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-159">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="29de4-160">Visual Studio 2017, dotnet CLI, Visual Studio Code 또는 원하는 편집기 중 자신에게 편한 로컬 개발 환경을 사용하시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-160">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="29de4-161">코드를 작성하고, 변경 내용을 실행 및 디버그하고, 자동화된 테스트를 실행하고, 변경 내용을 공유 소스 제어 리포지토리에 푸시할 준비가 완료될 때까지 소스 제어에 로컬로 커밋할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-161">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="29de4-162">2단계.</span><span class="sxs-lookup"><span data-stu-id="29de4-162">Step 2.</span></span> <span data-ttu-id="29de4-163">애플리케이션 코드 리포지토리</span><span class="sxs-lookup"><span data-stu-id="29de4-163">Application code repository</span></span>

<span data-ttu-id="29de4-164">코드를 팀과 공유할 준비가 완료되면 로컬 소스 리포지토리의 변경 내용을 팀의 공유 소스 리포지토리에 푸시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-164">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="29de4-165">사용자 지정 분기에서 작업한 경우 이 단계에서 일반적으로 코드를 공유 분기에 병합(아마도 [끌어오기 요청](https://docs.microsoft.com/azure/devops/git/pull-requests)을 사용하여)하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-165">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://docs.microsoft.com/azure/devops/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="29de4-166">3단계.</span><span class="sxs-lookup"><span data-stu-id="29de4-166">Step 3.</span></span> <span data-ttu-id="29de4-167">빌드 서버: 지속적인 통합</span><span class="sxs-lookup"><span data-stu-id="29de4-167">Build Server: Continuous integration.</span></span> <span data-ttu-id="29de4-168">빌드, 테스트, 패키지</span><span class="sxs-lookup"><span data-stu-id="29de4-168">build, test, package</span></span>

<span data-ttu-id="29de4-169">공유 애플리케이션 코드 리포지토리에 새 커밋이 만들어질 때마다 빌드 서버에서 새 빌드가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-169">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="29de4-170">CI 프로세스의 일환으로, 이 빌드는 애플리케이션을 완전히 컴파일하고 자동화된 테스트를 실행하여 모든 것이 예상대로 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-170">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="29de4-171">CI 프로세스의 최종 결과는 즉시 배포가 가능한 웹앱의 패키지 버전이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-171">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="29de4-172">4단계.</span><span class="sxs-lookup"><span data-stu-id="29de4-172">Step 4.</span></span> <span data-ttu-id="29de4-173">빌드 서버: 지속적인 업데이트</span><span class="sxs-lookup"><span data-stu-id="29de4-173">Build Server: Continuous delivery</span></span>

<span data-ttu-id="29de4-174">빌드가 성공하면 CD 프로세스에서는 생성된 빌드 아티팩트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-174">Once a build has succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="29de4-175">여기에는 웹 배포 패키지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-175">This will include a web deploy package.</span></span> <span data-ttu-id="29de4-176">빌드 서버는 이 패키지를 Azure App Service에 배포하여 기존 서비스를 새로 만든 서비스로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-176">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="29de4-177">일반적으로 이 단계는 스테이징 환경을 대상으로 하지만, 일부 애플리케이션은 CD 프로세스를 통해 프로덕션 환경에 직접 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-177">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="29de4-178">5단계.</span><span class="sxs-lookup"><span data-stu-id="29de4-178">Step 5.</span></span> <span data-ttu-id="29de4-179">Azure App Service 웹앱</span><span class="sxs-lookup"><span data-stu-id="29de4-179">Azure App Service Web App</span></span>

<span data-ttu-id="29de4-180">배포되면 ASP.NET Core 애플리케이션은 Azure App Service 웹앱의 컨텍스트 내에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="29de4-181">이 웹앱은 Azure Portal을 사용하여 모니터링하고 추가로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="29de4-182">6단계.</span><span class="sxs-lookup"><span data-stu-id="29de4-182">Step 6.</span></span> <span data-ttu-id="29de4-183">프로덕션 모니터링 및 진단</span><span class="sxs-lookup"><span data-stu-id="29de4-183">Production monitoring and diagnostics</span></span>

<span data-ttu-id="29de4-184">웹앱이 실행되는 동안 애플리케이션의 상태를 모니터링하고 진단 및 사용자 동작 데이터를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="29de4-185">Application Insights는 Visual Studio에 포함되어 있으며, ASP.NET 앱을 위한 자동 계측 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="29de4-186">사용량, 예외, 요청, 성능 및 로그에 대한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29de4-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="29de4-187">참조</span><span class="sxs-lookup"><span data-stu-id="29de4-187">References</span></span>

<span data-ttu-id="29de4-188">**ASP.NET Core 앱을 빌드하고 Azure에 배포**</span><span class="sxs-lookup"><span data-stu-id="29de4-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
><span data-ttu-id="29de4-189">[이전](test-asp-net-core-mvc-apps.md)
>[다음](azure-hosting-recommendations-for-asp-net-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="29de4-189">[Previous](test-asp-net-core-mvc-apps.md)
[Next](azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>
