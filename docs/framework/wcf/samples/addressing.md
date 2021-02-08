---
description: '자세히 알아보기: 주소 지정'
title: 주소 지정
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 40c13515f0a53e7e8e4dbf10708cebe0b2886a6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779181"
---
# <a name="addressing"></a><span data-ttu-id="1025f-103">주소 지정</span><span class="sxs-lookup"><span data-stu-id="1025f-103">Addressing</span></span>

<span data-ttu-id="1025f-104">Addressing 샘플에서는 엔드포인트 주소의 다양한 측면과 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-104">The Addressing sample demonstrates various aspects and features of endpoint addresses.</span></span> <span data-ttu-id="1025f-105">이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-105">The sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="1025f-106">이 샘플에서 서비스는 자체 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-106">In this sample the service is self-hosted.</span></span> <span data-ttu-id="1025f-107">서비스와 클라이언트는 모두 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-107">Both the service and the client are console applications.</span></span> <span data-ttu-id="1025f-108">서비스는 상대 및 절대 엔드포인트 주소를 조합하여 여러 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-108">The service defines multiple endpoints using a combination of relative and absolute endpoint addresses.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1025f-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1025f-110">서비스 구성 파일에는 기본 주소와 4개의 엔드포인트가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-110">The service configuration file specifies a base address and four endpoints.</span></span> <span data-ttu-id="1025f-111">기본 주소는 다음 샘플 구성에서처럼 service/host/baseAddresses 아래 add 요소를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-111">The base address is specified using the add element, under service/host/baseAddresses as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 <span data-ttu-id="1025f-112">다음 샘플 구성에서와 같이 첫 번째 엔드포인트 정의는 엔드포인트 주소가 기본 주소와 URI 컴퍼지션 다음에 오는 상대 주소의 조합인 상대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-112">The first endpoint definition shown in the following sample configuration specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of URI composition.</span></span>  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="1025f-113">이 경우 상대 주소가 비어 있으므로("") 엔드포인트 주소는 기본 주소와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-113">In this case, the relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="1025f-114">실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>
  
 <span data-ttu-id="1025f-115">두 번째 엔드포인트 정의도 다음 샘플 구성에서처럼 상대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span>  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="1025f-116">상대 주소 "test"가 기본 주소에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="1025f-117">실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service/test` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-117">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>
  
 <span data-ttu-id="1025f-118">세 번째 엔드포인트 정의는 다음 샘플 구성에서처럼 절대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-118">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="1025f-119">주소에서 기본 주소는 아무런 역할도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-119">The base address plays no role in the address.</span></span> <span data-ttu-id="1025f-120">실제 끝점 주소는 `http://localhost:8001/hello/servicemodelsamples` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-120">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>
  
 <span data-ttu-id="1025f-121">네 번째 엔드포인트 주소는 절대 주소 및 다른 전송(TCP)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-121">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="1025f-122">주소에서 기본 주소는 아무런 역할도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-122">The base address plays no role in the address.</span></span> <span data-ttu-id="1025f-123">실제 끝점 주소는 `net.tcp://localhost:9000/servicemodelsamples/service` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-123">The actual endpoint address is `net.tcp://localhost:9000/servicemodelsamples/service`.</span></span>
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="1025f-124">클라이언트는 4개의 서비스 엔드포인트 하나에만 액세스하지만 이러한 서비스 엔드포인트가 모두 해당 구성 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-124">The client accesses just one of the four service endpoints, but all four are defined in its configuration file.</span></span> <span data-ttu-id="1025f-125">클라이언트는 `CalculatorProxy` 개체를 만들 때 엔드포인트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-125">The client selects an endpoint when it creates the `CalculatorProxy` object.</span></span> <span data-ttu-id="1025f-126">구성 이름을 `CalculatorEndpoint1`부터 `CalculatorEndpoint4`까지 변경하여 각 엔드포인트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-126">By changing the configuration name from `CalculatorEndpoint1` through `CalculatorEndpoint4`, you can exercise each of the endpoints.</span></span>  
  
 <span data-ttu-id="1025f-127">샘플을 실행하면 서비스는 각 엔드포인트에 대한 주소, 바인딩 이름 및 계약 이름을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-127">When you run the sample, the service enumerates the address, binding name and contract name for each of its endpoints.</span></span> <span data-ttu-id="1025f-128">ServiceHost의 관점에서 보면 MEX(메타데이터 교환) 엔드포인트는 또 다른 엔드포인트이므로 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-128">The metadata exchange (MEX) endpoint is just another endpoint from the ServiceHost's perspective so it shows up in the list.</span></span>  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="1025f-129">클라이언트를 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-129">When you run the client, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="1025f-130">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-130">Press ENTER in each console window to shut down the service and client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1025f-131">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1025f-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1025f-132">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1025f-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1025f-134">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1025f-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1025f-135">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 엔드포인트 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-135">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1025f-136">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1025f-137">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1025f-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1025f-138">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1025f-139">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1025f-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
