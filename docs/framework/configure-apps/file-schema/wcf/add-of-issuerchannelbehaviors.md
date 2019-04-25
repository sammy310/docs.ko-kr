---
title: <issuerChannelBehaviors>의 <add>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673617"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="0a632-102">\<추가 >의 \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0a632-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="0a632-103">STS와 통신할 때 사용할 엔드포인트 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="0a632-104">끝점 동작을 포함 하는 경우는 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에서 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="0a632-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="0a632-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="0a632-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="0a632-106">\<behaviors>\\</span></span>
<span data-ttu-id="0a632-107">endpointBehaviors 섹션 \<동작 > \\</span><span class="sxs-lookup"><span data-stu-id="0a632-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="0a632-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="0a632-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="0a632-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="0a632-109">\<issuedToken>\\</span></span>
<span data-ttu-id="0a632-110">\<issuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="0a632-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="0a632-111">\<add></span><span class="sxs-lookup"><span data-stu-id="0a632-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="0a632-112">구문</span><span class="sxs-lookup"><span data-stu-id="0a632-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a632-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0a632-113">Attributes and Elements</span></span>

<span data-ttu-id="0a632-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="0a632-115">특성</span><span class="sxs-lookup"><span data-stu-id="0a632-115">Attributes</span></span>

|<span data-ttu-id="0a632-116">특성</span><span class="sxs-lookup"><span data-stu-id="0a632-116">Attribute</span></span>|<span data-ttu-id="0a632-117">설명</span><span class="sxs-lookup"><span data-stu-id="0a632-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0a632-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="0a632-118">issuerAddress</span></span>|<span data-ttu-id="0a632-119">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="0a632-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a632-120">behaviorConfiguration</span></span>|<span data-ttu-id="0a632-121">동일한 구성 파일에 정의된 엔드포인트 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0a632-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a632-122">Child Elements</span></span>

<span data-ttu-id="0a632-123">없음</span><span class="sxs-lookup"><span data-stu-id="0a632-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0a632-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a632-124">Parent Elements</span></span>

|<span data-ttu-id="0a632-125">요소</span><span class="sxs-lookup"><span data-stu-id="0a632-125">Element</span></span>|<span data-ttu-id="0a632-126">설명</span><span class="sxs-lookup"><span data-stu-id="0a632-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a632-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="0a632-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="0a632-128">지정한 서비스 토큰 서비스와 통신할 때 사용 되는 Windows Communication Foundation (WCF) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0a632-129">설명</span><span class="sxs-lookup"><span data-stu-id="0a632-129">Remarks</span></span>

<span data-ttu-id="0a632-130">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="0a632-131">`behaviorConfiguration` 응용 프로그램 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 Windows Communication Foundation (WCF)에서 만든 채널에서 사용 하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0a632-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a632-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a632-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="0a632-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="0a632-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0a632-134">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0a632-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0a632-135">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0a632-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0a632-136">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0a632-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0a632-137">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0a632-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="0a632-138">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0a632-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0a632-139">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="0a632-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0a632-140">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0a632-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0a632-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="0a632-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
