---
title: <client>의 <endpoint>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855314"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="1a292-102">\<클라이언트 >의 \<끝점 ></span><span class="sxs-lookup"><span data-stu-id="1a292-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="1a292-103">클라이언트에서 서버의 서비스 엔드포인트와 연결하는 데 사용하는 채널 엔드포인트의 contract, binding 및 address 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="1a292-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a292-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a292-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1a292-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1a292-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="1a292-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="1a292-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<끝점 >**</span><span class="sxs-lookup"><span data-stu-id="1a292-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a292-108">구문</span><span class="sxs-lookup"><span data-stu-id="1a292-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a292-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1a292-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1a292-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a292-111">특성</span><span class="sxs-lookup"><span data-stu-id="1a292-111">Attributes</span></span>  
  
|<span data-ttu-id="1a292-112">특성</span><span class="sxs-lookup"><span data-stu-id="1a292-112">Attribute</span></span>|<span data-ttu-id="1a292-113">Description</span><span class="sxs-lookup"><span data-stu-id="1a292-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a292-114">주소</span><span class="sxs-lookup"><span data-stu-id="1a292-114">address</span></span>|<span data-ttu-id="1a292-115">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1a292-116">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="1a292-117">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-117">The default is an empty string.</span></span> <span data-ttu-id="1a292-118">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="1a292-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a292-119">behaviorConfiguration</span></span>|<span data-ttu-id="1a292-120">엔드포인트를 인스턴스화할 때 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="1a292-121">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="1a292-122">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="1a292-123">바인딩(binding)</span><span class="sxs-lookup"><span data-stu-id="1a292-123">binding</span></span>|<span data-ttu-id="1a292-124">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1a292-125">사용할 바인딩의 형식을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="1a292-126">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="1a292-127">이 형식은 바인딩의 형식 이름 대신 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="1a292-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a292-128">bindingConfiguration</span></span>|<span data-ttu-id="1a292-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-129">Optional.</span></span> <span data-ttu-id="1a292-130">엔드포인트가 인스턴스화될 때 사용할 바인딩 구성의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="1a292-131">바인딩 구성은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="1a292-132">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1a292-133">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="1a292-134">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="1a292-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="1a292-135">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="1a292-136">계약(contract)</span><span class="sxs-lookup"><span data-stu-id="1a292-136">contract</span></span>|<span data-ttu-id="1a292-137">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="1a292-138">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="1a292-139">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="1a292-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a292-140">endpointConfiguration</span></span>|<span data-ttu-id="1a292-141">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="1a292-142">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="1a292-143">kind</span><span class="sxs-lookup"><span data-stu-id="1a292-143">kind</span></span>|<span data-ttu-id="1a292-144">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="1a292-145">이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다. 지정하지 않으면 일반 채널 엔드포인트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="1a292-146">name</span><span class="sxs-lookup"><span data-stu-id="1a292-146">name</span></span>|<span data-ttu-id="1a292-147">선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-147">Optional string attribute.</span></span> <span data-ttu-id="1a292-148">이 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="1a292-149">지정한 계약 형식에 대해 여러 클라이언트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="1a292-150">각 정의는 고유한 구성 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="1a292-151">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="1a292-152">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1a292-153">바인딩의 `name` 특성은 WSDL을 통해 정의를 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a292-154">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a292-154">Child Elements</span></span>  
  
|<span data-ttu-id="1a292-155">요소</span><span class="sxs-lookup"><span data-stu-id="1a292-155">Element</span></span>|<span data-ttu-id="1a292-156">Description</span><span class="sxs-lookup"><span data-stu-id="1a292-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a292-157">\<headers></span><span class="sxs-lookup"><span data-stu-id="1a292-157">\<headers></span></span>](headers.md)|<span data-ttu-id="1a292-158">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="1a292-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="1a292-159">\<identity></span></span>](identity.md)|<span data-ttu-id="1a292-160">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a292-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a292-161">Parent Elements</span></span>  
  
|<span data-ttu-id="1a292-162">요소</span><span class="sxs-lookup"><span data-stu-id="1a292-162">Element</span></span>|<span data-ttu-id="1a292-163">설명</span><span class="sxs-lookup"><span data-stu-id="1a292-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a292-164">\<client></span><span class="sxs-lookup"><span data-stu-id="1a292-164">\<client></span></span>](client.md)|<span data-ttu-id="1a292-165">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1a292-166">예제</span><span class="sxs-lookup"><span data-stu-id="1a292-166">Example</span></span>  
 <span data-ttu-id="1a292-167">이것은 채널 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1a292-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="1a292-168">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a292-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="1a292-169">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="1a292-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1a292-170">클라이언트</span><span class="sxs-lookup"><span data-stu-id="1a292-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
