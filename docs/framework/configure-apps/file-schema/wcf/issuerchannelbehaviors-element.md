---
title: <issuerChannelBehaviors> 요소
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397895"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="4410c-102">\<issuerChannelBehaviors > 요소</span><span class="sxs-lookup"><span data-stu-id="4410c-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="4410c-103">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작 (구성에 정의 됨)의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="4410c-104">정의 된 동작을 포함할 수 없습니다 [\<clientCredentials>](clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="4410c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4410c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4410c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4410c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4410c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4410c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="4410c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="4410c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="4410c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerChannelBehaviors >**</span><span class="sxs-lookup"><span data-stu-id="4410c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="4410c-113">구문</span><span class="sxs-lookup"><span data-stu-id="4410c-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4410c-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4410c-114">Attributes and Elements</span></span>

<span data-ttu-id="4410c-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4410c-116">특성</span><span class="sxs-lookup"><span data-stu-id="4410c-116">Attributes</span></span>

<span data-ttu-id="4410c-117">없음</span><span class="sxs-lookup"><span data-stu-id="4410c-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4410c-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4410c-118">Child Elements</span></span>

|<span data-ttu-id="4410c-119">요소</span><span class="sxs-lookup"><span data-stu-id="4410c-119">Element</span></span>|<span data-ttu-id="4410c-120">설명</span><span class="sxs-lookup"><span data-stu-id="4410c-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4410c-121">\<add></span><span class="sxs-lookup"><span data-stu-id="4410c-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="4410c-122">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4410c-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4410c-123">Parent Elements</span></span>

|<span data-ttu-id="4410c-124">요소</span><span class="sxs-lookup"><span data-stu-id="4410c-124">Element</span></span>|<span data-ttu-id="4410c-125">설명</span><span class="sxs-lookup"><span data-stu-id="4410c-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4410c-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="4410c-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="4410c-127">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4410c-128">설명</span><span class="sxs-lookup"><span data-stu-id="4410c-128">Remarks</span></span>

<span data-ttu-id="4410c-129">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="4410c-130">예를 들어 경우는 [\<dataContractSerializer >](datacontractserializer-element.md) 동작 요소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4410c-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="4410c-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="4410c-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="4410c-132">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="4410c-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4410c-133">보안 동작</span><span class="sxs-lookup"><span data-stu-id="4410c-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="4410c-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="4410c-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4410c-135">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="4410c-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4410c-136">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="4410c-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="4410c-137">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="4410c-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="4410c-138">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="4410c-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="4410c-139">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="4410c-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
