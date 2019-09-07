---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397889"
---
# <a name="issuermetadata"></a><span data-ttu-id="c8cb8-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="c8cb8-101">\<issuerMetadata></span></span>

<span data-ttu-id="c8cb8-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8cb8-103">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8cb8-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c8cb8-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c8cb8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="c8cb8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c8cb8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c8cb8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메시지 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c8cb8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c8cb8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="c8cb8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cb8-110">구문</span><span class="sxs-lookup"><span data-stu-id="c8cb8-110">Syntax</span></span>  
  
```xml  
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
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8cb8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c8cb8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8cb8-113">특성</span><span class="sxs-lookup"><span data-stu-id="c8cb8-113">Attributes</span></span>  
  
|<span data-ttu-id="c8cb8-114">특성</span><span class="sxs-lookup"><span data-stu-id="c8cb8-114">Attribute</span></span>|<span data-ttu-id="c8cb8-115">Description</span><span class="sxs-lookup"><span data-stu-id="c8cb8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8cb8-116">주소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-116">address</span></span>|<span data-ttu-id="c8cb8-117">필수 `string` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="c8cb8-118">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="c8cb8-119">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-119">The address must be an absolute URI.</span></span> <span data-ttu-id="c8cb8-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8cb8-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-121">Child Elements</span></span>  
  
|<span data-ttu-id="c8cb8-122">요소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-122">Element</span></span>|<span data-ttu-id="c8cb8-123">Description</span><span class="sxs-lookup"><span data-stu-id="c8cb8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8cb8-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="c8cb8-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="c8cb8-125">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="c8cb8-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="c8cb8-126">\<identity></span></span>](identity.md)|<span data-ttu-id="c8cb8-127">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8cb8-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c8cb8-129">요소</span><span class="sxs-lookup"><span data-stu-id="c8cb8-129">Element</span></span>|<span data-ttu-id="c8cb8-130">설명</span><span class="sxs-lookup"><span data-stu-id="c8cb8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8cb8-131">\<message></span><span class="sxs-lookup"><span data-stu-id="c8cb8-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c8cb8-132">WsFederationHttpBinding > 요소에 대 한 [ \<](wsfederationhttpbinding.md) 메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8cb8-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8cb8-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8cb8-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="c8cb8-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="c8cb8-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c8cb8-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c8cb8-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c8cb8-136">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="c8cb8-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c8cb8-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c8cb8-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
