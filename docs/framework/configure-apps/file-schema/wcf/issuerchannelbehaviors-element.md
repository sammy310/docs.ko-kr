---
description: '다음에 대 한 자세한 정보: <issuerChannelBehaviors> 요소'
title: <issuerChannelBehaviors> 요소
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: 6be79f2ee6afb442a7a399ce49df4ad59dff2db5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725547"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="b95e2-103">\::: no loc ( <issuerChannelBehaviors> )::: 요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-103">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="b95e2-104">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작 (구성에 정의 됨)의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-104">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="b95e2-105">정의 된 동작에는: [ \: : no loc ( <clientCredentials> ):::](clientcredentials.md) 요소가 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-105">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
<span data-ttu-id="b95e2-106">&nbsp;&nbsp;[\::: no loc (<System.servicemodel>):::](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-106">&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)</span></span>\
<span data-ttu-id="b95e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[\::: no loc ( <behaviors> ):::](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)</span></span>\
<span data-ttu-id="b95e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no loc ( <endpointBehaviors> ):::](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b95e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no loc ( <behavior> ):::](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b95e2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no loc ( <clientCredentials> ):::](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)</span></span>\
<span data-ttu-id="b95e2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\::: no loc ( <issuedToken> ):::](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="b95e2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)</span></span>\
<span data-ttu-id="b95e2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\::: no loc ( <issuerChannelBehaviors> ):::</span><span class="sxs-lookup"><span data-stu-id="b95e2-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="b95e2-113">구문</span><span class="sxs-lookup"><span data-stu-id="b95e2-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b95e2-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-114">Attributes and elements</span></span>

<span data-ttu-id="b95e2-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b95e2-116">특성</span><span class="sxs-lookup"><span data-stu-id="b95e2-116">Attributes</span></span>

<span data-ttu-id="b95e2-117">없음</span><span class="sxs-lookup"><span data-stu-id="b95e2-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b95e2-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-118">Child elements</span></span>

|<span data-ttu-id="b95e2-119">요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-119">Element</span></span>|<span data-ttu-id="b95e2-120">설명</span><span class="sxs-lookup"><span data-stu-id="b95e2-120">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="b95e2-121">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-121">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b95e2-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-122">Parent elements</span></span>

|<span data-ttu-id="b95e2-123">요소</span><span class="sxs-lookup"><span data-stu-id="b95e2-123">Element</span></span>|<span data-ttu-id="b95e2-124">설명</span><span class="sxs-lookup"><span data-stu-id="b95e2-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b95e2-125">\::: no loc ( <issuedToken> ):::</span><span class="sxs-lookup"><span data-stu-id="b95e2-125">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="b95e2-126">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-126">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b95e2-127">설명</span><span class="sxs-lookup"><span data-stu-id="b95e2-127">Remarks</span></span>

<span data-ttu-id="b95e2-128">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="b95e2-129">예를 들어:: [ \: no loc ( <dataContractSerializer> ):::](datacontractserializer-element.md) behavior 요소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b95e2-129">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="b95e2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b95e2-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="b95e2-131">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="b95e2-131">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b95e2-132">보안 동작</span><span class="sxs-lookup"><span data-stu-id="b95e2-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b95e2-133">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="b95e2-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b95e2-134">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b95e2-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b95e2-135">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b95e2-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b95e2-136">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="b95e2-136">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="b95e2-137">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="b95e2-137">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="b95e2-138">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="b95e2-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
