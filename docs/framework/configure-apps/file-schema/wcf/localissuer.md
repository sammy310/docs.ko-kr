---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 4ec5a99139112ae600c1c2bc44feb6d3f62da1e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931734"
---
# <a name="localissuer"></a><span data-ttu-id="fd0f5-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="fd0f5-101">\<localIssuer></span></span>
<span data-ttu-id="fd0f5-102">보안 토큰을 가져오는 데 사용할 로컬 발급자의 주소 및 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="fd0f5-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fd0f5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fd0f5-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fd0f5-104">\<behaviors></span></span>  
<span data-ttu-id="fd0f5-105">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="fd0f5-105">endpointBehaviors section</span></span>  
<span data-ttu-id="fd0f5-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fd0f5-106">\<behavior></span></span>  
<span data-ttu-id="fd0f5-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fd0f5-107">\<clientCredentials></span></span>  
<span data-ttu-id="fd0f5-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="fd0f5-108">\<issuedToken></span></span>  
<span data-ttu-id="fd0f5-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="fd0f5-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0f5-110">구문</span><span class="sxs-lookup"><span data-stu-id="fd0f5-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd0f5-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fd0f5-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd0f5-113">특성</span><span class="sxs-lookup"><span data-stu-id="fd0f5-113">Attributes</span></span>  
  
|<span data-ttu-id="fd0f5-114">특성</span><span class="sxs-lookup"><span data-stu-id="fd0f5-114">Attribute</span></span>|<span data-ttu-id="fd0f5-115">설명</span><span class="sxs-lookup"><span data-stu-id="fd0f5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd0f5-116">주소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-116">address</span></span>|<span data-ttu-id="fd0f5-117">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-117">Required string.</span></span> <span data-ttu-id="fd0f5-118">로컬 발급자의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="fd0f5-119">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="fd0f5-119">binding</span></span>|<span data-ttu-id="fd0f5-120">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-120">Optional string.</span></span> <span data-ttu-id="fd0f5-121">시스템에서 제공한 바인딩 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-121">One of the system-provided bindings.</span></span> <span data-ttu-id="fd0f5-122">목록은 [시스템 제공 바인딩](../../../wcf/system-provided-bindings.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-122">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="fd0f5-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd0f5-123">bindingConfiguration</span></span>|<span data-ttu-id="fd0f5-124">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-124">Optional string.</span></span> <span data-ttu-id="fd0f5-125">구성 파일에서 발견되는 바인딩 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd0f5-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-126">Child Elements</span></span>  
  
|<span data-ttu-id="fd0f5-127">요소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-127">Element</span></span>|<span data-ttu-id="fd0f5-128">Description</span><span class="sxs-lookup"><span data-stu-id="fd0f5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd0f5-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="fd0f5-129">\<identity></span></span>](identity.md)|<span data-ttu-id="fd0f5-130">로컬 발급자의 ID 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="fd0f5-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="fd0f5-131">\<headers></span></span>](headers-element.md)|<span data-ttu-id="fd0f5-132">로컬 발급자의 주소를 올바로 지정하는 데 필요한 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="fd0f5-133">`add` 키워드를 사용하여 이 컬렉션에 헤더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd0f5-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-134">Parent Elements</span></span>  
  
|<span data-ttu-id="fd0f5-135">요소</span><span class="sxs-lookup"><span data-stu-id="fd0f5-135">Element</span></span>|<span data-ttu-id="fd0f5-136">설명</span><span class="sxs-lookup"><span data-stu-id="fd0f5-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd0f5-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="fd0f5-137">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="fd0f5-138">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0f5-139">설명</span><span class="sxs-lookup"><span data-stu-id="fd0f5-139">Remarks</span></span>  
 <span data-ttu-id="fd0f5-140">STS(보안 토큰 서비스)에서 발급된 토큰을 가져오려면 클라이언트 애플리케이션에서 STS와 통신하는 데 사용할 주소 및 바인딩을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="fd0f5-141">에서 <xref:System.ServiceModel.WSFederationHttpBinding> 보안 토큰 서비스에 대 한 URL을 제공 하지 않거나 페더레이션된 `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` 바인딩의 발급자 주소가 또는 `null`이면 클라이언트의 WCF (Windows Communication Foundation) 채널에서로 `address`지정된값을사용합니다. 그리고`binding` STS와 통신 하 여 발급 된 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="fd0f5-142">로컬 발급자 [를 구성 하는 방법에 대 한 자세한 내용은 방법: 로컬 발급자](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd0f5-143">예제</span><span class="sxs-lookup"><span data-stu-id="fd0f5-143">Example</span></span>  
 <span data-ttu-id="fd0f5-144">다음 예제에서는 `address`, `binding` 및 `bindingConfiguration` 요소의 `localIssuer` 특성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd0f5-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd0f5-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd0f5-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="fd0f5-146">보안 동작</span><span class="sxs-lookup"><span data-stu-id="fd0f5-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fd0f5-147">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="fd0f5-147">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="fd0f5-148">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="fd0f5-148">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fd0f5-149">보안 동작</span><span class="sxs-lookup"><span data-stu-id="fd0f5-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fd0f5-150">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="fd0f5-150">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fd0f5-151">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fd0f5-151">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fd0f5-152">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="fd0f5-152">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fd0f5-153">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="fd0f5-153">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="fd0f5-154">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="fd0f5-154">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
