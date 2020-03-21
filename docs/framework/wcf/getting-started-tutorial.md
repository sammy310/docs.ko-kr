---
title: '자습서: Windows 통신 기반 응용 프로그램 시작'
description: 이 자습서에서는 WCF 응용 프로그램을 만들기 위한 소개를 제공합니다.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184119"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="16dbf-103">자습서: Windows 통신 기반 응용 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="16dbf-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="16dbf-104">다음 자습서 시리즈에서는 WCF(Windows 통신 재단) 프로그래밍 환경을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="16dbf-105">이 자습서를 순서대로 진행하면 WCF 응용 프로그램을 만드는 데 필요한 단계를 소개해 드립니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="16dbf-106">완료되면 실행 중인 WCF 서비스와 서비스를 호출하는 WCF 클라이언트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="16dbf-107">이 자습서에서는 Visual Studio를 개발 환경으로 사용하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="16dbf-108">다른 개발 환경을 사용하는 경우 Visual Studio 관련 지침을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="16dbf-109">다운로드하여 실행할 수 있는 샘플 WCF 응용 프로그램에 대한 Windows [통신 재단 샘플을](samples/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16dbf-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="16dbf-110">샘플에 대한 소개는 [시작 샘플 을](samples/getting-started-sample.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16dbf-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="16dbf-111">서비스 및 클라이언트 만들기에 대한 자세한 내용은 [기본 WCF 프로그래밍](basic-wcf-programming.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16dbf-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="16dbf-112">WCF 자습서</span><span class="sxs-lookup"><span data-stu-id="16dbf-112">WCF tutorials</span></span>

<span data-ttu-id="16dbf-113">처음 세 가지 자습서에서는 WCF 서비스 계약을 정의하는 방법, 이를 구현하는 방법 및 이를 호스트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="16dbf-114">사용자가 만드는 서비스는 콘솔 응용 프로그램 내에서 자체 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="16dbf-115">또한 IIS(Microsoft 인터넷 정보 서비스)에서 서비스를 호스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="16dbf-116">자세한 내용은 [IIS에서 WCF 서비스를 호스팅하는 방법을](feature-details/how-to-host-a-wcf-service-in-iis.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="16dbf-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="16dbf-117">코드를 사용하여 자습서에서 서비스를 구성하지만 [구성 파일 내에서 서비스를 구성할](configuring-services-using-configuration-files.md)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="16dbf-118">자습서: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="16dbf-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="16dbf-119">사용자 정의 인터페이스를 사용하여 WCF 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="16dbf-120">이 계약은 서비스가 노출하는 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="16dbf-121">자습서: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="16dbf-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="16dbf-122">계약을 정의한 후에는 서비스 클래스로 계약을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="16dbf-123">자습서: 기본 서비스 호스트 및 실행</span><span class="sxs-lookup"><span data-stu-id="16dbf-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="16dbf-124">서비스에 대한 엔드포인트를 구성하고 콘솔 응용 프로그램에서 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="16dbf-125">서비스가 활성화되려면 서비스를 구성하고 런타임 환경 내에서 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="16dbf-126">이 런타임 환경은 서비스를 만들고 해당 컨텍스트 및 수명을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="16dbf-127">다음 두 자습서에서는 클라이언트 응용 프로그램을 만들고 구성하고 사용하여 서비스가 노출하는 작업을 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="16dbf-128">서비스는 클라이언트 애플리케이션이 서비스와 통신하는 데 필요한 정보를 정의하는 메타데이터를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="16dbf-129">Visual Studio는 이 메타데이터에 액세스하는 프로세스를 자동화하고 이를 사용하여 서비스에 대한 클라이언트 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="16dbf-130">Visual Studio를 사용하지 않기로 결정한 경우 [서비스모델 메타데이터 유틸리티*도구(Svcutil.exe)를*](servicemodel-metadata-utility-tool-svcutil-exe.md) 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="16dbf-131">자습서: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="16dbf-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="16dbf-132">WCF 서비스에서 WCF 클라이언트 프록시를 만들기 위해 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="16dbf-133">Visual Studio를 사용하여 서비스 참조를 추가하거나 ServiceModel 메타데이터 유틸리티 도구를 사용하여 메타데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="16dbf-134">클라이언트가 서비스에 액세스하는 데 사용하는 끝점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="16dbf-135">자습서: 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="16dbf-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="16dbf-136">WCF 클라이언트 프록시를 사용하여 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="16dbf-137">참조</span><span class="sxs-lookup"><span data-stu-id="16dbf-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="16dbf-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16dbf-138">See also</span></span>

- [<span data-ttu-id="16dbf-139">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="16dbf-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="16dbf-140">문서 가이드</span><span class="sxs-lookup"><span data-stu-id="16dbf-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="16dbf-141">윈도우 커뮤니케이션 재단이란?</span><span class="sxs-lookup"><span data-stu-id="16dbf-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="16dbf-142">WCF 기능 세부 정보</span><span class="sxs-lookup"><span data-stu-id="16dbf-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="16dbf-143">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="16dbf-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="16dbf-144">클라이언트 구축</span><span class="sxs-lookup"><span data-stu-id="16dbf-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="16dbf-145">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="16dbf-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="16dbf-146">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="16dbf-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="16dbf-147">방법: 이중 계약을 통해 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="16dbf-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="16dbf-148">서비스 모델 메타 데이터 유틸리티 도구 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="16dbf-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="16dbf-149">방법: Svcutil.exe를 사용하여 메타데이터 문서를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="16dbf-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="16dbf-150">방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="16dbf-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="16dbf-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="16dbf-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="16dbf-152">시작 샘플</span><span class="sxs-lookup"><span data-stu-id="16dbf-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="16dbf-153">윈도우 커뮤니케이션 재단 샘플</span><span class="sxs-lookup"><span data-stu-id="16dbf-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="16dbf-154">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="16dbf-154">Self-Host</span></span>](samples/self-host.md)
