---
title: HPPTS 기반의 사용자 지정 바인딩 신뢰할 수 있는 세션
ms.date: 03/30/2017
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
ms.openlocfilehash: 051e7f56662a2ca67018ae7dd29189ff50245fc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183866"
---
# <a name="custom-binding-reliable-session-over-https"></a><span data-ttu-id="15616-102">HPPTS 기반의 사용자 지정 바인딩 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="15616-102">Custom Binding Reliable Session over HTTPS</span></span>
<span data-ttu-id="15616-103">이 샘플에서는 신뢰할 수 있는 세션에 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15616-103">This sample demonstrates the use of SSL transport security with Reliable Sessions.</span></span> <span data-ttu-id="15616-104">신뢰할 수 있는 세션에서는 WS-Reliable Messaging 프로토콜을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-104">Reliable Sessions implements the WS-Reliable Messaging protocol.</span></span> <span data-ttu-id="15616-105">신뢰할 수 있는 세션에 WS-Security를 작성하여 신뢰할 수 있는 보안 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-105">You can have a secure reliable session by composing WS-Security over Reliable Sessions.</span></span> <span data-ttu-id="15616-106">하지만 경우에 따라 대신 SSL에 HTTP 전송 보안을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-106">But sometimes, you may choose to instead use HTTP transport security with SSL.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="15616-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="15616-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="15616-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="15616-109">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15616-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a><span data-ttu-id="15616-111">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="15616-111">Sample Details</span></span>  
 <span data-ttu-id="15616-112">SSL을 사용하면 패킷 자체가 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="15616-112">SSL ensures that the packets themselves are secured.</span></span> <span data-ttu-id="15616-113">이는 WS-Secure Conversation을 사용하여 신뢰할 수 있는 세션을 보안하는 경우와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="15616-113">It is important to note that this is different from securing the reliable session using WS-Secure Conversation.</span></span>  
  
 <span data-ttu-id="15616-114">HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 먼저 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-114">To use reliable session over HTTPS, you must create a custom binding.</span></span> <span data-ttu-id="15616-115">이 샘플은 계산기 서비스를 구현하는 [시작 하기를](../../../../docs/framework/wcf/samples/getting-started-sample.md) 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-115">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="15616-116">사용자 지정 바인딩은 신뢰할 수 있는 세션 바인딩 요소 와 [ \<httpsTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="15616-116">A custom binding is created using the reliable session binding element and the [\<httpsTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md).</span></span> <span data-ttu-id="15616-117">다음 구성은 사용자 지정 바인딩의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="15616-117">The following configuration is of the custom binding.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="reliableSessionOverHttps"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed as http://localhost/servicemodelsamples/service.svc/mex-->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="reliableSessionOverHttps">  
          <reliableSession />  
          <httpsTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="true" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="15616-118">샘플의 프로그램 코드는 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md) 서비스의 코드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-118">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="15616-119">샘플을 빌드하고 실행하기 전에 Web Server Certificate Wizard를 사용하여 인증서를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-119">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="15616-120">구성 파일 설정의 엔드포인트 정의와 바인딩 정의를 사용하면 클라이언트의 다음 샘플 구성에 표시된 것과 같이 사용자 지정 바인딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-120">The endpoint definition and binding definition in the configuration file settings enable the use of custom binding as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint name=""  
                address="https://localhost/servicemodelsamples/service.svc"
                binding="customBinding"
                bindingConfiguration="reliableSessionOverHttps"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
      <bindings>  
        <customBinding>  
          <binding name="reliableSessionOverHttps">  
            <reliableSession />  
            <httpsTransport />  
          </binding>  
        </customBinding>
    </bindings>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="15616-121">지정된 주소에서는 https:// 체계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-121">The address specified uses the https:// scheme.</span></span>  
  
 <span data-ttu-id="15616-122">이 샘플에 사용된 인증서는 Makecert.exe로 만든 테스트 인증서이므로 브라우저에서 와 같은 https://localhost/servicemodelsamples/service.svchttps 주소에 액세스하려고 할 때 보안 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="15616-122">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="15616-123">WCF(Windows 통신 재단) 클라이언트가 테스트 인증서를 사용하여 작업할 수 있도록 보안 경고를 억제하기 위해 클라이언트에 몇 가지 추가 코드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-123">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="15616-124">이 코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15616-124">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="15616-125">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="15616-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="15616-126">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="15616-126">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="15616-127">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="15616-127">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="15616-128">다음 명령을 사용하여 ASP.NET 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-128">Install  ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="15616-129">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15616-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="15616-130">[IIS(인터넷 정보 서비스) 서버 인증서 설치 지침을](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)수행했습니까?</span><span class="sxs-lookup"><span data-stu-id="15616-130">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="15616-131">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="15616-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="15616-132">단일 또는 교차 컴퓨터 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="15616-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
