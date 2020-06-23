---
title: '방법: 전송 보안 및 메시지 자격 증명 사용'
description: WCF에서 전송 및 메시지 보안 모드를 제공 하는 메시지 자격 증명을 사용 하 여 전송 보안을 구현 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f632a4389eafc155cedcae94707c9418b6696f2c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246651"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="ce21c-103">방법: 전송 보안 및 메시지 자격 증명 사용</span><span class="sxs-lookup"><span data-stu-id="ce21c-103">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="ce21c-104">전송 및 메시지 자격 증명을 모두 사용 하 여 서비스를 보호 하는 것은 Windows Communication Foundation (WCF)에서 전송 및 메시지 보안 모드를 모두 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-104">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="ce21c-105">요컨대, 전송 계층 보안은 무결성과 기밀성을 제공하고, 메시지 계층 보안은 엄격한 전송 보안 메커니즘에서는 제공되지 않는 다양한 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-105">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="ce21c-106">이 항목에서는 <xref:System.ServiceModel.WSHttpBinding> 및 <xref:System.ServiceModel.NetTcpBinding> 바인딩을 사용하여 메시지 자격 증명을 통해 전송을 구현하는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-106">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="ce21c-107">보안 모드를 설정 하는 방법에 대 한 자세한 내용은 [방법: 보안 모드 설정](../how-to-set-the-security-mode.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce21c-107">For more information about setting the security mode, see [How to: Set the Security Mode](../how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="ce21c-108">보안 모드를 `TransportWithMessageCredential`로 설정하면 전송에서 전송 수준 보안을 제공하는 실제 메커니즘을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-108">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="ce21c-109">HTTP의 경우 메커니즘이 HTTPS(HTTP를 통한 SSL(Secure Sockets Layer))이고, TCP의 경우 TCP 또는 Windows를 통한 SSL입니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-109">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="ce21c-110">전송이 HTTP(<xref:System.ServiceModel.WSHttpBinding> 사용)인 경우 HTTP를 통한 SSL 전송 수준 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-110">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="ce21c-111">이 경우 이 항목의 뒷부분에 설명된 것처럼 포트에 바인딩된 SSL 인증서를 사용하여 서비스를 호스팅하는 컴퓨터를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-111">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="ce21c-112">전송이 TCP(<xref:System.ServiceModel.NetTcpBinding> 사용)인 경우 기본적으로 Windows 보안 또는 TCP를 통한 SSL 전송 수준 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-112">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="ce21c-113">TCP를 통한 SSL을 사용할 경우 이 항목의 뒷부분에 설명된 것처럼 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> 메서드를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-113">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="ce21c-114">전송 보안에 대해 인증서와 함께 WSHttpBinding을 사용하려면(코드)</span><span class="sxs-lookup"><span data-stu-id="ce21c-114">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="ce21c-115">HttpCfg.exe 도구를 사용하여 시스템의 포트에 SSL 인증서를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-115">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="ce21c-116">자세한 내용은 [방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce21c-116">For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="ce21c-117"><xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만들고 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 속성을 <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-117">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="ce21c-118"><xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-118">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="ce21c-119">(자세한 내용은 [자격 증명 유형 선택](selecting-a-credential-type.md)을 참조 하세요.) 다음 코드에서는 값을 사용 합니다 <xref:System.ServiceModel.MessageCredentialType.Certificate> .</span><span class="sxs-lookup"><span data-stu-id="ce21c-119">(For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="ce21c-120">적절한 기본 주소를 사용하여 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-120">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="ce21c-121">주소에서는 "HTTPS" 스키마를 사용하고 시스템의 실제 이름과 SSL 인증서가 바인딩되는 포트 번호를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-121">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="ce21c-122">또는 구성에서 기본 주소를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-122">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="ce21c-123">ph x="1" /&gt; 메서드를 사용하여 서비스 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-123">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="ce21c-124">다음 코드에 표시된 것처럼 <xref:System.ServiceModel.ServiceHost> 인스턴스를 만들고 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-124">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="ce21c-125">전송 보안에 대해 인증서와 함께 NetTcpBinding을 사용하려면(코드)</span><span class="sxs-lookup"><span data-stu-id="ce21c-125">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="ce21c-126"><xref:System.ServiceModel.NetTcpBinding> 클래스의 인스턴스를 만들고 <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> 속성을 <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-126">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="ce21c-127"><xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-127">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="ce21c-128">다음 코드에서는 <xref:System.ServiceModel.MessageCredentialType.Certificate> 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-128">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="ce21c-129">적절한 기본 주소를 사용하여 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-129">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="ce21c-130">주소에서 "net.tcp" 스키마를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-130">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="ce21c-131">또는 구성에서 기본 주소를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-131">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="ce21c-132"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-132">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="ce21c-133"><xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> 메서드를 사용하여 서비스에 대한 X.509 인증서를 명시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-133">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="ce21c-134">ph x="1" /&gt; 메서드를 사용하여 서비스 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-134">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="ce21c-135">다음 코드와 같이 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-135">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="ce21c-136">전송 보안에 대해 Windows와 함께 NetTcpBinding을 사용하려면(코드)</span><span class="sxs-lookup"><span data-stu-id="ce21c-136">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="ce21c-137"><xref:System.ServiceModel.NetTcpBinding> 클래스의 인스턴스를 만들고 <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> 속성을 <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-137">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="ce21c-138"><xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A>을 <xref:System.ServiceModel.TcpClientCredentialType.Windows>로 설정하여 Windows를 사용하도록 전송 보안을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-138">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="ce21c-139">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-139">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="ce21c-140"><xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-140">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="ce21c-141">다음 코드에서는 <xref:System.ServiceModel.MessageCredentialType.Certificate> 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-141">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="ce21c-142">적절한 기본 주소를 사용하여 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-142">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="ce21c-143">주소에서 "net.tcp" 스키마를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-143">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="ce21c-144">또는 구성에서 기본 주소를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-144">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="ce21c-145"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-145">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="ce21c-146"><xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> 메서드를 사용하여 서비스에 대한 X.509 인증서를 명시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-146">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="ce21c-147">ph x="1" /&gt; 메서드를 사용하여 서비스 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-147">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="ce21c-148">다음 코드와 같이 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-148">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="ce21c-149">구성 사용</span><span class="sxs-lookup"><span data-stu-id="ce21c-149">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="ce21c-150">WSHttpBinding을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ce21c-150">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="ce21c-151">포트에 바인딩된 SSL 인증서를 사용하여 컴퓨터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-151">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="ce21c-152">자세한 내용은 [방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce21c-152">(For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="ce21c-153">`transport`이 구성을 사용 하 여 <> 요소 값을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-153">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="ce21c-154">메시지 수준 보안에 대한 클라이언트 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-154">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="ce21c-155">다음 예에서는 `clientCredentialType` <`message`> 요소의 특성을로 설정 합니다 `UserName` .</span><span class="sxs-lookup"><span data-stu-id="ce21c-155">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="ce21c-156">전송 보안에 대해 인증서와 함께 NetTcpBinding을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ce21c-156">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="ce21c-157">TCP를 통한 SSL의 경우 `<behaviors>` 요소에서 인증서를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-157">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="ce21c-158">다음 예제에서는 기본 저장소 위치(로컬 컴퓨터 및 개인 저장소)에서 해당 발급자별로 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-158">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="ce21c-159">[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)바인딩 섹션에를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-159">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="ce21c-160">바인딩 요소를 추가하고 `name` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-160">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="ce21c-161"><> 요소를 추가 하 `security` 고 특성을 `mode` 로 설정 `TransportWithMessageCredential` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-161">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="ce21c-162"><요소를 추가 하 `message>` 고 특성을 `clientCredentialType` 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-162">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="ce21c-163">전송 보안에 대해 Windows와 함께 NetTcpBinding을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ce21c-163">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="ce21c-164">를 [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) 바인딩 섹션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-164">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="ce21c-165"><`binding`> 요소를 추가 하 고 `name` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-165">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="ce21c-166"><> 요소를 추가 하 `security` 고 특성을 `mode` 로 설정 `TransportWithMessageCredential` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-166">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="ce21c-167"><> 요소를 추가 하 `transport` 고 `clientCredentialType` 특성을로 설정 `Windows` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-167">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="ce21c-168"><`message`> 요소를 추가 하 고 `clientCredentialType` 특성을 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-168">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="ce21c-169">다음 코드에서는 값을 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce21c-169">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ce21c-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce21c-170">See also</span></span>

- [<span data-ttu-id="ce21c-171">방법: 보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="ce21c-171">How to: Set the Security Mode</span></span>](../how-to-set-the-security-mode.md)
- [<span data-ttu-id="ce21c-172">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ce21c-172">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="ce21c-173">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ce21c-173">Securing Services and Clients</span></span>](securing-services-and-clients.md)
