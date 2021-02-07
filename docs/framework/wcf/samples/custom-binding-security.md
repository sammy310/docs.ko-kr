---
description: '자세한 정보: 사용자 지정 바인딩 보안'
title: Custom Binding Security
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: f0ed4b40fe4e0869f34a4f6016123dc9f0a57f45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732633"
---
# <a name="custom-binding-security"></a><span data-ttu-id="112ef-103">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="112ef-103">Custom Binding Security</span></span>

<span data-ttu-id="112ef-104">이 샘플에서는 사용자 지정 바인딩을 사용하여 보안을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-104">This sample demonstrates how to configure security by using a custom binding.</span></span> <span data-ttu-id="112ef-105">여기서는 사용자 지정 바인딩을 사용하여 메시지를 안전하게 전송하고 메시지 수준 보안을 가능하게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-105">It shows how to use a custom binding to enable message-level security together with a secure transport.</span></span> <span data-ttu-id="112ef-106">이러한 방법은 클라이언트와 서비스 간에 메시지를 전송하는 데 보안 전송이 요구되면서 동시에 메시지가 메시지 수준에서 보호되어야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-106">This is useful when a secure transport is required to transmit the messages between client and service and simultaneously the messages must be secure on the message level.</span></span> <span data-ttu-id="112ef-107">이 구성은 시스템 제공 바인딩에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-107">This configuration is not supported by system-provided bindings.</span></span>

