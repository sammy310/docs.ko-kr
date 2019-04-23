---
title: <ws2007HttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: bac8b9c4af812e924296008fa81227d181b30c0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170848"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="469de-102">\<보안 >의 \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="469de-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="469de-103">사용 하는 보안 설정을 나타냅니다 합니다 [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="469de-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="469de-104">\<system.serviceModel></span></span>  
<span data-ttu-id="469de-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="469de-105">\<bindings></span></span>  
<span data-ttu-id="469de-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="469de-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="469de-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="469de-107">\<binding></span></span>  
<span data-ttu-id="469de-108">\<security></span><span class="sxs-lookup"><span data-stu-id="469de-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469de-109">구문</span><span class="sxs-lookup"><span data-stu-id="469de-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="469de-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="469de-110">Attributes and Elements</span></span>  
 <span data-ttu-id="469de-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="469de-112">특성</span><span class="sxs-lookup"><span data-stu-id="469de-112">Attributes</span></span>  
  
|<span data-ttu-id="469de-113">특성</span><span class="sxs-lookup"><span data-stu-id="469de-113">Attribute</span></span>|<span data-ttu-id="469de-114">설명</span><span class="sxs-lookup"><span data-stu-id="469de-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="469de-115">-선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-115">-   Optional.</span></span> <span data-ttu-id="469de-116">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="469de-117">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="469de-118">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="469de-119">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="469de-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="469de-120">값</span><span class="sxs-lookup"><span data-stu-id="469de-120">Value</span></span>|<span data-ttu-id="469de-121">설명</span><span class="sxs-lookup"><span data-stu-id="469de-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="469de-122">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="469de-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="469de-123">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="469de-124">SSL(Secure Sockets Layer) 인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="469de-125">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="469de-126">클라이언트 인증을 통해 제어 됩니다 합니다 `ClientCredentials` 특성을 [ \<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="469de-127">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="469de-128">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="469de-129">이 모드는 서비스 자격 증명을 out-of-band 클라이언트에서 사용할 수 있는지 여부, 사용할 알고리즘 모음 및 <xref:System.ServiceModel.Security.SecurityMessageProperty>를 통해 메시지 본문에 적용할 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="469de-130">클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="469de-131">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="469de-132">기본적으로 클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="469de-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="469de-133">Child Elements</span></span>  
  
|<span data-ttu-id="469de-134">요소</span><span class="sxs-lookup"><span data-stu-id="469de-134">Element</span></span>|<span data-ttu-id="469de-135">설명</span><span class="sxs-lookup"><span data-stu-id="469de-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="469de-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="469de-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="469de-137">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-137">Defines the transport security settings.</span></span> <span data-ttu-id="469de-138">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="469de-139">이 설정은 모드를 Transport로 설정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="469de-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="469de-140">\<message></span><span class="sxs-lookup"><span data-stu-id="469de-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="469de-141">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-141">Defines the security settings for the message.</span></span> <span data-ttu-id="469de-142">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="469de-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="469de-143">이 설정은 모드를 Transport로 설정한 경우에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="469de-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="469de-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="469de-144">Parent Elements</span></span>  
  
|<span data-ttu-id="469de-145">요소</span><span class="sxs-lookup"><span data-stu-id="469de-145">Element</span></span>|<span data-ttu-id="469de-146">설명</span><span class="sxs-lookup"><span data-stu-id="469de-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="469de-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="469de-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="469de-148">HTTP 전송 응용 프로그램에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="469de-149">설명</span><span class="sxs-lookup"><span data-stu-id="469de-149">Remarks</span></span>  
 <span data-ttu-id="469de-150">이 요소는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="469de-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="469de-151">이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.</span><span class="sxs-lookup"><span data-stu-id="469de-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469de-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="469de-152">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="469de-153">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="469de-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="469de-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="469de-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="469de-155">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="469de-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="469de-156">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="469de-156">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="469de-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="469de-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
