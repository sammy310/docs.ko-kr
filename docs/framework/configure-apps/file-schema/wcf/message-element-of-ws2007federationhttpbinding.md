---
title: <message> 의 요소 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: d71bce5e94568bdad3c52226fa1029a1dd87bfd9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204920"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="5e6dd-102">\<message> 의 요소 \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5e6dd-102">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="5e6dd-103">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5e6dd-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="5e6dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e6dd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e6dd-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5e6dd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5e6dd-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e6dd-107">특성</span><span class="sxs-lookup"><span data-stu-id="5e6dd-107">Attributes</span></span>  
  
|<span data-ttu-id="5e6dd-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5e6dd-108">Attribute</span></span>|<span data-ttu-id="5e6dd-109">설명</span><span class="sxs-lookup"><span data-stu-id="5e6dd-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="5e6dd-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-110">Optional.</span></span> <span data-ttu-id="5e6dd-111">메시지 암호화, 시그니처 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="5e6dd-112">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="5e6dd-113">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="5e6dd-114">사용 가능한 값은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-114">See the following table for possible values.</span></span> <span data-ttu-id="5e6dd-115">기본값은 Basic256입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="5e6dd-116">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="5e6dd-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e6dd-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="5e6dd-118">-   SymmetricKey</span></span><br /><span data-ttu-id="5e6dd-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="5e6dd-119">-   PublicKey</span></span><br /><span data-ttu-id="5e6dd-120">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="5e6dd-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="5e6dd-121">기본값은 SymmetricKey입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-121">The default is SymmetricKey.</span></span> <span data-ttu-id="5e6dd-122">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="5e6dd-123">발급할 토큰의 형식을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="5e6dd-124">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="5e6dd-125">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="5e6dd-126">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="5e6dd-127">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="5e6dd-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="5e6dd-128">Value</span><span class="sxs-lookup"><span data-stu-id="5e6dd-128">Value</span></span>|<span data-ttu-id="5e6dd-129">설명</span><span class="sxs-lookup"><span data-stu-id="5e6dd-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e6dd-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="5e6dd-130">Basic128</span></span>|<span data-ttu-id="5e6dd-131">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="5e6dd-132">Basic192</span></span>|<span data-ttu-id="5e6dd-133">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="5e6dd-134">Basic256</span></span>|<span data-ttu-id="5e6dd-135">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-136">Basic256Rsa15</span></span>|<span data-ttu-id="5e6dd-137">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-138">Basic192Rsa15</span></span>|<span data-ttu-id="5e6dd-139">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="5e6dd-140">TripleDes</span></span>|<span data-ttu-id="5e6dd-141">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-142">Basic128Rsa15</span></span>|<span data-ttu-id="5e6dd-143">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-144">TripleDesRsa15</span></span>|<span data-ttu-id="5e6dd-145">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="5e6dd-146">Basic128Sha256</span></span>|<span data-ttu-id="5e6dd-147">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="5e6dd-148">Basic192Sha256</span></span>|<span data-ttu-id="5e6dd-149">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="5e6dd-150">Basic256Sha256</span></span>|<span data-ttu-id="5e6dd-151">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="5e6dd-152">TripleDesSha256</span></span>|<span data-ttu-id="5e6dd-153">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="5e6dd-155">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="5e6dd-157">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="5e6dd-159">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5e6dd-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5e6dd-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="5e6dd-161">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e6dd-162">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5e6dd-162">Child Elements</span></span>  
  
|<span data-ttu-id="5e6dd-163">요소</span><span class="sxs-lookup"><span data-stu-id="5e6dd-163">Element</span></span>|<span data-ttu-id="5e6dd-164">설명</span><span class="sxs-lookup"><span data-stu-id="5e6dd-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="5e6dd-165">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="5e6dd-166">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="5e6dd-167">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="5e6dd-168">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="5e6dd-169">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="5e6dd-170">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-170">A collection of token request parameters.</span></span> <span data-ttu-id="5e6dd-171">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e6dd-172">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5e6dd-172">Parent Elements</span></span>  
  
|<span data-ttu-id="5e6dd-173">요소</span><span class="sxs-lookup"><span data-stu-id="5e6dd-173">Element</span></span>|<span data-ttu-id="5e6dd-174">설명</span><span class="sxs-lookup"><span data-stu-id="5e6dd-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="5e6dd-175">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e6dd-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e6dd-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e6dd-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="5e6dd-177">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5e6dd-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5e6dd-178">바인딩하</span><span class="sxs-lookup"><span data-stu-id="5e6dd-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5e6dd-179">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5e6dd-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5e6dd-180">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5e6dd-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
