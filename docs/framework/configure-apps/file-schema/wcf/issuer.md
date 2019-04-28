---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756262"
---
# <a name="issuer"></a><span data-ttu-id="5b656-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="5b656-101">\<issuer></span></span>
<span data-ttu-id="5b656-102">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="5b656-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5b656-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5b656-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5b656-104">\<bindings></span></span>  
<span data-ttu-id="5b656-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5b656-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="5b656-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5b656-106">\<binding></span></span>  
<span data-ttu-id="5b656-107">\<security></span><span class="sxs-lookup"><span data-stu-id="5b656-107">\<security></span></span>  
<span data-ttu-id="5b656-108">\<message></span><span class="sxs-lookup"><span data-stu-id="5b656-108">\<message></span></span>  
<span data-ttu-id="5b656-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="5b656-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b656-110">구문</span><span class="sxs-lookup"><span data-stu-id="5b656-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b656-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5b656-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5b656-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b656-113">특성</span><span class="sxs-lookup"><span data-stu-id="5b656-113">Attributes</span></span>  
  
|<span data-ttu-id="5b656-114">특성</span><span class="sxs-lookup"><span data-stu-id="5b656-114">Attribute</span></span>|<span data-ttu-id="5b656-115">설명</span><span class="sxs-lookup"><span data-stu-id="5b656-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b656-116">주소</span><span class="sxs-lookup"><span data-stu-id="5b656-116">address</span></span>|<span data-ttu-id="5b656-117">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-117">Required string.</span></span> <span data-ttu-id="5b656-118">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b656-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b656-119">Child Elements</span></span>  
  
|<span data-ttu-id="5b656-120">요소</span><span class="sxs-lookup"><span data-stu-id="5b656-120">Element</span></span>|<span data-ttu-id="5b656-121">설명</span><span class="sxs-lookup"><span data-stu-id="5b656-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b656-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="5b656-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="5b656-123">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="5b656-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="5b656-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="5b656-125">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b656-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b656-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5b656-127">요소</span><span class="sxs-lookup"><span data-stu-id="5b656-127">Element</span></span>|<span data-ttu-id="5b656-128">설명</span><span class="sxs-lookup"><span data-stu-id="5b656-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b656-129">\<message></span><span class="sxs-lookup"><span data-stu-id="5b656-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="5b656-130">에 대 한 메시지 수준 보안 설정을 정의 합니다 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b656-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b656-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="5b656-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="5b656-132">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="5b656-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5b656-133">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5b656-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5b656-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="5b656-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5b656-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5b656-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5b656-136">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="5b656-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="5b656-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="5b656-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
