---
title: <wsFederationHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c07d1ca18837f66548411262b84b9a326f5ec4a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399740"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="27129-102">\<wsFederationHttpBinding >의 \<보안 ></span><span class="sxs-lookup"><span data-stu-id="27129-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="27129-103">[ \<WsFederationHttpBinding >](wsfederationhttpbinding.md)의 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="27129-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27129-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27129-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27129-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27129-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="27129-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="27129-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="27129-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="27129-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="27129-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="27129-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<보안 >**</span><span class="sxs-lookup"><span data-stu-id="27129-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27129-110">구문</span><span class="sxs-lookup"><span data-stu-id="27129-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27129-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="27129-111">Attributes and Elements</span></span>  
 <span data-ttu-id="27129-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27129-113">특성</span><span class="sxs-lookup"><span data-stu-id="27129-113">Attributes</span></span>  
  
|<span data-ttu-id="27129-114">특성</span><span class="sxs-lookup"><span data-stu-id="27129-114">Attribute</span></span>|<span data-ttu-id="27129-115">Description</span><span class="sxs-lookup"><span data-stu-id="27129-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27129-116">모드</span><span class="sxs-lookup"><span data-stu-id="27129-116">Mode</span></span>|<span data-ttu-id="27129-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="27129-117">Optional.</span></span> <span data-ttu-id="27129-118">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="27129-119">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="27129-119">The default value is `Message`.</span></span> <span data-ttu-id="27129-120">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="27129-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="27129-121">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="27129-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="27129-122">값</span><span class="sxs-lookup"><span data-stu-id="27129-122">Value</span></span>|<span data-ttu-id="27129-123">설명</span><span class="sxs-lookup"><span data-stu-id="27129-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27129-124">없음</span><span class="sxs-lookup"><span data-stu-id="27129-124">None</span></span>|<span data-ttu-id="27129-125">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27129-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="27129-126">메시지</span><span class="sxs-lookup"><span data-stu-id="27129-126">Message</span></span>|<span data-ttu-id="27129-127">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="27129-128">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="27129-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="27129-129">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="27129-130">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="27129-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="27129-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="27129-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="27129-132">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="27129-133">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="27129-134">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="27129-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27129-135">자식 요소</span><span class="sxs-lookup"><span data-stu-id="27129-135">Child Elements</span></span>  
  
|<span data-ttu-id="27129-136">요소</span><span class="sxs-lookup"><span data-stu-id="27129-136">Element</span></span>|<span data-ttu-id="27129-137">Description</span><span class="sxs-lookup"><span data-stu-id="27129-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27129-138">\<message></span><span class="sxs-lookup"><span data-stu-id="27129-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="27129-139">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="27129-140">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="27129-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27129-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="27129-141">Parent Elements</span></span>  
  
|<span data-ttu-id="27129-142">요소</span><span class="sxs-lookup"><span data-stu-id="27129-142">Element</span></span>|<span data-ttu-id="27129-143">설명</span><span class="sxs-lookup"><span data-stu-id="27129-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27129-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="27129-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="27129-145">WsDualHttpBinding >의 모든 바인딩 기능을 [ \<](wsdualhttpbinding.md)정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27129-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27129-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="27129-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="27129-147">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="27129-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="27129-148">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="27129-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="27129-149">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="27129-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="27129-150">바인딩</span><span class="sxs-lookup"><span data-stu-id="27129-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="27129-151">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="27129-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="27129-152">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="27129-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="27129-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="27129-153">\<binding></span></span>](../../../misc/binding.md)
