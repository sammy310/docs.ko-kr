---
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
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893151"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="832e7-102">\<issuerChannelBehaviors> 요소</span><span class="sxs-lookup"><span data-stu-id="832e7-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="832e7-103">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작 (구성에 정의 됨)의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="832e7-104">정의 된 동작에는 요소가 포함 될 수 없습니다 [\<clientCredentials>](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="832e7-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="832e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="832e7-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="832e7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="832e7-106">Attributes and elements</span></span>

<span data-ttu-id="832e7-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="832e7-108">특성</span><span class="sxs-lookup"><span data-stu-id="832e7-108">Attributes</span></span>

<span data-ttu-id="832e7-109">없음</span><span class="sxs-lookup"><span data-stu-id="832e7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="832e7-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="832e7-110">Child elements</span></span>

|<span data-ttu-id="832e7-111">요소</span><span class="sxs-lookup"><span data-stu-id="832e7-111">Element</span></span>|<span data-ttu-id="832e7-112">Description</span><span class="sxs-lookup"><span data-stu-id="832e7-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="832e7-113">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="832e7-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="832e7-114">Parent elements</span></span>

|<span data-ttu-id="832e7-115">요소</span><span class="sxs-lookup"><span data-stu-id="832e7-115">Element</span></span>|<span data-ttu-id="832e7-116">Description</span><span class="sxs-lookup"><span data-stu-id="832e7-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="832e7-117">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="832e7-118">설명</span><span class="sxs-lookup"><span data-stu-id="832e7-118">Remarks</span></span>

<span data-ttu-id="832e7-119">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="832e7-120">예를 들어 [\<dataContractSerializer>](datacontractserializer-element.md) 동작 요소가 포함 되어야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="832e7-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="832e7-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832e7-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="832e7-122">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="832e7-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="832e7-123">보안 동작</span><span class="sxs-lookup"><span data-stu-id="832e7-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="832e7-124">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="832e7-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="832e7-125">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="832e7-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="832e7-126">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="832e7-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="832e7-127">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="832e7-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="832e7-128">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="832e7-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="832e7-129">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="832e7-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
