---
title: Azure 및 .NET 시작
description: Azure 및.NET에 대해 알아야 할 기본 사항을 알아봅니다.
ms.date: 06/20/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 5d14bd0d9930d41a8c60b58b9f5b0522f0c0e398
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700779"
---
# <a name="introduction-to-azure-and-net"></a><span data-ttu-id="ea0ff-103">Azure 및 .NET 소개</span><span class="sxs-lookup"><span data-stu-id="ea0ff-103">Introduction to Azure and .NET</span></span>

## <a name="what-is-azure"></a><span data-ttu-id="ea0ff-104">Azure란?</span><span class="sxs-lookup"><span data-stu-id="ea0ff-104">What is Azure?</span></span>

<span data-ttu-id="ea0ff-105">Azure는 최신 애플리케이션을 빌드하는 프로세스를 간소화하도록 설계된 클라우드 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-105">Azure is a cloud platform designed to simplify the process of building modern applications.</span></span>  <span data-ttu-id="ea0ff-106">애플리케이션을 Azure에서 완전히 호스트하든, Azure 서비스를 통해 온-프레미스 애플리케이션을 확장하든 Azure를 사용하면 스케일링 가능하고 안정적이며 유지 관리 가능한 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-106">Whether you choose to host your applications entirely in Azure or extend your on-premises applications with Azure services, Azure helps you create applications that are scalable, reliable, and maintainable.</span></span>  <span data-ttu-id="ea0ff-107">Visual Studio, Visual Studio Code와 같이 이미 사용하는 도구와 포괄적인 SDK 라이브러리를 광범위하게 지원하는 Azure는 .NET 개발자가 처음부터 생산성을 발휘하도록 지원하기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-107">With extensive support for tools you already use like Visual Studio and Visual Studio Code and a comprehensive SDK library, Azure is designed to make you, the .NET developer productive right from the start.</span></span>

## <a name="application-development-scenarios-on-azure"></a><span data-ttu-id="ea0ff-108">Azure의 애플리케이션 개발 시나리오</span><span class="sxs-lookup"><span data-stu-id="ea0ff-108">Application development scenarios on Azure</span></span>

<span data-ttu-id="ea0ff-109">요구에 따라 다양한 방법으로 Azure를 애플리케이션에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-109">You can incorporate Azure into your application in different ways depending on your needs.</span></span>

- <span data-ttu-id="ea0ff-110">**Azure에서 호스트하는 애플리케이션 -** Azure에서 웹 애플리케이션에서 API, 데이터베이스, 스토리지 서비스에 이르는 전체 애플리케이션 스택을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-110">**Application hosting on Azure -** Azure can host your entire application stack from web applications and APIs to databases to storage services.</span></span> <span data-ttu-id="ea0ff-111">Azure는 완전 관리형 서비스, 컨테이너, 가상 머신 등 다양한 호스팅 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-111">Azure supports a variety of hosting models from fully managed services to containers to virtual machines.</span></span> <span data-ttu-id="ea0ff-112">완전 관리형 Azure 서비스를 사용하는 경우 애플리케이션에서 Azure에 기본 제공되는 스케일링 성능, 고가용성, 보안을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-112">When using fully managed Azure services, your applications can take advantage of the scalability, high-availability, and security built in to Azure.</span></span>

- <span data-ttu-id="ea0ff-113">**애플리케이션에서 클라우드 서비스 사용 -** 기존 앱에서 Azure 서비스를 통합하여 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-113">**Consuming cloud services from applications -** Existing apps can incorporate Azure services to extend their capabilities.</span></span>  <span data-ttu-id="ea0ff-114">[Azure Cognitive Search](/azure/search/search-what-is-azure-search)를 사용한 전체 텍스트 검색 기능 추가, [Azure Key Vault](/azure/key-vault/)에 애플리케이션 비밀을 안전하게 저장, [Azure Cognitive Services](/azure/cognitive-services/)를 사용하여 비전, 음성, 언어 이해 기능 추가 등을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-114">This could include adding full-text searching capability with [Azure Cognitive Search](/azure/search/search-what-is-azure-search), securely storing application secrets in [Azure Key Vault](/azure/key-vault/) or adding vision, speech and language understanding capabilities with [Azure Cognitive Services](/azure/cognitive-services/).</span></span>  <span data-ttu-id="ea0ff-115">이러한 서비스는 Azure에서 완전히 관리되며 현재 애플리케이션 아키텍처나 배포 모델을 변경하지 않고 애플리케이션에 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-115">These services are fully managed by Azure and can be easily added to your application without changing your current application architecture or deployment model.</span></span>

