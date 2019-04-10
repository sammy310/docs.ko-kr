---
title: <endpoint> / <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 3af41ad5b5681b08aac44d984372ab5ac66caf5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231203"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="4e189-102">\<끝점 >의 \<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="4e189-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="4e189-103">클라이언트에서 서버의 서비스 엔드포인트와 연결하는 데 사용하는 채널 엔드포인트의 contract, binding 및 address 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="4e189-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e189-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e189-105">\<client></span><span class="sxs-lookup"><span data-stu-id="4e189-105">\<client></span></span>  
<span data-ttu-id="4e189-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="4e189-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e189-107">구문</span><span class="sxs-lookup"><span data-stu-id="4e189-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e189-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e189-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4e189-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e189-110">특성</span><span class="sxs-lookup"><span data-stu-id="4e189-110">Attributes</span></span>  
  
|<span data-ttu-id="4e189-111">특성</span><span class="sxs-lookup"><span data-stu-id="4e189-111">Attribute</span></span>|<span data-ttu-id="4e189-112">설명</span><span class="sxs-lookup"><span data-stu-id="4e189-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e189-113">주소</span><span class="sxs-lookup"><span data-stu-id="4e189-113">address</span></span>|<span data-ttu-id="4e189-114">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4e189-115">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="4e189-116">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-116">The default is an empty string.</span></span> <span data-ttu-id="4e189-117">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="4e189-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e189-118">behaviorConfiguration</span></span>|<span data-ttu-id="4e189-119">엔드포인트를 인스턴스화할 때 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="4e189-120">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="4e189-121">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="4e189-122">바인딩</span><span class="sxs-lookup"><span data-stu-id="4e189-122">binding</span></span>|<span data-ttu-id="4e189-123">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4e189-124">사용할 바인딩의 형식을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="4e189-125">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="4e189-126">이 형식은 바인딩의 형식 이름 대신 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="4e189-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e189-127">bindingConfiguration</span></span>|<span data-ttu-id="4e189-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-128">Optional.</span></span> <span data-ttu-id="4e189-129">엔드포인트가 인스턴스화될 때 사용할 바인딩 구성의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="4e189-130">바인딩 구성은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="4e189-131">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4e189-132">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="4e189-133">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="4e189-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="4e189-134">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="4e189-135">계약(contract)</span><span class="sxs-lookup"><span data-stu-id="4e189-135">contract</span></span>|<span data-ttu-id="4e189-136">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="4e189-137">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="4e189-138">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="4e189-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e189-139">endpointConfiguration</span></span>|<span data-ttu-id="4e189-140">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="4e189-141">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="4e189-142">kind</span><span class="sxs-lookup"><span data-stu-id="4e189-142">kind</span></span>|<span data-ttu-id="4e189-143">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="4e189-144">이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다. 지정하지 않으면 일반 채널 엔드포인트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="4e189-145">name</span><span class="sxs-lookup"><span data-stu-id="4e189-145">name</span></span>|<span data-ttu-id="4e189-146">선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-146">Optional string attribute.</span></span> <span data-ttu-id="4e189-147">이 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="4e189-148">지정한 계약 형식에 대해 여러 클라이언트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="4e189-149">각 정의는 고유한 구성 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="4e189-150">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="4e189-151">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4e189-152">바인딩의 `name` 특성은 WSDL을 통해 정의를 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e189-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e189-153">Child Elements</span></span>  
  
|<span data-ttu-id="4e189-154">요소</span><span class="sxs-lookup"><span data-stu-id="4e189-154">Element</span></span>|<span data-ttu-id="4e189-155">설명</span><span class="sxs-lookup"><span data-stu-id="4e189-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e189-156">\<headers></span><span class="sxs-lookup"><span data-stu-id="4e189-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="4e189-157">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="4e189-158">\<identity></span><span class="sxs-lookup"><span data-stu-id="4e189-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="4e189-159">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e189-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e189-160">Parent Elements</span></span>  
  
|<span data-ttu-id="4e189-161">요소</span><span class="sxs-lookup"><span data-stu-id="4e189-161">Element</span></span>|<span data-ttu-id="4e189-162">설명</span><span class="sxs-lookup"><span data-stu-id="4e189-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e189-163">\<client></span><span class="sxs-lookup"><span data-stu-id="4e189-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="4e189-164">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e189-165">예제</span><span class="sxs-lookup"><span data-stu-id="4e189-165">Example</span></span>  
 <span data-ttu-id="4e189-166">이것은 채널 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4e189-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="4e189-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e189-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="4e189-168">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4e189-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="4e189-169">클라이언트</span><span class="sxs-lookup"><span data-stu-id="4e189-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
