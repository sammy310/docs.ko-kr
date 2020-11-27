---
title: WCF 서비스를 위한 단순화된 구성
description: WCF를 사용 하 여 일반적인 서비스 및 클라이언트를 구현 하 고 구성 하는 방법에 대해 알아봅니다. 서비스는 구성 파일에 지정 된 끝점을 사용 하 여 통신 합니다.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 087618d603ea1c7df75ab5383f6c95b781dca847
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290025"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="0eda4-104">WCF 서비스를 위한 단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="0eda4-104">Simplified Configuration for WCF Services</span></span>

<span data-ttu-id="0eda4-105">이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 일반적인 서비스 및 클라이언트를 구현 하 고 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-105">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="0eda4-106">이 샘플은 다른 모든 기본 기술 샘플의 기준이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-106">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="0eda4-107">서비스와 통신 하기 위한 끝점을 노출 하는이 서비스는 .NET Framework 4에서 간소화 된 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-107">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="0eda4-108">.NET Framework 4 이전에는 다음 예제 구성 코드에 표시 된 것 처럼 끝점이 일반적으로 구성 파일 (Web.config)에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-108">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
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
  
 <span data-ttu-id="0eda4-109">.NET Framework 4에서 요소는 `<service>` 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-109">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="0eda4-110">서비스에서 엔드포인트를 정의하지 않을 경우 각 기본 주소의 엔드포인트와 구현된 계약이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-110">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="0eda4-111">기본 주소가 계약 이름에 추가되어 엔드포인트가 결정되고 바인딩은 주소 스키마에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-111">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="0eda4-112">다음 코드 예제에서는 단순화된 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-112">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="0eda4-113">구성 된 대로 `http://localhost/servicemodelsamples/service.svc` 동일한 컴퓨터의 클라이언트에서 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-113">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="0eda4-114">원격 컴퓨터의 클라이언트가 서비스에 액세스하려면 localhost 대신 정규화된 도메인 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-114">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="0eda4-115">기본적으로 서비스에서는 메타데이터를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-115">The service does not expose metadata by default.</span></span> <span data-ttu-id="0eda4-116">따라서 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-116">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
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
  
### <a name="to-use-this-sample"></a><span data-ttu-id="0eda4-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0eda4-117">To use this sample</span></span>  
  
1. <span data-ttu-id="0eda4-118">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0eda4-119">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0eda4-119">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0eda4-120">다음 단계에 따라 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-120">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="0eda4-121">**서비스** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택한 다음 **ctrl + F5** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-121">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="0eda4-122">서비스가 실행 중이라는 콘솔 출력이 나타날 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-122">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="0eda4-123">**클라이언트** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 선택한 다음 **ctrl + F5** 를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-123">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0eda4-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-124">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0eda4-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0eda4-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0eda4-126">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0eda4-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eda4-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="0eda4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0eda4-128">See also</span></span>

- <span data-ttu-id="0eda4-129">[AppFabric 관리 샘플](/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0eda4-129">[AppFabric Management Samples](/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="0eda4-130">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="0eda4-130">Simplified Configuration</span></span>](../simplified-configuration.md)
