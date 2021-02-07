---
description: '자세한 정보: WS 2007 페더레이션 HTTP 바인딩'
title: WS 2007 페더레이션 HTTP 바인딩
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 12363abb1c8c503db8ec4aac9197276c8ec41c58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715056"
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="d553a-103">WS 2007 페더레이션 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="d553a-103">WS 2007 Federation HTTP Binding</span></span>

<span data-ttu-id="d553a-104">이 샘플에서는 버전 1.3의 WS-Trust 사양을 지원하는 페더레이션 시나리오를 작성하는 데 사용할 수 있는 표준 바인딩인 <xref:System.ServiceModel.WS2007FederationHttpBinding>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-104">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>

> [!NOTE]
> <span data-ttu-id="d553a-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="d553a-106">이 샘플은 콘솔 기반 클라이언트 프로그램 (*Client.exe*), 콘솔 기반 *Securitytokenservice.exe*(보안 토큰 서비스 프로그램) 및 *Service.exe*(콘솔 기반 서비스 프로그램)로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-106">The sample consists of a console-based client program (*Client.exe*), a console-based security token service program (*Securitytokenservice.exe*), and a console-based service program (*Service.exe*).</span></span> <span data-ttu-id="d553a-107">서비스는 요청/회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-107">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="d553a-108">계약은 수학 연산(`ICalculator`, `Add`, `Subtract` 및 `Multiply`)을 노출하는 `Divide` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-108">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="d553a-109">클라이언트가 STS(보안 토큰 서비스)에서 보안 토큰을 가져오고 지정된 수학 연산을 서비스에 동기적으로 요청하면</span><span class="sxs-lookup"><span data-stu-id="d553a-109">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="d553a-110">서비스에서 결과로 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-110">The service then replies with the result.</span></span> <span data-ttu-id="d553a-111">콘솔 창에는 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-111">Client activity is visible in the console window.</span></span>

<span data-ttu-id="d553a-112">이 샘플에서는 `ICalculator` 요소를 사용하여 `ws2007FederationHttpBinding` 계약을 사용할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-112">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="d553a-113">클라이언트에서이 바인딩의 구성은 다음 코드와 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-113">The configuration of this binding on the client is shown in the following code:</span></span>

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Endpoint address and binding for Security Token Service -->
          <issuer address ="http://localhost:8000/sts/windows"
                  binding ="ws2007HttpBinding" />
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

