---
description: '자세히 알아보기: <message> 의 요소 <wsFederationHttpBinding>'
title: <message> 의 요소 <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 64978902081ec9e5a603804fed3b378da12fe42e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802192"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="ac151-103">\<message> 의 요소 \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ac151-103">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="ac151-104">의 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ac151-104">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="ac151-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac151-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac151-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ac151-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ac151-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac151-108">특성</span><span class="sxs-lookup"><span data-stu-id="ac151-108">Attributes</span></span>  
  
|<span data-ttu-id="ac151-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ac151-109">Attribute</span></span>|<span data-ttu-id="ac151-110">설명</span><span class="sxs-lookup"><span data-stu-id="ac151-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac151-111">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ac151-111">algorithmSuite</span></span>|<span data-ttu-id="ac151-112">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-112">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="ac151-113">이 특성의 유효한 값은 "algorithmSuite 특성" 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac151-113">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="ac151-114">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-114">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="ac151-115">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-115">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="ac151-116">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-116">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="ac151-117">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="ac151-117">issuedKeyType</span></span>|<span data-ttu-id="ac151-118">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-118">Specifies the type of key to be issued.</span></span> <span data-ttu-id="ac151-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ac151-120">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="ac151-120">-   SymmetricKey</span></span><br /><span data-ttu-id="ac151-121">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="ac151-121">-   PublicKey</span></span><br /><br /> <span data-ttu-id="ac151-122">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-122">The default is `SymmetricKey`.</span></span> <span data-ttu-id="ac151-123">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-123">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="ac151-124">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="ac151-124">issuedTokenType</span></span>|<span data-ttu-id="ac151-125">발급될 토큰 형식을 지정하는 URI가 들어 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-125">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="ac151-126">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-126">The default is `null`.</span></span>|  
|<span data-ttu-id="ac151-127">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="ac151-127">negotiateServiceCredential</span></span>|<span data-ttu-id="ac151-128">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-128">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="ac151-129">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-129">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="ac151-130">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="ac151-130">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="ac151-131">값</span><span class="sxs-lookup"><span data-stu-id="ac151-131">Value</span></span>|<span data-ttu-id="ac151-132">설명</span><span class="sxs-lookup"><span data-stu-id="ac151-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ac151-133">Basic128</span><span class="sxs-lookup"><span data-stu-id="ac151-133">Basic128</span></span>|<span data-ttu-id="ac151-134">Basic128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-134">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-135">Basic192</span><span class="sxs-lookup"><span data-stu-id="ac151-135">Basic192</span></span>|<span data-ttu-id="ac151-136">Basic192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-136">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-137">Basic256</span><span class="sxs-lookup"><span data-stu-id="ac151-137">Basic256</span></span>|<span data-ttu-id="ac151-138">Basic256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-138">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-139">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-139">Basic256Rsa15</span></span>|<span data-ttu-id="ac151-140">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-140">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-141">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-141">Basic192Rsa15</span></span>|<span data-ttu-id="ac151-142">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-142">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-143">TripleDes</span><span class="sxs-lookup"><span data-stu-id="ac151-143">TripleDes</span></span>|<span data-ttu-id="ac151-144">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-144">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-145">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-145">Basic128Rsa15</span></span>|<span data-ttu-id="ac151-146">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-146">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-147">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-147">TripleDesRsa15</span></span>|<span data-ttu-id="ac151-148">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-148">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-149">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="ac151-149">Basic128Sha256</span></span>|<span data-ttu-id="ac151-150">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-150">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-151">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="ac151-151">Basic192Sha256</span></span>|<span data-ttu-id="ac151-152">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-152">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-153">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="ac151-153">Basic256Sha256</span></span>|<span data-ttu-id="ac151-154">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-154">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-155">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="ac151-155">TripleDesSha256</span></span>|<span data-ttu-id="ac151-156">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-156">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ac151-157">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-157">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="ac151-158">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-158">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-159">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-159">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="ac151-160">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-160">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-161">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-161">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="ac151-162">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-162">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ac151-163">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ac151-163">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="ac151-164">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-164">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac151-165">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac151-165">Child Elements</span></span>  
  
|<span data-ttu-id="ac151-166">요소</span><span class="sxs-lookup"><span data-stu-id="ac151-166">Element</span></span>|<span data-ttu-id="ac151-167">설명</span><span class="sxs-lookup"><span data-stu-id="ac151-167">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="ac151-168">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-168">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="ac151-169">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-169">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="ac151-170">발급자</span><span class="sxs-lookup"><span data-stu-id="ac151-170">issuer</span></span>|<span data-ttu-id="ac151-171">보안 토큰을 발급하는 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-171">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="ac151-172">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-172">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="ac151-173">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="ac151-173">issuerMetadata</span></span>|<span data-ttu-id="ac151-174">발급자의 엔드포인트 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-174">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="ac151-175">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-175">A collection of token request parameters.</span></span> <span data-ttu-id="ac151-176">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-176">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac151-177">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac151-177">Parent Elements</span></span>  
  
|<span data-ttu-id="ac151-178">요소</span><span class="sxs-lookup"><span data-stu-id="ac151-178">Element</span></span>|<span data-ttu-id="ac151-179">설명</span><span class="sxs-lookup"><span data-stu-id="ac151-179">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="ac151-180">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ac151-180">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac151-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac151-181">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="ac151-182">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ac151-182">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ac151-183">바인딩</span><span class="sxs-lookup"><span data-stu-id="ac151-183">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ac151-184">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="ac151-184">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ac151-185">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ac151-185">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
