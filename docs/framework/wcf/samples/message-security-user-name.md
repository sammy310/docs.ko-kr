---
description: '자세한 정보: 메시지 보안 사용자 이름'
title: Message Security User Name
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: f02b1aecffddfc047cc96acc071ab5eefca91807
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752290"
---
# <a name="message-security-user-name"></a><span data-ttu-id="82a08-103">Message Security User Name</span><span class="sxs-lookup"><span data-stu-id="82a08-103">Message Security User Name</span></span>

<span data-ttu-id="82a08-104">이 샘플에서는 클라이언트에 대해 사용자 이름 인증과 함께 WS-Security를 사용하고 서버의 X.509v3 인증서를 사용하는 서버 인증을 요구하는 애플리케이션을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-104">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span> <span data-ttu-id="82a08-105">클라이언트와 서버 간의 모든 애플리케이션 메시지는 서명 및 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-105">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="82a08-106">기본적으로 클라이언트에 의해 제공되는 사용자 이름과 암호는 유효한 Windows 계정에 로그온하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-106">By default, the username and password supplied by the client are used to logon to a valid Windows account.</span></span> <span data-ttu-id="82a08-107">이 샘플은 [WSHttpBinding](wshttpbinding.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-107">This sample is based on the [WSHttpBinding](wshttpbinding.md).</span></span> <span data-ttu-id="82a08-108">이 샘플은 IIS(인터넷 정보 서비스)에 의해 호스트되는 클라이언트 콘솔 프로그램(Client.exe) 및 서비스 라이브러리(Service.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-108">This sample consists of a client console program (Client.exe) and a service library (Service.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="82a08-109">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-109">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82a08-110">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="82a08-111">또한 이 샘플에서는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-111">This sample also demonstrates:</span></span>  
  
- <span data-ttu-id="82a08-112">추가 권한 부여를 수행할 수 있도록 하는 Windows 계정에 대한 기본 매핑</span><span class="sxs-lookup"><span data-stu-id="82a08-112">The default mapping to Windows accounts so that additional authorization can be performed.</span></span>  
  
- <span data-ttu-id="82a08-113">서비스 코드에서 호출자의 ID 정보에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="82a08-113">How to access the caller's identity information from the service code.</span></span>  
  
 <span data-ttu-id="82a08-114">서비스는 Web.config 구성 파일을 사용 하 여 정의 되는 서비스와 통신 하기 위한 단일 끝점을 노출 합니다. 끝점은 주소, 바인딩 및 계약으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-114">The service exposes a single endpoint for communicating with the service, which is defined using the configuration file Web.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="82a08-115">바인딩은 기본적으로 메시지 보안을 사용 하는 표준으로 구성 됩니다 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="82a08-115">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), which defaults to using message security.</span></span> <span data-ttu-id="82a08-116">이 샘플은 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 클라이언트 사용자 이름 인증을 사용 하도록 표준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-116">This sample sets the standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to use client username authentication.</span></span> <span data-ttu-id="82a08-117">동작은 서비스 인증에 사용자 자격 증명을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-117">The behavior specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="82a08-118">서버 인증서는의 특성과 동일한 주체 이름 값을 포함 해야 합니다 `findValue` [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="82a08-118">The server certificate must contain the same value for the subject name as the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
      This configuration references the "localhost" certificate installed during the setup instructions.  
      -->  
        <serviceCredentials>  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="82a08-119">클라이언트 엔드포인트 구성은 서비스 엔드포인트의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-119">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="82a08-120">클라이언트 바인딩은 적절한 `securityMode` 및 `authenticationMode`를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-120">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span> <span data-ttu-id="82a08-121">다중 컴퓨터 구성에서 실행할 경우 서비스 엔드포인트 주소를 적절하게 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-121">When running in a cross-computer scenario, the service endpoint address must be changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="82a08-122">클라이언트 구현에서는 사용할 사용자 이름과 암호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-122">The client implementation sets the user name and password to use.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 <span data-ttu-id="82a08-123">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-123">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="82a08-124">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-124">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="82a08-125">MessageSecurity 샘플에 포함된 Setup.bat 배치 파일을 사용하면 인증서 기반 보안이 필요한 호스트된 애플리케이션을 실행하도록 관련 인증서가 있는 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-125">The Setup.bat batch file included with the MessageSecurity samples enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="82a08-126">배치 파일은 두 가지 모드로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-126">The batch file can be run in two modes.</span></span> <span data-ttu-id="82a08-127">단일 컴퓨터 모드에서 배치 파일을 실행하려면 명령줄에 `setup.bat`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-127">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="82a08-128">서비스 모드에서 실행하려면 `setup.bat service`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-128">To run it in service mode type `setup.bat service`.</span></span> <span data-ttu-id="82a08-129">다중 컴퓨터 구성에서 샘플을 실행할 경우 이 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-129">You use this mode when running the sample across computers.</span></span> <span data-ttu-id="82a08-130">자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82a08-130">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="82a08-131">다음은 배치 파일의 여러 다른 섹션에 대한 간략한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-131">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="82a08-132">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="82a08-132">Creating the server certificate</span></span>  
  
     <span data-ttu-id="82a08-133">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-133">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="82a08-134">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-134">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="82a08-135">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-135">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="82a08-136">`setup.bat service`와 같은 서비스의 인수와 함께 Setup.bat 배치 파일을 실행할 경우 %SERVER_NAME%은 컴퓨터의 정규화된 도메인 이름을 포함하고</span><span class="sxs-lookup"><span data-stu-id="82a08-136">If the Setup.bat batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span>  <span data-ttu-id="82a08-137">그렇지 않은 경우 기본적으로 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-137">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="82a08-138">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="82a08-138">Installing the server certificate into the client's trusted certificate store</span></span>  
  
     <span data-ttu-id="82a08-139">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-139">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="82a08-140">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-140">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="82a08-141">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-141">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="82a08-142">인증서의 프라이빗 키에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="82a08-142">Granting permissions on the certificate's private key</span></span>  
  
     <span data-ttu-id="82a08-143">Setup.bat 배치 파일의 다음 줄은 LocalMachine 저장소에 저장 된 서버 인증서를 ASP.NET 작업자 프로세스 계정에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-143">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="82a08-144">가 아닌를 사용 하는 경우 영어 버전의 Windows에서는 Setup.bat 파일을 편집 하 여 `NT AUTHORITY\NETWORK SERVICE` 계정 이름을 해당 지역으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-144">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82a08-145">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="82a08-145">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="82a08-146">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-146">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="82a08-147">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-147">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="82a08-148">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="82a08-148">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="82a08-149">Makecert.exe 및 FindPrivateKey.exe가 있는 폴더가 경로에 포함되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-149">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2. <span data-ttu-id="82a08-150">관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트 샘플 설치 폴더에서 Setup.bat를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-150">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="82a08-151">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-151">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82a08-152">Setup.bat 배치 파일은 Visual Studio 용 개발자 명령 프롬프트에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-152">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="82a08-153">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-153">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="82a08-154">이 환경 변수는 Visual Studio에 대 한 개발자 명령 프롬프트 내에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-154">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="82a08-155">주소를 입력 하 여 브라우저를 사용 하 여 서비스에 대 한 액세스를 확인 `http://localhost/servicemodelsamples/service.svc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-155">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>
  
4. <span data-ttu-id="82a08-156">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-156">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="82a08-157">클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-157">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="82a08-158">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82a08-158">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="82a08-159">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="82a08-159">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="82a08-160">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-160">Create a directory on the service computer.</span></span> <span data-ttu-id="82a08-161">IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-161">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services management tool.</span></span>  
  
2. <span data-ttu-id="82a08-162">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-162">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="82a08-163">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-163">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="82a08-164">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-164">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="82a08-165">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-165">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="82a08-166">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-166">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="82a08-167">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-167">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="82a08-168">서버에서 `setup.bat service` 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-168">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="82a08-169">`setup.bat`인수를 사용 하 여를 실행 하면 컴퓨터의 정규화 된 `service` 도메인 이름으로 서비스 인증서가 생성 되 고 서비스 인증서가 이름이 .cer 인 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-169">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="82a08-170">컴퓨터의 정규화된 도메인 이름과 일치하는 새 인증서 이름이 serviceCertificate 요소의 findValue 특성에 반영되도록 Web.config를 편집합니다`.`</span><span class="sxs-lookup"><span data-stu-id="82a08-170">Edit Web.config to reflect the new certificate name (in the findValue attribute in the serviceCertificate element) which is the same as the fully-qualified domain name of the computer`.`</span></span>  
  
7. <span data-ttu-id="82a08-171">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-171">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="82a08-172">클라이언트 컴퓨터의 Client.exe.config 파일에서 엔드포인트의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-172">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="82a08-173">클라이언트에서 관리자 권한으로 연 Visual Studio 용 개발자 명령 프롬프트에서 ImportServiceCert.bat를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-173">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="82a08-174">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-174">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="82a08-175">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-175">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="82a08-176">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82a08-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="82a08-177">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="82a08-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="82a08-178">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-178">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82a08-179">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-179">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="82a08-180">컴퓨터에서 인증서를 사용 하는 WCF (Windows Communication Foundation) 샘플을 실행 한 경우에는 CurrentUser-비트 사용자 저장소에 설치 된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a08-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="82a08-181">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="82a08-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
