---
title: <security>의 요소<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 450b2403b8cd4ec43a41fd27bccb3b77202820bb
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399901"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="4b9e8-102">\<ws2007FederationHttpBinding >의 \<security > 요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="4b9e8-103">Ws2007FederationHttpBinding > 요소의 보안 설정을 [ \<](ws2007federationhttpbinding.md) 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="4b9e8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b9e8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4b9e8-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4b9e8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4b9e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4b9e8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4b9e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4b9e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="4b9e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="4b9e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4b9e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b9e8-110">구문</span><span class="sxs-lookup"><span data-stu-id="4b9e8-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b9e8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b9e8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b9e8-113">특성</span><span class="sxs-lookup"><span data-stu-id="4b9e8-113">Attributes</span></span>  
  
|<span data-ttu-id="4b9e8-114">특성</span><span class="sxs-lookup"><span data-stu-id="4b9e8-114">Attribute</span></span>|<span data-ttu-id="4b9e8-115">Description</span><span class="sxs-lookup"><span data-stu-id="4b9e8-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4b9e8-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-116">Optional.</span></span> <span data-ttu-id="4b9e8-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="4b9e8-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-118">The default value is `Message`.</span></span> <span data-ttu-id="4b9e8-119">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4b9e8-120">mode 특성</span><span class="sxs-lookup"><span data-stu-id="4b9e8-120">mode Attribute</span></span>  
  
|<span data-ttu-id="4b9e8-121">값</span><span class="sxs-lookup"><span data-stu-id="4b9e8-121">Value</span></span>|<span data-ttu-id="4b9e8-122">설명</span><span class="sxs-lookup"><span data-stu-id="4b9e8-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b9e8-123">없음</span><span class="sxs-lookup"><span data-stu-id="4b9e8-123">None</span></span>|<span data-ttu-id="4b9e8-124">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="4b9e8-125">메시지</span><span class="sxs-lookup"><span data-stu-id="4b9e8-125">Message</span></span>|<span data-ttu-id="4b9e8-126">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="4b9e8-127">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="4b9e8-128">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="4b9e8-129">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="4b9e8-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="4b9e8-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="4b9e8-131">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="4b9e8-132">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="4b9e8-133">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b9e8-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-134">Child Elements</span></span>  
  
|<span data-ttu-id="4b9e8-135">요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-135">Element</span></span>|<span data-ttu-id="4b9e8-136">Description</span><span class="sxs-lookup"><span data-stu-id="4b9e8-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b9e8-137">\<message></span><span class="sxs-lookup"><span data-stu-id="4b9e8-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="4b9e8-138">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="4b9e8-139">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b9e8-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="4b9e8-141">요소</span><span class="sxs-lookup"><span data-stu-id="4b9e8-141">Element</span></span>|<span data-ttu-id="4b9e8-142">설명</span><span class="sxs-lookup"><span data-stu-id="4b9e8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b9e8-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b9e8-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4b9e8-144">WsDualHttpBinding >의 모든 바인딩 기능을 [ \<](wsdualhttpbinding.md)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b9e8-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b9e8-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="4b9e8-146">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="4b9e8-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="4b9e8-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="4b9e8-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4b9e8-148">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="4b9e8-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4b9e8-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="4b9e8-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4b9e8-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="4b9e8-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4b9e8-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4b9e8-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4b9e8-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b9e8-152">\<binding></span></span>](../../../misc/binding.md)
