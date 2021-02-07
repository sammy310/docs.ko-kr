---
description: '다음에 대 한 자세한 정보:: <endpoint><client>'
title: <client>의 <endpoint>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 4ace6d49ba18524729925b20cf08e5d57bcc40c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725783"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="df125-103">\<client>의 \<endpoint></span><span class="sxs-lookup"><span data-stu-id="df125-103">\<endpoint> of \<client></span></span>

<span data-ttu-id="df125-104">클라이언트에서 서버의 서비스 엔드포인트와 연결하는 데 사용하는 채널 엔드포인트의 contract, binding 및 address 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-104">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="df125-105">구문</span><span class="sxs-lookup"><span data-stu-id="df125-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df125-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="df125-106">Attributes and Elements</span></span>  

 <span data-ttu-id="df125-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df125-108">특성</span><span class="sxs-lookup"><span data-stu-id="df125-108">Attributes</span></span>  
  
|<span data-ttu-id="df125-109">attribute</span><span class="sxs-lookup"><span data-stu-id="df125-109">Attribute</span></span>|<span data-ttu-id="df125-110">설명</span><span class="sxs-lookup"><span data-stu-id="df125-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df125-111">address</span><span class="sxs-lookup"><span data-stu-id="df125-111">address</span></span>|<span data-ttu-id="df125-112">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="df125-113">엔드포인트의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-113">Specifies the address of the endpoint.</span></span> <span data-ttu-id="df125-114">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-114">The default is an empty string.</span></span> <span data-ttu-id="df125-115">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-115">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="df125-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="df125-116">behaviorConfiguration</span></span>|<span data-ttu-id="df125-117">엔드포인트를 인스턴스화할 때 사용할 동작의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-117">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="df125-118">동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-118">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="df125-119">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-119">The default is an empty string.</span></span>|  
|<span data-ttu-id="df125-120">바인딩</span><span class="sxs-lookup"><span data-stu-id="df125-120">binding</span></span>|<span data-ttu-id="df125-121">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-121">Required string attribute.</span></span><br /><br /> <span data-ttu-id="df125-122">사용할 바인딩의 형식을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-122">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="df125-123">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df125-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="df125-124">이 형식은 바인딩의 형식 이름 대신 섹션 이름으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="df125-124">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="df125-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="df125-125">bindingConfiguration</span></span>|<span data-ttu-id="df125-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-126">Optional.</span></span> <span data-ttu-id="df125-127">엔드포인트가 인스턴스화될 때 사용할 바인딩 구성의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-127">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="df125-128">바인딩 구성은 엔드포인트가 정의된 지점의 범위에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-128">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="df125-129">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-129">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="df125-130">이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df125-130">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="df125-131">사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="df125-131">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="df125-132">그렇지 않으면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df125-132">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="df125-133">계약</span><span class="sxs-lookup"><span data-stu-id="df125-133">contract</span></span>|<span data-ttu-id="df125-134">필수 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-134">Required string attribute.</span></span><br /><br /> <span data-ttu-id="df125-135">이 엔드포인트가 공개하는 계약을 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-135">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="df125-136">어셈블리는 계약 형식을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-136">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="df125-137">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="df125-137">endpointConfiguration</span></span>|<span data-ttu-id="df125-138">이 표준 엔드포인트의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-138">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="df125-139">이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-139">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="df125-140">kind</span><span class="sxs-lookup"><span data-stu-id="df125-140">kind</span></span>|<span data-ttu-id="df125-141">적용되는 표준 엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-141">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="df125-142">형식은 `<extensions>` 섹션 또는 machine.config에 등록해야 합니다. 지정하지 않으면 일반 채널 엔드포인트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="df125-142">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="df125-143">name</span><span class="sxs-lookup"><span data-stu-id="df125-143">name</span></span>|<span data-ttu-id="df125-144">선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-144">Optional string attribute.</span></span> <span data-ttu-id="df125-145">이 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="df125-145">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="df125-146">지정한 계약 형식에 대해 여러 클라이언트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df125-146">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="df125-147">각 정의는 고유한 구성 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="df125-147">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="df125-148">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df125-148">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="df125-149">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-149">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="df125-150">바인딩의 `name` 특성은 WSDL을 통해 정의를 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df125-150">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df125-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="df125-151">Child Elements</span></span>  
  
|<span data-ttu-id="df125-152">요소</span><span class="sxs-lookup"><span data-stu-id="df125-152">Element</span></span>|<span data-ttu-id="df125-153">설명</span><span class="sxs-lookup"><span data-stu-id="df125-153">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="df125-154">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-154">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="df125-155">한 엔드포인트에서 다른 엔드포인트와 메시지를 교환할 때 상대 엔드포인트를 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-155">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df125-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="df125-156">Parent Elements</span></span>  
  
|<span data-ttu-id="df125-157">요소</span><span class="sxs-lookup"><span data-stu-id="df125-157">Element</span></span>|<span data-ttu-id="df125-158">설명</span><span class="sxs-lookup"><span data-stu-id="df125-158">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="df125-159">클라이언트가 연결할 수 있는 엔드포인트의 목록을 정의하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-159">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="df125-160">예제</span><span class="sxs-lookup"><span data-stu-id="df125-160">Example</span></span>  

 <span data-ttu-id="df125-161">이것은 채널 엔드포인트 구성의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="df125-161">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="df125-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df125-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="df125-163">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="df125-163">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="df125-164">클라이언트</span><span class="sxs-lookup"><span data-stu-id="df125-164">Clients</span></span>](../../../wcf/feature-details/clients.md)
