---
title: 데이터 서비스 호스팅(WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 5dfa1d9f02f660b55ecf6598ef5012174a1ba853
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172595"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="9f5ea-102">데이터 서비스 호스팅(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f5ea-102">Hosting the Data Service (WCF Data Services)</span></span>

<span data-ttu-id="9f5ea-103">WCF Data Services를 사용 하 여 데이터를 OData (Open Data Protocol) 피드로 노출 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-103">By using WCF Data Services, you can create a service that exposes data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="9f5ea-104">이 데이터 서비스는 <xref:System.Data.Services.DataService%601>에서 상속되는 클래스로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="9f5ea-105">이 클래스는 OData에서 요구 하는 요청 메시지를 처리 하 고, 데이터 원본에 대 한 업데이트를 수행 하 고, 응답 메시지를 생성 하는 데 필요한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="9f5ea-106">그러나 데이터 서비스는 네트워크 소켓에 바인딩되어 들어오는 HTTP 요청을 수신 대기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="9f5ea-107">이 필요한 기능을 위해 데이터 서비스는 호스팅 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="9f5ea-108">데이터 서비스 호스트는 데이터 서비스를 대신하여 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-108">The data service host performs the following tasks on behalf of the data service:</span></span>

- <span data-ttu-id="9f5ea-109">요청을 수신 대기하고 이러한 요청을 데이터 서비스로 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-109">Listens for requests and routes these requests to the data service.</span></span>

- <span data-ttu-id="9f5ea-110">각 요청에 대한 데이터 서비스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-110">Creates an instance of the data service for each request.</span></span>

- <span data-ttu-id="9f5ea-111">데이터 서비스가 들어오는 요청을 처리하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-111">Requests that the data service process the incoming request.</span></span>

- <span data-ttu-id="9f5ea-112">데이터 서비스를 대신하여 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="9f5ea-113">데이터 서비스 호스팅을 간소화 하기 위해 WCF Data Services은 WCF (Windows Communication Foundation)와 통합 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="9f5ea-114">데이터 서비스는 ASP.NET 응용 프로그램에서 데이터 서비스 호스트 역할을 하는 기본 WCF 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-114">The data service provides a default WCF implementation that serves as the data service host in an ASP.NET application.</span></span> <span data-ttu-id="9f5ea-115">따라서 다음 방법 중 하나로 데이터 서비스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-115">Therefore, you can host a data service in one of the following ways:</span></span>

- <span data-ttu-id="9f5ea-116">ASP.NET 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-116">In an ASP.NET application.</span></span>

- <span data-ttu-id="9f5ea-117">자체 호스팅 WCF 서비스를 지원하는 관리되는 애플리케이션에서</span><span class="sxs-lookup"><span data-stu-id="9f5ea-117">In a managed application that supports self-hosted WCF services.</span></span>

- <span data-ttu-id="9f5ea-118">다른 사용자 지정 데이터 서비스 호스트에서</span><span class="sxs-lookup"><span data-stu-id="9f5ea-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="9f5ea-119">ASP.NET 애플리케이션에서 데이터 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="9f5ea-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="9f5ea-120">Visual Studio 2015의 **새 항목 추가** 대화 상자를 사용 하 여 ASP.NET 응용 프로그램에서 데이터 서비스를 정의 하는 경우이 도구는 프로젝트에 두 개의 새 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="9f5ea-121">첫 번째 파일은 확장명이 `.svc`이고 데이터 서비스를 인스턴스화하는 방법을 WCF 런타임에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="9f5ea-122">다음은 [빠른](quickstart-wcf-data-services.md)시작을 완료할 때 생성 되는 Northwind 샘플 데이터 서비스에 대 한이 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](quickstart-wcf-data-services.md):</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="9f5ea-123">이 지시문은 <xref:System.Data.Services.DataServiceHostFactory> 클래스를 사용하여 명명된 데이터 서비스 클래스에 대한 서비스 호스트를 만들도록 애플리케이션에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="9f5ea-124">`.svc` 파일의 코드 숨김 페이지에는 Northwind 샘플 데이터 서비스에 대해 다음과 같이 정의된 데이터 서비스 자체의 구현인 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="9f5ea-125">데이터 서비스는 WCF 서비스 처럼 동작 하기 때문에 데이터 서비스는 ASP.NET와 통합 되 고 WCF 웹 프로그래밍 모델을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-125">Because a data service behaves like a WCF service, the data service integrates with ASP.NET and follows the WCF Web programming model.</span></span> <span data-ttu-id="9f5ea-126">자세한 내용은 [Wcf 서비스 및 ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) 및 [Wcf 웹 HTTP 프로그래밍 모델](../../wcf/feature-details/wcf-web-http-programming-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-126">For more information, see [WCF Services and ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="9f5ea-127">자체 호스팅 WCF 서비스</span><span class="sxs-lookup"><span data-stu-id="9f5ea-127">Self-Hosted WCF Services</span></span>

 <span data-ttu-id="9f5ea-128">WCF 구현을 통합 하기 때문에 데이터 서비스를 WCF 서비스로 자체 호스트 하는 WCF Data Services 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="9f5ea-129">서비스는 콘솔 응용 프로그램과 같은 모든 .NET Framework 응용 프로그램에서 자체 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-129">A service can be self-hosted in any .NET Framework application, such as a console application.</span></span> <span data-ttu-id="9f5ea-130"><xref:System.Data.Services.DataServiceHost>에서 상속되는 <xref:System.ServiceModel.Web.WebServiceHost> 클래스는 특정 주소에서 데이터 서비스를 인스턴스화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="9f5ea-131">셀프 호스팅을 개발과 테스트에 사용하면 서비스의 배포와 문제 해결이 보다 쉬워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="9f5ea-132">그러나 이러한 종류의 호스팅에서는 ASP.NET 또는 인터넷 정보 서비스 (IIS)에서 제공 하는 고급 호스팅 및 관리 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-132">However, this kind of hosting does not provide the advanced hosting and management features provided by ASP.NET or by Internet Information Services (IIS).</span></span> <span data-ttu-id="9f5ea-133">자세한 내용은 [관리 되는 응용 프로그램에서 호스팅](../../wcf/feature-details/hosting-in-a-managed-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-133">For more information, see [Hosting in a Managed Application](../../wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="9f5ea-134">사용자 지정 데이터 서비스 호스트 정의</span><span class="sxs-lookup"><span data-stu-id="9f5ea-134">Defining a Custom Data Service Host</span></span>

 <span data-ttu-id="9f5ea-135">WCF 호스트 구현이 너무 제한적인 경우 데이터 서비스에 대한 사용자 지정 호스트도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="9f5ea-136"><xref:System.Data.Services.IDataServiceHost> 인터페이스를 구현하는 모든 클래스를 데이터 서비스에 대한 네트워크 호스트로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="9f5ea-137">사용자 지정 호스트는 <xref:System.Data.Services.IDataServiceHost> 인터페이스를 구현해야 하며 다음과 같은 데이터 서비스 호스트의 기본 임무를 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

- <span data-ttu-id="9f5ea-138">데이터 서비스에 서비스 루트 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-138">Provide the data service with the service root path.</span></span>

- <span data-ttu-id="9f5ea-139">적절한 <xref:System.Data.Services.IDataServiceHost> 멤버 구현에 대한 요청 및 응답 헤더 정보를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

- <span data-ttu-id="9f5ea-140">데이터 서비스에서 발생한 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-140">Handle exceptions raised by the data service.</span></span>

- <span data-ttu-id="9f5ea-141">쿼리 문자열의 매개 변수 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ea-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f5ea-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f5ea-142">See also</span></span>

- [<span data-ttu-id="9f5ea-143">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="9f5ea-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="9f5ea-144">서비스로 데이터 공개</span><span class="sxs-lookup"><span data-stu-id="9f5ea-144">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="9f5ea-145">데이터 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="9f5ea-145">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
