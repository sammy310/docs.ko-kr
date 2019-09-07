---
title: <issuerChannelBehaviors>의 <add>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398328"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="79a25-102">\<\<issuerChannelBehaviors > > 추가</span><span class="sxs-lookup"><span data-stu-id="79a25-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="79a25-103">STS와 통신할 때 사용할 엔드포인트 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="79a25-104">Endpoint behavior에 [ \<clientCredentials >](clientcredentials.md) 요소가 포함 되어 있으면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="79a25-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79a25-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="79a25-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="79a25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="79a25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="79a25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="79a25-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="79a25-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerChannelBehaviors >** ](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="79a25-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="79a25-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="79a25-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="79a25-114">구문</span><span class="sxs-lookup"><span data-stu-id="79a25-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="79a25-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="79a25-115">Attributes and Elements</span></span>

<span data-ttu-id="79a25-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="79a25-117">특성</span><span class="sxs-lookup"><span data-stu-id="79a25-117">Attributes</span></span>

|<span data-ttu-id="79a25-118">특성</span><span class="sxs-lookup"><span data-stu-id="79a25-118">Attribute</span></span>|<span data-ttu-id="79a25-119">Description</span><span class="sxs-lookup"><span data-stu-id="79a25-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="79a25-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="79a25-120">issuerAddress</span></span>|<span data-ttu-id="79a25-121">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="79a25-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="79a25-122">behaviorConfiguration</span></span>|<span data-ttu-id="79a25-123">동일한 구성 파일에 정의된 엔드포인트 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="79a25-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="79a25-124">Child Elements</span></span>

<span data-ttu-id="79a25-125">없음</span><span class="sxs-lookup"><span data-stu-id="79a25-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="79a25-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="79a25-126">Parent Elements</span></span>

|<span data-ttu-id="79a25-127">요소</span><span class="sxs-lookup"><span data-stu-id="79a25-127">Element</span></span>|<span data-ttu-id="79a25-128">Description</span><span class="sxs-lookup"><span data-stu-id="79a25-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79a25-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="79a25-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="79a25-130">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="79a25-131">설명</span><span class="sxs-lookup"><span data-stu-id="79a25-131">Remarks</span></span>

<span data-ttu-id="79a25-132">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="79a25-133">`behaviorConfiguration`응용 프로그램이 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 Windows Communication Foundation (WCF)에서 만든 채널에서 사용 하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="79a25-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a25-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="79a25-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="79a25-135">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="79a25-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="79a25-136">보안 동작</span><span class="sxs-lookup"><span data-stu-id="79a25-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="79a25-137">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="79a25-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="79a25-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="79a25-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="79a25-139">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="79a25-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="79a25-140">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="79a25-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="79a25-141">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="79a25-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="79a25-142">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="79a25-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="79a25-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="79a25-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
