---
title: <issuerChannelBehaviors> 요소
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929933"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="33a98-102">\<issuerChannelBehaviors > 요소</span><span class="sxs-lookup"><span data-stu-id="33a98-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="33a98-103">지정 된 서비스 토큰 서비스와 통신할 때 사용할 WCF (Windows Communication Foundation) 클라이언트 끝점 동작 (구성에 정의 됨)의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="33a98-104">정의 된 동작을 포함할 수 없습니다 [\<clientCredentials>](clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="33a98-105">구문</span><span class="sxs-lookup"><span data-stu-id="33a98-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33a98-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33a98-106">Attributes and Elements</span></span>

<span data-ttu-id="33a98-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="33a98-108">특성</span><span class="sxs-lookup"><span data-stu-id="33a98-108">Attributes</span></span>

<span data-ttu-id="33a98-109">없음</span><span class="sxs-lookup"><span data-stu-id="33a98-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="33a98-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33a98-110">Child Elements</span></span>

|<span data-ttu-id="33a98-111">요소</span><span class="sxs-lookup"><span data-stu-id="33a98-111">Element</span></span>|<span data-ttu-id="33a98-112">설명</span><span class="sxs-lookup"><span data-stu-id="33a98-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33a98-113">\<add></span><span class="sxs-lookup"><span data-stu-id="33a98-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="33a98-114">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33a98-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33a98-115">Parent Elements</span></span>

|<span data-ttu-id="33a98-116">요소</span><span class="sxs-lookup"><span data-stu-id="33a98-116">Element</span></span>|<span data-ttu-id="33a98-117">Description</span><span class="sxs-lookup"><span data-stu-id="33a98-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33a98-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="33a98-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="33a98-119">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33a98-120">설명</span><span class="sxs-lookup"><span data-stu-id="33a98-120">Remarks</span></span>

<span data-ttu-id="33a98-121">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="33a98-122">예를 들어 경우는 [\<dataContractSerializer >](datacontractserializer-element.md) 동작 요소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33a98-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="33a98-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="33a98-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="33a98-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="33a98-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="33a98-125">보안 동작</span><span class="sxs-lookup"><span data-stu-id="33a98-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="33a98-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="33a98-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="33a98-127">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="33a98-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="33a98-128">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="33a98-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="33a98-129">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="33a98-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="33a98-130">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="33a98-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="33a98-131">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="33a98-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
