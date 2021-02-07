---
description: '자세한 정보: SOAP 및 HTTP 끝점'
title: SOAP 및 HTTP 엔드포인트
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: e07f2d33656b6f697d25a684e49e60d748badc2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703538"
---
# <a name="soap-and-http-endpoints"></a><span data-ttu-id="56913-103">SOAP 및 HTTP 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="56913-103">SOAP and HTTP Endpoints</span></span>

<span data-ttu-id="56913-104">이 샘플에서는 WCF 웹 프로그래밍 모델을 사용 하 여 RPC 기반 서비스를 구현 하 고 SOAP 형식 및 "일반 이전 XML" (POX) 형식으로이를 노출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56913-104">This sample demonstrates how to implement an RPC-based service and expose it in the SOAP format and the "Plain Old XML" (POX) format using the WCF Web Programming model.</span></span> <span data-ttu-id="56913-105">서비스의 HTTP 바인딩에 대 한 자세한 내용은 [기본 Http 서비스](basic-http-service.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56913-105">See the [Basic HTTP Service](basic-http-service.md) sample for more details about the HTTP binding for the service.</span></span> <span data-ttu-id="56913-106">이 샘플에서는 서로 다른 바인딩을 사용하는 SOAP 및 HTTP를 통해 동일한 서비스를 노출하는 데 관련된 세부 정보를 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="56913-106">This sample focuses on the details that pertain to exposing the same service over SOAP and HTTP using different bindings.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="56913-107">데모</span><span class="sxs-lookup"><span data-stu-id="56913-107">Demonstrates</span></span>  

 <span data-ttu-id="56913-108">WCF를 사용 하 여 SOAP 및 HTTP를 통해 RPC 서비스 노출.</span><span class="sxs-lookup"><span data-stu-id="56913-108">Exposing an RPC service over SOAP and HTTP using WCF.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="56913-109">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="56913-109">Discussion</span></span>  

 <span data-ttu-id="56913-110">이 샘플은 WCF 서비스를 포함 하는 웹 응용 프로그램 프로젝트 (서비스)와 SOAP 및 HTTP 바인딩을 사용 하 여 서비스 작업을 호출 하는 콘솔 응용 프로그램 (클라이언트)의 두 구성 요소로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-110">This sample consists of two components: a Web Application project (Service) that contains a WCF service and a console application (Client) that invokes service operations using SOAP and HTTP bindings.</span></span>  
  
 <span data-ttu-id="56913-111">WCF 서비스는 `GetData` `PutData` 입력으로 전달 된 문자열을 에코 하는 2 개의 작업을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-111">The WCF service exposes 2 operations –`GetData` and `PutData` – that echo the string that was passed as input.</span></span> <span data-ttu-id="56913-112">서비스 작업에는 <xref:System.ServiceModel.Web.WebGetAttribute> 및<xref:System.ServiceModel.Web.WebInvokeAttribute>를 주석으로 답니다.</span><span class="sxs-lookup"><span data-stu-id="56913-112">The service operations are annotated with <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="56913-113">이러한 특성은 해당 작업의 HTTP 프로젝션을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-113">These attributes control the HTTP projection of these operations.</span></span> <span data-ttu-id="56913-114">또한 서비스 작업에는 SOAP 바인딩을 통해 노출되도록 설정하는 <xref:System.ServiceModel.OperationContractAttribute>를 주석으로 답니다.</span><span class="sxs-lookup"><span data-stu-id="56913-114">In addition, they are annotated with <xref:System.ServiceModel.OperationContractAttribute>, which enables them to be exposed over SOAP bindings.</span></span> <span data-ttu-id="56913-115">서비스의 `PutData` 메서드는 <xref:System.ServiceModel.Web.WebFaultException>을 throw하며, 이 예외는 HTTP 상태 코드를 사용하여 HTTP를 통해 다시 보내지고 SOAP을 통해 SOAP 오류로 다시 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="56913-115">The service’s `PutData` method throws a <xref:System.ServiceModel.Web.WebFaultException>, which gets sent back over HTTP using the HTTP status code and gets sent back over SOAP as a SOAP fault.</span></span>  
  
 <span data-ttu-id="56913-116">Web.config 파일은 3 개의 끝점을 사용 하 여 WCF 서비스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-116">The Web.config file configures the WCF service with 3 endpoints:</span></span>  
  
- <span data-ttu-id="56913-117">SOAP 기반 클라이언트에서 액세스할 수 있도록 서비스 메타데이터를 노출하는 ~/service.svc/mex 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="56913-117">The ~/service.svc/mex endpoint that exposes the service metadata for access by SOAP-based clients.</span></span>  
  
