---
title: <endpoint> 요소
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855386"
---
# <a name="endpoint-element"></a><span data-ttu-id="1f506-102">\<끝점 > 요소</span><span class="sxs-lookup"><span data-stu-id="1f506-102">\<endpoint> element</span></span>
<span data-ttu-id="1f506-103">서비스 공개에 사용되는 서비스 엔드포인트에 대한 바인딩, 계약 및 주소 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
<span data-ttu-id="1f506-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1f506-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1f506-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1f506-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1f506-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="1f506-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="1f506-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="1f506-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="1f506-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<끝점 >**</span><span class="sxs-lookup"><span data-stu-id="1f506-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f506-109">구문</span><span class="sxs-lookup"><span data-stu-id="1f506-109">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f506-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1f506-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1f506-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f506-112">특성</span><span class="sxs-lookup"><span data-stu-id="1f506-112">Attributes</span></span>  
  
|<span data-ttu-id="1f506-113">특성</span><span class="sxs-lookup"><span data-stu-id="1f506-113">Attribute</span></span>|<span data-ttu-id="1f506-114">설명</span><span class="sxs-lookup"><span data-stu-id="1f506-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f506-115">주소</span><span class="sxs-lookup"><span data-stu-id="1f506-115">address</span></span>|<span data-ttu-id="1f506-116">엔드포인트의 주소를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-116">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="1f506-117">주소는 절대 주소 또는 상대 주소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-117">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="1f506-118">상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-118">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="1f506-119">주소가 구성되지 않으면 해당 엔드포인트의 주소를 기본 주소로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-119">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="1f506-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f506-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f506-121">behaviorConfiguration</span></span>|<span data-ttu-id="1f506-122">엔드포인트에 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-122">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="1f506-123">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="1f506-123">binding</span></span>|<span data-ttu-id="1f506-124">사용할 바인딩 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-124">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="1f506-125">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="1f506-126">이 형식은 바인딩의 형식 이름이 아니라 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-126">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="1f506-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f506-127">bindingConfiguration</span></span>|<span data-ttu-id="1f506-128">엔드포인트가 인스턴스화될 때 사용하는 바인딩의 바인딩 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-128">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="1f506-129">바인딩 이름은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-129">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="1f506-130">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-130">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1f506-131">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-131">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="1f506-132">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1f506-132">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="1f506-133">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-133">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="1f506-134">bindingName</span><span class="sxs-lookup"><span data-stu-id="1f506-134">bindingName</span></span>|<span data-ttu-id="1f506-135">WSDL을 통해 정의를 내보내기 위한 바인딩의 정규화된 고유 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-135">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="1f506-136">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-136">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f506-137">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="1f506-137">bindingNamespace</span></span>|<span data-ttu-id="1f506-138">WSDL을 통해 정의를 내보내기 위한 바인딩 네임스페이스의 정규화된 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-138">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="1f506-139">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f506-140">계약(contract)</span><span class="sxs-lookup"><span data-stu-id="1f506-140">contract</span></span>|<span data-ttu-id="1f506-141">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-141">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="1f506-142">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-142">The assembly must implement the contract type.</span></span> <span data-ttu-id="1f506-143">서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-143">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="1f506-144">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-144">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f506-145">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="1f506-145">endpointConfiguration</span></span>|<span data-ttu-id="1f506-146">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-146">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="1f506-147">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-147">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="1f506-148">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="1f506-148">isSystemEndpoint</span></span>|<span data-ttu-id="1f506-149">엔드포인트가 인프라 엔드포인트인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-149">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="1f506-150">kind</span><span class="sxs-lookup"><span data-stu-id="1f506-150">kind</span></span>|<span data-ttu-id="1f506-151">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-151">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="1f506-152">이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다. 지정하지 않으면 일반 서비스 엔드포인트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-152">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="1f506-153">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="1f506-153">listenUriMode</span></span>|<span data-ttu-id="1f506-154">서비스에서 수신하도록 제공된 `ListenUri`를 전송에서 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-154">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="1f506-155">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-155">Valid values are</span></span><br /><br /> <span data-ttu-id="1f506-156">-명시적</span><span class="sxs-lookup"><span data-stu-id="1f506-156">-   Explicit</span></span><br /><span data-ttu-id="1f506-157">-   Unique</span><span class="sxs-lookup"><span data-stu-id="1f506-157">-   Unique</span></span><br /><br /> <span data-ttu-id="1f506-158">기본값은 Explicit입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-158">The default value is Explicit.</span></span>|  
|<span data-ttu-id="1f506-159">listenUri</span><span class="sxs-lookup"><span data-stu-id="1f506-159">listenUri</span></span>|<span data-ttu-id="1f506-160">서비스 엔드포인트가 수신하는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-160">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="1f506-161">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-161">The default is an empty string.</span></span>|  
|<span data-ttu-id="1f506-162">name</span><span class="sxs-lookup"><span data-stu-id="1f506-162">name</span></span>|<span data-ttu-id="1f506-163">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-163">Optional attribute.</span></span> <span data-ttu-id="1f506-164">서비스 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-164">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="1f506-165">기본값은 바인딩 이름과 계약 설명 이름을 연결한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-165">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="1f506-166">서비스에 엔드포인트가 여러 개일 수 있으므로 엔드포인트의 `name` 특성은 서비스 이름과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-166">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f506-167">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1f506-167">Child Elements</span></span>  
  
|<span data-ttu-id="1f506-168">요소</span><span class="sxs-lookup"><span data-stu-id="1f506-168">Element</span></span>|<span data-ttu-id="1f506-169">Description</span><span class="sxs-lookup"><span data-stu-id="1f506-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f506-170">\<headers></span><span class="sxs-lookup"><span data-stu-id="1f506-170">\<headers></span></span>](headers.md)|<span data-ttu-id="1f506-171">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-171">A collection of address headers.</span></span>|  
|[<span data-ttu-id="1f506-172">\<identity></span><span class="sxs-lookup"><span data-stu-id="1f506-172">\<identity></span></span>](identity.md)|<span data-ttu-id="1f506-173">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-173">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f506-174">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1f506-174">Parent Elements</span></span>  
  
|<span data-ttu-id="1f506-175">요소</span><span class="sxs-lookup"><span data-stu-id="1f506-175">Element</span></span>|<span data-ttu-id="1f506-176">설명</span><span class="sxs-lookup"><span data-stu-id="1f506-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f506-177">\<service></span><span class="sxs-lookup"><span data-stu-id="1f506-177">\<service></span></span>](service.md)|<span data-ttu-id="1f506-178">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-178">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1f506-179">예제</span><span class="sxs-lookup"><span data-stu-id="1f506-179">Example</span></span>  
 <span data-ttu-id="1f506-180">서비스 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1f506-180">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="1f506-181">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f506-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="1f506-182">종점 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="1f506-182">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="1f506-183">방법: 구성에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="1f506-183">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
