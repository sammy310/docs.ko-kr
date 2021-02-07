---
description: '다음에 대 한 자세한 정보:: <transport><netTcpBinding>'
title: <netTcpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 9005de300b41c9f53c62875ee185d0f8a3ee8d7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664550"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="9bf5e-103">\<netTcpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="9bf5e-103">\<transport> of \<netTcpBinding></span></span>

<span data-ttu-id="9bf5e-104">로 구성 된 끝점의 메시지 수준 보안 요구 사항 형식을 정의 합니다 [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9bf5e-104">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="9bf5e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9bf5e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bf5e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9bf5e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9bf5e-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bf5e-108">특성</span><span class="sxs-lookup"><span data-stu-id="9bf5e-108">Attributes</span></span>  
  
|<span data-ttu-id="9bf5e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="9bf5e-109">Attribute</span></span>|<span data-ttu-id="9bf5e-110">설명</span><span class="sxs-lookup"><span data-stu-id="9bf5e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bf5e-111">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9bf5e-111">clientCredentialType</span></span>|<span data-ttu-id="9bf5e-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-112">Optional.</span></span> <span data-ttu-id="9bf5e-113">전송 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-113">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="9bf5e-114">-기본값은 `Windows` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-114">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="9bf5e-115">-이 특성은 형식입니다 <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="9bf5e-115">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="9bf5e-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9bf5e-116">protectionLevel</span></span>|<span data-ttu-id="9bf5e-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-117">Optional.</span></span> <span data-ttu-id="9bf5e-118">TCP 전송의 수준에 보안을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-118">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="9bf5e-119">메시지에 서명하면 전송 중인 메시지를 제3자가 손상할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9bf5e-120">암호화는 전송 중에 데이터 수준에서 개인 정보를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-120">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="9bf5e-121">기본값은 `EncryptAndSign`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-121">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="9bf5e-122">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="9bf5e-122">sslProtocols</span></span>|<span data-ttu-id="9bf5e-123">지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-123">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="9bf5e-124">기본값은 Tls&#124;Tls11&#124;Tls12입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-124">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="9bf5e-125">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="9bf5e-125">policyEnforcement</span></span>|<span data-ttu-id="9bf5e-126">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9bf5e-127">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="9bf5e-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9bf5e-128">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9bf5e-129">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9bf5e-130">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9bf5e-131">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="9bf5e-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9bf5e-132">값</span><span class="sxs-lookup"><span data-stu-id="9bf5e-132">Value</span></span>|<span data-ttu-id="9bf5e-133">설명</span><span class="sxs-lookup"><span data-stu-id="9bf5e-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9bf5e-134">없음</span><span class="sxs-lookup"><span data-stu-id="9bf5e-134">None</span></span>|<span data-ttu-id="9bf5e-135">클라이언트는 익명입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-135">The client is anonymous.</span></span> <span data-ttu-id="9bf5e-136">여기에는 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-136">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="9bf5e-137">Windows</span><span class="sxs-lookup"><span data-stu-id="9bf5e-137">Windows</span></span>|<span data-ttu-id="9bf5e-138">SP 협상(Kerberos 협상)을 사용하는 클라이언트의 Windows 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-138">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="9bf5e-139">인증서</span><span class="sxs-lookup"><span data-stu-id="9bf5e-139">Certificate</span></span>|<span data-ttu-id="9bf5e-140">클라이언트는 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-140">The client is authenticated using a certificate.</span></span> <span data-ttu-id="9bf5e-141">클라이언트에서는 SSL 협상을 사용하며 서비스 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-141">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="9bf5e-142">protectionLevel 특성</span><span class="sxs-lookup"><span data-stu-id="9bf5e-142">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="9bf5e-143">값</span><span class="sxs-lookup"><span data-stu-id="9bf5e-143">Value</span></span>|<span data-ttu-id="9bf5e-144">설명</span><span class="sxs-lookup"><span data-stu-id="9bf5e-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9bf5e-145">없음</span><span class="sxs-lookup"><span data-stu-id="9bf5e-145">None</span></span>|<span data-ttu-id="9bf5e-146">보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-146">No protection.</span></span>|  
|<span data-ttu-id="9bf5e-147">Sign</span><span class="sxs-lookup"><span data-stu-id="9bf5e-147">Sign</span></span>|<span data-ttu-id="9bf5e-148">메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-148">Messages are signed.</span></span>|  
|<span data-ttu-id="9bf5e-149">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="9bf5e-149">EncryptAndSign</span></span>|<span data-ttu-id="9bf5e-150">-메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-150">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bf5e-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9bf5e-151">Child Elements</span></span>  

 <span data-ttu-id="9bf5e-152">없음</span><span class="sxs-lookup"><span data-stu-id="9bf5e-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9bf5e-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9bf5e-153">Parent Elements</span></span>  
  
|<span data-ttu-id="9bf5e-154">요소</span><span class="sxs-lookup"><span data-stu-id="9bf5e-154">Element</span></span>|<span data-ttu-id="9bf5e-155">설명</span><span class="sxs-lookup"><span data-stu-id="9bf5e-155">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="9bf5e-156">의 보안 기능을 지정 합니다 [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9bf5e-156">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bf5e-157">설명</span><span class="sxs-lookup"><span data-stu-id="9bf5e-157">Remarks</span></span>  

 <span data-ttu-id="9bf5e-158">SOAP 메시지의 무결성 및 기밀성과 상호 인증을 위해 전송 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-158">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="9bf5e-159">바인딩에서 이 보안 모드를 선택하면 보안 전송을 사용하여 채널 스택이 구성되고 Windows(협상) 또는 SSL over TCP 같은 전송 보안을 사용하여 SOAP 메시지가 보안됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf5e-159">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf5e-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bf5e-160">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="9bf5e-161">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9bf5e-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9bf5e-162">바인딩</span><span class="sxs-lookup"><span data-stu-id="9bf5e-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9bf5e-163">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9bf5e-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9bf5e-164">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9bf5e-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
