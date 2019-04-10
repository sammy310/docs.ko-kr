---
title: <security> / <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 75e3910473a353c2ef110106c34b4e92c018b51c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196127"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="8ee85-102">\<보안 >의 \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8ee85-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="8ee85-103">보안 설정을 정의 합니다 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="8ee85-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8ee85-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8ee85-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8ee85-105">\<bindings></span></span>  
<span data-ttu-id="8ee85-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="8ee85-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="8ee85-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8ee85-107">\<binding></span></span>  
<span data-ttu-id="8ee85-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8ee85-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee85-109">구문</span><span class="sxs-lookup"><span data-stu-id="8ee85-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ee85-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ee85-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8ee85-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ee85-112">특성</span><span class="sxs-lookup"><span data-stu-id="8ee85-112">Attributes</span></span>  
  
|<span data-ttu-id="8ee85-113">특성</span><span class="sxs-lookup"><span data-stu-id="8ee85-113">Attribute</span></span>|<span data-ttu-id="8ee85-114">설명</span><span class="sxs-lookup"><span data-stu-id="8ee85-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ee85-115">모드</span><span class="sxs-lookup"><span data-stu-id="8ee85-115">Mode</span></span>|<span data-ttu-id="8ee85-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-116">Optional.</span></span> <span data-ttu-id="8ee85-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="8ee85-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-118">The default value is `Message`.</span></span> <span data-ttu-id="8ee85-119">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8ee85-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="8ee85-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="8ee85-121">값</span><span class="sxs-lookup"><span data-stu-id="8ee85-121">Value</span></span>|<span data-ttu-id="8ee85-122">설명</span><span class="sxs-lookup"><span data-stu-id="8ee85-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8ee85-123">없음</span><span class="sxs-lookup"><span data-stu-id="8ee85-123">None</span></span>|<span data-ttu-id="8ee85-124">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="8ee85-125">메시지</span><span class="sxs-lookup"><span data-stu-id="8ee85-125">Message</span></span>|<span data-ttu-id="8ee85-126">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="8ee85-127">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="8ee85-128">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="8ee85-129">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="8ee85-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="8ee85-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="8ee85-131">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="8ee85-132">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="8ee85-133">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ee85-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ee85-134">Child Elements</span></span>  
  
|<span data-ttu-id="8ee85-135">요소</span><span class="sxs-lookup"><span data-stu-id="8ee85-135">Element</span></span>|<span data-ttu-id="8ee85-136">설명</span><span class="sxs-lookup"><span data-stu-id="8ee85-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ee85-137">\<message></span><span class="sxs-lookup"><span data-stu-id="8ee85-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="8ee85-138">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="8ee85-139">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ee85-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ee85-140">Parent Elements</span></span>  
  
|<span data-ttu-id="8ee85-141">요소</span><span class="sxs-lookup"><span data-stu-id="8ee85-141">Element</span></span>|<span data-ttu-id="8ee85-142">설명</span><span class="sxs-lookup"><span data-stu-id="8ee85-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ee85-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="8ee85-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8ee85-144">모든 바인딩 기능을 정의 합니다 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee85-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ee85-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ee85-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="8ee85-146">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="8ee85-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="8ee85-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8ee85-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8ee85-148">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="8ee85-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="8ee85-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="8ee85-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8ee85-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8ee85-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8ee85-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8ee85-151">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8ee85-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="8ee85-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