- <span data-ttu-id="ea0ff-116">**최신 서버리스 아키텍처 -** Azure Functions는 HTTP 요청에 응답, Blob 스토리지에서 파일 업로드 처리, 큐의 이벤트 처리 등의 이벤트 기반 워크플로를 처리하는 솔루션의 빌드를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-116">**Modern serverless architectures -** Azure Functions simplify building solutions to handle event-driven workflows, whether responding to HTTP requests, handling file uploads in Blob storage, or processing events in a queue.</span></span>  <span data-ttu-id="ea0ff-117">서버 또는 프레임워크 코드는 신경 쓰지 않고 이벤트 처리에 필요한 코드만 작성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-117">You write only the code necessary to handle your event without worrying about servers or framework code.</span></span>  <span data-ttu-id="ea0ff-118">또한 기타 Azure 및 타사 서비스에 대한 250개 넘는 커넥터를 활용하여 가장 까다로운 통합 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-118">Further, you can take advantage of over 250 connectors to other Azure and third-party services to tackle your toughest integration problems.</span></span>

## <a name="access-azure-services-from-net-applications"></a><span data-ttu-id="ea0ff-119">.NET 애플리케이션에서 Azure 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="ea0ff-119">Access Azure services from .NET applications</span></span>

<span data-ttu-id="ea0ff-120">앱이 Azure나 온-프레미스 어디에 호스트되어 있든 관계없이 **.NET용 Azure SDK** 를 통해 대부분의 Azure 서비스 액세스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-120">Whether your app is hosted in Azure or on-premises, access to most Azure services is provided through the **Azure SDK for .NET**.</span></span>  <span data-ttu-id="ea0ff-121">.NET용 Azure SDK는 일련의 NuGet 패키지로 제공되며 .NET Core(2.1 이상)와 .NET Framework(4.6.1 이상) 애플리케이션 모두에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-121">The Azure SDK for .NET is provided as a series of NuGet packages and can be used in both .NET Core (2.1 and higher) and .NET Framework (4.6.1 and higher) applications.</span></span> <span data-ttu-id="ea0ff-122">.NET용 Azure SDK를 사용하면 적합한 NuGet 패키지를 설치하고 클라이언트 개체를 인스턴스화하고 적절한 메서드를 호출하는 것만큼 쉽게 Azure 서비스를 애플리케이션에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-122">The Azure SDK for .NET makes incorporating Azure services into your application as easy as installing the correct NuGet package, instantiating a client object and calling the appropriate methods.</span></span> <span data-ttu-id="ea0ff-123">.NET용 Azure SDK에 대한 자세한 내용은 [.NET용 Azure SDK 개요](./sdk/azure-sdk-for-dotnet.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-123">More information on the Azure SDK for .NET can be found in the [Azure SDK for .NET Overview](./sdk/azure-sdk-for-dotnet.md).</span></span>

![.NET 애플리케이션에서 Azure SDK를 사용하여 Azure 서비스에 액세스하는 방법을 보여 주는 다이어그램](./media/azure-sdk-for-dotnet-overview.png)

## <a name="next-steps"></a><span data-ttu-id="ea0ff-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ea0ff-125">Next steps</span></span>

<span data-ttu-id="ea0ff-126">다음으로 .NET 개발을 위해 [일반적으로 사용되는 Azure 서비스](./key-azure-services.md)에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ff-126">Next, learn about the most [commonly used Azure services](./key-azure-services.md) for .NET development.</span></span>
