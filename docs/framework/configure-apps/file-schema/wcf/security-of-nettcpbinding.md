---
title: <netTcpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: 971b1ea979877f631766e438cc41bc0bdabfd346
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399795"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="84592-102">\<netTcpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="84592-102">\<security> of \<netTcpBinding></span></span>
<span data-ttu-id="84592-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="84592-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="84592-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="84592-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="84592-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="84592-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="84592-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="84592-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="84592-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="84592-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="84592-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="84592-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="84592-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84592-110">구문</span><span class="sxs-lookup"><span data-stu-id="84592-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84592-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="84592-111">Attributes and Elements</span></span>  
 <span data-ttu-id="84592-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84592-113">특성</span><span class="sxs-lookup"><span data-stu-id="84592-113">Attributes</span></span>  
  
|<span data-ttu-id="84592-114">특성</span><span class="sxs-lookup"><span data-stu-id="84592-114">Attribute</span></span>|<span data-ttu-id="84592-115">Description</span><span class="sxs-lookup"><span data-stu-id="84592-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84592-116">모드</span><span class="sxs-lookup"><span data-stu-id="84592-116">mode</span></span>|<span data-ttu-id="84592-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-117">Optional.</span></span> <span data-ttu-id="84592-118">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="84592-119">유효한 값이 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-119">Valid values are shown below.</span></span> <span data-ttu-id="84592-120">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-120">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="84592-121">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-121">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="84592-122">mode 특성</span><span class="sxs-lookup"><span data-stu-id="84592-122">mode Attribute</span></span>  
  
|<span data-ttu-id="84592-123">값</span><span class="sxs-lookup"><span data-stu-id="84592-123">Value</span></span>|<span data-ttu-id="84592-124">설명</span><span class="sxs-lookup"><span data-stu-id="84592-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84592-125">없음</span><span class="sxs-lookup"><span data-stu-id="84592-125">None</span></span>|<span data-ttu-id="84592-126">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-126">Security is disabled.</span></span>|  
|<span data-ttu-id="84592-127">전송</span><span class="sxs-lookup"><span data-stu-id="84592-127">Transport</span></span>|<span data-ttu-id="84592-128">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-128">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="84592-129">서비스는 SSL 인증서로 구성해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-129">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="84592-130">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-130">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="84592-131">메시지</span><span class="sxs-lookup"><span data-stu-id="84592-131">Message</span></span>|<span data-ttu-id="84592-132">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="84592-133">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-133">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="84592-134">이 모드는 서비스 자격 증명을 클라이언트에서 밴드 외 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="84592-135">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="84592-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="84592-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="84592-137">전송 보안이 메시지 보안과 결합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-137">Transport security is coupled with message security.</span></span> <span data-ttu-id="84592-138">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공되며 무결성, 기밀성 및 서버 인증을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-138">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="84592-139">SOAP 메시지 보안에서는 클라이언트 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-139">SOAP message security provides client authentication.</span></span> <span data-ttu-id="84592-140">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-140">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84592-141">자식 요소</span><span class="sxs-lookup"><span data-stu-id="84592-141">Child Elements</span></span>  
  
|<span data-ttu-id="84592-142">요소</span><span class="sxs-lookup"><span data-stu-id="84592-142">Element</span></span>|<span data-ttu-id="84592-143">Description</span><span class="sxs-lookup"><span data-stu-id="84592-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84592-144">\<transport></span><span class="sxs-lookup"><span data-stu-id="84592-144">\<transport></span></span>](transport-of-nettcpbinding.md)|<span data-ttu-id="84592-145">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-145">Defines the security settings for the transport.</span></span> <span data-ttu-id="84592-146">이 요소는 <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-146">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="84592-147">\<message></span><span class="sxs-lookup"><span data-stu-id="84592-147">\<message></span></span>](message-element-of-nettcpbinding.md)|<span data-ttu-id="84592-148">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-148">Defines the security settings for the message.</span></span> <span data-ttu-id="84592-149">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-149">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84592-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="84592-150">Parent Elements</span></span>  
  
|<span data-ttu-id="84592-151">요소</span><span class="sxs-lookup"><span data-stu-id="84592-151">Element</span></span>|<span data-ttu-id="84592-152">Description</span><span class="sxs-lookup"><span data-stu-id="84592-152">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84592-153">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="84592-153">binding</span></span>|<span data-ttu-id="84592-154">[ \<NetTcpBinding >](nettcpbinding.md)의 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-154">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84592-155">설명</span><span class="sxs-lookup"><span data-stu-id="84592-155">Remarks</span></span>  
 <span data-ttu-id="84592-156">각 표준 바인딩은 전송 보안 요구 사항을 제어하는 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-156">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="84592-157">일반적으로 이러한 매개 변수에는 메시지 수준 보안이 사용되는지 또는 전송 수준 보안이 사용되는지 지정한 보안 모드 및 선택한 클라이언트 자격 증명 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-157">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="84592-158">이러한 매개 변수가 나타내는 선택 옵션에 따라 채널 스택이 해당 보안을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84592-158">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="84592-159">WCF(Windows Communication Foundation)에서 제공하는 시스템 제공 바인딩은 가장 일반적인 일부 시나리오의 요구 사항을 충족하기 위한 집합입니다</span><span class="sxs-lookup"><span data-stu-id="84592-159">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="84592-160">이러한 각 바인딩을 사용하면 일부 특정 대상 시나리오의 보안 요구 사항을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84592-160">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="84592-161">이 구성 요소는 `netTcpBinding`의 보안 사양을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-161">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="84592-162">이것은 시스템 간 통신에 적합한 안전하고, 신뢰할 수 있으며, 최적화된 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="84592-162">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="84592-163">기본적으로 메시지 배달을 위한 TCP, 메시지 보안 및 인증을 위한 Windows 보안, 안정성을 위한 WS-Reliable Messaging 및 이진 메시지 인코딩을 지원하는 런타임 통신 스택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84592-163">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84592-164">참고자료</span><span class="sxs-lookup"><span data-stu-id="84592-164">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="84592-165">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="84592-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="84592-166">바인딩</span><span class="sxs-lookup"><span data-stu-id="84592-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="84592-167">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="84592-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="84592-168">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="84592-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="84592-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="84592-169">\<binding></span></span>](../../../misc/binding.md)
