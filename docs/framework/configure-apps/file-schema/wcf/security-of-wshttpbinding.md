---
title: <wsHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 9f984759fb52242bf8030a101b567c14627dd314
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158697"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="a16ed-102">\<wsHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="a16ed-102">\<security> of \<wsHttpBinding></span></span>

<span data-ttu-id="a16ed-103">의 보안 기능을 나타냅니다 [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a16ed-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="a16ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="a16ed-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a16ed-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a16ed-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a16ed-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a16ed-107">특성</span><span class="sxs-lookup"><span data-stu-id="a16ed-107">Attributes</span></span>  
  
|<span data-ttu-id="a16ed-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a16ed-108">Attribute</span></span>|<span data-ttu-id="a16ed-109">설명</span><span class="sxs-lookup"><span data-stu-id="a16ed-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a16ed-110">mode</span><span class="sxs-lookup"><span data-stu-id="a16ed-110">mode</span></span>|<span data-ttu-id="a16ed-111">필드.</span><span class="sxs-lookup"><span data-stu-id="a16ed-111">-   Optional.</span></span> <span data-ttu-id="a16ed-112">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a16ed-113">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-113">The default is `Message`.</span></span><br /><span data-ttu-id="a16ed-114">-이 특성은 형식입니다 <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="a16ed-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a16ed-115">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="a16ed-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="a16ed-116">Value</span><span class="sxs-lookup"><span data-stu-id="a16ed-116">Value</span></span>|<span data-ttu-id="a16ed-117">설명</span><span class="sxs-lookup"><span data-stu-id="a16ed-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a16ed-118">없음</span><span class="sxs-lookup"><span data-stu-id="a16ed-118">None</span></span>|<span data-ttu-id="a16ed-119">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-119">Security is disabled.</span></span>|  
|<span data-ttu-id="a16ed-120">전송</span><span class="sxs-lookup"><span data-stu-id="a16ed-120">Transport</span></span>|<span data-ttu-id="a16ed-121">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="a16ed-122">서비스는 SSL 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="a16ed-123">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="a16ed-124">클라이언트 인증은 `ClientCredentials`의</span><span class="sxs-lookup"><span data-stu-id="a16ed-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="a16ed-125">의입니다 [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="a16ed-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="a16ed-126">메시지</span><span class="sxs-lookup"><span data-stu-id="a16ed-126">Message</span></span>|<span data-ttu-id="a16ed-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a16ed-128">기본적으로 SOAP 본문은 암호화 및 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="a16ed-129">이 모드는 서비스 자격 증명을 클라이언트에서 out of band 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 그리고 Security.Message 속성을 통해 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="a16ed-130">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="a16ed-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a16ed-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="a16ed-132">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="a16ed-133">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a16ed-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a16ed-134">Child Elements</span></span>  
  
|<span data-ttu-id="a16ed-135">요소</span><span class="sxs-lookup"><span data-stu-id="a16ed-135">Element</span></span>|<span data-ttu-id="a16ed-136">설명</span><span class="sxs-lookup"><span data-stu-id="a16ed-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="a16ed-137">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-137">Defines the transport security settings.</span></span> <span data-ttu-id="a16ed-138">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="a16ed-139">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-139">Defines the security settings for the message.</span></span> <span data-ttu-id="a16ed-140">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a16ed-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a16ed-141">Parent Elements</span></span>  
  
|<span data-ttu-id="a16ed-142">요소</span><span class="sxs-lookup"><span data-stu-id="a16ed-142">Element</span></span>|<span data-ttu-id="a16ed-143">설명</span><span class="sxs-lookup"><span data-stu-id="a16ed-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="a16ed-144">HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a16ed-145">설명</span><span class="sxs-lookup"><span data-stu-id="a16ed-145">Remarks</span></span>  

 <span data-ttu-id="a16ed-146">WSHttpBinding 클래스는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="a16ed-147">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="a16ed-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16ed-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a16ed-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="a16ed-149">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a16ed-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a16ed-150">바인딩하</span><span class="sxs-lookup"><span data-stu-id="a16ed-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a16ed-151">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="a16ed-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a16ed-152">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a16ed-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