<span data-ttu-id="d553a-114">에서 [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` 값은 사용 해야 하는 보안 모드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-114">On the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="d553a-115">이 샘플에서는 `message` 보안이 사용 됩니다 .이 때문에 [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 가 내부에서 지정 됩니다 [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d553a-115">In this sample, `message` security is used, which is why the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="d553a-116">[\<issuer>](../../configure-apps/file-schema/wcf/issuer.md)내의 요소는 클라이언트가 [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 서비스에 인증할 수 있도록 클라이언트에 보안 토큰을 발급 하는 STS에 대 한 주소와 바인딩을 지정 합니다 `ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="d553a-116">The [\<issuer>](../../configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>
  
<span data-ttu-id="d553a-117">서비스에서이 바인딩의 구성은 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-117">The configuration of this binding on the service is shown in the following code:</span></span>

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Metadata address for Security Token Service -->
          <issuerMetadata address ="http://localhost:8000/sts/mex" >
            <identity>
              <certificateReference storeLocation ="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType ="FindBySubjectDistinguishedName"
                                    findValue ="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

<span data-ttu-id="d553a-118">에서 [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` 값은 사용 해야 하는 보안 모드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-118">On the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="d553a-119">이 샘플에서는 `message` 보안이 사용 됩니다 .이 때문에 [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) 가 내부에서 지정 됩니다 [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d553a-119">In this sample, `message` security is used, which is why the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="d553a-120">[\<issuerMetadata>](../../configure-apps/file-schema/wcf/issuermetadata.md)내의 요소는 `ws2007FederationHttpBinding` [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) STS에 대 한 메타 데이터를 검색 하는 데 사용할 수 있는 끝점의 주소와 id를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-120">The [\<issuerMetadata>](../../configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>

<span data-ttu-id="d553a-121">다음 코드에서는 서비스에 대 한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-121">The behavior for the service is shown in the following code:</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name ="ServiceBehaviour" >
      <serviceDebug includeExceptionDetailInFaults ="true"/>
      <serviceMetadata httpGetEnabled ="true"/>
      <serviceCredentials>
        <issuedTokenAuthentication>
          <knownCertificates>
            <add storeLocation ="LocalMachine"
                 storeName="TrustedPeople"
                 x509FindType="FindBySubjectDistinguishedName"
                 findValue="CN=STS" />
          </knownCertificates>
        </issuedTokenAuthentication>
        <serviceCertificate storeLocation ="LocalMachine"
                            storeName ="My"
                            x509FindType ="FindBySubjectDistinguishedName"
                            findValue ="CN=localhost"/>
      </serviceCredentials>
    </behavior>
  </serviceBehaviors>
</behaviors>
```
  
<span data-ttu-id="d553a-122">>를 통해 [\<issuedTokenAuthentication>](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 서비스는 인증 중에 클라이언트에 제공할 수 있는 토큰에 대 한 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-122">The [\<issuedTokenAuthentication>](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="d553a-123">이 구성은 주체 이름이 CN=STS인 인증서에 의해 서명된 토큰을 서비스에서 수락하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-123">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>

<span data-ttu-id="d553a-124">STS는 표준 <xref:System.ServiceModel.WS2007HttpBinding>을 사용하여 단일 엔드포인트를 사용할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-124">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="d553a-125">서비스는 토큰에 대한 클라이언트의 요청에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-125">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="d553a-126">클라이언트가 Windows 계정을 사용하여 인증될 경우 서비스는 클라이언트의 사용자 이름을 클레임으로 포함하는 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-126">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="d553a-127">토큰을 만드는 도중에 STS는 CN=STS 인증서와 연관된 프라이빗 키를 사용하여 토큰에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-127">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="d553a-128">또한 대칭 키를 만들고 CN=localhost 인증서와 연관된 공개 키를 사용하여 이를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-128">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="d553a-129">토큰을 클라이언트에게 반환할 때 STS는 대칭 키도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-129">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="d553a-130">클라이언트는 발급된 토큰을 `ICalculator` 서비스에 제공하고 대칭 키로 메시지에 서명하여 해당 키를 알고 있음을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-130">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>

<span data-ttu-id="d553a-131">샘플을 실행하면 보안 토큰에 대한 요청이 STS 콘솔 창에 표시되고</span><span class="sxs-lookup"><span data-stu-id="d553a-131">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="d553a-132">작업의 요청과 응답이 클라이언트 및 서비스 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-132">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="d553a-133">애플리케이션을 종료하려면 아무 콘솔 창에서나 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-133">Press ENTER in any of the console windows to shut down the application.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

<span data-ttu-id="d553a-134">이 샘플에 포함 된 *Setup.bat* 파일을 사용 하면 자체 호스팅 응용 프로그램을 실행 하도록 관련 인증서가 있는 서버 및 STS를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-134">The *Setup.bat* file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="d553a-135">배치 파일은 LocalMachine/TrustedPeople 인증서 저장소에서 두 개의 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-135">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="d553a-136">주체 이름 CN=STS를 가지는 첫 번째 인증서는 클라이언트에 발급되는 보안 토큰에 서명하기 위해 STS에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-136">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="d553a-137">주체 이름 CN=localhost를 가지는 두 번째 인증서는 서비스에서 해독할 수 있도록 STS에서 키를 암호화할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-137">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d553a-138">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d553a-138">To set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="d553a-139">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-139">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="d553a-140">관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 Setup.bat 파일을 실행 하 여 필요한 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-140">Open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>

 <span data-ttu-id="d553a-141">이 배치 파일은 Windows SDK와 함께 배포 되는 *Certmgr.exe* 및 Makecert.exe를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-141">This batch file uses *Certmgr.exe* and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="d553a-142">그러나 스크립트에서 이러한 도구를 찾을 수 있도록 하려면 Visual Studio 명령 프롬프트 내에서 *Setup.bat* 를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-142">However, you must run *Setup.bat* from within a Visual Studio command prompt to enable the script to find these tools.</span></span>

1. <span data-ttu-id="d553a-143">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="d553a-144">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d553a-144">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="d553a-145">Windows Vista를 사용 하는 경우 관리자 권한으로 *Service.exe*, *Client.exe* 및 *SecurityTokenService.exe* 를 실행 해야 합니다 (파일을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행** 을 클릭).</span><span class="sxs-lookup"><span data-stu-id="d553a-145">If you are using Windows Vista, you must run *Service.exe*, *Client.exe*, and *SecurityTokenService.exe* with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d553a-146">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-146">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d553a-147">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d553a-147">Check for the following (default) directory before continuing:</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d553a-148">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d553a-149">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d553a-149">This sample is located in the following directory:</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`