<span data-ttu-id="112ef-108">이 샘플은 클라이언트 콘솔 프로그램(EXE) 및 서비스 콘솔 프로그램(EXE)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-108">This sample consists of a client console program (EXE) and a service console program (EXE).</span></span> <span data-ttu-id="112ef-109">서비스는 이중 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-109">The service implements a duplex contract.</span></span> <span data-ttu-id="112ef-110">계약은 수학 연산(Add, Subtract, Multiply 및 Divide)을 노출시키는 `ICalculatorDuplex` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-110">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="112ef-111">`ICalculatorDuplex` 인터페이스를 사용하여 클라이언트는 수학 연산을 수행하고 세션 도중 실행 결과를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-111">The `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over a session.</span></span> <span data-ttu-id="112ef-112">서비스는 독립적으로 `ICalculatorDuplexCallback` 인터페이스에서 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-112">Independently, the service may return results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="112ef-113">클라이언트와 서비스 간에 전송되는 메시지 집합을 서로 연결하기 위해 컨텍스트를 설정해야 하므로 이중 계약에는 세션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-113">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span> <span data-ttu-id="112ef-114">이중 통신을 지원하는 보안된 사용자 지정 바인딩이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-114">A custom binding is defined that supports duplex communication and is secure.</span></span>

> [!NOTE]
> <span data-ttu-id="112ef-115">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="112ef-116">서비스 구성에서는 다음을 지원하는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-116">The service configuration defines a custom binding that supports the following:</span></span>

- <span data-ttu-id="112ef-117">TLS/SSL 프로토콜을 사용하여 보호되는 TCP 통신</span><span class="sxs-lookup"><span data-stu-id="112ef-117">TCP communication protected by using the TLS/SSL protocol.</span></span>

- <span data-ttu-id="112ef-118">Windows 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="112ef-118">Windows message security.</span></span>

<span data-ttu-id="112ef-119">사용자 지정 바인딩 구성은 메시지 수준 보안을 동시에 사용하도록 하여 보안 전송을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-119">The custom binding configuration enables secure transport by simultaneously enabling the message-level security.</span></span> <span data-ttu-id="112ef-120">바인딩 요소의 순서는 사용자 지정 바인딩을 정의 하는 데 중요 합니다. 각는 채널 스택의 계층을 나타냅니다 ( [사용자 지정 바인딩](../extending/custom-bindings.md)참조).</span><span class="sxs-lookup"><span data-stu-id="112ef-120">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span> <span data-ttu-id="112ef-121">다음 샘플 구성과 같이 사용자 지정 바인딩은 서비스 및 클라이언트 구성 파일에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-121">The custom binding is defined in the service and client configuration files, as shown in the following sample configuration.</span></span>

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

<span data-ttu-id="112ef-122">사용자 지정 바인딩은 서비스 인증서를 사용하여 전송 수준에서 서비스를 인증하고 클라이언트와 서비스 간 전송 시 메시지를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-122">The custom binding uses a service certificate to authenticate the service on the transport level and to protect the messages during the transmission between client and service.</span></span> <span data-ttu-id="112ef-123">이러한 작업은 `sslStreamSecurity` 바인딩 요소에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-123">This is accomplished by the `sslStreamSecurity` binding element.</span></span> <span data-ttu-id="112ef-124">다음 샘플 구성과 같이 서비스의 인증서는 서비스 동작을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-124">The service's certificate is configured using a service behavior as shown in the following sample configuration.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="112ef-125">또한 사용자 지정 바인딩은 기본 자격 증명 형식인 Windows 자격 증명 형식의 메시지 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-125">Additionally, the custom binding uses message security with Windows credential type - this is the default credential type.</span></span> <span data-ttu-id="112ef-126">이러한 작업은 `security` 바인딩 요소에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-126">This is accomplished by the `security` binding element.</span></span> <span data-ttu-id="112ef-127">Kerberos 인증 메커니즘이 사용 가능한 경우 클라이언트 및 서비스는 모두 메시지 수준 보안을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-127">Both client and service are authenticated using message-level security if the Kerberos authentication mechanism is available.</span></span> <span data-ttu-id="112ef-128">Active Directory 환경에서 샘플이 실행될 경우 이 방법이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-128">This happens if the sample is run in the Active Directory environment.</span></span> <span data-ttu-id="112ef-129">Kerberos 인증 메커니즘을 사용할 수 없는 경우에는 NTLM 인증이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-129">If the Kerberos authentication mechanism is not available, NTLM authentication is used.</span></span> <span data-ttu-id="112ef-130">NTLM은 서비스에 대해 클라이언트를 인증하지만 클라이언트에 대해 서비스를 인증하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-130">NTLM authenticates the client to the service but does not authenticate the service to the client.</span></span> <span data-ttu-id="112ef-131">`security`바인딩 요소는를 사용 하도록 구성 되며,이로 `SecureConversation` `authenticationType` 인해 클라이언트와 서비스 모두에 보안 세션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-131">The `security` binding element is configured to use `SecureConversation` `authenticationType`, which results in the creation of a security session on both the client and the service.</span></span> <span data-ttu-id="112ef-132">이러한 구성은 서비스의 이중 계약을 사용할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-132">This is required to enable the service's duplex contract to work.</span></span>

<span data-ttu-id="112ef-133">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-133">When you run the sample, the operation requests and responses are displayed in the client's console window.</span></span> <span data-ttu-id="112ef-134">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-134">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="112ef-135">샘플을 실행하면 서비스에서 전송된 콜백 인터페이스에서 클라이언트에 반환된 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-135">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="112ef-136">각 중간 결과가 표시된 다음 모든 작업이 완료되면 전체 수식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-136">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="112ef-137">클라이언트를 종료하려면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-137">Press ENTER to shut down the client.</span></span>

<span data-ttu-id="112ef-138">포함된 Setup.bat 파일을 사용하면 인증서 기반 보안이 필요한 호스팅된 애플리케이션을 실행하도록 관련 서비스 인증서가 있는 클라이언트와 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-138">The included Setup.bat file enables you to configure the client and server with the relevant service certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="112ef-139">다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-139">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="112ef-140">다음 부분에는 이 샘플에 적용되는 배치 파일을 적절한 구성에서 실행하도록 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-140">The following provides a brief overview of the different sections of the batch files that apply to this sample so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="112ef-141">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="112ef-141">Creating the server certificate.</span></span>

  <span data-ttu-id="112ef-142">Setup.bat 파일에서 다음 줄은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-142">The following lines from the Setup.bat file create the server certificate to be used.</span></span> <span data-ttu-id="112ef-143">`%SERVER_NAME%`변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-143">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="112ef-144">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-144">Change this variable to specify your own server name.</span></span> <span data-ttu-id="112ef-145">이 배치 파일에서 서버 이름의 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-145">This batch file defaults the server name to localhost.</span></span>

  <span data-ttu-id="112ef-146">인증서는 웹 호스팅 서비스에 대한 CurrentUser 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-146">The certificate is stored in the CurrentUser store for the Web-hosted services.</span></span>

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- <span data-ttu-id="112ef-147">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="112ef-147">Installing the server certificate into the client's trusted certificate store.</span></span>

  <span data-ttu-id="112ef-148">Setup.bat 파일에서 다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-148">The following lines in the Setup.bat file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="112ef-149">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-149">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="112ef-150">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-150">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > <span data-ttu-id="112ef-151">Setup.bat 배치 파일은 Visual Studio 2010 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-151">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="112ef-152">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-152">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="112ef-153">이 환경 변수는 Visual Studio 2010 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-153">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="112ef-154">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="112ef-154">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="112ef-155">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-155">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="112ef-156">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-156">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="112ef-157">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="112ef-157">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="112ef-158">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="112ef-158">To run the sample on the same computer</span></span>

1. <span data-ttu-id="112ef-159">관리자 권한으로 Visual Studio 창에 대 한 개발자 명령 프롬프트를 열고 샘플 설치 폴더에서 Setup.bat를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-159">Open a Developer Command Prompt for Visual Studio window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="112ef-160">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-160">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="112ef-161">Setup.bat 배치 파일은 Visual Studio 2012 명령 프롬프트에서 실행 되도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-161">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="112ef-162">Visual Studio 2012 명령 프롬프트 내에서 설정 된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일을 포함 하는 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-162">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="112ef-163">\service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-163">Launch Service.exe from \service\bin.</span></span>

3. <span data-ttu-id="112ef-164">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-164">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="112ef-165">클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-165">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="112ef-166">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="112ef-166">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="112ef-167">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="112ef-167">To run the sample across computers</span></span>

1. <span data-ttu-id="112ef-168">서비스 컴퓨터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-168">On the service computer:</span></span>

    1. <span data-ttu-id="112ef-169">서비스 컴퓨터에서 servicemodelsamples라는 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-169">Create a virtual directory named servicemodelsamples on the service computer.</span></span>

    2. <span data-ttu-id="112ef-170">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-170">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="112ef-171">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-171">Ensure that you copy the files in the \bin subdirectory.</span></span>

    3. <span data-ttu-id="112ef-172">Setup.bat 및 Cleanup.bat 파일을 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-172">Copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>

    4. <span data-ttu-id="112ef-173">관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서 다음 명령을 실행 `Setup.bat service` 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-173">Run the following command in a Developer Command Prompt for Visual Studio opened with administrator privileges: `Setup.bat service`.</span></span> <span data-ttu-id="112ef-174">이렇게 하면 배치 파일이 실행된 컴퓨터의 이름과 일치하는 주체 이름을 가진 서비스 인증서가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-174">This creates the service certificate with the subject name matching the name of the computer the batch file was run on.</span></span>

        > [!NOTE]
        > <span data-ttu-id="112ef-175">Setup.bat 배치 파일은 Visual Studio 2010 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-175">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="112ef-176">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-176">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="112ef-177">이 환경 변수는 Visual Studio 2010 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-177">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

    5. <span data-ttu-id="112ef-178">[\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)이전 단계에서 생성 된 인증서의 주체 이름이 반영 되도록 Service.exe.config 파일 내에서를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-178">Change the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) inside the Service.exe.config file to reflect the subject name of the certificate generated in the previous step.</span></span>

    6. <span data-ttu-id="112ef-179">명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-179">Run Service.exe from a command prompt.</span></span>

2. <span data-ttu-id="112ef-180">클라이언트 컴퓨터의 경우:</span><span class="sxs-lookup"><span data-stu-id="112ef-180">On the client computer:</span></span>

    1. <span data-ttu-id="112ef-181">\client\bin\ 폴더에서 클라이언트 컴퓨터로 클라이언트 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-181">Copy the client program files from the \client\bin\ folder to the client computer.</span></span> <span data-ttu-id="112ef-182">Cleanup.bat 파일도 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-182">Also copy the Cleanup.bat file.</span></span>

    2. <span data-ttu-id="112ef-183">Cleanup.bat를 실행하여 이전 샘플에서 이전의 모든 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-183">Run Cleanup.bat to remove any old certificates from previous samples.</span></span>

    3. <span data-ttu-id="112ef-184">관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 서비스 컴퓨터에서 다음 명령을 실행 하 여 서비스의 인증서를 내보냅니다 ( `%SERVER_NAME%` 서비스가 실행 되는 컴퓨터의 정규화 된 이름으로 대체).</span><span class="sxs-lookup"><span data-stu-id="112ef-184">Export the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the service computer (substitute `%SERVER_NAME%` with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. <span data-ttu-id="112ef-185">%SERVER_NAME%.cer을 클라이언트 컴퓨터에 복사합니다. %SERVER_NAME%은 서비스가 실행되고 있는 컴퓨터의 정규화된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-185">Copy %SERVER_NAME%.cer to the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running).</span></span>

    5. <span data-ttu-id="112ef-186">관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 클라이언트 컴퓨터에서 다음 명령을 실행 하 여 서비스의 인증서를 가져옵니다 .% SERVER_NAME%는 서비스가 실행 되 고 있는 컴퓨터의 정규화 된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-186">Import the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        <span data-ttu-id="112ef-187">신뢰할 수 있는 발급자에 의해 인증서가 발급된 경우 c, d 및 e 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-187">Steps c, d, and e are not necessary if the certificate is issued by a Trusted Issuer.</span></span>

    6. <span data-ttu-id="112ef-188">클라이언트의 App.config 파일을 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-188">Modify the client’s App.config file as follows:</span></span>

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. <span data-ttu-id="112ef-189">도메인 환경에서 NetworkService 또는 LocalSystem 계정이 아닌 계정으로 서비스가 실행 중이면 서비스를 실행하는 데 사용되는 해당 계정에 기초하여 적절한 UPN 또는 SPN을 설정하기 위해 클라이언트의 App.config 파일에서 서비스 엔드포인트에 대한 엔드포인트 ID를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-189">If the service is running under an account other than the NetworkService or LocalSystem account in a domain environment, you might need to modify the endpoint identity for the service endpoint inside the client's App.config file to set the appropriate UPN or SPN based on the account that is used to run the service.</span></span> <span data-ttu-id="112ef-190">끝점 id에 대 한 자세한 내용은 [서비스 id 및 인증](../feature-details/service-identity-and-authentication.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="112ef-190">For more information about endpoint identity, see the [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md) topic.</span></span>

    8. <span data-ttu-id="112ef-191">명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-191">Run Client.exe from a command prompt.</span></span>

### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="112ef-192">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="112ef-192">To clean up after the sample</span></span>

- <span data-ttu-id="112ef-193">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="112ef-193">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>
