---
title: WCF 보안 프로그래밍
description: 인증, 기밀성 및 무결성을 포함 하 여 보안 WCF 응용 프로그램을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: 8e77c667dd8904c10bbab88e1413690677cef53b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244987"
---
# <a name="programming-wcf-security"></a><span data-ttu-id="7f2ba-103">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7f2ba-103">Programming WCF Security</span></span>
<span data-ttu-id="7f2ba-104">이 항목에서는 WCF (보안 Windows Communication Foundation) 응용 프로그램을 만드는 데 사용 되는 기본 프로그래밍 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-104">This topic describes the fundamental programming tasks used to create a secure Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="7f2ba-105">이 항목에서는 *전송 보안*이라는 인증, 기밀성 및 무결성만 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-105">This topic covers only authentication, confidentiality, and integrity, collectively known as *transfer security*.</span></span> <span data-ttu-id="7f2ba-106">이 항목에서는 권한 부여 (리소스 또는 서비스에 대 한 액세스 제어)에 대해 다루지 않습니다. 권한 부여에 대 한 자세한 내용은 [권한 부여](authorization-in-wcf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-106">This topic does not cover authorization (the control of access to resources or services); for information on authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f2ba-107">특히 WCF와 관련 하 여 보안 개념에 대 한 유용한 정보를 보려면 MSDN의 패턴 및 사례 자습서 (영문)의 [시나리오, 패턴 및 구현 지침 (WSE) 3.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648183(v=pandp.10))을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-107">For a valuable introduction to security concepts, especially in regard to WCF, see the set of patterns and practices tutorials on MSDN at [Scenarios, Patterns, and Implementation Guidance for Web Services Enhancements (WSE) 3.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648183(v=pandp.10)).</span></span>  
  
 <span data-ttu-id="7f2ba-108">WCF 보안 프로그래밍은 보안 모드, 클라이언트 자격 증명 형식 및 자격 증명 값을 설정 하는 세 가지 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-108">Programming WCF security is based on three steps setting the following: the security mode, a client credential type, and the credential values.</span></span> <span data-ttu-id="7f2ba-109">코드 또는 구성을 통해 이러한 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-109">You can perform these steps either through code or configuration.</span></span>  
  
## <a name="setting-the-security-mode"></a><span data-ttu-id="7f2ba-110">보안 모드 설정</span><span class="sxs-lookup"><span data-stu-id="7f2ba-110">Setting the Security Mode</span></span>  
 <span data-ttu-id="7f2ba-111">다음은 WCF에서 보안 모드를 사용 하 여 프로그래밍 하는 일반적인 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-111">The following explains the general steps for programming with the security mode in WCF:</span></span>  
  
1. <span data-ttu-id="7f2ba-112">애플리케이션 요구 사항에 적합한 미리 정의된 바인딩 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-112">Select one of the predefined bindings appropriate to your application requirements.</span></span> <span data-ttu-id="7f2ba-113">바인딩 선택 목록에 대해서는 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-113">For a list of the binding choices, see [System-Provided Bindings](../system-provided-bindings.md).</span></span> <span data-ttu-id="7f2ba-114">기본적으로 거의 모든 바인딩에서 보안을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-114">By default, nearly every binding has security enabled.</span></span> <span data-ttu-id="7f2ba-115">한 가지 예외는 <xref:System.ServiceModel.BasicHttpBinding> 클래스 (구성 사용,)입니다 [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7f2ba-115">The one exception is the <xref:System.ServiceModel.BasicHttpBinding> class (using configuration, the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)).</span></span>  
  
     <span data-ttu-id="7f2ba-116">선택한 바인딩에 따라 전송이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-116">The binding you select determines the transport.</span></span> <span data-ttu-id="7f2ba-117">예를 들어, <xref:System.ServiceModel.WSHttpBinding>에서는 HTTP를 전송으로 사용하고 <xref:System.ServiceModel.NetTcpBinding>에서는 TCP를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-117">For example, <xref:System.ServiceModel.WSHttpBinding> uses HTTP as the transport; <xref:System.ServiceModel.NetTcpBinding> uses TCP.</span></span>  
  
