---
description: 다음에 대해 자세히 알아보세요. <issuer>
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 771fb8d0bee4e78b598bd20c4d99ec5180f9fb1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725638"
---
# \<issuer>

<span data-ttu-id="729de-102">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="729de-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="729de-103">구문</span><span class="sxs-lookup"><span data-stu-id="729de-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="729de-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="729de-104">Attributes and Elements</span></span>  

 <span data-ttu-id="729de-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="729de-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="729de-106">특성</span><span class="sxs-lookup"><span data-stu-id="729de-106">Attributes</span></span>  
  
|<span data-ttu-id="729de-107">attribute</span><span class="sxs-lookup"><span data-stu-id="729de-107">Attribute</span></span>|<span data-ttu-id="729de-108">설명</span><span class="sxs-lookup"><span data-stu-id="729de-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="729de-109">address</span><span class="sxs-lookup"><span data-stu-id="729de-109">address</span></span>|<span data-ttu-id="729de-110">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="729de-110">Required string.</span></span> <span data-ttu-id="729de-111">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="729de-111">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="729de-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="729de-112">Child Elements</span></span>  
  
|<span data-ttu-id="729de-113">요소</span><span class="sxs-lookup"><span data-stu-id="729de-113">Element</span></span>|<span data-ttu-id="729de-114">설명</span><span class="sxs-lookup"><span data-stu-id="729de-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="729de-115">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="729de-115">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="729de-116">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="729de-116">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="729de-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="729de-117">Parent Elements</span></span>  
  
|<span data-ttu-id="729de-118">요소</span><span class="sxs-lookup"><span data-stu-id="729de-118">Element</span></span>|<span data-ttu-id="729de-119">설명</span><span class="sxs-lookup"><span data-stu-id="729de-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="729de-120">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="729de-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="729de-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="729de-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="729de-122">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="729de-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="729de-123">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="729de-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="729de-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="729de-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="729de-125">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="729de-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="729de-126">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="729de-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="729de-127">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="729de-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
