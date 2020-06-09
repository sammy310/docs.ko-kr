---
title: 메시지 보안 인증서
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: 1dec66631368543eecd548ac1ec9bbcda466d746
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584856"
---
# <a name="message-security-certificate"></a><span data-ttu-id="b8420-102">메시지 보안 인증서</span><span class="sxs-lookup"><span data-stu-id="b8420-102">Message Security Certificate</span></span>
<span data-ttu-id="b8420-103">이 샘플에서는 클라이언트에 대해 X.509 v3 인증서를 통한 WS-Security 인증을 사용하며 서버의 X.509 v3 인증서를 사용한 서버 인증을 수행해야 하는 애플리케이션의 구현 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="b8420-104">이 샘플에서는 클라이언트와 서버 간의 모든 애플리케이션 메시지가 서명 및 암호화되도록 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="b8420-105">이 샘플은 [WSHttpBinding](wshttpbinding.md) 을 기반으로 하며, 인터넷 정보 서비스 (IIS)에서 호스팅하는 클라이언트 콘솔 프로그램 및 서비스 라이브러리로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-105">This sample is based on the [WSHttpBinding](wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="b8420-106">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8420-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b8420-108">이 샘플에서는 다음 샘플 코드에 표시된 것과 같이 구성을 이용하여 인증을 제어하는 방법과 보안 컨텍스트에서 호출자의 ID를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="b8420-109">서비스에서는 서비스와 통신하기 위한 하나의 엔드포인트와 WS-MetadataExchange 프로토콜을 사용하여 서비스의 WSDL 문서를 노출하기 위한 하나의 엔드포인트를 노출하며 이러한 엔드포인트는 구성 파일(Web.config)을 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="b8420-110">엔드포인트는 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="b8420-111">바인딩은 표준 요소를 사용 하 여 구성 되며 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 기본값은 메시지 보안을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-111">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="b8420-112">이 샘플에서는 클라이언트 인증을 요구하도록 `clientCredentialType` 특성을 Certificate로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="b8420-113">동작에서는 클라이언트가 서비스를 인증할 때 사용되는 서비스의 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="b8420-114">서버 인증서 주체 이름은 요소의 특성에 지정 됩니다 `findValue` [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="b8420-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="b8420-115">클라이언트 엔드포인트 구성은 서비스 엔드포인트의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="b8420-116">클라이언트 바인딩은 적절한 보안 모드 및 인증 모드를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="b8420-117">다중 컴퓨터 구성에서 실행할 경우 서비스 엔드포인트 주소를 적절하게 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b8420-118">클라이언트 구현에서는 구성 파일이나 코드를 통해 사용할 인증서를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="b8420-119">다음 샘플에서는 구성 파일에서 사용할 인증서를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b8420-120">다음 샘플에서는 프로그램에서 서비스를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="b8420-121">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b8420-122">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="b8420-123">Message Security 샘플에 포함된 Setup.bat 배치 파일을 사용하면 인증서 기반 보안이 필요한 자체 호스팅 애플리케이션을 실행하도록 관련 인증서가 있는 클라이언트와 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="b8420-124">이 배치 파일을 세 가지 모드로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="b8420-125">단일 컴퓨터 모드에서 실행 하려면 Visual Studio에 대 한 개발자 명령 프롬프트에 setup.exe를 입력 **합니다.** 서비스 모드의 경우 **setup.exe 서비스를 입력 합니다.** 클라이언트 모드의 경우 **setup.exe 클라이언트**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-125">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="b8420-126">다중 컴퓨터 구성에서 샘플을 실행할 경우 클라이언트 및 서버 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="b8420-127">자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8420-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="b8420-128">다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
- <span data-ttu-id="b8420-129">클라이언트 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="b8420-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="b8420-130">배치 파일의 다음 줄에서는 클라이언트 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="b8420-131">지정된 클라이언트 이름은 만든 인증서의 제목 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="b8420-132">인증서는 `My` 저장소 위치에 있는 `CurrentUser` 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="b8420-133">서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="b8420-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="b8420-134">배치 파일의 다음 줄에서는 서버에서 관련된 신뢰 여부를 결정할 수 있도록 서버의 TrustedPeople 저장소에 클라이언트 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="b8420-135">신뢰할 수 있는 사용자 저장소에 설치 된 인증서를 WCF (Windows Communication Foundation) 서비스에서 신뢰할 수 있도록 하려면 클라이언트 인증서 유효성 검사 모드를 또는로 설정 해야 합니다 `PeerOrChainTrust` `PeerTrust` .</span><span class="sxs-lookup"><span data-stu-id="b8420-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="b8420-136">구성 파일을 사용하여 이 작업을 수행하는 방법을 보려면 앞서 소개된 서비스 구성 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b8420-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```  
  
