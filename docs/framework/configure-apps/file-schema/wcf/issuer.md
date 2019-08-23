---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929368"
---
# <a name="issuer"></a><span data-ttu-id="d7fb1-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="d7fb1-101">\<issuer></span></span>
<span data-ttu-id="d7fb1-102">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="d7fb1-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d7fb1-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d7fb1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d7fb1-104">\<bindings></span></span>  
<span data-ttu-id="d7fb1-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d7fb1-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="d7fb1-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d7fb1-106">\<binding></span></span>  
<span data-ttu-id="d7fb1-107">\<security></span><span class="sxs-lookup"><span data-stu-id="d7fb1-107">\<security></span></span>  
<span data-ttu-id="d7fb1-108">\<message></span><span class="sxs-lookup"><span data-stu-id="d7fb1-108">\<message></span></span>  
<span data-ttu-id="d7fb1-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="d7fb1-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7fb1-110">구문</span><span class="sxs-lookup"><span data-stu-id="d7fb1-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7fb1-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d7fb1-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7fb1-113">특성</span><span class="sxs-lookup"><span data-stu-id="d7fb1-113">Attributes</span></span>  
  
|<span data-ttu-id="d7fb1-114">특성</span><span class="sxs-lookup"><span data-stu-id="d7fb1-114">Attribute</span></span>|<span data-ttu-id="d7fb1-115">Description</span><span class="sxs-lookup"><span data-stu-id="d7fb1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7fb1-116">주소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-116">address</span></span>|<span data-ttu-id="d7fb1-117">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-117">Required string.</span></span> <span data-ttu-id="d7fb1-118">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7fb1-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-119">Child Elements</span></span>  
  
|<span data-ttu-id="d7fb1-120">요소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-120">Element</span></span>|<span data-ttu-id="d7fb1-121">Description</span><span class="sxs-lookup"><span data-stu-id="d7fb1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7fb1-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="d7fb1-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d7fb1-123">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="d7fb1-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="d7fb1-124">\<identity></span></span>](identity.md)|<span data-ttu-id="d7fb1-125">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7fb1-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d7fb1-127">요소</span><span class="sxs-lookup"><span data-stu-id="d7fb1-127">Element</span></span>|<span data-ttu-id="d7fb1-128">설명</span><span class="sxs-lookup"><span data-stu-id="d7fb1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7fb1-129">\<message></span><span class="sxs-lookup"><span data-stu-id="d7fb1-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d7fb1-130">WsFederationHttpBinding > 요소에 대 한 [ \<](wsfederationhttpbinding.md) 메시지 수준 보안 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb1-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7fb1-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7fb1-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="d7fb1-132">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="d7fb1-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d7fb1-133">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d7fb1-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d7fb1-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="d7fb1-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d7fb1-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d7fb1-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d7fb1-136">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="d7fb1-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d7fb1-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="d7fb1-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
