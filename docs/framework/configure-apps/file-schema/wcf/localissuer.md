---
description: 다음에 대해 자세히 알아보세요. <localIssuer>
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 38928f1bfd7740aa902de46958740a1e8fe63e5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725482"
---
# \<localIssuer>

<span data-ttu-id="c40ac-102">보안 토큰을 가져오는 데 사용할 로컬 발급자의 주소 및 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="c40ac-103">구문</span><span class="sxs-lookup"><span data-stu-id="c40ac-103">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c40ac-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c40ac-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c40ac-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c40ac-106">특성</span><span class="sxs-lookup"><span data-stu-id="c40ac-106">Attributes</span></span>  
  
|<span data-ttu-id="c40ac-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c40ac-107">Attribute</span></span>|<span data-ttu-id="c40ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="c40ac-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c40ac-109">address</span><span class="sxs-lookup"><span data-stu-id="c40ac-109">address</span></span>|<span data-ttu-id="c40ac-110">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-110">Required string.</span></span> <span data-ttu-id="c40ac-111">로컬 발급자의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-111">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="c40ac-112">바인딩</span><span class="sxs-lookup"><span data-stu-id="c40ac-112">binding</span></span>|<span data-ttu-id="c40ac-113">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-113">Optional string.</span></span> <span data-ttu-id="c40ac-114">시스템에서 제공한 바인딩 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-114">One of the system-provided bindings.</span></span> <span data-ttu-id="c40ac-115">목록은 [시스템 제공 바인딩](../../../wcf/system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c40ac-115">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="c40ac-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c40ac-116">bindingConfiguration</span></span>|<span data-ttu-id="c40ac-117">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-117">Optional string.</span></span> <span data-ttu-id="c40ac-118">구성 파일에서 발견되는 바인딩 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-118">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c40ac-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c40ac-119">Child Elements</span></span>  
  
|<span data-ttu-id="c40ac-120">요소</span><span class="sxs-lookup"><span data-stu-id="c40ac-120">Element</span></span>|<span data-ttu-id="c40ac-121">설명</span><span class="sxs-lookup"><span data-stu-id="c40ac-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="c40ac-122">로컬 발급자의 ID 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-122">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="c40ac-123">로컬 발급자의 주소를 올바로 지정하는 데 필요한 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-123">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="c40ac-124">`add` 키워드를 사용하여 이 컬렉션에 헤더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-124">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c40ac-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c40ac-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c40ac-126">요소</span><span class="sxs-lookup"><span data-stu-id="c40ac-126">Element</span></span>|<span data-ttu-id="c40ac-127">설명</span><span class="sxs-lookup"><span data-stu-id="c40ac-127">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="c40ac-128">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-128">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c40ac-129">설명</span><span class="sxs-lookup"><span data-stu-id="c40ac-129">Remarks</span></span>  

 <span data-ttu-id="c40ac-130">STS(보안 토큰 서비스)에서 발급된 토큰을 가져오려면 클라이언트 애플리케이션에서 STS와 통신하는 데 사용할 주소 및 바인딩을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-130">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="c40ac-131">에서 <xref:System.ServiceModel.WSFederationHttpBinding> 보안 토큰 서비스에 대 한 URL을 제공 하지 않거나 페더레이션된 바인딩의 발급자 주소가 `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` 또는 이면 `null` 클라이언트의 WCF (Windows Communication Foundation) 채널에서 및에 지정 된 값을 사용 하 여 `address` `binding` STS와 통신 하 여 발급 된 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-131">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="c40ac-132">로컬 발급자를 구성 하는 방법에 대 한 자세한 내용은 [방법: 로컬 발급자 구성](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c40ac-132">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c40ac-133">예제</span><span class="sxs-lookup"><span data-stu-id="c40ac-133">Example</span></span>  

 <span data-ttu-id="c40ac-134">다음 예제에서는 `address`, `binding` 및 `bindingConfiguration` 요소의 `localIssuer` 특성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c40ac-134">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="c40ac-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c40ac-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="c40ac-136">보안 동작</span><span class="sxs-lookup"><span data-stu-id="c40ac-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c40ac-137">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="c40ac-137">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="c40ac-138">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="c40ac-138">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c40ac-139">보안 동작</span><span class="sxs-lookup"><span data-stu-id="c40ac-139">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c40ac-140">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c40ac-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c40ac-141">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c40ac-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c40ac-142">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c40ac-142">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c40ac-143">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="c40ac-143">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="c40ac-144">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c40ac-144">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
