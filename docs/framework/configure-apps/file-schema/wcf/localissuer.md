---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766404"
---
# <a name="localissuer"></a><span data-ttu-id="8c961-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="8c961-101">\<localIssuer></span></span>
<span data-ttu-id="8c961-102">보안 토큰을 가져오는 데 사용할 로컬 발급자의 주소 및 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="8c961-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c961-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c961-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8c961-104">\<behaviors></span></span>  
<span data-ttu-id="8c961-105">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="8c961-105">endpointBehaviors section</span></span>  
<span data-ttu-id="8c961-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8c961-106">\<behavior></span></span>  
<span data-ttu-id="8c961-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8c961-107">\<clientCredentials></span></span>  
<span data-ttu-id="8c961-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8c961-108">\<issuedToken></span></span>  
<span data-ttu-id="8c961-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="8c961-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c961-110">구문</span><span class="sxs-lookup"><span data-stu-id="8c961-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c961-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c961-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c961-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c961-113">특성</span><span class="sxs-lookup"><span data-stu-id="8c961-113">Attributes</span></span>  
  
|<span data-ttu-id="8c961-114">특성</span><span class="sxs-lookup"><span data-stu-id="8c961-114">Attribute</span></span>|<span data-ttu-id="8c961-115">설명</span><span class="sxs-lookup"><span data-stu-id="8c961-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c961-116">주소</span><span class="sxs-lookup"><span data-stu-id="8c961-116">address</span></span>|<span data-ttu-id="8c961-117">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-117">Required string.</span></span> <span data-ttu-id="8c961-118">로컬 발급자의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="8c961-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="8c961-119">binding</span></span>|<span data-ttu-id="8c961-120">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-120">Optional string.</span></span> <span data-ttu-id="8c961-121">시스템에서 제공한 바인딩 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-121">One of the system-provided bindings.</span></span> <span data-ttu-id="8c961-122">목록에 대해서 [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="8c961-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c961-123">bindingConfiguration</span></span>|<span data-ttu-id="8c961-124">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-124">Optional string.</span></span> <span data-ttu-id="8c961-125">구성 파일에서 발견되는 바인딩 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c961-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c961-126">Child Elements</span></span>  
  
|<span data-ttu-id="8c961-127">요소</span><span class="sxs-lookup"><span data-stu-id="8c961-127">Element</span></span>|<span data-ttu-id="8c961-128">설명</span><span class="sxs-lookup"><span data-stu-id="8c961-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c961-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="8c961-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8c961-130">로컬 발급자의 ID 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="8c961-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="8c961-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8c961-132">로컬 발급자의 주소를 올바로 지정하는 데 필요한 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="8c961-133">`add` 키워드를 사용하여 이 컬렉션에 헤더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c961-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c961-134">Parent Elements</span></span>  
  
|<span data-ttu-id="8c961-135">요소</span><span class="sxs-lookup"><span data-stu-id="8c961-135">Element</span></span>|<span data-ttu-id="8c961-136">설명</span><span class="sxs-lookup"><span data-stu-id="8c961-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c961-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8c961-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="8c961-138">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c961-139">설명</span><span class="sxs-lookup"><span data-stu-id="8c961-139">Remarks</span></span>  
 <span data-ttu-id="8c961-140">STS(보안 토큰 서비스)에서 발급된 토큰을 가져오려면 클라이언트 응용 프로그램에서 STS와 통신하는 데 사용할 주소 및 바인딩을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="8c961-141">경우는 <xref:System.ServiceModel.WSFederationHttpBinding> 페더레이션 바인딩의 발급자 주소가 때 또는 보안 토큰 서비스에 대 한 URL을 제공 하지 않습니다 `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` 또는 `null`, 클라이언트의 Windows Communication Foundation (WCF) 채널 하여지정된값을사용하여`address`고 `binding` 발급 된 토큰을 가져오려면 STS와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="8c961-142">로컬 발급자를 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c961-143">예제</span><span class="sxs-lookup"><span data-stu-id="8c961-143">Example</span></span>  
 <span data-ttu-id="8c961-144">다음 예제에서는 `address`, `binding` 및 `bindingConfiguration` 요소의 `localIssuer` 특성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c961-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c961-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c961-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="8c961-146">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8c961-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8c961-147">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="8c961-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="8c961-148">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="8c961-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8c961-149">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8c961-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8c961-150">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8c961-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8c961-151">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8c961-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8c961-152">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8c961-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="8c961-153">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="8c961-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8c961-154">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="8c961-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
