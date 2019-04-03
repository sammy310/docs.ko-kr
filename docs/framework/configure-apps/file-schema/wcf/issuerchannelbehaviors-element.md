---
title: <issuerChannelBehaviors> 요소
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890477"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="9eb52-102">\<issuerChannelBehaviors > 요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="9eb52-103">지정한 서비스 토큰 서비스와 통신할 때 사용 되는 Windows Communication Foundation (WCF) 클라이언트 끝점 동작 (구성에 정의 됨)의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="9eb52-104">정의 된 동작을 포함할 수 없습니다 [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="9eb52-105">구문</span><span class="sxs-lookup"><span data-stu-id="9eb52-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9eb52-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-106">Attributes and Elements</span></span>

<span data-ttu-id="9eb52-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9eb52-108">특성</span><span class="sxs-lookup"><span data-stu-id="9eb52-108">Attributes</span></span>

<span data-ttu-id="9eb52-109">없음</span><span class="sxs-lookup"><span data-stu-id="9eb52-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9eb52-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-110">Child Elements</span></span>

|<span data-ttu-id="9eb52-111">요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-111">Element</span></span>|<span data-ttu-id="9eb52-112">설명</span><span class="sxs-lookup"><span data-stu-id="9eb52-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9eb52-113">\<add></span><span class="sxs-lookup"><span data-stu-id="9eb52-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="9eb52-114">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9eb52-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-115">Parent Elements</span></span>

|<span data-ttu-id="9eb52-116">요소</span><span class="sxs-lookup"><span data-stu-id="9eb52-116">Element</span></span>|<span data-ttu-id="9eb52-117">설명</span><span class="sxs-lookup"><span data-stu-id="9eb52-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9eb52-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="9eb52-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="9eb52-119">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9eb52-120">설명</span><span class="sxs-lookup"><span data-stu-id="9eb52-120">Remarks</span></span>

<span data-ttu-id="9eb52-121">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="9eb52-122">예를 들어 경우는 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 동작 요소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb52-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eb52-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="9eb52-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="9eb52-124">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="9eb52-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9eb52-125">보안 동작</span><span class="sxs-lookup"><span data-stu-id="9eb52-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9eb52-126">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="9eb52-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9eb52-127">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9eb52-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9eb52-128">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9eb52-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="9eb52-129">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="9eb52-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9eb52-130">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="9eb52-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="9eb52-131">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="9eb52-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
