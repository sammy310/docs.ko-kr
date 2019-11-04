---
title: WSHttpBinding
ms.date: 03/30/2017
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
ms.openlocfilehash: 5a2d190fe7dfd5305b47da0e6e67de822cfd695b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424454"
---
# <a name="wshttpbinding"></a><span data-ttu-id="c2052-102">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c2052-102">WSHttpBinding</span></span>
<span data-ttu-id="c2052-103">이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 일반 서비스와 일반 클라이언트를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-103">This sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c2052-104">이 샘플은 인터넷 정보 서비스(IIS)에 의해 호스팅되는 클라이언트 콘솔 프로그램(client.exe)과 서비스 라이브러리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-104">This sample consists of a client console program (client.exe) and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c2052-105">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-105">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="c2052-106">계약은 수학 연산(Add, Subtract, Multiply 및 Divide)을 노출시키는 `ICalculator` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-106">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="c2052-107">클라이언트에서 지정된 수학 작업을 동기적으로 요청하면 서비스에서 결과로 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-107">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="c2052-108">콘솔 창에는 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-108">Client activity is visible in the console window.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c2052-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c2052-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c2052-110">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="c2052-111">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c2052-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-112">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
> <span data-ttu-id="c2052-113">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c2052-114">이 샘플에서는 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)를 사용 하 여 `ICalculator` 계약을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-114">This sample exposes the `ICalculator` contract using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="c2052-115">이 바인딩의 구성은 Web.config 파일에서 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-115">The configuration of this binding has been expanded in the Web.config file.</span></span>  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="c2052-116">기본 `binding` 요소에서 `maxReceivedMessageSize` 값을 사용하면 들어오는 메시지의 최대 크기를 바이트 단위로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-116">On the base `binding` element, the `maxReceivedMessageSize` value lets you configure the maximum size of an incoming message (in bytes).</span></span> <span data-ttu-id="c2052-117">`hostNameComparisonMode` 값을 사용하면 메시지를 서비스로 역 멀티플렉싱할 때 호스트 이름이 고려되는지 여부를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-117">The `hostNameComparisonMode` value lets you configure whether the hostname is considered when de-multiplexing messages to the service.</span></span> <span data-ttu-id="c2052-118">`messageEncoding` 값을 사용하면 메시지에 텍스트 또는 MTOM 인코딩 중 어느 것을 사용할지 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-118">The `messageEncoding` value lets you configure whether to use Text or MTOM encoding for messages.</span></span> <span data-ttu-id="c2052-119">`textEncoding` 값을 사용하면 메시지의 문자 인코딩을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-119">The `textEncoding` value lets you configure the character encoding for messages.</span></span> <span data-ttu-id="c2052-120">`bypassProxyOnLocal` 값을 사용하면 로컬 통신에 HTTP 프록시를 사용할지 여부를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-120">The `bypassProxyOnLocal` value lets you configure whether to use an HTTP proxy for local communication.</span></span> <span data-ttu-id="c2052-121">`transactionFlow` 값을 사용하면 현재 트랜잭션의 흐름 여부를 알 수 있습니다(작업이 트랜잭션 흐름용으로 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="c2052-121">The `transactionFlow` value configures whether the current transaction is flowed (if an operation is configured for transaction flow).</span></span>  
  
 <span data-ttu-id="c2052-122">[\<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) 요소에서 사용 하도록 설정 된 부울 값은 신뢰할 수 있는 세션을 사용할지 여부를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-122">On the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) element, the enabled Boolean value configures whether reliable sessions are enabled.</span></span> <span data-ttu-id="c2052-123">`ordered` 값을 사용하면 메시지 순서의 보존 여부를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-123">The `ordered` value configures whether message ordering is preserved.</span></span> <span data-ttu-id="c2052-124">`inactivityTimeout` 값은 세션에 오류가 발생할 때까지 유휴 상태로 남을 수 있는 시간을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-124">The `inactivityTimeout` value configures how long a session can be idle before being faulted.</span></span>  
  
 <span data-ttu-id="c2052-125">[\<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)에서 `mode` 값은 사용 해야 하는 보안 모드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-125">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="c2052-126">이 샘플에서는 메시지 보안이 사용 되므로 [\<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) [\<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)내에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-126">In this sample, messages security is being used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="c2052-127">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c2052-128">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c2052-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c2052-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c2052-130">다음 명령을 사용 하 여 ASP.NET 4.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-130">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="c2052-131">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="c2052-132">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2052-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="c2052-133">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c2052-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
