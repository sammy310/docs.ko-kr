---
description: '자세히 알아보기: <security> 의 요소 <ws2007FederationHttpBinding>'
title: <security> 의 요소 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 0caa2c3791c0dc3c8db0d9ee27175a28e52f6baa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683296"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="37681-103">\<security> 의 요소 \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="37681-103">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="37681-104">요소의 보안 설정을 정의 합니다 [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="37681-104">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="37681-105">구문</span><span class="sxs-lookup"><span data-stu-id="37681-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37681-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="37681-106">Attributes and Elements</span></span>  

 <span data-ttu-id="37681-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37681-108">특성</span><span class="sxs-lookup"><span data-stu-id="37681-108">Attributes</span></span>  
  
|<span data-ttu-id="37681-109">attribute</span><span class="sxs-lookup"><span data-stu-id="37681-109">Attribute</span></span>|<span data-ttu-id="37681-110">설명</span><span class="sxs-lookup"><span data-stu-id="37681-110">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="37681-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="37681-111">Optional.</span></span> <span data-ttu-id="37681-112">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="37681-113">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="37681-113">The default value is `Message`.</span></span> <span data-ttu-id="37681-114">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="37681-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="37681-115">mode 특성</span><span class="sxs-lookup"><span data-stu-id="37681-115">mode Attribute</span></span>  
  
|<span data-ttu-id="37681-116">값</span><span class="sxs-lookup"><span data-stu-id="37681-116">Value</span></span>|<span data-ttu-id="37681-117">설명</span><span class="sxs-lookup"><span data-stu-id="37681-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37681-118">없음</span><span class="sxs-lookup"><span data-stu-id="37681-118">None</span></span>|<span data-ttu-id="37681-119">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37681-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="37681-120">메시지</span><span class="sxs-lookup"><span data-stu-id="37681-120">Message</span></span>|<span data-ttu-id="37681-121">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="37681-122">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="37681-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="37681-123">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-123">The service must be configured with a certificate.</span></span> <span data-ttu-id="37681-124">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="37681-124">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="37681-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="37681-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="37681-126">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="37681-127">인증서를 사용하여 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="37681-128">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="37681-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37681-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="37681-129">Child Elements</span></span>  
  
|<span data-ttu-id="37681-130">요소</span><span class="sxs-lookup"><span data-stu-id="37681-130">Element</span></span>|<span data-ttu-id="37681-131">설명</span><span class="sxs-lookup"><span data-stu-id="37681-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="37681-132">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="37681-133">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="37681-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37681-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="37681-134">Parent Elements</span></span>  
  
|<span data-ttu-id="37681-135">요소</span><span class="sxs-lookup"><span data-stu-id="37681-135">Element</span></span>|<span data-ttu-id="37681-136">설명</span><span class="sxs-lookup"><span data-stu-id="37681-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="37681-137">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="37681-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37681-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37681-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="37681-139">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="37681-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="37681-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="37681-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="37681-141">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="37681-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="37681-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="37681-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="37681-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="37681-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="37681-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="37681-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
