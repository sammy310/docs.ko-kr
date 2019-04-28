---
title: <security> 요소 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 15740144b0aad7eb2798db4712e4769d08d893a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670549"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="26e6e-102">\<보안 > 요소의 \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="26e6e-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="26e6e-103">보안 설정을 정의 합니다 [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="26e6e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26e6e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="26e6e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="26e6e-105">\<bindings></span></span>  
<span data-ttu-id="26e6e-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="26e6e-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="26e6e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="26e6e-107">\<binding></span></span>  
<span data-ttu-id="26e6e-108">\<security></span><span class="sxs-lookup"><span data-stu-id="26e6e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e6e-109">구문</span><span class="sxs-lookup"><span data-stu-id="26e6e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26e6e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="26e6e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="26e6e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26e6e-112">특성</span><span class="sxs-lookup"><span data-stu-id="26e6e-112">Attributes</span></span>  
  
|<span data-ttu-id="26e6e-113">특성</span><span class="sxs-lookup"><span data-stu-id="26e6e-113">Attribute</span></span>|<span data-ttu-id="26e6e-114">설명</span><span class="sxs-lookup"><span data-stu-id="26e6e-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="26e6e-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-115">Optional.</span></span> <span data-ttu-id="26e6e-116">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="26e6e-117">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-117">The default value is `Message`.</span></span> <span data-ttu-id="26e6e-118">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="26e6e-119">mode 특성</span><span class="sxs-lookup"><span data-stu-id="26e6e-119">mode Attribute</span></span>  
  
|<span data-ttu-id="26e6e-120">값</span><span class="sxs-lookup"><span data-stu-id="26e6e-120">Value</span></span>|<span data-ttu-id="26e6e-121">설명</span><span class="sxs-lookup"><span data-stu-id="26e6e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="26e6e-122">없음</span><span class="sxs-lookup"><span data-stu-id="26e6e-122">None</span></span>|<span data-ttu-id="26e6e-123">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="26e6e-124">메시지</span><span class="sxs-lookup"><span data-stu-id="26e6e-124">Message</span></span>|<span data-ttu-id="26e6e-125">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="26e6e-126">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="26e6e-127">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="26e6e-128">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="26e6e-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="26e6e-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="26e6e-130">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="26e6e-131">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="26e6e-132">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26e6e-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="26e6e-133">Child Elements</span></span>  
  
|<span data-ttu-id="26e6e-134">요소</span><span class="sxs-lookup"><span data-stu-id="26e6e-134">Element</span></span>|<span data-ttu-id="26e6e-135">설명</span><span class="sxs-lookup"><span data-stu-id="26e6e-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26e6e-136">\<message></span><span class="sxs-lookup"><span data-stu-id="26e6e-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="26e6e-137">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="26e6e-138">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26e6e-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="26e6e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="26e6e-140">요소</span><span class="sxs-lookup"><span data-stu-id="26e6e-140">Element</span></span>|<span data-ttu-id="26e6e-141">설명</span><span class="sxs-lookup"><span data-stu-id="26e6e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26e6e-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="26e6e-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="26e6e-143">모든 바인딩 기능을 정의 합니다 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26e6e-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26e6e-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="26e6e-144">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="26e6e-145">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="26e6e-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="26e6e-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="26e6e-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="26e6e-147">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="26e6e-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="26e6e-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="26e6e-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="26e6e-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="26e6e-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="26e6e-150">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="26e6e-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="26e6e-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="26e6e-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
