---
description: '자세한 정보: 메시지 보안 샘플'
title: Message Security 샘플
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: adec9df3b2a3b5ba022ec2123a8d90d85869246b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752303"
---
# <a name="message-security-sample"></a><span data-ttu-id="52ad6-103">Message Security 샘플</span><span class="sxs-lookup"><span data-stu-id="52ad6-103">Message Security Sample</span></span>

<span data-ttu-id="52ad6-104">이 샘플에서는 `basicHttpBinding` 및 메시지 보안을 사용하는 애플리케이션을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-104">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="52ad6-105">이 샘플은 계산기 서비스를 구현 하는 [시작](getting-started-sample.md) 을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52ad6-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="52ad6-107">`basicHttpBinding`의 보안 모드는 `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` 및 `None` 등의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-107">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="52ad6-108">다음 샘플 서비스 App.config 파일에서 엔드포인트 정의는 `basicHttpBinding`을 지정하며, 다음 샘플 구성에서 보여 주는 것처럼 `Binding1`이라는 바인딩 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-108">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="52ad6-109">바인딩 구성은 `mode` [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` `clientCredentialType` [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) `Certificate` 다음 샘플 구성에 표시 된 것 처럼의 특성을로 설정 하 고의 특성을로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-109">The binding configuration sets the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="52ad6-110">서비스가 클라이언트에게 자신을 인증하는 데 사용하는 인증서는 구성 파일의 behaviors 섹션에 있는 `serviceCredentials` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-110">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="52ad6-111">클라이언트가 서비스에 자신을 인증하는 데 사용하는 인증서에 적용되는 유효성 검사 모드 또한 behaviors 섹션에서 `clientCertificate` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-111">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="52ad6-112">동일한 바인딩 및 보안 세부 정보가 클라이언트 구성 파일에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-112">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="52ad6-113">호출자의 ID는 다음 코드를 사용하여 서비스 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-113">The identity of the caller is displayed in the service console window by using the following code:</span></span>  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 <span data-ttu-id="52ad6-114">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="52ad6-115">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-115">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="52ad6-116">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="52ad6-116">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="52ad6-117">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="52ad6-118">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="52ad6-119">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="52ad6-119">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="52ad6-120">샘플 설치 폴더에서 Setup.bat를 실행하여</span><span class="sxs-lookup"><span data-stu-id="52ad6-120">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="52ad6-121">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-121">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="52ad6-122">Setup.bat 배치 파일은 Windows SDK 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-122">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="52ad6-123">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-123">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="52ad6-124">이 환경 변수는 Windows SDK 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-124">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2. <span data-ttu-id="52ad6-125">\service\bin에서 서비스 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-125">Run the service application from \service\bin.</span></span>  
  
3. <span data-ttu-id="52ad6-126">\client\bin에서 클라이언트 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-126">Run the client application from \client\bin.</span></span> <span data-ttu-id="52ad6-127">클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-127">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="52ad6-128">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52ad6-128">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
5. <span data-ttu-id="52ad6-129">샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-129">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="52ad6-130">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-130">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="52ad6-131">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="52ad6-131">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="52ad6-132">서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-132">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="52ad6-133">서비스 프로그램 파일을 서버의 서비스 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-133">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="52ad6-134">Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일도 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-134">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3. <span data-ttu-id="52ad6-135">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-135">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="52ad6-136">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-136">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="52ad6-137">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-137">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="52ad6-138">서버에서 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-138">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="52ad6-139">`setup.bat`인수를 사용 하 여를 실행 하면 컴퓨터의 정규화 된 `service` 도메인 이름으로 서비스 인증서가 생성 되 고 서비스 인증서가 이름이 .cer 인 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-139">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="52ad6-140">`findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 컴퓨터의 정규화 된 도메인 이름과 같은 새 인증서 이름 (요소의 특성)을 반영 하도록 Service.exe.config를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-140">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="52ad6-141">또한 기본 주소 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.`.`</span><span class="sxs-lookup"><span data-stu-id="52ad6-141">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7. <span data-ttu-id="52ad6-142">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-142">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="52ad6-143">클라이언트에서 `setup.bat client`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-143">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="52ad6-144">`setup.bat` 인수를 사용하여 `client`를 실행하면 client.com이라는 클라이언트 인증서가 생성되어 Client.cer이라는 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-144">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="52ad6-145">클라이언트 컴퓨터의 Client.exe.config 파일에서 엔드포인트의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-145">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="52ad6-146">이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-146">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="52ad6-147">또한 `findValue` 의 특성을 [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) 서버의 정규화 된 도메인 이름인 새 서비스 인증서 이름으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-147">Also change the `findValue` attribute of the [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="52ad6-148">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-148">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="52ad6-149">클라이언트에서 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-149">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="52ad6-150">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-150">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="52ad6-151">서버에서 ImportClientCert.bat를 실행하여 Client.cer 파일에서 LocalMachine - TrustedPeople 저장소로 클라이언트 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-151">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="52ad6-152">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-152">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="52ad6-153">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-153">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1. <span data-ttu-id="52ad6-154">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52ad6-154">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="52ad6-155">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="52ad6-155">To clean up after the sample</span></span>  
  
- <span data-ttu-id="52ad6-156">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-156">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="52ad6-157">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-157">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="52ad6-158">컴퓨터에서 인증서를 사용 하는 WCF (Windows Communication Foundation) 샘플을 실행 한 경우 CurrentUser-비트 사용자 저장소에 설치 된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-158">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="52ad6-159">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="52ad6-159">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="52ad6-160">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-160">The samples may already be installed on your machine.</span></span> <span data-ttu-id="52ad6-161">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="52ad6-161">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="52ad6-162">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-162">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="52ad6-163">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ad6-163">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`
