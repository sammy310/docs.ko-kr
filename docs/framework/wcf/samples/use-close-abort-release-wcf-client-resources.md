---
title: 닫기 및 중단을 사용하여 WCF 클라이언트 리소스 해제
description: 네트워크에 오류가 발생 하면 Dispose가 실패 하 고 예외를 throw 할 수 있습니다. 이로 인해 원치 않는 동작이 발생할 수 있습니다. 네트워크에 오류가 발생 한 경우 Close 및 Abort를 사용 하 여 클라이언트 리소스를 해제 합니다.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 38861252a470f71a6fa88554e289344e2918d710
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715327"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a><span data-ttu-id="4d5e9-105">네트워크 연결이 끊어진 경우 릴리스 리소스를 안전 하 게 닫고 중단</span><span class="sxs-lookup"><span data-stu-id="4d5e9-105">Close and Abort release resources safely when network connections have dropped</span></span>

<span data-ttu-id="4d5e9-106">이 샘플에서는 `Close` 및 `Abort` 메서드를 사용 하 여 형식화 된 클라이언트를 사용 하는 경우 리소스를 정리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-106">This sample demonstrates using the `Close` and `Abort` methods to clean up resources when using a typed client.</span></span> <span data-ttu-id="4d5e9-107">네트워크 연결이 강력 하지 않을 경우 `using` 문은 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-107">The `using` statement causes exceptions when the network connection is not robust.</span></span> <span data-ttu-id="4d5e9-108">이 샘플은 계산기 서비스를 구현 하는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="4d5e9-109">이 샘플에서 클라이언트는 콘솔 애플리케이션(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="4d5e9-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="4d5e9-111">이 샘플에서는 형식화된 클라이언트와 함께 C# "using" 문을 사용할 경우 발생하는 일반적인 두 가지 문제와 예외 발생 후 올바르게 정리되는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-111">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>

<span data-ttu-id="4d5e9-112">C# "using" 문을 사용하면 결과적으로 `Dispose`()가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-112">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="4d5e9-113">이는 네트워크 오류 발생 시에 예외를 throw할 수 있는 `Close`()와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-113">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="4d5e9-114">"using" 블록의 닫는 중괄호에서 `Dispose`() 호출이 암시적으로 발생하므로 이 예외 원인은 코드를 작성하는 사용자와 읽는 사용자 모두가 알아차리지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-114">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="4d5e9-115">이로 인해 애플리케이션 오류가 발생할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-115">This represents a potential source of application errors.</span></span>

<span data-ttu-id="4d5e9-116">`DemonstrateProblemUsingCanThrow` 메서드에서 나타나는 첫 번째 문제는 닫는 중괄호로 인해 예외가 throw되고 닫는 중괄호 뒤의 코드가 실행되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-116">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

<span data-ttu-id="4d5e9-117">using 블록 안의 어떠한 항목도 예외를 throw하지 않거나 using 블록 안의 모든 예외가 catch될 경우에도 닫는 중괄호에서 암시적 `Console.WriteLine`() 호출이 예외를 throw할 수 있으므로 `Dispose`이 발생하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-117">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.WriteLine` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>

<span data-ttu-id="4d5e9-118">`DemonstrateProblemUsingCanThrowAndMask` 메서드에서 나타나는 두 번째 문제는 예외를 throw하는 닫는 중괄호와 관련된 또 다른 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-118">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

<span data-ttu-id="4d5e9-119">`Dispose`()가 "finally" 블록 안에서 발생하므로 `ApplicationException`()가 실패할 경우 `Dispose`은 using 블록 외부에서 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-119">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="4d5e9-120">외부 코드가 `ApplicationException`이 발생하는 시점을 알아야 할 경우 "using" 구문은 이 예외를 마스킹하여 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-120">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>

<span data-ttu-id="4d5e9-121">마지막으로 이 샘플에서는 `DemonstrateCleanupWithExceptions`에 예외가 발생할 경우 올바르게 정리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-121">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="4d5e9-122">이를 위해 오류를 보고하고 `Abort`를 호출하는 try/catch 블록이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-122">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="4d5e9-123">클라이언트 호출에서 예외를 catch 하는 방법에 대 한 자세한 내용은 [예상 된 예외](../../../../docs/framework/wcf/samples/expected-exceptions.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-123">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> <span data-ttu-id="4d5e9-124">using 문 및 ServiceHost: 자체 호스팅되는 대부분의 애플리케이션은 서비스를 호스팅하는 것 외에 다른 작업을 거의 수행하지 않고 ServiceHost.Close에서 거의 예외를 throw하지 않으므로 이러한 애플리케이션은 ServiceHost와 함께 using 문을 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-124">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="4d5e9-125">그러나 ServiceHost.Close에서 `CommunicationException`을 throw할 수 있으므로 ServiceHost를 닫은 후 애플리케이션이 계속될 경우 using 문을 사용하지 않아야 하고 위에 제공된 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-125">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>

<span data-ttu-id="4d5e9-126">샘플을 실행하면 작업 응답 및 예외가 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-126">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>

<span data-ttu-id="4d5e9-127">클라이언트 프로세스는 각각 `Divide` 호출을 시도하는 세 개의 시나리오를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-127">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="4d5e9-128">첫 번째 시나리오는 `Dispose`()의 예외로 인해 코드를 건너뛰는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-128">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="4d5e9-129">두 번째 시나리오는 `Dispose`()의 예외로 인해 중요한 예외가 마스킹되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-129">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="4d5e9-130">세 번째 시나리오는 올바른 정리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-130">The third scenario demonstrates correct clean up.</span></span>

<span data-ttu-id="4d5e9-131">클라이언트 프로세스로부터의 예상 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-131">The expected output from the client process is:</span></span>

```console
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4d5e9-132">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4d5e9-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="4d5e9-133">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="4d5e9-134">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="4d5e9-135">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d5e9-136">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4d5e9-137">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="4d5e9-138">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4d5e9-139">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5e9-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`