2. <span data-ttu-id="7f2ba-118">바인딩에 대한 보안 모드 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-118">Select one of the security modes for the binding.</span></span> <span data-ttu-id="7f2ba-119">선택한 바인딩에 따라 사용 가능한 모드 선택 사항이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-119">Note that the binding you select determines the available mode choices.</span></span> <span data-ttu-id="7f2ba-120">예를 들어, <xref:System.ServiceModel.WSDualHttpBinding>에서는 전송 보안을 허용하지 않으므로, 전송 보안은 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-120">For example, the <xref:System.ServiceModel.WSDualHttpBinding> does not allow transport security (it is not an option).</span></span> <span data-ttu-id="7f2ba-121">마찬가지로 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>과 <xref:System.ServiceModel.NetNamedPipeBinding>에서는 모두 메시지 보안을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-121">Similarly, neither the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> nor the <xref:System.ServiceModel.NetNamedPipeBinding> allows message security.</span></span>  
  
     <span data-ttu-id="7f2ba-122">다음과 같은 세 가지 선택 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-122">You have three choices:</span></span>  
  
    1. `Transport`  
  
         <span data-ttu-id="7f2ba-123">전송 보안은 선택한 바인딩에서 사용하는 메커니즘에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-123">Transport security depends on the mechanism that the binding you have selected uses.</span></span> <span data-ttu-id="7f2ba-124">예를 들어, `WSHttpBinding`을 사용하는 경우 보안 메커니즘은 SSL(Secure Sockets Layer)(또한 HTTPS에 대한 메커니즘)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-124">For example, if you are using `WSHttpBinding` then the security mechanism is Secure Sockets Layer (SSL) (also the mechanism for the HTTPS protocol).</span></span> <span data-ttu-id="7f2ba-125">일반적으로 전송 보안의 주요 이점은 사용 중인 전송에 관계 없이 처리 능력이 우수하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-125">Generally speaking, the main advantage of transport security is that it delivers good throughput no matter which transport you are using.</span></span> <span data-ttu-id="7f2ba-126">그러나 두 가지 제한이 있습니다. 첫째, 전송 메커니즘이 사용자를 인증하는 데 사용되는 자격 증명 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-126">However, it does have two limitations: The first is that the transport mechanism dictates the credential type used to authenticate a user.</span></span> <span data-ttu-id="7f2ba-127">이는 서비스가 다른 형식의 자격 증명을 요구하는 다른 서비스와 상호 작용해야 하는 경우에만 단점이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-127">This is a drawback only if a service needs to interoperate with other services that demand different types of credentials.</span></span> <span data-ttu-id="7f2ba-128">둘째는 메시지 수준에서 보안이 적용되지 않기 때문에 엔드투엔드 방식 대신 hop-by-hop 방식으로 보안이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-128">The second is that, because the security is not applied at the message level, security is implemented in a hop-by-hop manner rather than end-to-end.</span></span> <span data-ttu-id="7f2ba-129">이 제한은 클라이언트와 서비스 사이의 메시지 경로에 매개자가 포함되어 있는 경우에만 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-129">This latter limitation is an issue only if the message path between client and service includes intermediaries.</span></span> <span data-ttu-id="7f2ba-130">사용할 전송에 대 한 자세한 내용은 [전송 선택](choosing-a-transport.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-130">For more information about which transport to use, see [Choosing a Transport](choosing-a-transport.md).</span></span> <span data-ttu-id="7f2ba-131">전송 보안을 사용 하는 방법에 대 한 자세한 내용은 [전송 보안 개요](transport-security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-131">For more information about using transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>  
  
    2. `Message`  
  
         <span data-ttu-id="7f2ba-132">메시지 보안은 모든 메시지에 메시지를 보안된 상태로 유지하는 데 필요한 헤더와 데이터가 포함되어 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-132">Message security means that every message includes the necessary headers and data to keep the message secure.</span></span> <span data-ttu-id="7f2ba-133">헤더의 구성이 다양하므로 여러 자격 증명을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-133">Because the composition of the headers varies, you can include any number of credentials.</span></span> <span data-ttu-id="7f2ba-134">이는 전송 메커니즘이 제공할 수 없는 특정 자격 증명 형식을 요구하는 다른 서비스와 상호 작용할 경우나 서비스마다 다른 자격 증명 형식을 요구하는 여러 서비스에서 메시지를 사용해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-134">This becomes a factor if you are interoperating with other services that demand a specific credential type that a transport mechanism can't supply, or if the message must be used with more than one service, where each service demands a different credential type.</span></span>  
  
         <span data-ttu-id="7f2ba-135">자세한 내용은 [메시지 보안](message-security-in-wcf.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-135">For more information, see [Message Security](message-security-in-wcf.md).</span></span>  
  
    3. `TransportWithMessageCredential`  
  
         <span data-ttu-id="7f2ba-136">이 선택 옵션에서는 전송 계층을 사용하여 메시지 전송을 보안하지만, 모든 메시지에 다른 서비스에 필요한 풍부한 자격 증명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-136">This choice uses the transport layer to secure the message transfer, while every message includes the rich credentials other services need.</span></span> <span data-ttu-id="7f2ba-137">이 옵션은 전송 보안의 성능 이점과 메시지 보안의 풍부한 자격 증명 이점을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-137">This combines the performance advantage of transport security with the rich credentials advantage of message security.</span></span> <span data-ttu-id="7f2ba-138"><xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> 및 <xref:System.ServiceModel.WSHttpBinding> 바인딩에서 이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-138">This is available with the following bindings: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding>, and <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3. <span data-ttu-id="7f2ba-139">HTTP(HTTPS)에 대해 전송 보안을 사용하려면 SSL 인증서를 사용하여 호스트를 구성하고 포트에서 SSL을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-139">If you decide to use transport security for HTTP (in other words, HTTPS), you must also configure the host with an SSL certificate and enable SSL on a port.</span></span> <span data-ttu-id="7f2ba-140">자세한 내용은 [HTTP 전송 보안](http-transport-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-140">For more information, see [HTTP Transport Security](http-transport-security.md).</span></span>  
  
4. <span data-ttu-id="7f2ba-141"><xref:System.ServiceModel.WSHttpBinding>을 사용하고 보안 세션을 설정할 필요가 없는 경우 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-141">If you are using the <xref:System.ServiceModel.WSHttpBinding> and do not need to establish a secure session, set the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="7f2ba-142">클라이언트와 서비스에서 대칭 키를 사용하여 채널을 만들 때(클라이언트와 서버가 대화 상자가 닫힐 때까지 대화 기간 동안 동일한 키를 사용), 보안 세션이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-142">A secure session occurs when a client and service create a channel using a symmetric key (both client and server use the same key for the length of a conversation, until the dialog is closed).</span></span>  
  
## <a name="setting-the-client-credential-type"></a><span data-ttu-id="7f2ba-143">클라이언트 자격 증명 형식 설정</span><span class="sxs-lookup"><span data-stu-id="7f2ba-143">Setting the Client Credential Type</span></span>  
 <span data-ttu-id="7f2ba-144">클라이언트 자격 증명 형식을 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-144">Select a client credential type as appropriate.</span></span> <span data-ttu-id="7f2ba-145">자세한 내용은 [자격 증명 유형 선택](selecting-a-credential-type.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-145">For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).</span></span> <span data-ttu-id="7f2ba-146">다음과 같은 클라이언트 자격 증명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-146">The following client credential types are available:</span></span>  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 <span data-ttu-id="7f2ba-147">모드 설정 방법에 따라 자격 증명 형식을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-147">Depending on how you set the mode, you must set the credential type.</span></span> <span data-ttu-id="7f2ba-148">다음 구성 예제에 표시된 것처럼 `wsHttpBinding`을 선택하고 모드를 "Message"로 설정한 경우 메시지 요소의 `clientCredentialType` 특성 값을 `None`, `Windows`, `UserName`, `Certificate`, `IssuedToken` 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-148">For example, if you have selected the `wsHttpBinding`, and have set the mode to "Message," then you can also set the `clientCredentialType` attribute of the Message element to one of the following values: `None`, `Windows`, `UserName`, `Certificate`, and `IssuedToken`, as shown in the following configuration example.</span></span>  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>
  </wsHttpBinding>
</bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="7f2ba-149">코드</span><span class="sxs-lookup"><span data-stu-id="7f2ba-149">Or in code:</span></span>  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a><span data-ttu-id="7f2ba-150">서비스 자격 증명 값 설정</span><span class="sxs-lookup"><span data-stu-id="7f2ba-150">Setting Service Credential Values</span></span>  
 <span data-ttu-id="7f2ba-151">클라이언트 자격 증명 형식을 선택한 경우 사용할 서비스 및 클라이언트에 대한 실제 자격 증명을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-151">Once you select a client credential type, you must set the actual credentials for the service and client to use.</span></span> <span data-ttu-id="7f2ba-152">서비스에서 자격 증명은 <xref:System.ServiceModel.Description.ServiceCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 클래스의 <xref:System.ServiceModel.ServiceHostBase> 속성에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-152">On the service, credentials are set using the <xref:System.ServiceModel.Description.ServiceCredentials> class and returned by the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property of the <xref:System.ServiceModel.ServiceHostBase> class.</span></span> <span data-ttu-id="7f2ba-153">사용 중인 바인딩은 서비스 자격 증명 형식, 선택한 보안 모드 및 클라이언트 자격 증명 형식을 함축합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-153">The binding in use implies the service credential type, the security mode chosen, and the type of the client credential.</span></span> <span data-ttu-id="7f2ba-154">다음 코드에서는 서비스 자격 증명에 대한 인증서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-154">The following code sets a certificate for a service credential.</span></span>  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a><span data-ttu-id="7f2ba-155">클라이언트 자격 증명 값 설정</span><span class="sxs-lookup"><span data-stu-id="7f2ba-155">Setting Client Credential Values</span></span>  
 <span data-ttu-id="7f2ba-156">클라이언트에서 클라이언트 자격 증명 값은 <xref:System.ServiceModel.Description.ClientCredentials> 클래스를 사용하여 설정하고 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-156">On the client, set client credential values using the <xref:System.ServiceModel.Description.ClientCredentials> class and returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="7f2ba-157">다음 코드에서는 TCP 프로토콜을 사용하여 인증서를 클라이언트에 대한 자격 증명으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f2ba-157">The following code sets a certificate as a credential on a client using the TCP protocol.</span></span>  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7f2ba-158">참조</span><span class="sxs-lookup"><span data-stu-id="7f2ba-158">See also</span></span>

- [<span data-ttu-id="7f2ba-159">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7f2ba-159">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- [<span data-ttu-id="7f2ba-160">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="7f2ba-160">Common Security Scenarios</span></span>](common-security-scenarios.md)
