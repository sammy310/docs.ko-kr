---
title: WCF 서비스를 위한 단순화된 구성
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: f3c4df5ae3fe5426c8b26142807f16b60db001c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183347"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="900aa-102">WCF 서비스를 위한 단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="900aa-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="900aa-103">이 샘플에서는 WCF(Windows 통신 재단)를 사용하여 일반적인 서비스 및 클라이언트를 구현하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="900aa-104">이 샘플은 다른 모든 기본 기술 샘플의 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="900aa-105">서비스와 통신하기 위한 끝점을 노출하는 이 서비스는 .NET Framework 4의 단순화된 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="900aa-106">.NET Framework 4 이전에는 다음 예제 구성 코드와 같이 끝점이 일반적으로 구성 파일(Web.config)에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="900aa-107">.NET Framework 4에서 `<service>` 요소는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="900aa-108">서비스에서 엔드포인트를 정의하지 않을 경우 각 기본 주소의 엔드포인트와 구현된 계약이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="900aa-109">기본 주소가 계약 이름에 추가되어 엔드포인트가 결정되고 바인딩은 주소 스키마에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="900aa-110">다음 코드 예제에서는 단순화된 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="900aa-111">구성된 대로 동일한 컴퓨터의 클라이언트에서 `http://localhost/servicemodelsamples/service.svc` 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="900aa-112">원격 컴퓨터의 클라이언트가 서비스에 액세스하려면 localhost 대신 정규화된 도메인 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="900aa-113">기본적으로 서비스에서는 메타데이터를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="900aa-114">따라서 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="900aa-115">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="900aa-115">To use this sample</span></span>  
  
1. <span data-ttu-id="900aa-116">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="900aa-117">솔루션을 빌드하려면 Windows 통신 [기초 샘플 빌드의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="900aa-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="900aa-118">다음 단계에 따라 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="900aa-119">**서비스** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정을**선택한 다음 **Ctrl+F5를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="900aa-120">서비스가 실행 중이라는 콘솔 출력이 나타날 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="900aa-121">**클라이언트** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정을**선택한 다음 **Ctrl+F5를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="900aa-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="900aa-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="900aa-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="900aa-124">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="900aa-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900aa-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="900aa-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="900aa-126">See also</span></span>

- <span data-ttu-id="900aa-127">[AppFabric 관리 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="900aa-127">[AppFabric Management Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="900aa-128">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="900aa-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
