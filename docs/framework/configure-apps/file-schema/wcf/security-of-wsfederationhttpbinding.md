---
title: <wsFederationHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736323"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="17102-102">\<wsFederationHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="17102-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="17102-103">의 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="17102-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="17102-104">구문</span><span class="sxs-lookup"><span data-stu-id="17102-104">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17102-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="17102-105">Attributes and Elements</span></span>  
 <span data-ttu-id="17102-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17102-107">특성</span><span class="sxs-lookup"><span data-stu-id="17102-107">Attributes</span></span>  
  
|<span data-ttu-id="17102-108">attribute</span><span class="sxs-lookup"><span data-stu-id="17102-108">Attribute</span></span>|<span data-ttu-id="17102-109">Description</span><span class="sxs-lookup"><span data-stu-id="17102-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17102-110">Mode</span><span class="sxs-lookup"><span data-stu-id="17102-110">Mode</span></span>|<span data-ttu-id="17102-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="17102-111">Optional.</span></span> <span data-ttu-id="17102-112">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="17102-113">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="17102-113">The default value is `Message`.</span></span> <span data-ttu-id="17102-114">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="17102-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="17102-115">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="17102-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="17102-116">값</span><span class="sxs-lookup"><span data-stu-id="17102-116">Value</span></span>|<span data-ttu-id="17102-117">Description</span><span class="sxs-lookup"><span data-stu-id="17102-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="17102-118">None</span><span class="sxs-lookup"><span data-stu-id="17102-118">None</span></span>|<span data-ttu-id="17102-119">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17102-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="17102-120">메시지</span><span class="sxs-lookup"><span data-stu-id="17102-120">Message</span></span>|<span data-ttu-id="17102-121">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="17102-122">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17102-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="17102-123">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="17102-124">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17102-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="17102-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="17102-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="17102-126">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="17102-127">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="17102-128">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17102-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17102-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="17102-129">Child Elements</span></span>  
  
|<span data-ttu-id="17102-130">요소</span><span class="sxs-lookup"><span data-stu-id="17102-130">Element</span></span>|<span data-ttu-id="17102-131">Description</span><span class="sxs-lookup"><span data-stu-id="17102-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="17102-132">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="17102-133">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="17102-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17102-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="17102-134">Parent Elements</span></span>  
  
|<span data-ttu-id="17102-135">요소</span><span class="sxs-lookup"><span data-stu-id="17102-135">Element</span></span>|<span data-ttu-id="17102-136">Description</span><span class="sxs-lookup"><span data-stu-id="17102-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="17102-137">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="17102-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17102-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17102-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="17102-139">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="17102-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="17102-140">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="17102-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="17102-141">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="17102-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="17102-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="17102-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="17102-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="17102-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="17102-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="17102-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
