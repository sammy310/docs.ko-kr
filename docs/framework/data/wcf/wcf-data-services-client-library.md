---
title: WCF Data Services 클라이언트 라이브러리
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 545442b0086361c8ce8c0482801afc10b1fee96e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779675"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="ed8cc-102">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ed8cc-102">WCF Data Services Client Library</span></span>
<span data-ttu-id="ed8cc-103">HTTP 요청을 보내고 데이터 서비스에서 반환하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드를 처리할 수 있는 애플리케이션은 모두 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 데이터 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-103">Any application can interact with an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]-based data service if it can send an HTTP request and process the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that a data service returns.</span></span> <span data-ttu-id="ed8cc-104">이 상호 운용성을 통해 광범위한 웹 사용 애플리케이션에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 기반 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-104">This interoperability enables you to access [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based services from a broad range of Web-enabled applications.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="ed8cc-105">에는 .NET Framework 또는 Silverlight 기반 응용 프로그램에서 피드를 사용할 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 때 보다 다양 한 프로그래밍 환경을 제공 하는 클라이언트 라이브러리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-105">includes client libraries that provide a richer programming experience when you consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="ed8cc-106">클라이언트 라이브러리의 두 가지 주요 클래스는 <xref:System.Data.Services.Client.DataServiceContext> 클래스와 <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-106">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="ed8cc-107"><xref:System.Data.Services.Client.DataServiceContext> 클래스는 지정한 데이터 서비스에 대해 지원되는 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-107">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="ed8cc-108">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 서비스는 상태 비저장 특성을 갖지만 컨텍스트는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-108">Although [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] services are stateless, the context is not.</span></span> <span data-ttu-id="ed8cc-109">따라서 변경 관리 등의 기능 <xref:System.Data.Services.Client.DataServiceContext> 을 지원 하기 위해 클래스를 사용 하 여 데이터 서비스와의 상호 작용 간에 클라이언트의 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-109">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="ed8cc-110">또한 이 클래스는 ID를 관리하고 변경 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-110">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="ed8cc-111"><xref:System.Data.Services.Client.DataServiceQuery%601> 클래스는 특정 엔터티 집합에 대한 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-111">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="ed8cc-112">이 단원에서는 클라이언트 라이브러리를 사용하여 .NET Framework 클라이언트 애플리케이션에서 데이터에 액세스하고 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-112">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="ed8cc-113">Silverlight 기반 응용 프로그램에서 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리를 사용 하는 방법에 대 한 자세한 내용은 [WCF Data Services (silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-113">For more information about how to use the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016).</span></span> <span data-ttu-id="ed8cc-114">다른 종류의 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용할 수 있는 다른 클라이언트 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-114">Other client libraries are available that enable you to consume an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in other kinds of applications.</span></span> <span data-ttu-id="ed8cc-115">자세한 내용은 [ODATA SDK](https://go.microsoft.com/fwlink/?LinkID=185796)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-115">For more information, see the [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed8cc-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ed8cc-116">In This Section</span></span>  
 [<span data-ttu-id="ed8cc-117">데이터 서비스 클라이언트 라이브러리 생성</span><span class="sxs-lookup"><span data-stu-id="ed8cc-117">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-118">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 기반으로 하는 클라이언트 데이터 서비스 클래스 및 클라이언트 라이브러리를 생성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-118">Describes how to generate a client library and client data service classes that are based on [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="ed8cc-119">데이터 서비스 쿼리</span><span class="sxs-lookup"><span data-stu-id="ed8cc-119">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-120">클라이언트 라이브러리를 사용하여 .NET Framework 기반 애플리케이션에서 데이터 서비스를 쿼리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-120">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="ed8cc-121">지연 콘텐츠 로드</span><span class="sxs-lookup"><span data-stu-id="ed8cc-121">Loading Deferred Content</span></span>](loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-122">초기 쿼리 응답에 포함되지 않은 추가 콘텐츠를 로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-122">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="ed8cc-123">데이터 서비스 업데이트</span><span class="sxs-lookup"><span data-stu-id="ed8cc-123">Updating the Data Service</span></span>](updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-124">클라이언트 라이브러리를 사용하여 엔터티와 관계를 만들고 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-124">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="ed8cc-125">비동기 작업</span><span class="sxs-lookup"><span data-stu-id="ed8cc-125">Asynchronous Operations</span></span>](asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-126">비동기 방식으로 데이터 서비스와 작업할 수 있도록 클라이언트 라이브러리에서 제공하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-126">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="ed8cc-127">일괄 처리 작업</span><span class="sxs-lookup"><span data-stu-id="ed8cc-127">Batching Operations</span></span>](batching-operations-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-128">클라이언트 라이브러리를 사용하여 여러 요청을 데이터 서비스에 단일 일괄 처리로 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-128">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="ed8cc-129">컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="ed8cc-129">Binding Data to Controls</span></span>](binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-130">데이터 서비스에서 반환 된 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 컨트롤을 바인딩하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-130">Describes how to bind controls to a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="ed8cc-131">서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="ed8cc-131">Calling Service Operations</span></span>](calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-132">클라이언트 라이브러리를 사용하여 서비스 작업을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-132">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="ed8cc-133">데이터 서비스 컨텍스트 관리</span><span class="sxs-lookup"><span data-stu-id="ed8cc-133">Managing the Data Service Context</span></span>](managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-134">클라이언트 라이브러리의 동작을 관리하는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-134">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="ed8cc-135">이진 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="ed8cc-135">Working with Binary Data</span></span>](working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="ed8cc-136">데이터 서비스에서 데이터 스트림으로 반환하는 이진 데이터에 액세스하고 해당 데이터를 변경하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8cc-136">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8cc-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed8cc-137">See also</span></span>

- [<span data-ttu-id="ed8cc-138">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="ed8cc-138">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="ed8cc-139">시작</span><span class="sxs-lookup"><span data-stu-id="ed8cc-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