- <span data-ttu-id="56913-118">클라이언트가 HTTP 바인딩을 사용하여 서비스에 액세스할 수 있도록 하는 ~/service.svc/http 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="56913-118">The ~/service.svc/http endpoint that enables clients to access the service using the HTTP binding.</span></span>  
  
- <span data-ttu-id="56913-119">클라이언트가 SOAP 및 HTTP 바인딩을 사용하여 서비스에 액세스할 수 있도록 하는 ~/service.svc/soap 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="56913-119">The ~/service.svc/soap endpoint that allows the clients to access the service using the SOAP over HTTP binding.</span></span>  
  
 <span data-ttu-id="56913-120">HTTP 끝점은가로 설정 된 <`webHttp`> 표준 끝점으로 구성 됩니다 `helpEnabled` `true` .</span><span class="sxs-lookup"><span data-stu-id="56913-120">The HTTP endpoint is configured with a <`webHttp`> standard endpoint which has `helpEnabled` set to `true`.</span></span> <span data-ttu-id="56913-121">따라서 서비스에서는 HTTP 기반 클라이언트가 서비스에 액세스하는 데 사용할 수 있는 XHTML 기반 도움말 페이지를 ~/service.svc/http/help에 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-121">As a result, the service exposes an XHTML based help page at ~/service.svc/http/help that HTTP-based clients can use to access the service.</span></span>  
  
 <span data-ttu-id="56913-122">클라이언트 프로젝트는 **서비스 참조 추가** 를 통해 생성 된 SOAP 프록시를 사용 하 여 서비스에 액세스 하 고를 사용 하 여 서비스에 액세스 하는 방법을 보여 줍니다 <xref:System.Net.WebClient> .</span><span class="sxs-lookup"><span data-stu-id="56913-122">The client project demonstrates accessing the service using a SOAP proxy (generated through **Add Service Reference**) and accessing the service using <xref:System.Net.WebClient>.</span></span>  
  
 <span data-ttu-id="56913-123">이 샘플은 웹 호스팅 서비스와 콘솔 애플리케이션으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-123">The sample consists of a Web-hosted service and a console application.</span></span> <span data-ttu-id="56913-124">콘솔 애플리케이션이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="56913-124">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="56913-125">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="56913-125">To run the sample</span></span>  
  
1. <span data-ttu-id="56913-126">SOAP and HTTP Endpoints 샘플의 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56913-126">Open the solution for the SOAP and HTTP Endpoints Sample.</span></span>  
  
2. <span data-ttu-id="56913-127">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-127">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3. <span data-ttu-id="56913-128">아직 열려 있지 않은 경우 CTRL + W, S를 눌러 **솔루션 탐색기** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56913-128">If it is not already open, press CTRL+W, S to open the **Solution Explorer** window.</span></span>  
  
4. <span data-ttu-id="56913-129">**솔루션 탐색기** 창에서 **서비스** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **새 인스턴스 시작** 상황에 맞는 메뉴가 표시 되도록 **디버그** 상황에 맞는 메뉴 옵션 위에 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-129">From the **Solution Explorer** window, right-click the **Service** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="56913-130">**새 인스턴스 시작** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-130">Click **Start New Instance**.</span></span> <span data-ttu-id="56913-131">그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-131">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5. <span data-ttu-id="56913-132">솔루션 탐색기 창에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **새 인스턴스 시작** 상황에 맞는 메뉴가 나타나도록 **디버그** 상황에 맞는 메뉴 옵션 위에 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-132">From the Solution Explorer windows, right-click the Client project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="56913-133">**새 인스턴스 시작** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-133">Click **Start New Instance**.</span></span>  
  
6. <span data-ttu-id="56913-134">클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="56913-134">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="56913-135">언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-135">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7. <span data-ttu-id="56913-136">샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="56913-136">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8. <span data-ttu-id="56913-137">아무 키나 눌러 클라이언트 콘솔 애플리케이션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-137">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="56913-138">Shift+F5를 눌러 서비스 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-138">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="56913-139">Windows 알림 영역에서 ASP.NET development 서버 아이콘을 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴에서 **중지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-139">In the Windows Notification Area, right-click the ASP.NET development server icon and select **Stop** from the context menu.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="56913-140">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-140">The samples may already be installed on your machine.</span></span> <span data-ttu-id="56913-141">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="56913-141">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="56913-142">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="56913-143">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-143">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
