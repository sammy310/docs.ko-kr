---
title: <endpointBehaviors>의 <behavior>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: f14e80798a9b088508f23d718c8b386286ad65a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919838"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="13cc5-102">\<endpointbehaviors의 \<동작 > ></span><span class="sxs-lookup"><span data-stu-id="13cc5-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="13cc5-103">`behavior` 요소는 엔드포인트의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="13cc5-104">각 동작은 해당 `name`으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="13cc5-105">엔드포인트는 이 이름을 통해 각 동작에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="13cc5-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="13cc5-107">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13cc5-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="13cc5-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="13cc5-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="13cc5-109">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="13cc5-109">\<behaviors></span></span>  
<span data-ttu-id="13cc5-110">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="13cc5-110">\<endpointBehaviors></span></span>  
<span data-ttu-id="13cc5-111">\<behavior></span><span class="sxs-lookup"><span data-stu-id="13cc5-111">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cc5-112">구문</span><span class="sxs-lookup"><span data-stu-id="13cc5-112">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13cc5-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="13cc5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="13cc5-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13cc5-115">특성</span><span class="sxs-lookup"><span data-stu-id="13cc5-115">Attributes</span></span>  
  
|<span data-ttu-id="13cc5-116">특성</span><span class="sxs-lookup"><span data-stu-id="13cc5-116">Attribute</span></span>|<span data-ttu-id="13cc5-117">설명</span><span class="sxs-lookup"><span data-stu-id="13cc5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13cc5-118">name</span><span class="sxs-lookup"><span data-stu-id="13cc5-118">name</span></span>|<span data-ttu-id="13cc5-119">동작의 구성 이름을 포함하는 고유 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="13cc5-120">이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="13cc5-121">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-121">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="13cc5-122">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13cc5-122">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13cc5-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="13cc5-123">Child Elements</span></span>  
  
|<span data-ttu-id="13cc5-124">요소</span><span class="sxs-lookup"><span data-stu-id="13cc5-124">Element</span></span>|<span data-ttu-id="13cc5-125">Description</span><span class="sxs-lookup"><span data-stu-id="13cc5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13cc5-126">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="13cc5-126">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="13cc5-127">클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-127">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="13cc5-128">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="13cc5-128">\<callbackDebug></span></span>](callbackdebug.md)|<span data-ttu-id="13cc5-129">WCF (Windows Communication Foundation) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-129">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[<span data-ttu-id="13cc5-130">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="13cc5-130">\<callbackTimeouts></span></span>](callbacktimeouts.md)|<span data-ttu-id="13cc5-131">클라이언트 콜백에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-131">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="13cc5-132">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="13cc5-132">\<clientVia></span></span>](clientvia.md)|<span data-ttu-id="13cc5-133">메시지가 이동할 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-133">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="13cc5-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="13cc5-134">\<dataContractSerializer></span></span>](datacontractserializer.md)|<span data-ttu-id="13cc5-135">DataContractSerializer에 대한 구성 데이터가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-135">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="13cc5-136">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="13cc5-136">\<dispatcherSynchronization></span></span>](dispatchersynchronization.md)|<span data-ttu-id="13cc5-137">서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-137">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="13cc5-138">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="13cc5-138">\<enableWebScript></span></span>](enablewebscript.md)|<span data-ttu-id="13cc5-139">ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-139">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="13cc5-140">동작은 \<webHttpBinding > 표준 바인딩과 \<webMessageEncoding > binding 요소 중 하 나와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-140">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="13cc5-141">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="13cc5-141">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="13cc5-142">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-142">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="13cc5-143">\<soapProcessing></span><span class="sxs-lookup"><span data-stu-id="13cc5-143">\<soapProcessing></span></span>](soapprocessing.md)|<span data-ttu-id="13cc5-144">서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 엔드포인트 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-144">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="13cc5-145">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="13cc5-145">\<synchronousReceive></span></span>](synchronousreceive-element.md)|<span data-ttu-id="13cc5-146">서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-146">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="13cc5-147">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-147">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="13cc5-148">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="13cc5-148">\<transactedBatching></span></span>](transactedbatching.md)|<span data-ttu-id="13cc5-149">받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-149">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="13cc5-150">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="13cc5-150">\<webHttp></span></span>](webhttp.md)|<span data-ttu-id="13cc5-151">구성을 통해 엔드포인트에서 WebHttpBehavior를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-151">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="13cc5-152">이 동작은 \<webHttpBinding > 표준 바인딩과 함께 사용 될 경우 WCF 서비스에 대해 웹 프로그래밍 모델을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-152">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13cc5-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="13cc5-153">Parent Elements</span></span>  
  
|<span data-ttu-id="13cc5-154">요소</span><span class="sxs-lookup"><span data-stu-id="13cc5-154">Element</span></span>|<span data-ttu-id="13cc5-155">Description</span><span class="sxs-lookup"><span data-stu-id="13cc5-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13cc5-156">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="13cc5-156">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="13cc5-157">엔드포인트 동작 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="13cc5-157">A collection of endpoint behavior elements.</span></span>|
