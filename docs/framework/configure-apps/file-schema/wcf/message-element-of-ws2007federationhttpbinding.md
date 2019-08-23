---
title: <message>의 요소<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 4340727026cb151f2efe813dfa005c1c5a1908be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931619"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="9a5a2-102">\<ws2007FederationHttpBinding >의 \<메시지 > 요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="9a5a2-103">Ws2007FederationHttpBinding > 요소에 대 한 [ \<](ws2007federationhttpbinding.md) 메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="9a5a2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9a5a2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9a5a2-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9a5a2-105">\<bindings></span></span>  
<span data-ttu-id="9a5a2-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9a5a2-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="9a5a2-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a5a2-107">\<binding></span></span>  
<span data-ttu-id="9a5a2-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9a5a2-108">\<security></span></span>  
<span data-ttu-id="9a5a2-109">\<message></span><span class="sxs-lookup"><span data-stu-id="9a5a2-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5a2-110">구문</span><span class="sxs-lookup"><span data-stu-id="9a5a2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a5a2-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9a5a2-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a5a2-113">특성</span><span class="sxs-lookup"><span data-stu-id="9a5a2-113">Attributes</span></span>  
  
|<span data-ttu-id="9a5a2-114">특성</span><span class="sxs-lookup"><span data-stu-id="9a5a2-114">Attribute</span></span>|<span data-ttu-id="9a5a2-115">설명</span><span class="sxs-lookup"><span data-stu-id="9a5a2-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="9a5a2-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-116">Optional.</span></span> <span data-ttu-id="9a5a2-117">메시지 암호화, 시그니처 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="9a5a2-118">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="9a5a2-119">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="9a5a2-120">사용 가능한 값은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-120">See the following table for possible values.</span></span> <span data-ttu-id="9a5a2-121">기본값은 Basic256입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="9a5a2-122">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="9a5a2-123">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9a5a2-124">-   SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="9a5a2-124">-   SymmetricKey</span></span><br /><span data-ttu-id="9a5a2-125">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="9a5a2-125">-   PublicKey</span></span><br /><span data-ttu-id="9a5a2-126">-   BearerKey</span><span class="sxs-lookup"><span data-stu-id="9a5a2-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="9a5a2-127">기본값은 SymmetricKey입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-127">The default is SymmetricKey.</span></span> <span data-ttu-id="9a5a2-128">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="9a5a2-129">발급할 토큰의 형식을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="9a5a2-130">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="9a5a2-131">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="9a5a2-132">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="9a5a2-133">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="9a5a2-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="9a5a2-134">값</span><span class="sxs-lookup"><span data-stu-id="9a5a2-134">Value</span></span>|<span data-ttu-id="9a5a2-135">Description</span><span class="sxs-lookup"><span data-stu-id="9a5a2-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a5a2-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="9a5a2-136">Basic128</span></span>|<span data-ttu-id="9a5a2-137">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="9a5a2-138">Basic192</span></span>|<span data-ttu-id="9a5a2-139">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="9a5a2-140">Basic256</span></span>|<span data-ttu-id="9a5a2-141">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-142">Basic256Rsa15</span></span>|<span data-ttu-id="9a5a2-143">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-144">Basic192Rsa15</span></span>|<span data-ttu-id="9a5a2-145">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="9a5a2-146">TripleDes</span></span>|<span data-ttu-id="9a5a2-147">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-148">Basic128Rsa15</span></span>|<span data-ttu-id="9a5a2-149">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-150">TripleDesRsa15</span></span>|<span data-ttu-id="9a5a2-151">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="9a5a2-152">Basic128Sha256</span></span>|<span data-ttu-id="9a5a2-153">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="9a5a2-154">Basic192Sha256</span></span>|<span data-ttu-id="9a5a2-155">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="9a5a2-156">Basic256Sha256</span></span>|<span data-ttu-id="9a5a2-157">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="9a5a2-158">TripleDesSha256</span></span>|<span data-ttu-id="9a5a2-159">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="9a5a2-161">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="9a5a2-163">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="9a5a2-165">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="9a5a2-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="9a5a2-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="9a5a2-167">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a5a2-168">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-168">Child Elements</span></span>  
  
|<span data-ttu-id="9a5a2-169">요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-169">Element</span></span>|<span data-ttu-id="9a5a2-170">설명</span><span class="sxs-lookup"><span data-stu-id="9a5a2-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a5a2-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="9a5a2-171">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="9a5a2-172">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="9a5a2-173">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="9a5a2-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="9a5a2-174">\<issuer></span></span>](issuer.md)|<span data-ttu-id="9a5a2-175">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="9a5a2-176">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="9a5a2-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="9a5a2-177">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="9a5a2-178">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="9a5a2-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="9a5a2-179">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="9a5a2-180">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-180">A collection of token request parameters.</span></span> <span data-ttu-id="9a5a2-181">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a5a2-182">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-182">Parent Elements</span></span>  
  
|<span data-ttu-id="9a5a2-183">요소</span><span class="sxs-lookup"><span data-stu-id="9a5a2-183">Element</span></span>|<span data-ttu-id="9a5a2-184">설명</span><span class="sxs-lookup"><span data-stu-id="9a5a2-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a5a2-185">\<security></span><span class="sxs-lookup"><span data-stu-id="9a5a2-185">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="9a5a2-186">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5a2-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a5a2-187">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a5a2-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="9a5a2-188">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9a5a2-188">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9a5a2-189">바인딩</span><span class="sxs-lookup"><span data-stu-id="9a5a2-189">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a5a2-190">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9a5a2-190">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9a5a2-191">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9a5a2-191">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9a5a2-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a5a2-192">\<binding></span></span>](../../../misc/binding.md)
