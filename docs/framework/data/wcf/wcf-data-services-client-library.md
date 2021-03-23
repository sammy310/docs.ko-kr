---
title: WCF Data Services 클라이언트 라이브러리
description: WCF Data Services 클라이언트 라이브러리를 사용 하 여 .NET Framework 클라이언트 응용 프로그램에서 데이터에 액세스 하 고 해당 데이터를 변경 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 3d8a0f869454ce24d847127c2097239886f3395b
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805664"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="e76a6-103">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e76a6-103">WCF Data Services Client Library</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="e76a6-104">모든 응용 프로그램은 HTTP 요청을 보내고 데이터 서비스에서 반환 하는 OData 피드를 처리할 수 있는 경우 OData (Open Data Protocol) 기반 데이터 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-104">Any application can interact with an Open Data Protocol (OData)-based data service if it can send an HTTP request and process the OData feed that a data service returns.</span></span> <span data-ttu-id="e76a6-105">이러한 상호 운용성을 통해 광범위 한 웹 사용 응용 프로그램에서 OData 기반 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-105">This interoperability enables you to access OData-based services from a broad range of Web-enabled applications.</span></span> <span data-ttu-id="e76a6-106">WCF Data Services에는 .NET Framework 또는 Silverlight 기반 응용 프로그램에서 OData 피드를 사용할 때 보다 다양 한 프로그래밍 환경을 제공 하는 클라이언트 라이브러리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-106">WCF Data Services includes client libraries that provide a richer programming experience when you consume OData feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="e76a6-107">클라이언트 라이브러리의 두 가지 주요 클래스는 <xref:System.Data.Services.Client.DataServiceContext> 클래스와 <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-107">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="e76a6-108"><xref:System.Data.Services.Client.DataServiceContext> 클래스는 지정한 데이터 서비스에 대해 지원되는 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-108">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="e76a6-109">OData 서비스는 상태 비저장 이지만 컨텍스트는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-109">Although OData services are stateless, the context is not.</span></span> <span data-ttu-id="e76a6-110">따라서 <xref:System.Data.Services.Client.DataServiceContext> 변경 관리 등의 기능을 지원 하기 위해 클래스를 사용 하 여 데이터 서비스와의 상호 작용 간에 클라이언트의 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-110">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="e76a6-111">또한 이 클래스는 ID를 관리하고 변경 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-111">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="e76a6-112"><xref:System.Data.Services.Client.DataServiceQuery%601> 클래스는 특정 엔터티 집합에 대한 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-112">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="e76a6-113">이 단원에서는 클라이언트 라이브러리를 사용하여 .NET Framework 클라이언트 애플리케이션에서 데이터에 액세스하고 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-113">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="e76a6-114">Silverlight 기반 응용 프로그램에서 WCF Data Services 클라이언트 라이브러리를 사용 하는 방법에 대 한 자세한 내용은 [WCF Data Services (silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e76a6-114">For more information about how to use the WCF Data Services client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).</span></span> <span data-ttu-id="e76a6-115">다른 종류의 응용 프로그램에서 OData 피드를 사용할 수 있는 다른 클라이언트 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-115">Other client libraries are available that enable you to consume an OData feed in other kinds of applications.</span></span> <span data-ttu-id="e76a6-116">OData SDK에 대 한 자세한 내용은 [ODATA sdk-샘플 코드](https://www.odata.org/ecosystem/#sdk)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e76a6-116">For more information on OData SDK, see [OData SDK - Sample Code](https://www.odata.org/ecosystem/#sdk).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e76a6-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e76a6-117">In This Section</span></span>  

 [<span data-ttu-id="e76a6-118">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="e76a6-118">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="e76a6-119">OData 피드를 기반으로 하는 클라이언트 데이터 서비스 클래스 및 클라이언트 라이브러리를 생성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-119">Describes how to generate a client library and client data service classes that are based on OData feeds.</span></span>  
  
 [<span data-ttu-id="e76a6-120">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="e76a6-120">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="e76a6-121">클라이언트 라이브러리를 사용하여 .NET Framework 기반 애플리케이션에서 데이터 서비스를 쿼리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-121">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="e76a6-122">지연 콘텐츠 로드</span><span class="sxs-lookup"><span data-stu-id="e76a6-122">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="e76a6-123">초기 쿼리 응답에 포함되지 않은 추가 콘텐츠를 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-123">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="e76a6-124">데이터 서비스 업데이트</span><span class="sxs-lookup"><span data-stu-id="e76a6-124">Updating the Data Service</span></span>](updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="e76a6-125">클라이언트 라이브러리를 사용하여 엔터티와 관계를 만들고 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-125">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="e76a6-126">비동기 작업</span><span class="sxs-lookup"><span data-stu-id="e76a6-126">Asynchronous Operations</span></span>](asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="e76a6-127">비동기 방식으로 데이터 서비스와 작업할 수 있도록 클라이언트 라이브러리에서 제공하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-127">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="e76a6-128">일괄 처리 작업</span><span class="sxs-lookup"><span data-stu-id="e76a6-128">Batching Operations</span></span>](batching-operations-wcf-data-services.md)  
 <span data-ttu-id="e76a6-129">클라이언트 라이브러리를 사용하여 여러 요청을 데이터 서비스에 단일 일괄 처리로 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-129">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="e76a6-130">컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="e76a6-130">Binding Data to Controls</span></span>](binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="e76a6-131">데이터 서비스에서 반환 하는 OData 피드에 컨트롤을 바인딩하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-131">Describes how to bind controls to a OData feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="e76a6-132">서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="e76a6-132">Calling Service Operations</span></span>](calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="e76a6-133">클라이언트 라이브러리를 사용하여 서비스 작업을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-133">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="e76a6-134">데이터 서비스 컨텍스트 관리</span><span class="sxs-lookup"><span data-stu-id="e76a6-134">Managing the Data Service Context</span></span>](managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="e76a6-135">클라이언트 라이브러리의 동작을 관리하는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-135">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="e76a6-136">이진 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="e76a6-136">Working with Binary Data</span></span>](working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="e76a6-137">데이터 서비스에서 데이터 스트림으로 반환하는 이진 데이터에 액세스하고 해당 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e76a6-137">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76a6-138">참조</span><span class="sxs-lookup"><span data-stu-id="e76a6-138">See also</span></span>

- [<span data-ttu-id="e76a6-139">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="e76a6-139">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="e76a6-140">시작</span><span class="sxs-lookup"><span data-stu-id="e76a6-140">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