- <span data-ttu-id="b8420-137">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="b8420-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="b8420-138">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="b8420-139">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="b8420-140">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="b8420-141">Setup. .bat 배치 파일이 서비스의 인수 (예: **.bat service**)로 실행 되는 경우% SERVER_NAME%에는 컴퓨터의 정규화 된 도메인 이름이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="b8420-142">그렇지 않은 경우 기본적으로 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-142">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="b8420-143">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="b8420-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="b8420-144">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="b8420-145">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="b8420-146">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="b8420-147">인증서의 프라이빗 키에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="b8420-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="b8420-148">설정 .bat 파일의 다음 줄은 LocalMachine 저장소에 저장 된 서버 인증서를 ASP.NET 작업자 프로세스 계정에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
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
    > <span data-ttu-id="b8420-149">영어가 아닌 Windows 버전을 사용 하는 경우에는 Setup.exe 파일을 편집 하 고 "NT AUTHORITY\NETWORK SERVICE" 계정 이름을 해당 지역으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8420-150">이 배치 파일에서 사용되는 도구는 C:\Program Files\Microsoft Visual Studio 8\Common7\tools 또는 C:\Program Files\Microsoft SDKs\Windows\v6.0\bin에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="b8420-151">이러한 디렉터리 중 하나가 시스템 경로에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="b8420-152">Visual Studio가 설치 된 경우 경로에이 디렉터리를 가져오는 가장 쉬운 방법은 Visual Studio에 대 한 개발자 명령 프롬프트를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="b8420-153">**시작**을 클릭 한 다음 **모든 프로그램**, **Visual Studio 2012**, **도구**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="b8420-154">이 명령 프롬프트에는 이미 구성된 적절한 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="b8420-155">그렇지 않을 경우 해당 디렉터리를 경로에 수동으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b8420-156">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b8420-157">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b8420-157">Check for the following (default) directory before continuing:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b8420-158">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8420-159">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-159">This sample is located in the following directory:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b8420-160">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b8420-160">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b8420-161">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b8420-162">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="b8420-163">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b8420-163">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="b8420-164">관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 샘플 설치 폴더에서 Setup.exe를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-164">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="b8420-165">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b8420-166">설치 .bat 배치 파일은 Visual Studio 용 개발자 명령 프롬프트에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-166">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="b8420-167">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="b8420-168">이 환경 변수는 Visual Studio (2010)에 대 한 개발자 명령 프롬프트 내에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-168">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="b8420-169">주소를 입력 하 여 브라우저를 사용 하 여 서비스에 대 한 액세스를 확인 `http://localhost/servicemodelsamples/service.svc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="b8420-170">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="b8420-171">클라이언트 콘솔 애플리케이션에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-171">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="b8420-172">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8420-172">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="b8420-173">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b8420-173">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="b8420-174">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-174">Create a directory on the service computer.</span></span> <span data-ttu-id="b8420-175">IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="b8420-176">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="b8420-177">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="b8420-178">Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="b8420-179">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="b8420-180">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="b8420-181">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="b8420-182">서버에서 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트에 **설치 .bat 서비스** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-182">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="b8420-183">**Service** 인수를 사용 하 여 **setup.exe** 를 실행 하면 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서가 생성 되 고 서비스 인증서가 이름이 .cer 인 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="b8420-184">`findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 컴퓨터의 정규화 된 도메인 이름과 같은 새 인증서 이름 (의 특성)이 반영 되도록 web.config를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="b8420-185">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="b8420-186">클라이언트에서 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트에서 **setup.exe 클라이언트** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-186">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="b8420-187">**클라이언트** 인수를 사용 하 여 **setup.exe** 를 실행 하면 이름이 client.com 인 클라이언트 인증서가 만들어지고 클라이언트 인증서가 클라이언트 .cer 파일에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="b8420-188">클라이언트 컴퓨터의 Client.exe.config 파일에서 엔드포인트의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="b8420-189">이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="b8420-190">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="b8420-191">클라이언트에서 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트 열고 importservicecert.bat를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-191">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="b8420-192">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="b8420-193">서버에서 관리자 권한으로 Visual Studio에 대 한 개발자 명령 프롬프트 Importclientcert.bat를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-193">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="b8420-194">이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="b8420-195">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="b8420-196">클라이언트와 서비스가 통신할 수 없는 경우 [WCF 샘플에 대 한 문제 해결 팁](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8420-196">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="b8420-197">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="b8420-197">To clean up after the sample</span></span>  
  
- <span data-ttu-id="b8420-198">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b8420-199">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="b8420-200">컴퓨터에서 인증서를 사용 하는 WCF (Windows Communication Foundation) 샘플을 실행 한 경우에는 CurrentUser-비트 사용자 저장소에 설치 된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8420-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="b8420-201">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="b8420-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
