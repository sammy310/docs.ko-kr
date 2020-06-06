---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397889"
---
# \<issuerMetadata>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="ebfa6-101">구문</span><span class="sxs-lookup"><span data-stu-id="ebfa6-101">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebfa6-102">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ebfa6-102">Attributes and Elements</span></span>  
 <span data-ttu-id="ebfa6-103">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-103">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebfa6-104">특성</span><span class="sxs-lookup"><span data-stu-id="ebfa6-104">Attributes</span></span>  
  
|<span data-ttu-id="ebfa6-105">attribute</span><span class="sxs-lookup"><span data-stu-id="ebfa6-105">Attribute</span></span>|<span data-ttu-id="ebfa6-106">Description</span><span class="sxs-lookup"><span data-stu-id="ebfa6-106">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebfa6-107">address</span><span class="sxs-lookup"><span data-stu-id="ebfa6-107">address</span></span>|<span data-ttu-id="ebfa6-108">필수 `string` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-108">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="ebfa6-109">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-109">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ebfa6-110">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-110">The address must be an absolute URI.</span></span> <span data-ttu-id="ebfa6-111">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-111">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebfa6-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ebfa6-112">Child Elements</span></span>  
  
|<span data-ttu-id="ebfa6-113">요소</span><span class="sxs-lookup"><span data-stu-id="ebfa6-113">Element</span></span>|<span data-ttu-id="ebfa6-114">Description</span><span class="sxs-lookup"><span data-stu-id="ebfa6-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="ebfa6-115">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-115">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="ebfa6-116">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfa6-116">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebfa6-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ebfa6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ebfa6-118">요소</span><span class="sxs-lookup"><span data-stu-id="ebfa6-118">Element</span></span>|<span data-ttu-id="ebfa6-119">Description</span><span class="sxs-lookup"><span data-stu-id="ebfa6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="ebfa6-120">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ebfa6-120">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebfa6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebfa6-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="ebfa6-122">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="ebfa6-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ebfa6-123">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="ebfa6-123">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ebfa6-124">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="ebfa6-124">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ebfa6-125">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="ebfa6-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
