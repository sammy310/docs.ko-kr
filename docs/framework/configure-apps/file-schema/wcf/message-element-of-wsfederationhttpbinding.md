---
title: <message> 의 요소 <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: ea320b1d97e742d4f90ec55502f3bd429803283d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204894"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="e6f1e-102">\<message> 의 요소 \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e6f1e-102">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="e6f1e-103">의 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e6f1e-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="e6f1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6f1e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6f1e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e6f1e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e6f1e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6f1e-107">특성</span><span class="sxs-lookup"><span data-stu-id="e6f1e-107">Attributes</span></span>  
  
|<span data-ttu-id="e6f1e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e6f1e-108">Attribute</span></span>|<span data-ttu-id="e6f1e-109">설명</span><span class="sxs-lookup"><span data-stu-id="e6f1e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6f1e-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="e6f1e-110">algorithmSuite</span></span>|<span data-ttu-id="e6f1e-111">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="e6f1e-112">이 특성의 유효한 값은 "algorithmSuite 특성" 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="e6f1e-113">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="e6f1e-114">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="e6f1e-115">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="e6f1e-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="e6f1e-116">issuedKeyType</span></span>|<span data-ttu-id="e6f1e-117">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="e6f1e-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e6f1e-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="e6f1e-119">-   SymmetricKey</span></span><br /><span data-ttu-id="e6f1e-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="e6f1e-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="e6f1e-121">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="e6f1e-122">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="e6f1e-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="e6f1e-123">issuedTokenType</span></span>|<span data-ttu-id="e6f1e-124">발급될 토큰 형식을 지정하는 URI가 들어 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="e6f1e-125">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-125">The default is `null`.</span></span>|  
|<span data-ttu-id="e6f1e-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="e6f1e-126">negotiateServiceCredential</span></span>|<span data-ttu-id="e6f1e-127">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="e6f1e-128">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="e6f1e-129">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="e6f1e-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="e6f1e-130">Value</span><span class="sxs-lookup"><span data-stu-id="e6f1e-130">Value</span></span>|<span data-ttu-id="e6f1e-131">설명</span><span class="sxs-lookup"><span data-stu-id="e6f1e-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6f1e-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="e6f1e-132">Basic128</span></span>|<span data-ttu-id="e6f1e-133">Basic128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="e6f1e-134">Basic192</span></span>|<span data-ttu-id="e6f1e-135">Basic192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="e6f1e-136">Basic256</span></span>|<span data-ttu-id="e6f1e-137">Basic256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-138">Basic256Rsa15</span></span>|<span data-ttu-id="e6f1e-139">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-140">Basic192Rsa15</span></span>|<span data-ttu-id="e6f1e-141">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="e6f1e-142">TripleDes</span></span>|<span data-ttu-id="e6f1e-143">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-144">Basic128Rsa15</span></span>|<span data-ttu-id="e6f1e-145">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-146">TripleDesRsa15</span></span>|<span data-ttu-id="e6f1e-147">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="e6f1e-148">Basic128Sha256</span></span>|<span data-ttu-id="e6f1e-149">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="e6f1e-150">Basic192Sha256</span></span>|<span data-ttu-id="e6f1e-151">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="e6f1e-152">Basic256Sha256</span></span>|<span data-ttu-id="e6f1e-153">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="e6f1e-154">TripleDesSha256</span></span>|<span data-ttu-id="e6f1e-155">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="e6f1e-157">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="e6f1e-159">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="e6f1e-161">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e6f1e-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e6f1e-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="e6f1e-163">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6f1e-164">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e6f1e-164">Child Elements</span></span>  
  
|<span data-ttu-id="e6f1e-165">요소</span><span class="sxs-lookup"><span data-stu-id="e6f1e-165">Element</span></span>|<span data-ttu-id="e6f1e-166">설명</span><span class="sxs-lookup"><span data-stu-id="e6f1e-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="e6f1e-167">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="e6f1e-168">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="e6f1e-169">발급자</span><span class="sxs-lookup"><span data-stu-id="e6f1e-169">issuer</span></span>|<span data-ttu-id="e6f1e-170">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="e6f1e-171">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="e6f1e-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="e6f1e-172">issuerMetadata</span></span>|<span data-ttu-id="e6f1e-173">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="e6f1e-174">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-174">A collection of token request parameters.</span></span> <span data-ttu-id="e6f1e-175">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6f1e-176">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e6f1e-176">Parent Elements</span></span>  
  
|<span data-ttu-id="e6f1e-177">요소</span><span class="sxs-lookup"><span data-stu-id="e6f1e-177">Element</span></span>|<span data-ttu-id="e6f1e-178">설명</span><span class="sxs-lookup"><span data-stu-id="e6f1e-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="e6f1e-179">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6f1e-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6f1e-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="e6f1e-181">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e6f1e-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e6f1e-182">바인딩하</span><span class="sxs-lookup"><span data-stu-id="e6f1e-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e6f1e-183">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="e6f1e-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e6f1e-184">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="e6f1e-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
