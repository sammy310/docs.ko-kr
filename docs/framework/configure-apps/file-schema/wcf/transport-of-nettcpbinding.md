---
title: <netTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 265b68e058919d1d5c5f1dbcfb1419b57be9aeab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915558"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="d62a6-102">\<netTcpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="d62a6-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="d62a6-103">[ \<NetTcpBinding >](nettcpbinding.md)로 구성 된 끝점의 메시지 수준 보안 요구 사항 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="d62a6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d62a6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d62a6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d62a6-105">\<bindings></span></span>  
<span data-ttu-id="d62a6-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d62a6-106">\<netTcpBinding></span></span>  
<span data-ttu-id="d62a6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d62a6-107">\<binding></span></span>  
<span data-ttu-id="d62a6-108">\<security></span><span class="sxs-lookup"><span data-stu-id="d62a6-108">\<security></span></span>  
<span data-ttu-id="d62a6-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="d62a6-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d62a6-110">구문</span><span class="sxs-lookup"><span data-stu-id="d62a6-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d62a6-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d62a6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d62a6-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d62a6-113">특성</span><span class="sxs-lookup"><span data-stu-id="d62a6-113">Attributes</span></span>  
  
|<span data-ttu-id="d62a6-114">특성</span><span class="sxs-lookup"><span data-stu-id="d62a6-114">Attribute</span></span>|<span data-ttu-id="d62a6-115">Description</span><span class="sxs-lookup"><span data-stu-id="d62a6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d62a6-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d62a6-116">clientCredentialType</span></span>|<span data-ttu-id="d62a6-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-117">Optional.</span></span> <span data-ttu-id="d62a6-118">전송 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="d62a6-119">-기본값 `Windows`은입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="d62a6-120">-이 특성은 형식 <xref:System.ServiceModel.TcpClientCredentialType>입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="d62a6-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="d62a6-121">protectionLevel</span></span>|<span data-ttu-id="d62a6-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-122">Optional.</span></span> <span data-ttu-id="d62a6-123">TCP 전송의 수준에 보안을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="d62a6-124">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="d62a6-125">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="d62a6-126">기본값은 `EncryptAndSign`입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="d62a6-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="d62a6-127">sslProtocols</span></span>|<span data-ttu-id="d62a6-128">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="d62a6-129">기본값은 Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="d62a6-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="d62a6-130">policyEnforcement</span></span>|<span data-ttu-id="d62a6-131">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="d62a6-132">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="d62a6-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="d62a6-133">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="d62a6-134">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="d62a6-135">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d62a6-136">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="d62a6-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d62a6-137">값</span><span class="sxs-lookup"><span data-stu-id="d62a6-137">Value</span></span>|<span data-ttu-id="d62a6-138">설명</span><span class="sxs-lookup"><span data-stu-id="d62a6-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d62a6-139">없음</span><span class="sxs-lookup"><span data-stu-id="d62a6-139">None</span></span>|<span data-ttu-id="d62a6-140">클라이언트는 익명입니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-140">The client is anonymous.</span></span> <span data-ttu-id="d62a6-141">여기에는 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="d62a6-142">Windows</span><span class="sxs-lookup"><span data-stu-id="d62a6-142">Windows</span></span>|<span data-ttu-id="d62a6-143">SP 협상(Kerberos 협상)을 사용하는 클라이언트의 Windows 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="d62a6-144">Certificate</span><span class="sxs-lookup"><span data-stu-id="d62a6-144">Certificate</span></span>|<span data-ttu-id="d62a6-145">클라이언트는 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="d62a6-146">클라이언트에서는 SSL 협상을 사용하며 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="d62a6-147">protectionLevel 특성</span><span class="sxs-lookup"><span data-stu-id="d62a6-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="d62a6-148">값</span><span class="sxs-lookup"><span data-stu-id="d62a6-148">Value</span></span>|<span data-ttu-id="d62a6-149">설명</span><span class="sxs-lookup"><span data-stu-id="d62a6-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d62a6-150">없음</span><span class="sxs-lookup"><span data-stu-id="d62a6-150">None</span></span>|<span data-ttu-id="d62a6-151">보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-151">No protection.</span></span>|  
|<span data-ttu-id="d62a6-152">Sign</span><span class="sxs-lookup"><span data-stu-id="d62a6-152">Sign</span></span>|<span data-ttu-id="d62a6-153">메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-153">Messages are signed.</span></span>|  
|<span data-ttu-id="d62a6-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="d62a6-154">EncryptAndSign</span></span>|<span data-ttu-id="d62a6-155">-메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d62a6-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d62a6-156">Child Elements</span></span>  
 <span data-ttu-id="d62a6-157">없음</span><span class="sxs-lookup"><span data-stu-id="d62a6-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d62a6-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d62a6-158">Parent Elements</span></span>  
  
|<span data-ttu-id="d62a6-159">요소</span><span class="sxs-lookup"><span data-stu-id="d62a6-159">Element</span></span>|<span data-ttu-id="d62a6-160">설명</span><span class="sxs-lookup"><span data-stu-id="d62a6-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d62a6-161">\<security></span><span class="sxs-lookup"><span data-stu-id="d62a6-161">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="d62a6-162">[ \<NetTcpBinding >](nettcpbinding.md)의 보안 기능을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-162">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d62a6-163">설명</span><span class="sxs-lookup"><span data-stu-id="d62a6-163">Remarks</span></span>  
 <span data-ttu-id="d62a6-164">SOAP 메시지의 무결성 및 기밀성과 상호 인증을 위해 전송 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="d62a6-165">바인딩에서 이 보안 모드를 선택하면 보안 전송을 사용하여 채널 스택이 구성되고 Windows(협상) 또는 SSL over TCP 같은 전송 보안을 사용하여 SOAP 메시지가 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="d62a6-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62a6-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="d62a6-166">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="d62a6-167">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d62a6-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d62a6-168">바인딩</span><span class="sxs-lookup"><span data-stu-id="d62a6-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d62a6-169">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d62a6-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d62a6-170">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d62a6-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d62a6-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="d62a6-171">\<binding></span></span>](../../../misc/binding.md)
