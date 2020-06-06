---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139697"
---
# \<behaviors>
<span data-ttu-id="19555-101">이 요소는 이름이 `endpointBehaviors` 및 `serviceBehaviors`인 두 개의 자식 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19555-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="19555-102">각 컬렉션은 엔드포인트 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19555-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="19555-103">각 동작 요소는 고유한 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="19555-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="19555-104">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19555-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="19555-105">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19555-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="19555-106">구문</span><span class="sxs-lookup"><span data-stu-id="19555-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19555-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19555-107">Attributes and Elements</span></span>  
 <span data-ttu-id="19555-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19555-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19555-109">특성</span><span class="sxs-lookup"><span data-stu-id="19555-109">Attributes</span></span>  
 <span data-ttu-id="19555-110">None</span><span class="sxs-lookup"><span data-stu-id="19555-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19555-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19555-111">Child Elements</span></span>  
  
|<span data-ttu-id="19555-112">요소</span><span class="sxs-lookup"><span data-stu-id="19555-112">Element</span></span>|<span data-ttu-id="19555-113">Description</span><span class="sxs-lookup"><span data-stu-id="19555-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="19555-114">이 구성 섹션은 특정 엔드포인트에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19555-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="19555-115">이 구성 섹션은 특정 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="19555-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19555-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19555-116">Parent Elements</span></span>  
  
|<span data-ttu-id="19555-117">요소</span><span class="sxs-lookup"><span data-stu-id="19555-117">Element</span></span>|<span data-ttu-id="19555-118">Description</span><span class="sxs-lookup"><span data-stu-id="19555-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="19555-119">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19555-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19555-120">설명</span><span class="sxs-lookup"><span data-stu-id="19555-120">Remarks</span></span>  
 <span data-ttu-id="19555-121">`<remove>` 요소를 사용하여 컬렉션에서 특정 동작을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19555-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="19555-122">이렇게 하려면 제거할 동작의 이름을 `name` 요소의 `<remove>` 특성에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19555-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="19555-123">`<clear>` 요소를 사용하여 컬렉션의 모든 내용을 지워 동작 컬렉션이 비어 있는 상태로 시작되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19555-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19555-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19555-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="19555-125">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="19555-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="19555-126">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="19555-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="19555-127">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="19555-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="19555-128">서비스 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="19555-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="19555-129">보안 동작</span><span class="sxs-lookup"><span data-stu-id="19555-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
