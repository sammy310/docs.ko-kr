---
title: WS 신뢰할 수 있는 세션
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: 38eef85446568dd6cac09c4fdc3fb76d958f423c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424497"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="2b41b-102">WS 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="2b41b-102">WS Reliable Session</span></span>
<span data-ttu-id="2b41b-103">이 샘플에서는 신뢰할 수 있는 세션의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="2b41b-104">신뢰할 수 있는 세션은 신뢰할 수 있는 메시징 및 세션 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="2b41b-105">신뢰할 수 있는 메시징 기능은 실패 시 통신을 다시 시도하고 메시지 차례로 도착과 같은 배달 보증을 지정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="2b41b-106">세션은 호출 간에 클라이언트의 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="2b41b-107">이 샘플에서는 클라이언트 상태를 유지 관리하기 위한 세션을 구현하고 차례로 배달 보증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2b41b-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2b41b-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2b41b-109">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="2b41b-110">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2b41b-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-111">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="2b41b-112">이 샘플은 계산기 서비스를 구현 하는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="2b41b-113">신뢰할 수 있는 세션 기능은 클라이언트와 서비스의 애플리케이션 구성 파일에서 사용하도록 설정 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="2b41b-114">이 샘플에서 서비스는 IIS(인터넷 정보 서비스)에서 호스트되고 클라이언트는 콘솔 애플리케이션(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b41b-115">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2b41b-116">이 샘플에서는 `wsHttpBinding`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="2b41b-117">클라이언트와 서비스 둘 다의 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="2b41b-118">바인딩 형식은 다음 샘플 구성에서와 같이 엔드포인트 요소의 `binding` 특성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="2b41b-119">엔드포인트에는 "Binding1"이라는 바인딩 구성을 참조하는 `bindingConfiguration` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="2b41b-120">바인딩 구성은 [\<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) 의 `enabled` 특성을 `true`로 설정 하 여 신뢰할 수 있는 세션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="2b41b-121">ordered 특성을 `true` 또는 `false`로 설정하여 신뢰할 수 있는 순서가 지정된 세션에 대해 배달 보증을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="2b41b-122">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="2b41b-123">다음 샘플 코드와 같이 서비스 구현 클래스에서는 각 클라이언트에 대한 별개의 클래스 인스턴스를 유지 관리하기 위해 <xref:System.ServiceModel.InstanceContextMode.PerSession> 인스턴스 만들기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="2b41b-124">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2b41b-125">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2b41b-126">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2b41b-126">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2b41b-127">다음 명령을 사용 하 여 ASP.NET 4.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-127">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="2b41b-128">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="2b41b-129">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b41b-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="2b41b-130">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2b41b-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
