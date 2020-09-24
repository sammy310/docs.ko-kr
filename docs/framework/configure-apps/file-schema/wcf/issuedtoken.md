---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9f3feb11fbe45cbb4b952c70feaa99f9c481dd2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157371"
---
# \<issuedToken>

<span data-ttu-id="0696f-101">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-101">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
## <a name="syntax"></a><span data-ttu-id="0696f-102">구문</span><span class="sxs-lookup"><span data-stu-id="0696f-102">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0696f-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0696f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0696f-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0696f-105">특성</span><span class="sxs-lookup"><span data-stu-id="0696f-105">Attributes</span></span>  
  
|<span data-ttu-id="0696f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0696f-106">Attribute</span></span>|<span data-ttu-id="0696f-107">설명</span><span class="sxs-lookup"><span data-stu-id="0696f-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="0696f-108">토큰이 캐시되는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-108">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="0696f-109">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-109">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="0696f-110">핸드셰이크 작업에 사용되는 임의의 값(엔트로피)을 지정하는 선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-110">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="0696f-111">값에는 `ClientEntropy`, `ServerEntropy` 및 `CombinedEntropy`가 포함되며, 기본값은 `CombinedEntropy`입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-111">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="0696f-112">이 특성은 <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="0696f-113">토큰을 갱신하기 전에 경과할 수 있는 유효한 기간(토큰 발급자가 제공)의 백분율을 지정하는 선택적 정수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-113">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="0696f-114">값은 0부터 100까지이며,</span><span class="sxs-lookup"><span data-stu-id="0696f-114">Values are from 0 to 100.</span></span> <span data-ttu-id="0696f-115">기본값은 갱신을 시도하기 전에 60%의 시간 경과를 지정하는 60입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-115">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="0696f-116">발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-116">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="0696f-117">로컬 발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-117">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="0696f-118">토큰 발급자(STS)가 시간을 지정하지 않은 경우 발급된 토큰이 캐시되는 기간을 지정하는 선택적 Timespan 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-118">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="0696f-119">기본값은 "10675199.02:48:05.4775807"입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-119">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0696f-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0696f-120">Child Elements</span></span>  
  
|<span data-ttu-id="0696f-121">요소</span><span class="sxs-lookup"><span data-stu-id="0696f-121">Element</span></span>|<span data-ttu-id="0696f-122">설명</span><span class="sxs-lookup"><span data-stu-id="0696f-122">Description</span></span>|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="0696f-123">엔드포인트와의 통신에 사용되는 토큰 및 바인딩의 로컬 발급자 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-123">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="0696f-124">로컬 발급자에 연결할 때 사용할 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-124">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0696f-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0696f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0696f-126">요소</span><span class="sxs-lookup"><span data-stu-id="0696f-126">Element</span></span>|<span data-ttu-id="0696f-127">설명</span><span class="sxs-lookup"><span data-stu-id="0696f-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="0696f-128">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-128">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0696f-129">설명</span><span class="sxs-lookup"><span data-stu-id="0696f-129">Remarks</span></span>  

 <span data-ttu-id="0696f-130">발급된 토큰은 사용자 지정 자격 증명 형식으로, 예를 들어 페더레이션 시나리오에서 STS(보안 토큰 서비스)를 사용하여 인증할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-130">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="0696f-131">기본적으로 토큰은 SAML 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-131">By default, the token is a SAML token.</span></span> <span data-ttu-id="0696f-132">자세한 내용은 [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md), [페더레이션 및 발급 된 토큰](../../../wcf/feature-details/federation-and-issued-tokens.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0696f-132">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md), and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="0696f-133">이 섹션에는 토큰 로컬 발급자를 구성하는 데 사용되는 요소 또는 보안 토큰 서비스에서 사용되는 동작이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0696f-133">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="0696f-134">로컬 발급자를 사용 하도록 클라이언트를 구성 하는 방법에 대 한 지침은 [방법: 로컬 발급자 구성](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0696f-134">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0696f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0696f-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="0696f-136">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0696f-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0696f-137">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0696f-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0696f-138">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0696f-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0696f-139">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0696f-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0696f-140">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0696f-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0696f-141">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="0696f-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0696f-142">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0696f-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
