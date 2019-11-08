---
title: <ws2007FederationHttpBinding>의 <message> 요소
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739004"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="01a4c-102">\<ws2007FederationHttpBinding의 \<message > 요소 ></span><span class="sxs-lookup"><span data-stu-id="01a4c-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="01a4c-103">[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md) 요소에 대 한 메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="01a4c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01a4c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01a4c-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="01a4c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="01a4c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="01a4c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="01a4c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="01a4c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="01a4c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="01a4c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="01a4c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="01a4c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="01a4c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**메시지 >**</span><span class="sxs-lookup"><span data-stu-id="01a4c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a4c-111">구문</span><span class="sxs-lookup"><span data-stu-id="01a4c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01a4c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="01a4c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="01a4c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01a4c-114">특성</span><span class="sxs-lookup"><span data-stu-id="01a4c-114">Attributes</span></span>  
  
|<span data-ttu-id="01a4c-115">특성</span><span class="sxs-lookup"><span data-stu-id="01a4c-115">Attribute</span></span>|<span data-ttu-id="01a4c-116">설명</span><span class="sxs-lookup"><span data-stu-id="01a4c-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="01a4c-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="01a4c-117">Optional.</span></span> <span data-ttu-id="01a4c-118">메시지 암호화, 시그니처 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="01a4c-119">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="01a4c-120">이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="01a4c-121">사용 가능한 값은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01a4c-121">See the following table for possible values.</span></span> <span data-ttu-id="01a4c-122">기본값은 Basic256입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="01a4c-123">발급할 키의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="01a4c-124">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="01a4c-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="01a4c-125">-   SymmetricKey</span></span><br /><span data-ttu-id="01a4c-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="01a4c-126">-   PublicKey</span></span><br /><span data-ttu-id="01a4c-127">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="01a4c-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="01a4c-128">기본값은 SymmetricKey입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-128">The default is SymmetricKey.</span></span> <span data-ttu-id="01a4c-129">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="01a4c-130">발급할 토큰의 형식을 지정 하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="01a4c-131">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="01a4c-132">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="01a4c-133">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="01a4c-134">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="01a4c-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="01a4c-135">값</span><span class="sxs-lookup"><span data-stu-id="01a4c-135">Value</span></span>|<span data-ttu-id="01a4c-136">설명</span><span class="sxs-lookup"><span data-stu-id="01a4c-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01a4c-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="01a4c-137">Basic128</span></span>|<span data-ttu-id="01a4c-138">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="01a4c-139">Basic192</span></span>|<span data-ttu-id="01a4c-140">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="01a4c-141">Basic256</span></span>|<span data-ttu-id="01a4c-142">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-143">Basic256Rsa15</span></span>|<span data-ttu-id="01a4c-144">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-145">Basic192Rsa15</span></span>|<span data-ttu-id="01a4c-146">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="01a4c-147">TripleDes</span></span>|<span data-ttu-id="01a4c-148">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-149">Basic128Rsa15</span></span>|<span data-ttu-id="01a4c-150">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-151">TripleDesRsa15</span></span>|<span data-ttu-id="01a4c-152">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="01a4c-153">Basic128Sha256</span></span>|<span data-ttu-id="01a4c-154">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="01a4c-155">Basic192Sha256</span></span>|<span data-ttu-id="01a4c-156">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="01a4c-157">Basic256Sha256</span></span>|<span data-ttu-id="01a4c-158">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="01a4c-159">TripleDesSha256</span></span>|<span data-ttu-id="01a4c-160">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="01a4c-162">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="01a4c-164">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="01a4c-166">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="01a4c-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="01a4c-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="01a4c-168">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01a4c-169">자식 요소</span><span class="sxs-lookup"><span data-stu-id="01a4c-169">Child Elements</span></span>  
  
|<span data-ttu-id="01a4c-170">요소</span><span class="sxs-lookup"><span data-stu-id="01a4c-170">Element</span></span>|<span data-ttu-id="01a4c-171">설명</span><span class="sxs-lookup"><span data-stu-id="01a4c-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01a4c-172">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="01a4c-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="01a4c-173">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="01a4c-174">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="01a4c-175">\<발급자 ></span><span class="sxs-lookup"><span data-stu-id="01a4c-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="01a4c-176">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="01a4c-177">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="01a4c-178">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="01a4c-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="01a4c-179">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="01a4c-180">tokenRequestParameters를 \<</span><span class="sxs-lookup"><span data-stu-id="01a4c-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="01a4c-181">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-181">A collection of token request parameters.</span></span> <span data-ttu-id="01a4c-182">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01a4c-183">부모 요소</span><span class="sxs-lookup"><span data-stu-id="01a4c-183">Parent Elements</span></span>  
  
|<span data-ttu-id="01a4c-184">요소</span><span class="sxs-lookup"><span data-stu-id="01a4c-184">Element</span></span>|<span data-ttu-id="01a4c-185">설명</span><span class="sxs-lookup"><span data-stu-id="01a4c-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01a4c-186">\<security ></span><span class="sxs-lookup"><span data-stu-id="01a4c-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="01a4c-187">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01a4c-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01a4c-188">참조</span><span class="sxs-lookup"><span data-stu-id="01a4c-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="01a4c-189">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="01a4c-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="01a4c-190">바인딩</span><span class="sxs-lookup"><span data-stu-id="01a4c-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="01a4c-191">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="01a4c-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="01a4c-192">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="01a4c-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="01a4c-193">\<binding ></span><span class="sxs-lookup"><span data-stu-id="01a4c-193">\<binding></span></span>](bindings.md)
