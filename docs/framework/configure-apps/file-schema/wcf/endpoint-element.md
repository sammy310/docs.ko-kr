---
title: <endpoint> 요소
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855386"
---
# <a name="endpoint-element"></a><span data-ttu-id="11043-102">\<endpoint> 요소</span><span class="sxs-lookup"><span data-stu-id="11043-102">\<endpoint> element</span></span>
<span data-ttu-id="11043-103">서비스 공개에 사용되는 서비스 엔드포인트에 대한 바인딩, 계약 및 주소 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="11043-104">구문</span><span class="sxs-lookup"><span data-stu-id="11043-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11043-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="11043-105">Attributes and Elements</span></span>  
 <span data-ttu-id="11043-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11043-107">특성</span><span class="sxs-lookup"><span data-stu-id="11043-107">Attributes</span></span>  
  
|<span data-ttu-id="11043-108">attribute</span><span class="sxs-lookup"><span data-stu-id="11043-108">Attribute</span></span>|<span data-ttu-id="11043-109">Description</span><span class="sxs-lookup"><span data-stu-id="11043-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11043-110">address</span><span class="sxs-lookup"><span data-stu-id="11043-110">address</span></span>|<span data-ttu-id="11043-111">엔드포인트의 주소를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="11043-112">주소는 절대 주소 또는 상대 주소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11043-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="11043-113">상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="11043-114">주소가 구성되지 않으면 해당 엔드포인트의 주소를 기본 주소로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="11043-115">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="11043-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="11043-116">behaviorConfiguration</span></span>|<span data-ttu-id="11043-117">엔드포인트에 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="11043-118">바인딩</span><span class="sxs-lookup"><span data-stu-id="11043-118">binding</span></span>|<span data-ttu-id="11043-119">사용할 바인딩 형식을 지정하는 필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="11043-120">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11043-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="11043-121">이 형식은 바인딩의 형식 이름이 아니라 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="11043-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="11043-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="11043-122">bindingConfiguration</span></span>|<span data-ttu-id="11043-123">엔드포인트가 인스턴스화될 때 사용하는 바인딩의 바인딩 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="11043-124">바인딩 이름은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="11043-125">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="11043-126">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11043-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="11043-127">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="11043-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="11043-128">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11043-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="11043-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="11043-129">bindingName</span></span>|<span data-ttu-id="11043-130">WSDL을 통해 정의를 내보내기 위한 바인딩의 정규화된 고유 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="11043-131">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="11043-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="11043-132">bindingNamespace</span></span>|<span data-ttu-id="11043-133">WSDL을 통해 정의를 내보내기 위한 바인딩 네임스페이스의 정규화된 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="11043-134">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="11043-135">계약</span><span class="sxs-lookup"><span data-stu-id="11043-135">contract</span></span>|<span data-ttu-id="11043-136">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="11043-137">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="11043-138">서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11043-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="11043-139">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="11043-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="11043-140">endpointConfiguration</span></span>|<span data-ttu-id="11043-141">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="11043-142">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="11043-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="11043-143">isSystemEndpoint</span></span>|<span data-ttu-id="11043-144">엔드포인트가 인프라 엔드포인트인지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="11043-145">kind</span><span class="sxs-lookup"><span data-stu-id="11043-145">kind</span></span>|<span data-ttu-id="11043-146">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="11043-147">형식은 섹션 또는 machine.config에 등록 되어야 합니다 `<extensions>` . 아무 것도 지정 하지 않으면 일반 서비스 끝점이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="11043-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="11043-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="11043-148">listenUriMode</span></span>|<span data-ttu-id="11043-149">서비스에서 수신하도록 제공된 `ListenUri`를 전송에서 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11043-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="11043-150">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11043-150">Valid values are</span></span><br /><br /> <span data-ttu-id="11043-151">-명시적</span><span class="sxs-lookup"><span data-stu-id="11043-151">-   Explicit</span></span><br /><span data-ttu-id="11043-152">-고유</span><span class="sxs-lookup"><span data-stu-id="11043-152">-   Unique</span></span><br /><br /> <span data-ttu-id="11043-153">기본값은 Explicit입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="11043-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="11043-154">listenUri</span></span>|<span data-ttu-id="11043-155">서비스 엔드포인트가 수신하는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="11043-156">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="11043-157">name</span><span class="sxs-lookup"><span data-stu-id="11043-157">name</span></span>|<span data-ttu-id="11043-158">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-158">Optional attribute.</span></span> <span data-ttu-id="11043-159">서비스 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="11043-160">기본값은 바인딩 이름과 계약 설명 이름을 연결한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="11043-161">서비스에 엔드포인트가 여러 개일 수 있으므로 엔드포인트의 `name` 특성은 서비스 이름과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="11043-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11043-162">자식 요소</span><span class="sxs-lookup"><span data-stu-id="11043-162">Child Elements</span></span>  
  
|<span data-ttu-id="11043-163">요소</span><span class="sxs-lookup"><span data-stu-id="11043-163">Element</span></span>|<span data-ttu-id="11043-164">Description</span><span class="sxs-lookup"><span data-stu-id="11043-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="11043-165">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="11043-166">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11043-167">부모 요소</span><span class="sxs-lookup"><span data-stu-id="11043-167">Parent Elements</span></span>  
  
|<span data-ttu-id="11043-168">요소</span><span class="sxs-lookup"><span data-stu-id="11043-168">Element</span></span>|<span data-ttu-id="11043-169">Description</span><span class="sxs-lookup"><span data-stu-id="11043-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="11043-170">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="11043-171">예제</span><span class="sxs-lookup"><span data-stu-id="11043-171">Example</span></span>  
 <span data-ttu-id="11043-172">서비스 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="11043-172">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11043-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11043-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="11043-174">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="11043-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="11043-175">방법: 구성에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="11043-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
