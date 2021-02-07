---
description: '다음에 대 한 자세한 정보:: <add><issuerChannelBehaviors>'
title: <issuerChannelBehaviors>의 <add>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: ccd8ba015b7a6837c74ce2c051a794d36ce8ceaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750301"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="3f437-103">\<issuerChannelBehaviors>의 \<add></span><span class="sxs-lookup"><span data-stu-id="3f437-103">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="3f437-104">STS와 통신할 때 사용할 엔드포인트 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-104">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="3f437-105">끝점 동작에 요소가 포함 되어 있으면 [\<clientCredentials>](clientcredentials.md) 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-105">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="3f437-106">구문</span><span class="sxs-lookup"><span data-stu-id="3f437-106">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f437-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3f437-107">Attributes and Elements</span></span>

<span data-ttu-id="3f437-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="3f437-109">특성</span><span class="sxs-lookup"><span data-stu-id="3f437-109">Attributes</span></span>

|<span data-ttu-id="3f437-110">attribute</span><span class="sxs-lookup"><span data-stu-id="3f437-110">Attribute</span></span>|<span data-ttu-id="3f437-111">설명</span><span class="sxs-lookup"><span data-stu-id="3f437-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3f437-112">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="3f437-112">issuerAddress</span></span>|<span data-ttu-id="3f437-113">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-113">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="3f437-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f437-114">behaviorConfiguration</span></span>|<span data-ttu-id="3f437-115">동일한 구성 파일에 정의된 엔드포인트 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-115">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3f437-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f437-116">Child Elements</span></span>

<span data-ttu-id="3f437-117">없음</span><span class="sxs-lookup"><span data-stu-id="3f437-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3f437-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f437-118">Parent Elements</span></span>

|<span data-ttu-id="3f437-119">요소</span><span class="sxs-lookup"><span data-stu-id="3f437-119">Element</span></span>|<span data-ttu-id="3f437-120">설명</span><span class="sxs-lookup"><span data-stu-id="3f437-120">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="3f437-121">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-121">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3f437-122">설명</span><span class="sxs-lookup"><span data-stu-id="3f437-122">Remarks</span></span>

<span data-ttu-id="3f437-123">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-123">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="3f437-124">`behaviorConfiguration` 응용 프로그램이 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 Windows Communication Foundation (WCF)에서 만든 채널에서 사용 하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3f437-124">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f437-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f437-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="3f437-126">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="3f437-126">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3f437-127">보안 동작</span><span class="sxs-lookup"><span data-stu-id="3f437-127">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3f437-128">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="3f437-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3f437-129">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3f437-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3f437-130">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3f437-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="3f437-131">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="3f437-131">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3f437-132">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="3f437-132">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3f437-133">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="3f437-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
