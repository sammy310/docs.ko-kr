---
title: <message>의 요소<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: e26e1f94fb38e0654fd0bc9f06c6096a488bccfe
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400274"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="69797-102">\<wsFederationHttpBinding >의 \<메시지 > 요소</span><span class="sxs-lookup"><span data-stu-id="69797-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="69797-103">WsFederationHttpBinding >에 대 한 [ \<](wsfederationhttpbinding.md)메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="69797-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69797-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69797-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="69797-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="69797-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="69797-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="69797-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="69797-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="69797-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="69797-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="69797-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="69797-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="69797-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<메시지 >**</span><span class="sxs-lookup"><span data-stu-id="69797-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69797-111">구문</span><span class="sxs-lookup"><span data-stu-id="69797-111">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69797-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="69797-112">Attributes and Elements</span></span>  
 <span data-ttu-id="69797-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69797-114">특성</span><span class="sxs-lookup"><span data-stu-id="69797-114">Attributes</span></span>  
  
|<span data-ttu-id="69797-115">특성</span><span class="sxs-lookup"><span data-stu-id="69797-115">Attribute</span></span>|<span data-ttu-id="69797-116">Description</span><span class="sxs-lookup"><span data-stu-id="69797-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69797-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="69797-117">algorithmSuite</span></span>|<span data-ttu-id="69797-118">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="69797-119">이 특성의 유효한 값은 "algorithmSuite 특성" 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69797-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="69797-120">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="69797-121">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="69797-122">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="69797-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="69797-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="69797-123">issuedKeyType</span></span>|<span data-ttu-id="69797-124">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="69797-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69797-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="69797-126">-   SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="69797-126">-   SymmetricKey</span></span><br /><span data-ttu-id="69797-127">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="69797-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="69797-128">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="69797-129">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="69797-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="69797-130">issuedTokenType</span></span>|<span data-ttu-id="69797-131">발급될 토큰 형식을 지정하는 URI가 들어 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="69797-132">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-132">The default is `null`.</span></span>|  
|<span data-ttu-id="69797-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="69797-133">negotiateServiceCredential</span></span>|<span data-ttu-id="69797-134">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="69797-135">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="69797-136">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="69797-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="69797-137">값</span><span class="sxs-lookup"><span data-stu-id="69797-137">Value</span></span>|<span data-ttu-id="69797-138">Description</span><span class="sxs-lookup"><span data-stu-id="69797-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69797-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="69797-139">Basic128</span></span>|<span data-ttu-id="69797-140">Basic128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="69797-141">Basic192</span></span>|<span data-ttu-id="69797-142">Basic192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="69797-143">Basic256</span></span>|<span data-ttu-id="69797-144">Basic256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-145">Basic256Rsa15</span></span>|<span data-ttu-id="69797-146">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-147">Basic192Rsa15</span></span>|<span data-ttu-id="69797-148">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="69797-149">TripleDes</span></span>|<span data-ttu-id="69797-150">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-151">Basic128Rsa15</span></span>|<span data-ttu-id="69797-152">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="69797-153">TripleDesRsa15</span></span>|<span data-ttu-id="69797-154">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="69797-155">Basic128Sha256</span></span>|<span data-ttu-id="69797-156">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="69797-157">Basic192Sha256</span></span>|<span data-ttu-id="69797-158">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="69797-159">Basic256Sha256</span></span>|<span data-ttu-id="69797-160">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="69797-161">TripleDesSha256</span></span>|<span data-ttu-id="69797-162">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="69797-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="69797-164">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="69797-166">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="69797-168">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="69797-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="69797-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="69797-170">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69797-171">자식 요소</span><span class="sxs-lookup"><span data-stu-id="69797-171">Child Elements</span></span>  
  
|<span data-ttu-id="69797-172">요소</span><span class="sxs-lookup"><span data-stu-id="69797-172">Element</span></span>|<span data-ttu-id="69797-173">Description</span><span class="sxs-lookup"><span data-stu-id="69797-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69797-174">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="69797-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="69797-175">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="69797-176">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="69797-177">issuer</span><span class="sxs-lookup"><span data-stu-id="69797-177">issuer</span></span>|<span data-ttu-id="69797-178">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="69797-179">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="69797-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="69797-180">issuerMetadata</span></span>|<span data-ttu-id="69797-181">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="69797-182">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="69797-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="69797-183">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-183">A collection of token request parameters.</span></span> <span data-ttu-id="69797-184">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="69797-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69797-185">부모 요소</span><span class="sxs-lookup"><span data-stu-id="69797-185">Parent Elements</span></span>  
  
|<span data-ttu-id="69797-186">요소</span><span class="sxs-lookup"><span data-stu-id="69797-186">Element</span></span>|<span data-ttu-id="69797-187">설명</span><span class="sxs-lookup"><span data-stu-id="69797-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69797-188">\<security></span><span class="sxs-lookup"><span data-stu-id="69797-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="69797-189">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69797-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69797-190">참고자료</span><span class="sxs-lookup"><span data-stu-id="69797-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="69797-191">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="69797-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="69797-192">바인딩</span><span class="sxs-lookup"><span data-stu-id="69797-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="69797-193">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="69797-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69797-194">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="69797-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="69797-195">\<binding></span><span class="sxs-lookup"><span data-stu-id="69797-195">\<binding></span></span>](../../../misc/binding.md)
