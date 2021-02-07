---
description: '자세히 알아보기: 본문으로 라우팅'
title: 본문에 의한 경로
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: 1c9505484c4af34c5e1f2f98524c01fb378c005f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703785"
---
# <a name="route-by-body"></a><span data-ttu-id="0a8d0-103">본문에 의한 경로</span><span class="sxs-lookup"><span data-stu-id="0a8d0-103">Route by Body</span></span>

<span data-ttu-id="0a8d0-104">이 샘플에서는 SOAP 작업이 있는 메시지 개체를 수락하는 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-104">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="0a8d0-105">이 샘플은 계산기 서비스를 구현 하는 [시작](getting-started-sample.md) 을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="0a8d0-106">서비스는 `Calculate` 요청 매개 변수를 받아 <xref:System.ServiceModel.Channels.Message> 응답을 반환하는 단일 <xref:System.ServiceModel.Channels.Message> 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-106">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="0a8d0-107">이 샘플에서 클라이언트는 콘솔 애플리케이션(.exe)이고 서비스는 IIS에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-107">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a8d0-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0a8d0-109">이 샘플에서는 본문 콘텐츠에 기반한 메시지 디스패치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-109">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="0a8d0-110">WCF (기본 제공 Windows Communication Foundation) 서비스 모델 메시지 디스패치 메커니즘은 메시지 동작을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-110">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="0a8d0-111">반면 모든 작업을 Action=""으로 정의하는 기존 웹 서비스도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-111">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="0a8d0-112">동작 정보를 기준으로 계속 요청 메시지를 디스패치하는 WSDL을 기반으로 하여 서비스를 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-112">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="0a8d0-113">이 샘플에서는 WSDL을 기반으로 하는 서비스 계약을 보여 줍니다. WSDL은 샘플에 포함된 Service.wsdl에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-113">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="0a8d0-114">서비스 계약은 [시작](getting-started-sample.md)에 사용 되는 것과 유사한 계산기입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-114">The service contract is Calculator, similar to the one used in [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="0a8d0-115">하지만 `[OperationContract]`는 모든 작업에 대해 `Action=""`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-115">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```csharp  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="0a8d0-116">계약이 지정되면 서비스에서는 작업 사이에서 메시지를 디스패치할 수 있도록 사용자 지정 디스패치 동작 `DispatchByBodyBehavior`를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-116">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="0a8d0-117">이 디스패치 동작은 `DispatchByBodyElementOperationSelector` 각 래퍼 요소의 QName으로 키가 지정 된 작업 이름의 테이블을 사용 하 여 사용자 지정 작업 선택기를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-117">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="0a8d0-118">`DispatchByBodyElementOperationSelector`는 본문의 첫 번째 자식에 대한 시작 태그를 살펴보고 이전에 설명한 테이블을 사용하여 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-118">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="0a8d0-119">클라이언트는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용 하 여 서비스에서 내보낸 WSDL에서 자동 생성 된 프록시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-119">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="0a8d0-120">모든 작업의 동작이 비어 있어도 자동 생성된 프록시의 동작 매개 변수를 제외하고는 클라이언트 코드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-120">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="0a8d0-121">클라이언트 코드는 몇 가지 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-121">The client code performs several calculations.</span></span> <span data-ttu-id="0a8d0-122">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0a8d0-123">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0a8d0-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="0a8d0-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0a8d0-125">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0a8d0-126">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0a8d0-127">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0a8d0-128">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0a8d0-129">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-129">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0a8d0-130">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0a8d0-131">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a8d0-131">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
