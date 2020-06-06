---
title: <client>의 <endpoint>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855314"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="2ca2d-102">\<client>의 \<endpoint></span><span class="sxs-lookup"><span data-stu-id="2ca2d-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="2ca2d-103">클라이언트에서 서버의 서비스 엔드포인트와 연결하는 데 사용하는 채널 엔드포인트의 contract, binding 및 address 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="2ca2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ca2d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ca2d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ca2d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2ca2d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ca2d-107">특성</span><span class="sxs-lookup"><span data-stu-id="2ca2d-107">Attributes</span></span>  
  
|<span data-ttu-id="2ca2d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2ca2d-108">Attribute</span></span>|<span data-ttu-id="2ca2d-109">Description</span><span class="sxs-lookup"><span data-stu-id="2ca2d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ca2d-110">address</span><span class="sxs-lookup"><span data-stu-id="2ca2d-110">address</span></span>|<span data-ttu-id="2ca2d-111">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="2ca2d-112">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="2ca2d-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-113">The default is an empty string.</span></span> <span data-ttu-id="2ca2d-114">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="2ca2d-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ca2d-115">behaviorConfiguration</span></span>|<span data-ttu-id="2ca2d-116">엔드포인트를 인스턴스화할 때 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="2ca2d-117">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="2ca2d-118">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="2ca2d-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="2ca2d-119">binding</span></span>|<span data-ttu-id="2ca2d-120">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="2ca2d-121">사용할 바인딩의 형식을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="2ca2d-122">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="2ca2d-123">이 형식은 바인딩의 형식 이름 대신 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="2ca2d-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ca2d-124">bindingConfiguration</span></span>|<span data-ttu-id="2ca2d-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-125">Optional.</span></span> <span data-ttu-id="2ca2d-126">엔드포인트가 인스턴스화될 때 사용할 바인딩 구성의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="2ca2d-127">바인딩 구성은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="2ca2d-128">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="2ca2d-129">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="2ca2d-130">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="2ca2d-131">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="2ca2d-132">계약</span><span class="sxs-lookup"><span data-stu-id="2ca2d-132">contract</span></span>|<span data-ttu-id="2ca2d-133">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="2ca2d-134">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="2ca2d-135">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="2ca2d-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="2ca2d-136">endpointConfiguration</span></span>|<span data-ttu-id="2ca2d-137">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="2ca2d-138">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="2ca2d-139">kind</span><span class="sxs-lookup"><span data-stu-id="2ca2d-139">kind</span></span>|<span data-ttu-id="2ca2d-140">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="2ca2d-141">형식은 섹션 또는 machine.config에 등록 되어야 합니다 `<extensions>` . 아무 것도 지정 하지 않으면 공통 채널 끝점이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="2ca2d-142">name</span><span class="sxs-lookup"><span data-stu-id="2ca2d-142">name</span></span>|<span data-ttu-id="2ca2d-143">선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-143">Optional string attribute.</span></span> <span data-ttu-id="2ca2d-144">이 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="2ca2d-145">지정한 계약 형식에 대해 여러 클라이언트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="2ca2d-146">각 정의는 고유한 구성 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="2ca2d-147">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="2ca2d-148">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="2ca2d-149">바인딩의 `name` 특성은 WSDL을 통해 정의를 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ca2d-150">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ca2d-150">Child Elements</span></span>  
  
|<span data-ttu-id="2ca2d-151">요소</span><span class="sxs-lookup"><span data-stu-id="2ca2d-151">Element</span></span>|<span data-ttu-id="2ca2d-152">Description</span><span class="sxs-lookup"><span data-stu-id="2ca2d-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="2ca2d-153">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="2ca2d-154">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ca2d-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ca2d-155">Parent Elements</span></span>  
  
|<span data-ttu-id="2ca2d-156">요소</span><span class="sxs-lookup"><span data-stu-id="2ca2d-156">Element</span></span>|<span data-ttu-id="2ca2d-157">Description</span><span class="sxs-lookup"><span data-stu-id="2ca2d-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="2ca2d-158">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ca2d-159">예제</span><span class="sxs-lookup"><span data-stu-id="2ca2d-159">Example</span></span>  
 <span data-ttu-id="2ca2d-160">이것은 채널 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca2d-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="2ca2d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ca2d-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="2ca2d-162">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2ca2d-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="2ca2d-163">클라이언트</span><span class="sxs-lookup"><span data-stu-id="2ca2d-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
