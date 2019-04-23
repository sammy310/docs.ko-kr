---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 108c349a44ed3ac902652f86241c1e96a622549b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204239"
---
# <a name="behaviors"></a><span data-ttu-id="9ca4a-101">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9ca4a-101">\<behaviors></span></span>
<span data-ttu-id="9ca4a-102">이 요소는 이름이 `endpointBehaviors` 및 `serviceBehaviors`인 두 개의 자식 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="9ca4a-103">각 컬렉션은 엔드포인트 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="9ca4a-104">각 동작 요소는 고유한 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="9ca4a-105">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9ca4a-106">기본 구성 및 이름 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="9ca4a-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ca4a-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca4a-108">구문</span><span class="sxs-lookup"><span data-stu-id="9ca4a-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ca4a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ca4a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9ca4a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ca4a-111">특성</span><span class="sxs-lookup"><span data-stu-id="9ca4a-111">Attributes</span></span>  
 <span data-ttu-id="9ca4a-112">없음</span><span class="sxs-lookup"><span data-stu-id="9ca4a-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ca4a-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ca4a-113">Child Elements</span></span>  
  
|<span data-ttu-id="9ca4a-114">요소</span><span class="sxs-lookup"><span data-stu-id="9ca4a-114">Element</span></span>|<span data-ttu-id="9ca4a-115">설명</span><span class="sxs-lookup"><span data-stu-id="9ca4a-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ca4a-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ca4a-116">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="9ca4a-117">이 구성 섹션은 특정 엔드포인트에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="9ca4a-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ca4a-118">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="9ca4a-119">이 구성 섹션은 특정 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ca4a-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ca4a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9ca4a-121">요소</span><span class="sxs-lookup"><span data-stu-id="9ca4a-121">Element</span></span>|<span data-ttu-id="9ca4a-122">설명</span><span class="sxs-lookup"><span data-stu-id="9ca4a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ca4a-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ca4a-123">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="9ca4a-124">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca4a-125">설명</span><span class="sxs-lookup"><span data-stu-id="9ca4a-125">Remarks</span></span>  
 <span data-ttu-id="9ca4a-126">`<remove>` 요소를 사용하여 컬렉션에서 특정 동작을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="9ca4a-127">이렇게 하려면 제거할 동작의 이름을 `name` 요소의 `<remove>` 특성에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="9ca4a-128">`<clear>` 요소를 사용하여 컬렉션의 모든 내용을 지워 동작 컬렉션이 비어 있는 상태로 시작되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca4a-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca4a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ca4a-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="9ca4a-130">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="9ca4a-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="9ca4a-131">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="9ca4a-131">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="9ca4a-132">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="9ca4a-132">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="9ca4a-133">서비스 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="9ca4a-133">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="9ca4a-134">보안 동작</span><span class="sxs-lookup"><span data-stu-id="9ca4a-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
