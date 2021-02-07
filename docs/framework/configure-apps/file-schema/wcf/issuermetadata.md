---
description: 다음에 대해 자세히 알아보세요. <issuerMetadata>
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 86671b6b704f5753cf4bd45c2dfd90a368070b22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725534"
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
  
## <a name="syntax"></a><span data-ttu-id="22d26-102">구문</span><span class="sxs-lookup"><span data-stu-id="22d26-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22d26-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="22d26-103">Attributes and Elements</span></span>  

 <span data-ttu-id="22d26-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22d26-105">특성</span><span class="sxs-lookup"><span data-stu-id="22d26-105">Attributes</span></span>  
  
|<span data-ttu-id="22d26-106">attribute</span><span class="sxs-lookup"><span data-stu-id="22d26-106">Attribute</span></span>|<span data-ttu-id="22d26-107">설명</span><span class="sxs-lookup"><span data-stu-id="22d26-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22d26-108">address</span><span class="sxs-lookup"><span data-stu-id="22d26-108">address</span></span>|<span data-ttu-id="22d26-109">필수 `string` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-109">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="22d26-110">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-110">Specifies the address of the endpoint.</span></span> <span data-ttu-id="22d26-111">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-111">The address must be an absolute URI.</span></span> <span data-ttu-id="22d26-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-112">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22d26-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="22d26-113">Child Elements</span></span>  
  
|<span data-ttu-id="22d26-114">요소</span><span class="sxs-lookup"><span data-stu-id="22d26-114">Element</span></span>|<span data-ttu-id="22d26-115">설명</span><span class="sxs-lookup"><span data-stu-id="22d26-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="22d26-116">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-116">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="22d26-117">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="22d26-117">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22d26-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="22d26-118">Parent Elements</span></span>  
  
|<span data-ttu-id="22d26-119">요소</span><span class="sxs-lookup"><span data-stu-id="22d26-119">Element</span></span>|<span data-ttu-id="22d26-120">설명</span><span class="sxs-lookup"><span data-stu-id="22d26-120">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="22d26-121">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="22d26-121">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22d26-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22d26-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="22d26-123">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="22d26-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="22d26-124">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="22d26-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="22d26-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="22d26-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="22d26-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="22d26-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
