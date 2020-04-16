---
title: Azure .NET 및 .NET Core 개발자용 도구
description: Windows, Linux 및 Mac 환경에서 Azure .NET 라이브러리를 사용하여 시작하는 도구를 가져옵니다.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433165"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="c252e-103">.NET 및 .NET Core Azure 개발자용 도구</span><span class="sxs-lookup"><span data-stu-id="c252e-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="c252e-104">SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-104">SDK downloads</span></span>

<span data-ttu-id="c252e-105">.NET에 대한 Azure 라이브러리는 [NuGet 패키지로 구현됩니다.](https://www.nuget.org/packages?q=windowsazureofficial)</span><span class="sxs-lookup"><span data-stu-id="c252e-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="c252e-106">Azure 서비스로 구성된 설치 지침은 [API 참조를](/dotnet/api/overview/azure/?view=azure-dotnet) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c252e-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="c252e-107">개발 도구</span><span class="sxs-lookup"><span data-stu-id="c252e-107">Development tools</span></span>

<span data-ttu-id="c252e-108">Visual Studio에는 많은 Azure 서비스에 대한 도구가 내장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="c252e-109">일부 Azure 서비스에는 [Azure 저장소 탐색기와](https://azure.microsoft.com/features/storage-explorer/)같은 추가 도구 또는 에뮬레이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="c252e-110">필요한 경우 Azure 서비스에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c252e-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="c252e-111">이 지침은 운영 체제에 권장되는 시작 개발 환경을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="c252e-112">Windows</span><span class="sxs-lookup"><span data-stu-id="c252e-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="c252e-113">Visual Studio 버전 2017 이상Azure 개발에 대 한 기본 제공 지원.</span><span class="sxs-lookup"><span data-stu-id="c252e-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="c252e-114">아래 단계는 Visual Studio에서 Azure 개발 지원을 사용하도록 설정하는 것을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="c252e-115">Visual Studio 2015 및 이전 의 경우 <a href="vs2015-install.md">다음 지침을 따르십시오.</a></span><span class="sxs-lookup"><span data-stu-id="c252e-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="c252e-116">1단계: 비주얼 스튜디오 2019 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="c252e-117">Visual Studio 2019가 이미 설치되어 있는 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c252e-118">Visual Studio 2019 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="c252e-119">2단계: 두 개의 Azure 워크로드 설치</span><span class="sxs-lookup"><span data-stu-id="c252e-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="c252e-120">Visual Studio 설치 관리자에서 Visual Studio를 설치하거나 기존 설치를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="c252e-121">*Azure 개발* 및 *ASP.NET 및 웹 개발* 워크로드가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="c252e-122">3단계: Azure에서 .NET을 사용하여 개발</span><span class="sxs-lookup"><span data-stu-id="c252e-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="c252e-123">[Azure App Service에서 첫 ASP.NET Core 웹 앱 배포](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="c252e-124">macOS</span><span class="sxs-lookup"><span data-stu-id="c252e-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="c252e-125">Mac용 Visual Studio에는 Azure 개발에 필요한 모든 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="c252e-126">1단계: Mac용 Visual Studio 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c252e-127">Mac용 Visual Studio 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="c252e-128">설치 하는 동안 Azure 도구는 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="c252e-129">Linux</span><span class="sxs-lookup"><span data-stu-id="c252e-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="c252e-130">Visual Studio Code에는 Linux에서 Azure 개발에 필요한 모든 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="c252e-131">1 단계: .NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="c252e-132">.NET Core 앱용 SDK 및 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c252e-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c252e-133">.NET Core SDK 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="c252e-134">2단계: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c252e-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="c252e-135">모든 운영 체제에서.NET Core 앱 편집 및 디버그: Windows, Mac, Linux</span><span class="sxs-lookup"><span data-stu-id="c252e-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c252e-136">Visual Studio Code 다운로드</span><span class="sxs-lookup"><span data-stu-id="c252e-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
