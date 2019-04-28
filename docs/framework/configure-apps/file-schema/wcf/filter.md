---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704039"
---
# <a name="filter"></a><span data-ttu-id="67a99-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="67a99-101">\<filter></span></span>

<span data-ttu-id="67a99-102">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터를 정의<xref:System.ServiceModel.Dispatcher.MessageFilter> 도 지원 데이터 나 필터에 필요한 매개 변수를 들어오는 메시지를 평가할 때 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="67a99-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="67a99-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="67a99-104">구문</span><span class="sxs-lookup"><span data-stu-id="67a99-104">Syntax</span></span>  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67a99-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="67a99-105">Attributes and elements</span></span>

<span data-ttu-id="67a99-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="67a99-107">특성</span><span class="sxs-lookup"><span data-stu-id="67a99-107">Attributes</span></span>

| <span data-ttu-id="67a99-108">특성</span><span class="sxs-lookup"><span data-stu-id="67a99-108">Attribute</span></span>  | <span data-ttu-id="67a99-109">설명</span><span class="sxs-lookup"><span data-stu-id="67a99-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="67a99-110">customType</span><span class="sxs-lookup"><span data-stu-id="67a99-110">customType</span></span> | <span data-ttu-id="67a99-111">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="67a99-112">하는 경우 `filterType` 로 설정 된 `custom`,이 특성에 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="67a99-113">`filterData` 사용자 지정 형식 필터를 평가 하는 동안 사용할 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="67a99-114">filterData</span><span class="sxs-lookup"><span data-stu-id="67a99-114">filterData</span></span> | <span data-ttu-id="67a99-115">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-115">A string containing the filter data.</span></span> <span data-ttu-id="67a99-116">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a99-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="67a99-117">filterType</span><span class="sxs-lookup"><span data-stu-id="67a99-117">filterType</span></span> | <span data-ttu-id="67a99-118">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-118">A string containing the filter type.</span></span> <span data-ttu-id="67a99-119">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="67a99-120">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a99-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="67a99-121">name</span><span class="sxs-lookup"><span data-stu-id="67a99-121">name</span></span>       | <span data-ttu-id="67a99-122">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="67a99-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="67a99-123">Child elements</span></span>

<span data-ttu-id="67a99-124">없음</span><span class="sxs-lookup"><span data-stu-id="67a99-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="67a99-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="67a99-125">Parent elements</span></span>

| <span data-ttu-id="67a99-126">요소</span><span class="sxs-lookup"><span data-stu-id="67a99-126">Element</span></span> | <span data-ttu-id="67a99-127">설명</span><span class="sxs-lookup"><span data-stu-id="67a99-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="67a99-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="67a99-128">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="67a99-129">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a99-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="67a99-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="67a99-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
