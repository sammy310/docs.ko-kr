---
description: '다음에 대 한 자세한 정보:: <security><wsFederationHttpBinding>'
title: <wsFederationHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c01c7a50b05f1723b3620407eb5e5761bae35cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786800"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="58360-103">\<wsFederationHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="58360-103">\<security> of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="58360-104">의 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="58360-104">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="58360-105">구문</span><span class="sxs-lookup"><span data-stu-id="58360-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58360-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="58360-106">Attributes and Elements</span></span>  

 <span data-ttu-id="58360-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58360-108">특성</span><span class="sxs-lookup"><span data-stu-id="58360-108">Attributes</span></span>  
  
|<span data-ttu-id="58360-109">attribute</span><span class="sxs-lookup"><span data-stu-id="58360-109">Attribute</span></span>|<span data-ttu-id="58360-110">설명</span><span class="sxs-lookup"><span data-stu-id="58360-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58360-111">Mode</span><span class="sxs-lookup"><span data-stu-id="58360-111">Mode</span></span>|<span data-ttu-id="58360-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58360-112">Optional.</span></span> <span data-ttu-id="58360-113">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-113">Specifies the type of security that is applied.</span></span> <span data-ttu-id="58360-114">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="58360-114">The default value is `Message`.</span></span> <span data-ttu-id="58360-115">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="58360-115">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="58360-116">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="58360-116">Mode Attribute</span></span>  
  
|<span data-ttu-id="58360-117">값</span><span class="sxs-lookup"><span data-stu-id="58360-117">Value</span></span>|<span data-ttu-id="58360-118">설명</span><span class="sxs-lookup"><span data-stu-id="58360-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="58360-119">없음</span><span class="sxs-lookup"><span data-stu-id="58360-119">None</span></span>|<span data-ttu-id="58360-120">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58360-120">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="58360-121">메시지</span><span class="sxs-lookup"><span data-stu-id="58360-121">Message</span></span>|<span data-ttu-id="58360-122">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-122">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="58360-123">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58360-123">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="58360-124">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-124">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="58360-125">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58360-125">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="58360-126">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="58360-126">TransportWithMessageCredential</span></span>|<span data-ttu-id="58360-127">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-127">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="58360-128">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="58360-129">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58360-129">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58360-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="58360-130">Child Elements</span></span>  
  
|<span data-ttu-id="58360-131">요소</span><span class="sxs-lookup"><span data-stu-id="58360-131">Element</span></span>|<span data-ttu-id="58360-132">설명</span><span class="sxs-lookup"><span data-stu-id="58360-132">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="58360-133">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-133">Defines the settings for the message-level security.</span></span> <span data-ttu-id="58360-134">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="58360-134">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58360-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="58360-135">Parent Elements</span></span>  
  
|<span data-ttu-id="58360-136">요소</span><span class="sxs-lookup"><span data-stu-id="58360-136">Element</span></span>|<span data-ttu-id="58360-137">설명</span><span class="sxs-lookup"><span data-stu-id="58360-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="58360-138">의 모든 바인딩 기능을 정의 [\<wsDualHttpBinding>](wsdualhttpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="58360-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58360-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58360-139">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="58360-140">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="58360-140">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="58360-141">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="58360-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="58360-142">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="58360-142">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="58360-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="58360-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="58360-144">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="58360-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="58360-145">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="58360-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
