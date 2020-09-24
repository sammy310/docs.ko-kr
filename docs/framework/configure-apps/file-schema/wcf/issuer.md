---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 9e92bbcacf529a97e1ae936e93e38c98eab19cab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157267"
---
# \<issuer>

<span data-ttu-id="8e225-101">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="8e225-102">구문</span><span class="sxs-lookup"><span data-stu-id="8e225-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e225-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e225-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8e225-104">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e225-105">특성</span><span class="sxs-lookup"><span data-stu-id="8e225-105">Attributes</span></span>  
  
|<span data-ttu-id="8e225-106">attribute</span><span class="sxs-lookup"><span data-stu-id="8e225-106">Attribute</span></span>|<span data-ttu-id="8e225-107">설명</span><span class="sxs-lookup"><span data-stu-id="8e225-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e225-108">address</span><span class="sxs-lookup"><span data-stu-id="8e225-108">address</span></span>|<span data-ttu-id="8e225-109">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-109">Required string.</span></span> <span data-ttu-id="8e225-110">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e225-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e225-111">Child Elements</span></span>  
  
|<span data-ttu-id="8e225-112">요소</span><span class="sxs-lookup"><span data-stu-id="8e225-112">Element</span></span>|<span data-ttu-id="8e225-113">설명</span><span class="sxs-lookup"><span data-stu-id="8e225-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="8e225-114">작성기에서 만들 수 있는 엔드포인트의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="8e225-115">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e225-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e225-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e225-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8e225-117">요소</span><span class="sxs-lookup"><span data-stu-id="8e225-117">Element</span></span>|<span data-ttu-id="8e225-118">설명</span><span class="sxs-lookup"><span data-stu-id="8e225-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="8e225-119">요소에 대 한 메시지 수준 보안 설정을 정의 합니다 [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8e225-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e225-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e225-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="8e225-121">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="8e225-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8e225-122">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8e225-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8e225-123">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="8e225-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8e225-124">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8e225-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8e225-125">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="8e225-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8e225-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8e225-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
