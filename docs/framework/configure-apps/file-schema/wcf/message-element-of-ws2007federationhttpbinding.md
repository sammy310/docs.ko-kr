---
description: '자세히 알아보기: <message> 의 요소 <ws2007FederationHttpBinding>'
title: <message> 의 요소 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f9116a5075f30421dfb26adc29ec0b167db33673
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725456"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="87d99-103">\<message> 의 요소 \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="87d99-103">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="87d99-104">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="87d99-104">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="87d99-105">구문</span><span class="sxs-lookup"><span data-stu-id="87d99-105">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
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
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87d99-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87d99-106">Attributes and Elements</span></span>  

 <span data-ttu-id="87d99-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87d99-108">특성</span><span class="sxs-lookup"><span data-stu-id="87d99-108">Attributes</span></span>  
  
|<span data-ttu-id="87d99-109">attribute</span><span class="sxs-lookup"><span data-stu-id="87d99-109">Attribute</span></span>|<span data-ttu-id="87d99-110">설명</span><span class="sxs-lookup"><span data-stu-id="87d99-110">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="87d99-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-111">Optional.</span></span> <span data-ttu-id="87d99-112">메시지 암호화, 시그니처 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-112">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="87d99-113">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-113">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="87d99-114">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-114">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="87d99-115">사용 가능한 값은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87d99-115">See the following table for possible values.</span></span> <span data-ttu-id="87d99-116">기본값은 Basic256입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-116">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="87d99-117">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="87d99-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="87d99-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="87d99-119">-   SymmetricKey</span></span><br /><span data-ttu-id="87d99-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="87d99-120">-   PublicKey</span></span><br /><span data-ttu-id="87d99-121">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="87d99-121">-   BearerKey</span></span><br /><br /> <span data-ttu-id="87d99-122">기본값은 SymmetricKey입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-122">The default is SymmetricKey.</span></span> <span data-ttu-id="87d99-123">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-123">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="87d99-124">발급할 토큰의 형식을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-124">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="87d99-125">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-125">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="87d99-126">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-126">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="87d99-127">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-127">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="87d99-128">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="87d99-128">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="87d99-129">값</span><span class="sxs-lookup"><span data-stu-id="87d99-129">Value</span></span>|<span data-ttu-id="87d99-130">설명</span><span class="sxs-lookup"><span data-stu-id="87d99-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="87d99-131">Basic128</span><span class="sxs-lookup"><span data-stu-id="87d99-131">Basic128</span></span>|<span data-ttu-id="87d99-132">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-132">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-133">Basic192</span><span class="sxs-lookup"><span data-stu-id="87d99-133">Basic192</span></span>|<span data-ttu-id="87d99-134">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-134">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-135">Basic256</span><span class="sxs-lookup"><span data-stu-id="87d99-135">Basic256</span></span>|<span data-ttu-id="87d99-136">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-136">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-137">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-137">Basic256Rsa15</span></span>|<span data-ttu-id="87d99-138">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-138">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-139">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-139">Basic192Rsa15</span></span>|<span data-ttu-id="87d99-140">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-140">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-141">TripleDes</span><span class="sxs-lookup"><span data-stu-id="87d99-141">TripleDes</span></span>|<span data-ttu-id="87d99-142">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-142">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-143">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-143">Basic128Rsa15</span></span>|<span data-ttu-id="87d99-144">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-144">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-145">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-145">TripleDesRsa15</span></span>|<span data-ttu-id="87d99-146">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-146">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-147">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="87d99-147">Basic128Sha256</span></span>|<span data-ttu-id="87d99-148">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-148">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-149">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="87d99-149">Basic192Sha256</span></span>|<span data-ttu-id="87d99-150">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-150">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-151">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="87d99-151">Basic256Sha256</span></span>|<span data-ttu-id="87d99-152">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-152">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-153">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="87d99-153">TripleDesSha256</span></span>|<span data-ttu-id="87d99-154">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-154">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="87d99-155">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-155">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="87d99-156">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-156">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-157">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-157">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="87d99-158">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-158">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-159">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-159">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="87d99-160">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-160">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="87d99-161">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="87d99-161">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="87d99-162">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87d99-163">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87d99-163">Child Elements</span></span>  
  
|<span data-ttu-id="87d99-164">요소</span><span class="sxs-lookup"><span data-stu-id="87d99-164">Element</span></span>|<span data-ttu-id="87d99-165">설명</span><span class="sxs-lookup"><span data-stu-id="87d99-165">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="87d99-166">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-166">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="87d99-167">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-167">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="87d99-168">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-168">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="87d99-169">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-169">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="87d99-170">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-170">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="87d99-171">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-171">A collection of token request parameters.</span></span> <span data-ttu-id="87d99-172">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-172">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87d99-173">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87d99-173">Parent Elements</span></span>  
  
|<span data-ttu-id="87d99-174">요소</span><span class="sxs-lookup"><span data-stu-id="87d99-174">Element</span></span>|<span data-ttu-id="87d99-175">설명</span><span class="sxs-lookup"><span data-stu-id="87d99-175">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="87d99-176">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87d99-176">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87d99-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87d99-177">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="87d99-178">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="87d99-178">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="87d99-179">바인딩</span><span class="sxs-lookup"><span data-stu-id="87d99-179">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="87d99-180">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="87d99-180">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="87d99-181">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="87d99-181">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
