---
title: <ws2007HttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736395"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="387d0-102">\<보안 > \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="387d0-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="387d0-103">[\<ws2007HttpBinding >](ws2007httpbinding.md) 요소에 사용 되는 보안 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="387d0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="387d0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="387d0-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="387d0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="387d0-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="387d0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="387d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="387d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="387d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="387d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="387d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**보안 >**</span><span class="sxs-lookup"><span data-stu-id="387d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="387d0-110">구문</span><span class="sxs-lookup"><span data-stu-id="387d0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="387d0-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="387d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="387d0-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="387d0-113">특성</span><span class="sxs-lookup"><span data-stu-id="387d0-113">Attributes</span></span>  
  
|<span data-ttu-id="387d0-114">특성</span><span class="sxs-lookup"><span data-stu-id="387d0-114">Attribute</span></span>|<span data-ttu-id="387d0-115">설명</span><span class="sxs-lookup"><span data-stu-id="387d0-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="387d0-116">필드.</span><span class="sxs-lookup"><span data-stu-id="387d0-116">-   Optional.</span></span> <span data-ttu-id="387d0-117">적용 되는 보안 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="387d0-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="387d0-119">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="387d0-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="387d0-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="387d0-121">값</span><span class="sxs-lookup"><span data-stu-id="387d0-121">Value</span></span>|<span data-ttu-id="387d0-122">설명</span><span class="sxs-lookup"><span data-stu-id="387d0-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="387d0-123">보안이 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="387d0-124">HTTPS를 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="387d0-125">SSL(Secure Sockets Layer) 인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="387d0-126">메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="387d0-127">클라이언트 인증은 [\<transport >](transport-of-ws2007httpbinding.md) 요소의 `ClientCredentials` 특성을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="387d0-128">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="387d0-129">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="387d0-130">이 모드는 서비스 자격 증명을 out-of-band 클라이언트에서 사용할 수 있는지 여부, 사용할 알고리즘 모음 및 <xref:System.ServiceModel.Security.SecurityMessageProperty>를 통해 메시지 본문에 적용할 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="387d0-131">클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="387d0-132">이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="387d0-133">기본적으로 클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="387d0-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="387d0-134">Child Elements</span></span>  
  
|<span data-ttu-id="387d0-135">요소</span><span class="sxs-lookup"><span data-stu-id="387d0-135">Element</span></span>|<span data-ttu-id="387d0-136">설명</span><span class="sxs-lookup"><span data-stu-id="387d0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="387d0-137">\<전송 ></span><span class="sxs-lookup"><span data-stu-id="387d0-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="387d0-138">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-138">Defines the transport security settings.</span></span> <span data-ttu-id="387d0-139">이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="387d0-140">이 설정은 모드를 Transport로 설정한 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="387d0-141">\<message ></span><span class="sxs-lookup"><span data-stu-id="387d0-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="387d0-142">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-142">Defines the security settings for the message.</span></span> <span data-ttu-id="387d0-143">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="387d0-144">이 설정은 모드를 Transport로 설정한 경우에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="387d0-145">부모 요소</span><span class="sxs-lookup"><span data-stu-id="387d0-145">Parent Elements</span></span>  
  
|<span data-ttu-id="387d0-146">요소</span><span class="sxs-lookup"><span data-stu-id="387d0-146">Element</span></span>|<span data-ttu-id="387d0-147">설명</span><span class="sxs-lookup"><span data-stu-id="387d0-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="387d0-148">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="387d0-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="387d0-149">HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="387d0-150">주의</span><span class="sxs-lookup"><span data-stu-id="387d0-150">Remarks</span></span>  
 <span data-ttu-id="387d0-151">이 요소는 WS-\* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="387d0-152">이 바인딩에 대 한 전송 보안은 HTTP 또는 HTTPS를 통한 SSL(Secure Sockets Layer) (SSL)입니다.</span><span class="sxs-lookup"><span data-stu-id="387d0-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387d0-153">참조</span><span class="sxs-lookup"><span data-stu-id="387d0-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="387d0-154">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="387d0-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="387d0-155">바인딩</span><span class="sxs-lookup"><span data-stu-id="387d0-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="387d0-156">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="387d0-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="387d0-157">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="387d0-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="387d0-158">\<binding ></span><span class="sxs-lookup"><span data-stu-id="387d0-158">\<binding></span></span>](bindings.md)
