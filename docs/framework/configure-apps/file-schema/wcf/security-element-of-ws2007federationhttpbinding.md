---
title: <security>의 요소<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738728"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="145fd-102">\<security>의 요소\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="145fd-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="145fd-103">요소의 보안 설정을 정의 합니다 [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="145fd-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="145fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="145fd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="145fd-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="145fd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="145fd-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="145fd-107">특성</span><span class="sxs-lookup"><span data-stu-id="145fd-107">Attributes</span></span>  
  
|<span data-ttu-id="145fd-108">attribute</span><span class="sxs-lookup"><span data-stu-id="145fd-108">Attribute</span></span>|<span data-ttu-id="145fd-109">설명</span><span class="sxs-lookup"><span data-stu-id="145fd-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="145fd-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-110">Optional.</span></span> <span data-ttu-id="145fd-111">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="145fd-112">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-112">The default value is `Message`.</span></span> <span data-ttu-id="145fd-113">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="145fd-114">mode 특성</span><span class="sxs-lookup"><span data-stu-id="145fd-114">mode Attribute</span></span>  
  
|<span data-ttu-id="145fd-115">값</span><span class="sxs-lookup"><span data-stu-id="145fd-115">Value</span></span>|<span data-ttu-id="145fd-116">Description</span><span class="sxs-lookup"><span data-stu-id="145fd-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="145fd-117">None</span><span class="sxs-lookup"><span data-stu-id="145fd-117">None</span></span>|<span data-ttu-id="145fd-118">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="145fd-119">메시지</span><span class="sxs-lookup"><span data-stu-id="145fd-119">Message</span></span>|<span data-ttu-id="145fd-120">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="145fd-121">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="145fd-122">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="145fd-123">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="145fd-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="145fd-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="145fd-125">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="145fd-126">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="145fd-127">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="145fd-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="145fd-128">Child Elements</span></span>  
  
|<span data-ttu-id="145fd-129">요소</span><span class="sxs-lookup"><span data-stu-id="145fd-129">Element</span></span>|<span data-ttu-id="145fd-130">Description</span><span class="sxs-lookup"><span data-stu-id="145fd-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="145fd-131">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="145fd-132">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="145fd-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="145fd-133">Parent Elements</span></span>  
  
|<span data-ttu-id="145fd-134">요소</span><span class="sxs-lookup"><span data-stu-id="145fd-134">Element</span></span>|<span data-ttu-id="145fd-135">Description</span><span class="sxs-lookup"><span data-stu-id="145fd-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="145fd-136">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="145fd-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="145fd-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="145fd-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="145fd-138">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="145fd-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="145fd-139">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="145fd-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="145fd-140">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="145fd-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="145fd-141">바인딩</span><span class="sxs-lookup"><span data-stu-id="145fd-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="145fd-142">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="145fd-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="145fd-143">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="145fd-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
