---
title: 메타데이터 게시 동작
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: dade6d1a53fd99b994fb3c027db4e51392bfdcda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144398"
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="99dbf-102">메타데이터 게시 동작</span><span class="sxs-lookup"><span data-stu-id="99dbf-102">Metadata Publishing Behavior</span></span>
<span data-ttu-id="99dbf-103">Metadata Publishing Behavior 샘플에서는 서비스의 메타데이터 게시 기능을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-103">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="99dbf-104">잠재적으로 중요한 서비스 메타데이터의 의도하지 않은 공개를 방지하기 위해 WCF(Windows 통신 Foundation) 서비스의 기본 구성은 메타데이터 게시를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-104">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="99dbf-105">이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-105">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99dbf-106">쉽게 구별할 수 있도록 이 샘플에서는 보안이 설정되지 않은 메타데이터 게시 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-106">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="99dbf-107">이러한 엔드포인트는 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 엔드포인트를 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-107">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="99dbf-108">메타데이터 끝점을 보호하는 샘플은 [사용자 지정 보안 메타데이터 끝점](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="99dbf-108">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="99dbf-109">샘플은 `ICalculator` 서비스 계약을 구현하는 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-109">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="99dbf-110">이 샘플에서 클라이언트는 콘솔 애플리케이션(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-110">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99dbf-111">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="99dbf-112">서비스에서 메타데이터를 노출하려면 서비스에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>가 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-112">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="99dbf-113">이 동작이 존재하는 경우 <xref:System.ServiceModel.Description.IMetadataExchange> 계약을 WS-MetadataExchange(MEX) 프로토콜의 구현으로 노출하도록 엔드포인트를 구성함으로써 메타데이터를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-113">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="99dbf-114">편의상 이 계약에는 "IMetadataExchange"라는 약식 구성 이름이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-114">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="99dbf-115">이 샘플에서는 보안 모드가 `mexHttpBinding`으로 설정된 `wsHttpBinding`과 동일한 `None`이라는 편리한 표준 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-115">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="99dbf-116">"mex"의 상대 주소는 끝점에서 사용되며, 서비스 기본 주소에 대해 해결되면 의 `http://localhost/servicemodelsamples/service.svc/mex`끝점 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-116">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="99dbf-117">다음에서는 동작 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-117">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="99dbf-118">다음에서는 MEX 엔드포인트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-118">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="99dbf-119">이 샘플에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 속성을 `true`로 설정하며, 따라서 HTTP GET을 사용하여 서비스의 메타데이터를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-119">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="99dbf-120">HTTP GET 메타데이터 엔드포인트를 사용하려면 서비스가 HTTP 기본 주소를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-120">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="99dbf-121">서비스의 기본 주소에 쿼리 문자열 `?wsdl`을 사용하여 메타데이터에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-121">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="99dbf-122">예를 들어 웹 브라우저에서 서비스에 대한 WSDL을 보려면 주소를 `http://localhost/servicemodelsamples/service.svc?wsdl`사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-122">For example, to see the WSDL for the service in a Web browser you would use the address `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span> <span data-ttu-id="99dbf-123">또는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>를 `true`로 설정하여 HTTPS를 통해 메타데이터를 노출하는 데 이 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-123">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="99dbf-124">이 경우 HTTPS 기본 주소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-124">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="99dbf-125">서비스의 MEX 끝점에 액세스하려면 [ServiceModel 메타데이터 유틸리티 도구(Svcutil.exe)를](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-125">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="99dbf-126">그러면 서비스의 메타데이터를 기준으로 클라이언트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-126">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="99dbf-127">HTTP GET을 사용하여 서비스의 메타데이터에 액세스하려면 `http://localhost/servicemodelsamples/service.svc?wsdl`브라우저를 로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-127">To access the service's metadata using HTTP GET, point your browser to `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span>  
  
 <span data-ttu-id="99dbf-128">이 동작을 제거하고 서비스를 열려고 시도하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-128">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="99dbf-129">이 동작이 없으면 `IMetadataExchange` 계약이 구성된 엔드포인트에 구현이 없으므로 그러한 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-129">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="99dbf-130">`HttpGetEnabled`를 `false`로 설정할 경우 서비스의 메타데이터 대신 CalculatorService 도움말 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-130">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="99dbf-131">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="99dbf-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="99dbf-132">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="99dbf-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="99dbf-134">단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="99dbf-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99dbf-135">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="99dbf-136">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="99dbf-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="99dbf-137">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="99dbf-138">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99dbf-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
