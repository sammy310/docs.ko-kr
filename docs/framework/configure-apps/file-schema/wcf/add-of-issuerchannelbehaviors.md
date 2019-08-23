---
title: <issuerChannelBehaviors>의 <add>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920120"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="295e2-102">\<\<issuerChannelBehaviors > > 추가</span><span class="sxs-lookup"><span data-stu-id="295e2-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="295e2-103">STS와 통신할 때 사용할 엔드포인트 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="295e2-104">Endpoint behavior에 [ \<clientCredentials >](clientcredentials.md) 요소가 포함 되어 있으면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="295e2-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="295e2-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="295e2-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="295e2-106">\<behaviors></span></span>\
<span data-ttu-id="295e2-107">endpointbehaviors 섹션 \<동작 > </span><span class="sxs-lookup"><span data-stu-id="295e2-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="295e2-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="295e2-108">\<clientCredentials></span></span>\
<span data-ttu-id="295e2-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="295e2-109">\<issuedToken></span></span>\
<span data-ttu-id="295e2-110">\<issuerChannelBehaviors > 요소 </span><span class="sxs-lookup"><span data-stu-id="295e2-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="295e2-111">\<add></span><span class="sxs-lookup"><span data-stu-id="295e2-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="295e2-112">구문</span><span class="sxs-lookup"><span data-stu-id="295e2-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="295e2-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="295e2-113">Attributes and Elements</span></span>

<span data-ttu-id="295e2-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="295e2-115">특성</span><span class="sxs-lookup"><span data-stu-id="295e2-115">Attributes</span></span>

|<span data-ttu-id="295e2-116">특성</span><span class="sxs-lookup"><span data-stu-id="295e2-116">Attribute</span></span>|<span data-ttu-id="295e2-117">설명</span><span class="sxs-lookup"><span data-stu-id="295e2-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="295e2-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="295e2-118">issuerAddress</span></span>|<span data-ttu-id="295e2-119">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="295e2-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="295e2-120">behaviorConfiguration</span></span>|<span data-ttu-id="295e2-121">동일한 구성 파일에 정의된 엔드포인트 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="295e2-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="295e2-122">Child Elements</span></span>

<span data-ttu-id="295e2-123">없음</span><span class="sxs-lookup"><span data-stu-id="295e2-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="295e2-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="295e2-124">Parent Elements</span></span>

|<span data-ttu-id="295e2-125">요소</span><span class="sxs-lookup"><span data-stu-id="295e2-125">Element</span></span>|<span data-ttu-id="295e2-126">설명</span><span class="sxs-lookup"><span data-stu-id="295e2-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="295e2-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="295e2-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="295e2-128">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="295e2-129">설명</span><span class="sxs-lookup"><span data-stu-id="295e2-129">Remarks</span></span>

<span data-ttu-id="295e2-130">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="295e2-131">`behaviorConfiguration`응용 프로그램이 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 Windows Communication Foundation (WCF)에서 만든 채널에서 사용 하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="295e2-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="295e2-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="295e2-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="295e2-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="295e2-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="295e2-134">보안 동작</span><span class="sxs-lookup"><span data-stu-id="295e2-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="295e2-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="295e2-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="295e2-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="295e2-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="295e2-137">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="295e2-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="295e2-138">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="295e2-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="295e2-139">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="295e2-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="295e2-140">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="295e2-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="295e2-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="295e2-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
