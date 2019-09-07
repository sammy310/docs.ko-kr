---
title: <wsHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: f7a4ef98637a7c966665fdd02ad26929bd4ba6ac
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399720"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="41946-102">\<wsHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="41946-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="41946-103">[ \<WsHttpBinding >](wshttpbinding.md)의 보안 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41946-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
<span data-ttu-id="41946-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41946-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41946-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="41946-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="41946-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="41946-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="41946-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="41946-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="41946-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="41946-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="41946-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="41946-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41946-110">구문</span><span class="sxs-lookup"><span data-stu-id="41946-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41946-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="41946-111">Attributes and Elements</span></span>  
 <span data-ttu-id="41946-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41946-113">특성</span><span class="sxs-lookup"><span data-stu-id="41946-113">Attributes</span></span>  
  
|<span data-ttu-id="41946-114">특성</span><span class="sxs-lookup"><span data-stu-id="41946-114">Attribute</span></span>|<span data-ttu-id="41946-115">Description</span><span class="sxs-lookup"><span data-stu-id="41946-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41946-116">모드</span><span class="sxs-lookup"><span data-stu-id="41946-116">mode</span></span>|<span data-ttu-id="41946-117">필드.</span><span class="sxs-lookup"><span data-stu-id="41946-117">-   Optional.</span></span> <span data-ttu-id="41946-118">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="41946-119">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="41946-119">The default is `Message`.</span></span><br /><span data-ttu-id="41946-120">-이 특성은 형식 <xref:System.ServiceModel.SecurityMode>입니다.</span><span class="sxs-lookup"><span data-stu-id="41946-120">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="41946-121">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="41946-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="41946-122">값</span><span class="sxs-lookup"><span data-stu-id="41946-122">Value</span></span>|<span data-ttu-id="41946-123">설명</span><span class="sxs-lookup"><span data-stu-id="41946-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41946-124">없음</span><span class="sxs-lookup"><span data-stu-id="41946-124">None</span></span>|<span data-ttu-id="41946-125">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41946-125">Security is disabled.</span></span>|  
|<span data-ttu-id="41946-126">전송</span><span class="sxs-lookup"><span data-stu-id="41946-126">Transport</span></span>|<span data-ttu-id="41946-127">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-127">Security is provided using HTTPS.</span></span> <span data-ttu-id="41946-128">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-128">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="41946-129">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-129">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="41946-130">클라이언트 인증은 `ClientCredentials`의</span><span class="sxs-lookup"><span data-stu-id="41946-130">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="41946-131">전송 >의입니다. [ \<](transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="41946-131">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="41946-132">메시지</span><span class="sxs-lookup"><span data-stu-id="41946-132">Message</span></span>|<span data-ttu-id="41946-133">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="41946-134">기본적으로 SOAP 본문은 암호화 및 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-134">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="41946-135">이 모드는 서비스 자격 증명을 클라이언트에서 out of band 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 그리고 Security.Message 속성을 통해 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-135">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="41946-136">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-136">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="41946-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="41946-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="41946-138">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-138">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="41946-139">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="41946-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41946-140">자식 요소</span><span class="sxs-lookup"><span data-stu-id="41946-140">Child Elements</span></span>  
  
|<span data-ttu-id="41946-141">요소</span><span class="sxs-lookup"><span data-stu-id="41946-141">Element</span></span>|<span data-ttu-id="41946-142">Description</span><span class="sxs-lookup"><span data-stu-id="41946-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41946-143">\<transport></span><span class="sxs-lookup"><span data-stu-id="41946-143">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="41946-144">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-144">Defines the transport security settings.</span></span> <span data-ttu-id="41946-145">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-145">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="41946-146">\<message></span><span class="sxs-lookup"><span data-stu-id="41946-146">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="41946-147">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-147">Defines the security settings for the message.</span></span> <span data-ttu-id="41946-148">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="41946-148">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41946-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="41946-149">Parent Elements</span></span>  
  
|<span data-ttu-id="41946-150">요소</span><span class="sxs-lookup"><span data-stu-id="41946-150">Element</span></span>|<span data-ttu-id="41946-151">Description</span><span class="sxs-lookup"><span data-stu-id="41946-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41946-152">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="41946-152">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="41946-153">HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="41946-153">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41946-154">설명</span><span class="sxs-lookup"><span data-stu-id="41946-154">Remarks</span></span>  
 <span data-ttu-id="41946-155">WSHttpBinding 클래스는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41946-155">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="41946-156">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="41946-156">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41946-157">참고자료</span><span class="sxs-lookup"><span data-stu-id="41946-157">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="41946-158">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="41946-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="41946-159">바인딩</span><span class="sxs-lookup"><span data-stu-id="41946-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="41946-160">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="41946-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="41946-161">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="41946-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="41946-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="41946-162">\<binding></span></span>](../../../misc/binding.md)
