---
title: '방법: 채널 보안 자격 증명 지정'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 9236985ef461044e480847003d9d249b7e232783
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266768"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="a0d69-102">방법: 채널 보안 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="a0d69-102">How to: Specify Channel Security Credentials</span></span>

<span data-ttu-id="a0d69-103">WCF (Windows Communication Foundation) 서비스 모니커를 사용 하면 COM 응용 프로그램에서 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="a0d69-104">대부분의 WCF 서비스에서는 클라이언트에서 인증 및 권한 부여에 대 한 자격 증명을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="a0d69-105">WCF 클라이언트에서 WCF 서비스를 호출 하는 경우 관리 코드 또는 응용 프로그램 구성 파일에서 이러한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="a0d69-106">COM 응용 프로그램에서 WCF 서비스를 호출 하는 경우 인터페이스를 사용 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 하 여 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="a0d69-107">이 항목에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 인터페이스를 사용하여 자격 증명을 지정하는 다양한 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0d69-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials>는 IDispatch 기반 인터페이스이며 Visual Studio 환경에서는 IntelliSense 기능을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="a0d69-109">이 문서에서는 [메시지 보안 샘플](../samples/message-security-sample.md)에 정의 된 WCF 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-109">This article will use the WCF service defined in the [Message Security Sample](../samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="a0d69-110">클라이언트 인증서 지정</span><span class="sxs-lookup"><span data-stu-id="a0d69-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="a0d69-111">Message Security 디렉터리에서 Setup.bat 파일을 실행하여 필요한 테스트 인증서를 만든 후 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="a0d69-112">메시지 보안 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="a0d69-113">`[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]`인터페이스 정의에를 추가 `ICalculator` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="a0d69-114">`bindingNamespace="http://Microsoft.ServiceModel.Samples"`서비스에 대 한 App.config의 끝점 태그에를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="a0d69-115">메시지 보안 샘플을 빌드하고 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="a0d69-116">Internet Explorer를 사용 하 여 서비스의 URI ()로 이동 `http://localhost:8000/ServiceModelSamples/Service` 하 여 서비스가 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-116">Use Internet Explorer and browse to the service's URI (`http://localhost:8000/ServiceModelSamples/Service`) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="a0d69-117">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="a0d69-118">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. <span data-ttu-id="a0d69-119">Visual Basic 애플리케이션을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="a0d69-120">Visual Basic 애플리케이션에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="a0d69-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> 또는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29>을 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> 대신 사용하여 클라이언트 인증서를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> <span data-ttu-id="a0d69-122">이 호출이 작동하려면 클라이언트가 실행 중인 컴퓨터에서 클라이언트 인증서가 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0d69-123">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="a0d69-124">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a0d69-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="a0d69-125">사용자 이름 및 암호 지정</span><span class="sxs-lookup"><span data-stu-id="a0d69-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="a0d69-126">`wsHttpBinding`을 사용하도록 Service App.config 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="a0d69-127">이 때 사용자 이름과 암호를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="a0d69-128">`clientCredentialType`을 UserName으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="a0d69-129">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="a0d69-130">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="a0d69-131">Visual Basic 애플리케이션을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="a0d69-132">Visual Basic 애플리케이션에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a0d69-133">이 샘플의 서비스 모니커에 지정된 바인딩이 WSHttpBinding_ICalculator로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="a0d69-134">또한 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>을 호출할 때 유효한 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="a0d69-135">Windows 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="a0d69-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="a0d69-136">Service App.config 파일에서 `clientCredentialType`을 Windows로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="a0d69-137">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="a0d69-138">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="a0d69-139">Visual Basic 애플리케이션을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="a0d69-140">Visual Basic 애플리케이션에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a0d69-141">"domain", "userID" 및 "password"를 유효한 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="a0d69-142">발급 토큰 지정</span><span class="sxs-lookup"><span data-stu-id="a0d69-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="a0d69-143">발급 토큰은 페더레이션 보안을 사용하는 애플리케이션에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="a0d69-144">페더레이션된 보안에 대 한 자세한 내용은 [페더레이션 및 발급 된 토큰](federation-and-issued-tokens.md) 및 [페더레이션 샘플](../samples/federation-sample.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0d69-144">For more information about federated security, see [Federation and Issued Tokens](federation-and-issued-tokens.md) and [Federation Sample](../samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="a0d69-145">다음 Visual Basic 코드 예제에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0d69-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="a0d69-146">이 메서드의 매개 변수에 대한 자세한 내용은 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0d69-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d69-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0d69-147">See also</span></span>

- [<span data-ttu-id="a0d69-148">페더레이션</span><span class="sxs-lookup"><span data-stu-id="a0d69-148">Federation</span></span>](federation.md)
- [<span data-ttu-id="a0d69-149">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="a0d69-149">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="a0d69-150">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="a0d69-150">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="a0d69-151">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="a0d69-151">Message Security</span></span>](message-security-in-wcf.md)
- [<span data-ttu-id="a0d69-152">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="a0d69-152">Bindings and Security</span></span>](bindings-and-security.md)
