---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397914"
---
# <a name="issuer"></a><span data-ttu-id="2a380-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2a380-101">\<issuer></span></span>
<span data-ttu-id="2a380-102">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="2a380-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a380-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2a380-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2a380-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2a380-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="2a380-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2a380-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2a380-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메시지 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a380-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="2a380-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<발급자 >**</span><span class="sxs-lookup"><span data-stu-id="2a380-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a380-111">구문</span><span class="sxs-lookup"><span data-stu-id="2a380-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a380-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a380-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2a380-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a380-114">특성</span><span class="sxs-lookup"><span data-stu-id="2a380-114">Attributes</span></span>  
  
|<span data-ttu-id="2a380-115">특성</span><span class="sxs-lookup"><span data-stu-id="2a380-115">Attribute</span></span>|<span data-ttu-id="2a380-116">Description</span><span class="sxs-lookup"><span data-stu-id="2a380-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a380-117">주소</span><span class="sxs-lookup"><span data-stu-id="2a380-117">address</span></span>|<span data-ttu-id="2a380-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-118">Required string.</span></span> <span data-ttu-id="2a380-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a380-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a380-120">Child Elements</span></span>  
  
|<span data-ttu-id="2a380-121">요소</span><span class="sxs-lookup"><span data-stu-id="2a380-121">Element</span></span>|<span data-ttu-id="2a380-122">Description</span><span class="sxs-lookup"><span data-stu-id="2a380-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a380-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="2a380-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="2a380-124">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="2a380-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="2a380-125">\<identity></span></span>](identity.md)|<span data-ttu-id="2a380-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a380-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a380-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2a380-128">요소</span><span class="sxs-lookup"><span data-stu-id="2a380-128">Element</span></span>|<span data-ttu-id="2a380-129">설명</span><span class="sxs-lookup"><span data-stu-id="2a380-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a380-130">\<message></span><span class="sxs-lookup"><span data-stu-id="2a380-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="2a380-131">WsFederationHttpBinding > 요소에 대 한 [ \<](wsfederationhttpbinding.md) 메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a380-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a380-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a380-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="2a380-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="2a380-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2a380-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2a380-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2a380-135">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="2a380-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2a380-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2a380-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2a380-137">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="2a380-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2a380-138">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="2a380-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
