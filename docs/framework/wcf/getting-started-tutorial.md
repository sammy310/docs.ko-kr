---
title: '자습서: Windows Communication Foundation 응용 프로그램 시작'
description: 이 자습서는 WCF 응용 프로그램 만들기에 대 한 소개를 제공 합니다.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: d4613edefeb8db2c0d1e11e925f8ac41329efb0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137932"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="26a4e-103">자습서: Windows Communication Foundation 응용 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="26a4e-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="26a4e-104">다음 일련의 자습서는 프로그래밍 환경의 Windows Communication Foundation (WCF)를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="26a4e-105">작업 순서에서이 자습서를 통해 WCF 응용 프로그램을 만드는 데 필요한 단계를 대략적으로 이해할을 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="26a4e-106">를 마친 후에 실행 중인 WCF 서비스 및 서비스를 호출 하는 WCF 클라이언트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span> 

<span data-ttu-id="26a4e-107">이 자습서에서는 개발 환경으로 Visual Studio를 사용 하는 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="26a4e-108">다른 개발 환경을 사용 하는 경우 Visual Studio 관련 지침을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span> 

<span data-ttu-id="26a4e-109">샘플 WCF 응용 프로그램 다운로드 하 고 실행할 수 있는 참조 [Windows Communication Foundation 샘플](samples/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="26a4e-110">샘플에 대 한 소개를 참조 하세요 [시작 샘플](samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="26a4e-111">자세한 내용은 서비스 및 클라이언트 만들기에 대 한 참조 [기본 WCF 프로그래밍](basic-wcf-programming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="26a4e-112">WCF 자습서</span><span class="sxs-lookup"><span data-stu-id="26a4e-112">WCF tutorials</span></span>

<span data-ttu-id="26a4e-113">처음 세 개의 자습서에는 WCF 서비스 계약을 정의 하는 방법, 구현 하는 방법 및 호스트 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="26a4e-114">사용자가 만든 서비스 콘솔 응용 프로그램 내에서 자체 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="26a4e-115">Microsoft 인터넷 정보 서비스 (IIS)에서 서비스를 호스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="26a4e-116">자세한 내용은 [방법: IIS에서 WCF 서비스 호스팅](feature-details/how-to-host-a-wcf-service-in-iis.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="26a4e-117">코드를 사용 하 여 자습서에서 서비스를 구성 하지만 수도 있습니다 [구성 파일 내에서 서비스 구성](configuring-services-using-configuration-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span> 

- [<span data-ttu-id="26a4e-118">자습서: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="26a4e-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="26a4e-119">사용자 정의 인터페이스를 사용 하 여 WCF 계약을 만들어야합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="26a4e-120">이 계약은 서비스에서 제공 하는 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="26a4e-121">자습서: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="26a4e-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="26a4e-122">계약을 정의한 후 서비스 클래스를 사용 하 여 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="26a4e-123">자습서: 기본 서비스 호스트 및 실행</span><span class="sxs-lookup"><span data-stu-id="26a4e-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="26a4e-124">서비스 끝점을 구성 하 고 콘솔 응용 프로그램에서 서비스를 호스팅하십시오.</span><span class="sxs-lookup"><span data-stu-id="26a4e-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="26a4e-125">활성화 되는 서비스에 대 한 런타임 환경 내에서 호스트를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="26a4e-126">이 런타임 환경 서비스를 만들고 컨텍스트와 수명을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="26a4e-127">다음 두 자습서에는 만들기, 구성 하는 방법을 설명 하 고 사용 하 여 서비스 작업을 호출 하려면 클라이언트 응용 프로그램을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="26a4e-128">서비스는 클라이언트 응용 프로그램이 서비스와 통신하는 데 필요한 정보를 정의하는 메타데이터를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="26a4e-129">Visual Studio는이 메타 데이터에 액세스 하는 프로세스를 자동화 및 서비스용 클라이언트 응용 프로그램을 생성 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="26a4e-130">Visual Studio를 사용 하지 않으려는 경우 사용할 수 있습니다 합니다 [ServiceModel Metadata 유틸리티 도구 (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="26a4e-131">자습서: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="26a4e-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="26a4e-132">WCF 서비스에서 WCF 클라이언트 프록시를 만들기에 대 한 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="26a4e-133">서비스 참조를 추가 하려면 Visual Studio를 사용 하 여 메타 데이터를 검색 하거나 ServiceModel Metadata 유틸리티 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="26a4e-134">클라이언트가 서비스에 액세스를 사용 하는 끝점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="26a4e-135">자습서: 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="26a4e-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="26a4e-136">WCF 클라이언트 프록시를 사용 하 여 서비스 작업을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a4e-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="26a4e-137">참조</span><span class="sxs-lookup"><span data-stu-id="26a4e-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="26a4e-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="26a4e-138">See also</span></span>

- [<span data-ttu-id="26a4e-139">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="26a4e-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="26a4e-140">설명서에 대 한 가이드</span><span class="sxs-lookup"><span data-stu-id="26a4e-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="26a4e-141">Windows Communication Foundation은 무엇입니까</span><span class="sxs-lookup"><span data-stu-id="26a4e-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="26a4e-142">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="26a4e-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="26a4e-143">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="26a4e-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="26a4e-144">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="26a4e-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="26a4e-145">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="26a4e-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="26a4e-146">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="26a4e-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="26a4e-147">방법: 이중 계약을와 함께 access services</span><span class="sxs-lookup"><span data-stu-id="26a4e-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="26a4e-148">ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="26a4e-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="26a4e-149">방법: Svcutil.exe를 사용 하 여 메타 데이터 문서 다운로드</span><span class="sxs-lookup"><span data-stu-id="26a4e-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="26a4e-150">방법: 구성 파일을 사용 하 여 서비스의 메타 데이터 게시</span><span class="sxs-lookup"><span data-stu-id="26a4e-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="26a4e-151">바인딩을 사용 하 여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="26a4e-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="26a4e-152">Getting started 샘플</span><span class="sxs-lookup"><span data-stu-id="26a4e-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="26a4e-153">Windows Communication Foundation 샘플</span><span class="sxs-lookup"><span data-stu-id="26a4e-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="26a4e-154">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="26a4e-154">Self-Host</span></span>](samples/self-host.md)
